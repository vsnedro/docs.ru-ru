---
title: Набор данных и руководство по безопасности DataTable
ms.date: 07/14/2020
dev_langs:
- csharp
ms.openlocfilehash: e9973df02ff478eedc932099fb8be0526a97b899
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679459"
---
# <a name="dataset-and-datatable-security-guidance"></a>Набор данных и руководство по безопасности DataTable

Эта статья относится к следующим продуктам:

* .NET Framework (все версии)
* .NET Core и более поздние версии
* .NET 5.0 и более поздней версии

Типы [DataSet](/dotnet/api/system.data.dataset) и [DataTable](/dotnet/api/system.data.datatable) являются устаревшими компонентами .NET, которые позволяют представлять наборы данных как управляемые объекты. Эти компоненты появились в .NET 1,0 как часть исходной [инфраструктуры ADO.NET](./index.md). Их цель — предоставить управляемое представление по реляционному набору данных, чтобы отказаться от того, является ли базовый источник данных XML, SQL или другой технологией.

Дополнительные сведения о ADO.NET, включая более современные парадигмы представления данных, см. [в документации по ADO.NET](../index.md).

## <a name="default-restrictions-when-deserializing-a-dataset-or-datatable-from-xml"></a>Ограничения по умолчанию при десериализации набора данных или DataTable из XML

Во всех поддерживаемых версиях .NET Framework, .NET Core и .NET, а также `DataSet` `DataTable` накладываются следующие ограничения на типы объектов, которые могут присутствовать в десериализованных данных. По умолчанию этот список ограничен:

* Примитивы и примитивные эквиваленты: `bool` , `char` , `sbyte` , `byte` , `short` , `ushort` , `int` , `uint` ,,, `long` `ulong` `float` `double` `decimal` `DateTime` `DateTimeOffset` `TimeSpan` `string` `Guid` `SqlBinary` `SqlBoolean` `SqlByte` `SqlBytes` `SqlChars` `SqlDateTime` `SqlDecimal` `SqlDouble` `SqlGuid` `SqlInt16` `SqlInt32` `SqlInt64` `SqlMoney` `SqlSingle` `SqlString` ,,,,,,,,,,,,,,,,,,,,,, и.
* Часто используемые не примитивы: `Type` , `Uri` и `BigInteger` .
* Часто используемые типы _System. Drawing_ : `Color` , `Point` , `PointF` , `Rectangle` , `RectangleF` , `Size` и `SizeF` .
* `Enum` типов.
* Массивы и списки приведенных выше типов.

Если входящие XML-данные содержат объект, тип которого отсутствует в этом списке:

* Исключение создается со следующим сообщением и трассировкой стека.  
Сообщение об ошибке:  
System. InvalidOperationException: тип " \<Type Name\> , версия = \<n.n.n.n\> , Culture = \<culture\> , PublicKeyToken = \<token value\> " не допускается здесь. [https://go.microsoft.com/fwlink/?linkid=2132227](https://go.microsoft.com/fwlink/?linkid=2132227)Дополнительные сведения см. в разделе.  
Трассировка стека:  
в System. Data. Типелимитер. Енсуретипеисалловед (тип Type, Типелимитер Каптуредлимитер)  
в System. Data. DataColumn. Упдатеколумнтипе (тип Type, StorageType typeCode)  
в System. Data. DataColumn. set_DataType (значение типа)  

* Операция десериализации завершается ошибкой.

При загрузке XML в существующий `DataSet` экземпляр или `DataTable` можно учитывать существующие определения столбцов. Если таблица уже содержит определение столбца пользовательского типа, этот тип временно добавляется в список разрешений на время выполнения операции десериализации XML.

> [!NOTE]
> После добавления столбцов в объект `DataTable` `ReadXml` не будет считывать схему из XML, и если схема не совпадает, она также не будет считывать записи, поэтому необходимо будет добавить все столбцы самостоятельно, чтобы использовать этот метод.

```csharp
XmlReader xmlReader = GetXmlReader();

// Assume the XML blob contains data for type MyCustomClass.
// The following call to ReadXml fails because MyCustomClass isn't in the allowed types list.

DataTable table = new DataTable("MyDataTable");
table.ReadXml(xmlReader);

// However, the following call to ReadXml succeeds, since the DataTable instance
// already defines a column of type MyCustomClass.

DataTable table = new DataTable("MyDataTable");
table.Columns.Add("MyColumn", typeof(MyCustomClass));
table.ReadXml(xmlReader); // this call will succeed
```

Ограничения типа объекта также применяются при использовании `XmlSerializer` для десериализации экземпляра `DataSet` или `DataTable` . Однако они могут не применяться при использовании `BinaryFormatter` для десериализации экземпляра `DataSet` или `DataTable` .

Ограничения типа объекта не применяются при использовании `DataAdapter.Fill` , например при `DataTable` заполнении экземпляра непосредственно из базы данных без использования API-интерфейсов десериализации XML.

### <a name="extend-the-list-of-allowed-types"></a>Расширение списка разрешенных типов

Приложение может расширить список разрешенных типов, включив в него пользовательские типы, а также встроенные типы, перечисленные выше. При расширении списка разрешенных типов изменение затрагивает _все_ `DataSet` `DataTable` экземпляры приложения и в нем. Невозможно удалить типы из списка разрешенных типов.

#### <a name="extend-through-configuration-net-framework-40---48"></a>Расширение через конфигурацию (.NET Framework 4,0-4,8)

_App.config_ можно использовать для расширения списка разрешенных типов. Чтобы расширить список разрешенных типов, сделайте следующее:

* Используйте `<configSections>` элемент, чтобы добавить ссылку на раздел конфигурации _System. Data_ .
* Используйте `<system.data.dataset.serialization>` / `<allowedTypes>` для указания дополнительных типов.

Каждый `<add>` элемент должен указывать только один тип, используя полное имя типа сборки. Чтобы добавить дополнительные типы в список разрешенных типов, используйте несколько `<add>` элементов.

В следующем примере показано расширение списка разрешенных типов путем добавления пользовательского типа `Fabrikam.CustomType` .

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <sectionGroup name="system.data.dataset.serialization" type="System.Data.SerializationSettingsSectionGroup, System.Data, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="allowedTypes" type="System.Data.AllowedTypesSectionHandler, System.Data, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>
    </sectionGroup>
  </configSections>
  <system.data.dataset.serialization>
    <allowedTypes>
      <!-- <add type="assembly qualified type name" /> -->
      <add type="Fabrikam.CustomType, Fabrikam, Version=1.0.0.0, Culture=neutral, PublicKeyToken=2b3831f2f2b744f7" />
      <!-- additional <add /> elements as needed -->
    </allowedTypes>
  </system.data.dataset.serialization>
</configuration>
```

Чтобы получить полное имя сборки типа, используйте свойство [Type. AssemblyQualifiedName](/dotnet/api/system.type.assemblyqualifiedname) , как показано в следующем коде.

```csharp
string assemblyQualifiedName = typeof(Fabrikam.CustomType).AssemblyQualifiedName;
```

<a name="etc"></a>

#### <a name="extend-through-configuration-net-framework-20---35"></a>Расширение через конфигурацию (.NET Framework 2,0-3,5)

Если приложение предназначено для .NET Framework 2,0 или 3,5, вы по-прежнему можете использовать описанный выше механизм _App.config_ для расширения списка разрешенных типов. Однако `<configSections>` элемент будет выглядеть немного иначе, как показано в следующем коде:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <!-- The below <sectionGroup> and <section> are specific to .NET Framework 2.0 and 3.5. -->
    <sectionGroup name="system.data.dataset.serialization" type="System.Data.SerializationSettingsSectionGroup, System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="allowedTypes" type="System.Data.AllowedTypesSectionHandler, System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>
    </sectionGroup>
  </configSections>
  <system.data.dataset.serialization>
    <allowedTypes>
      <!-- <add /> elements, as demonstrated in the .NET Framework 4.0 - 4.8 sample code above. -->
    </allowedTypes>
  </system.data.dataset.serialization>
</configuration>
```

#### <a name="extend-programmatically-net-framework-net-core-net-50"></a>Расширение программным способом (.NET Framework, .NET Core, .NET 5.0 +)

Список разрешенных типов также можно расширить программно с помощью [AppDomain. SetData](/dotnet/api/system.appdomain.setdata) с хорошо известным ключом _System. Data. датасетдефаулталловедтипес_, как показано в следующем коде.

```csharp
Type[] extraAllowedTypes = new Type[]
{
    typeof(Fabrikam.CustomType),
    typeof(Contoso.AdditionalCustomType)
};

AppDomain.CurrentDomain.SetData("System.Data.DataSetDefaultAllowedTypes", extraAllowedTypes);
```

При использовании механизма расширения значение, связанное с ключом _System. Data. датасетдефаулталловедтипес_ , должно иметь тип `Type[]` .

В .NET Framework список разрешенных типов можно расширить с помощью _App.config_ и `AppDomain.SetData` . В этом случае `DataSet` и `DataTable` позволяет десериализовать объект как часть данных, если его тип имеется в любом из списков.

### <a name="run-an-app-in-audit-mode-net-framework"></a>Запуск приложения в режиме аудита (.NET Framework)

В .NET Framework `DataSet` и `DataTable` Предоставьте возможность режима аудита. Если включен режим аудита `DataSet` и `DataTable` Сравнение типов входящих объектов со списком разрешенных типов. Однако если объект, тип которого не разрешен, отображается, исключение **не** создается. Вместо этого `DataSet` и `DataTable` уведомлять все подключенные `TraceListener` экземпляры о наличии подозрительного типа, позволяя `TraceListener` записывать эти сведения в журнал. Исключение не создается, и Операция десериализации сохраняется.

> [!WARNING]
> Запуск приложения в режиме аудита должен быть только временной мерой, используемой для тестирования. Если включен режим аудита `DataSet` и `DataTable` не применяются ограничения типа, что может вызвать брешь в системе безопасности в приложении. Дополнительные сведения см. в разделах [Удаление всех ограничений на типы](#ratr) и [безопасность с учетом ненадежных входных данных](#swr).

Режим аудита можно включить с помощью _App.config_:

* Сведения о правильном значении для размещения элемента см. в разделе [расширение конфигурации](#etc) в этом документе `<configSections>` .
* Используйте `<allowedTypes auditOnly="true">` для включения режима аудита, как показано в следующей разметке.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <!-- See the section of this document titled "Extending through configuration" for the appropriate
         <sectionGroup> and <section> elements to put here, depending on whether you're running .NET
         Framework 2.0 - 3.5 or 4.0 - 4.8. -->
  </configSections>
  <system.data.dataset.serialization>
    <allowedTypes auditOnly="true"> <!-- setting auditOnly="true" enables audit mode -->
      <!-- Optional <add /> elements as needed. -->
    </allowedTypes>
  </system.data.dataset.serialization>
</configuration>
```

После включения режима аудита можно использовать _App.config_ , чтобы подключиться к `TraceListener` `DataSet` встроенному `TraceSource.` источнику трассировки по имени _System. Data. DataSet_. В следующем примере демонстрируется запись событий трассировки в консоль _и_ в файл журнала на диске.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.diagnostics>
    <sources>
      <source name="System.Data.DataSet"
              switchType="System.Diagnostics.SourceSwitch"
              switchValue="Warning">
        <listeners>
          <!-- write to the console -->
          <add name="console"
               type="System.Diagnostics.ConsoleTraceListener" />
          <!-- *and* write to a log file on disk -->
          <add name="filelog"
               type="System.Diagnostics.TextWriterTraceListener"
               initializeData="c:\logs\mylog.txt" />
        </listeners>
      </source>
    </sources>
  </system.diagnostics>
</configuration>
```

Дополнительные сведения о `TraceSource` и см `TraceListener` . в документе [практические руководства. использование TraceSource и фильтров с прослушивателями трассировки](../../../debug-trace-profile/how-to-use-tracesource-and-filters-with-trace-listeners.md).

> [!NOTE]
> Запуск приложения в режиме аудита недоступен в .NET Core или .NET 5,0 и более поздних версиях.

<a name="ratr"></a>

### <a name="remove-all-type-restrictions"></a>Удалить все ограничения типа

Если приложение должно удалить все ограничения, ограничивающие тип `DataSet` , в и `DataTable` :

* Существует несколько вариантов отключения ограничений типа.
* Доступные параметры зависят от платформы, для которой предназначено приложение.

> [!WARNING]
> Удаление всех ограничений типа может вызвать брешь в системе безопасности внутри приложения. При использовании этого механизма убедитесь, что приложение не **использует** `DataSet` или `DataTable` для чтения недоверенных входных данных. Дополнительные сведения см. в статье [CVE-2020-1147](https://portal.msrc.microsoft.com/en-us/security-guidance/advisory/CVE-2020-1147) и следующем разделе [безопасность с учетом ненадежных входов](#swr).

#### <a name="through-appcontext-configuration-net-framework-46---48-net-core-21-and-later-net-50-and-later"></a>Через AppContext Configuration (.NET Framework 4,6-4,8, .NET Core 2,1 и более поздних версий, .NET 5,0 и более поздние версии)

`AppContext`Параметр, `Switch.System.Data.AllowArbitraryDataSetTypeInstantiation` при установке которого `true` удаляет все ограничения, ограничивающие типы `DataSet` , от и `DataTable` .

В .NET Framework этот коммутатор можно включить с помощью _App.config_, как показано в следующей конфигурации:

```xml
<configuration>
   <runtime>
      <!-- Warning: setting the following switch can introduce a security problem. -->
      <AppContextSwitchOverrides value="Switch.System.Data.AllowArbitraryDataSetTypeInstantiation=true" />
   </runtime>
</configuration>
```

В ASP.NET `<AppContextSwitchOverrides>` элемент недоступен. Вместо этого коммутатор можно включить с помощью _Web.config_, как показано в следующей конфигурации:

```xml
<configuration>
    <appSettings>
        <!-- Warning: setting the following switch can introduce a security problem. -->
        <add key="AppContext.SetSwitch:Switch.System.Data.AllowArbitraryDataSetTypeInstantiation" value="true" />
    </appSettings>
</configuration>
```

Дополнительные сведения см. в описании [\<AppContextSwitchOverrides>](../../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) элемента.

В .NET Core, .NET 5 и ASP.NET Core этот параметр управляется _runtimeconfig.jsв_, как показано в следующем примере JSON:

```json
{
  "runtimeOptions": {
    "configProperties": {
      "Switch.System.Data.AllowArbitraryDataSetTypeInstantiation": true
    }
  }
}
```

Дополнительные сведения см. в разделе ["параметры конфигурации среды выполнения .NET Core"](../../../../core/run-time-config/index.md).

`AllowArbitraryDataSetTypeInstantiation` также можно задать программно с помощью [AppContext. сетсвитч](/dotnet/api/system.appcontext.setswitch) вместо файла конфигурации, как показано в следующем коде:

```csharp
// Warning: setting the following switch can introduce a security problem.
AppContext.SetSwitch("Switch.System.Data.AllowArbitraryDataSetTypeInstantiation", true);
```

 При выборе предыдущего программного подхода вызов метода `AppContext.SetSwitch` должен выполняться на раннем этапе запуска приложений.

#### <a name="through-the-machine-wide-registry-net-framework-20---48"></a>Через реестр на уровне компьютера (.NET Framework 2,0-4,8);

Если параметр `AppContext` недоступен, проверка ограничений типов может быть отключена с помощью реестра Windows:

* Администратор должен настроить реестр.
* Использование реестра является изменением на уровне компьютера и влияет на _все_ приложения, выполняющиеся на компьютере.

| Type  |  Значение |
|---|---|
| **Раздел реестра** | `HKLM\SOFTWARE\Microsoft\.NETFramework\AppContext` |
| **Имя значения** | `Switch.System.Data.AllowArbitraryDataSetTypeInstantiation` |
| **Тип значения** | `REG_SZ` |
| **Данные** | `true` |

В 64-разрядной операционной системе это значение необходимо добавить как для 64-разрядного ключа (показанного выше), так и для ключа 32-bit. 32-разрядный ключ находится в папке `HKLM\SOFTWARE\WOW6432Node\Microsoft\.NETFramework\AppContext` .

Дополнительные сведения об использовании реестра для настройки `AppContext` см. в разделе [«AppContext для потребителей библиотек»](/dotnet/api/system.appcontext#appcontext-for-library-consumers).

<a name="swr"></a>

## <a name="safety-with-regard-to-untrusted-input"></a>Безопасность в отношении ненадежных входных данных

Хотя `DataSet` и `DataTable` накладывают ограничения по умолчанию на типы, которые могут присутствовать при ДЕСЕРИАЛИЗАЦИИ XML-полезных данных, __ `DataSet` и `DataTable` в общем случае ненадежны при заполнении недоверенными входными данными.__ Ниже приведен неисчерпывающий список способов, с помощью которых `DataSet` `DataTable` экземпляр или может считывать ненадежные входные данные.

* Объект `DataAdapter` ссылается на базу данных, а `DataAdapter.Fill` метод используется для заполнения `DataSet` с помощью содержимого запроса к базе данных.
* `DataSet.ReadXml`Метод или `DataTable.ReadXml` используется для чтения XML-файла, содержащего сведения о столбцах и строках.
* `DataSet`Экземпляр или `DataTable` сериализуется как часть ASP.NET (SOAP) веб-служб или КОНЕЧНОЙ точки WCF.
* Сериализатор, такой как `XmlSerializer` , используется для десериализации `DataSet` `DataTable` экземпляра или из потока XML.
* Сериализатор, такой как `JsonConvert` , используется для десериализации `DataSet` `DataTable` экземпляра или из потока JSON. `JsonConvert` — Это метод в популярном [Newtonsoft.Jsе](https://www.newtonsoft.com/json) стороннего производителя для библиотеки.
* Сериализатор, такой как `BinaryFormatter` , используется для десериализации `DataSet` `DataTable` экземпляра или из потока необработанных байтов.

В этом документе обсуждаются вопросы безопасности в предыдущих сценариях.

## <a name="use-dataadapterfill-to-populate-a-dataset-from-an-untrusted-data-source"></a>Использование `DataAdapter.Fill` для заполнения `DataSet` из ненадежного источника данных

`DataSet`Экземпляр можно заполнить с помощью `DataAdapter` [ `DataAdapter.Fill` метода](/dotnet/api/system.data.common.dataadapter.fill), как показано в следующем примере.

```csharp
// Assumes that connection is a valid SqlConnection object.
string queryString =
  "SELECT CustomerID, CompanyName FROM dbo.Customers";
SqlDataAdapter adapter = new SqlDataAdapter(queryString, connection);

DataSet customers = new DataSet();
adapter.Fill(customers, "Customers");
```

(Приведенный выше пример кода является частью более крупного примера, найденного при [заполнении набора данных из DataAdapter](../populating-a-dataset-from-a-dataadapter.md).)

> Большинство приложений могут упростить и предположить, что их уровень базы данных является доверенным. Тем не менее, если вы в привычке [моделирования угроз](https://www.microsoft.com/securityengineering/sdl/threatmodeling) для приложений, модель угроз может считать, что между приложением (клиентом) и уровнем базы данных (сервер) есть граница доверия. Использование [взаимной проверки подлинности](/sql/relational-databases/native-client/features/service-principal-name-spn-support-in-client-connections) или [проверки подлинности AAD](/azure/azure-sql/database/authentication-aad-overview) между клиентом и сервером является одним из способов помочь в устранении рисков, связанных с этим. Оставшаяся часть этого раздела посвящена возможному результату подключения клиента к серверу, который не является доверенным.

Последствия, указывающие на `DataAdapter` ненадежный источник данных, зависят от реализации `DataAdapter` самого себя.

### <a name="sqldataadapter"></a>SqlDataAdapter;

Для встроенного типа [SqlDataAdapter](/dotnet/api/microsoft.data.sqlclient.sqldataadapter)ссылка на ненадежный источник данных может привести к атаке типа "отказ в обслуживании" (DOS). Атака с помощью DoS может привести к тому, что приложение перестанет отвечать или аварийно завершить работу. Если злоумышленник может разместить библиотеку DLL вместе с приложением, он также может обеспечить возможность выполнения локального кода.

### <a name="other-dataadapter-types"></a>Другие типы DataAdapter

Сторонние `DataAdapter` реализации должны самостоятельно выполнять оценку того, какие гарантии безопасности они предоставляют в ненадежных входных данных. .NET не может предоставлять гарантии безопасности в отношении этих реализаций.

<a name="dsrdtr"></a>

## <a name="datasetreadxml-and-datatablereadxml"></a>DataSet. ReadXml и DataTable. ReadXml

`DataSet.ReadXml`Методы и `DataTable.ReadXml` не являются надежными при использовании с ненадежными входными данными. Мы настоятельно рекомендуем пользователям использовать один из вариантов, описанных далее в этом документе.

Реализации `DataSet.ReadXml` и `DataTable.ReadXml` изначально были созданы до того, как уязвимые места сериализации были хорошо понятными категориями угроз. В результате код не соответствует текущим рекомендациям по обеспечению безопасности. Эти API-интерфейсы можно использовать в качестве векторов, чтобы злоумышленники могли совершать атаки через DoS в отношении приложений. Эти атаки могут привести к невозможности отклика веб-службы или вызвать непредвиденное завершение процесса. Платформа не обеспечивает устранение рисков для этих категорий атак, и .NET считает это поведение «по разработке».

.NET выпускает обновления для системы безопасности, чтобы устранить некоторые проблемы, такие как раскрытие информации или удаленное выполнение кода в `DataSet.ReadXml` и `DataTable.ReadXml` . Обновления для системы безопасности .NET могут не обеспечивать полную защиту от этих категорий угроз. Мы рекомендуем всем потребителям проанализировать особенности конкретных сценариев применения и оценить их уязвимость в отношении этих рисков.

Потребители должны учитывать, что обновления безопасности этих API могут повлиять на совместимость приложений в некоторых ситуациях. Кроме того, существует вероятность того, что в этих API будет обнаружена романская уязвимость, для которой .NET не может фактически публиковать обновление для системы безопасности.

Рекомендуется, чтобы потребители этих API были:

* Попробуйте использовать один из вариантов, описанных далее в этом документе.
* Выполните оценку отдельных рисков для своих приложений.

Это единственная обязанность потребителя, позволяющая определить, следует ли использовать эти API. Потребители должны оценивать любые вопросы безопасности, технические и юридические риски, включая нормативные требования, которые могут сопровождаться использованием этих API.

## <a name="dataset-and-datatable-via-aspnet-web-services-or-wcf"></a>DataSet и DataTable через веб-службы ASP.NET или WCF

Можно принять `DataSet` или `DataTable` экземпляр в веб-службе ASP.NET (SOAP), как показано в следующем коде:

```csharp
using System.Data;
using System.Web.Services;

[WebService(Namespace = "http://contoso.com/")]
public class MyService : WebService
{
    [WebMethod]
    public string MyWebMethod(DataTable dataTable)
    {
        /* Web method implementation. */
    }
}
```

Вариация в этом случае не принимает `DataSet` или не `DataTable` напрямую в качестве параметра, а принимает его как часть общего сериализованного графа объектов SOAP, как показано в следующем коде:

```csharp
using System.Data;
using System.Web.Services;

[WebService(Namespace = "http://contoso.com/")]
public class MyService : WebService
{
    [WebMethod]
    public string MyWebMethod(MyClass data)
    {
        /* Web method implementation. */
    }
}

public class MyClass
{
    // Property of type DataTable, automatically serialized and
    // deserialized as part of the overall MyClass payload.
    public DataTable MyDataTable { get; set; }
}
```

Или используйте WCF вместо веб-служб ASP.NET:

```csharp
using System.Data;
using System.ServiceModel;

[ServiceContract(Namespace = "http://contoso.com/")]
public interface IMyContract
{
    [OperationContract]
    string MyMethod(DataTable dataTable);
    [OperationContract]
    string MyOtherMethod(MyClass data);
}

public class MyClass
{
    // Property of type DataTable, automatically serialized and
    // deserialized as part of the overall MyClass payload.
    public DataTable MyDataTable { get; set; }
}
```

Во всех этих случаях модель угроз и гарантии безопасности аналогичны [разделам DataSet. ReadXml и DataTable. ReadXml](#dsrdtr).

## <a name="deserialize-a-dataset-or-datatable-via-xmlserializer"></a>Десериализация набора данных или DataTable через XmlSerializer

Разработчики могут использовать `XmlSerializer` для десериализации `DataSet` и `DataTable` экземпляров, как показано в следующем коде:

```csharp
using System.Data;
using System.IO;
using System.Xml.Serialization;

public DataSet PerformDeserialization1(Stream stream) {
    XmlSerializer serializer = new XmlSerializer(typeof(DataSet));
    return (DataSet)serializer.Deserialize(stream);
}

public MyClass PerformDeserialization2(Stream stream) {
    XmlSerializer serializer = new XmlSerializer(typeof(MyClass));
    return (MyClass)serializer.Deserialize(stream);
}

public class MyClass
{
    // Property of type DataTable, automatically serialized and
    // deserialized as part of the overall MyClass payload.
    public DataTable MyDataTable { get; set; }
}
```

В таких случаях модель угроз и гарантии безопасности совпадают с [разделом DataSet. ReadXml и DataTable. ReadXml.](#dsrdtr)

## <a name="deserialize-a-dataset-or-datatable-via-jsonconvert"></a>Десериализация набора данных или DataTable через JsonConvert

Популярную библиотеку [JSON.NET](https://www.newtonsoft.com/json) сторонних производителей Newtonsoft можно использовать для десериализации `DataSet` и `DataTable` экземпляров, как показано в следующем коде:

```csharp
using System.Data;
using Newtonsoft.Json;

public DataSet PerformDeserialization1(string json) {
    return JsonConvert.DeserializeObject<DataSet>(data);
}

public MyClass PerformDeserialization2(string json) {
    return JsonConvert.DeserializeObject<MyClass>(data);
}

public class MyClass
{
    // Property of type DataTable, automatically serialized and
    // deserialized as part of the overall MyClass payload.
    public DataTable MyDataTable { get; set; }
}
```

Десериализация `DataSet` или `DataTable` таким образом из ненадежного BLOB-объекта JSON небезопасно. Этот шаблон уязвим для атак типа "отказ в обслуживании". Такая атака может привести к сбою приложения или отрисовывать его, не реагируя на запросы.

> [!NOTE]
> Корпорация Майкрософт не гарантирует или не поддерживает реализацию сторонних библиотек, таких как _Newtonsoft.Js_. Эти сведения предоставляются для полноты и являются точными на момент написания этой статьи.

## <a name="deserialize-a-dataset-or-datatable-via-binaryformatter"></a>Десериализация набора данных или DataTable через BinaryFormatter

Разработчики никогда не должны использовать `BinaryFormatter` , `NetDataContractSerializer` , `SoapFormatter` или связанные ***ненадежные*** модули форматирования для десериализации `DataSet` `DataTable` экземпляра или из ненадежных полезных данных:

* Это является уязвимым для полной атаки удаленного выполнения кода.
* Использование пользовательской функции недостаточно `SerializationBinder` для предотвращения такой атаки.

## <a name="safe-replacements"></a>Защищенные замены

Для приложений, которые:

* Принимают или променяйте `DataSet` `DataTable` конечную точку SOAP. asmx или конечную точку WCF.
* Десериализация непроверенных данных в экземпляр `DataSet` или `DataTable` .

Рассмотрите возможность замены объектной модели для использования [Entity Framework](/ef). Entity Framework:

* — Это полнофункциональная, современная, объектно-ориентированная платформа, которая может представлять реляционные данные.
* Предоставляет [обширную экосистему](/ef/core/providers/) поставщиков баз данных, облегчающих проецирование запросов к базам данных с помощью объектных моделей Entity Framework.
* Предлагает встроенные средства защиты при десериализации данных из ненадежных источников.

Для приложений, использующих `.aspx` конечные точки SOAP, рассмотрите возможность изменения этих конечных точек для использования [WCF](../../../wcf/index.md). WCF — это наиболее полнофункциональная замена `.asmx` веб-служб. Конечные точки WCF [могут быть предоставлены через SOAP](../../../wcf/feature-details/how-to-expose-a-contract-to-soap-and-web-clients.md) для совместимости с существующими вызывающими объектами.

## <a name="code-analyzers"></a>Анализаторы кода

Правила безопасности анализатора кода, которые выполняются при компиляции исходного кода, могут помочь найти уязвимости, связанные с этой проблемой безопасности, в C# и Visual Basicном коде. Microsoft. CodeAnalysis. Фкскопанализерс — это пакет NuGet анализаторов кода, который распространяется на [NuGet.org](https://www.nuget.org/).

Обзор анализаторов кода см. в разделе [Обзор анализаторов исходного кода](/visualstudio/code-quality/roslyn-analyzers-overview).

Включите следующие правила Microsoft. CodeAnalysis. Фкскопанализерс:

- [CA2350](/visualstudio/code-quality/ca2350): не используйте DataTable. ReadXml () с ненадежными данными
- [CA2351](/visualstudio/code-quality/ca2351): не используйте DataSet. ReadXml () с ненадежными данными
- [CA2352](/visualstudio/code-quality/ca2352): ненадежный набор данных или DataTable в сериализуемых типах может быть уязвим для атак удаленного выполнения кода
- [CA2353](/visualstudio/code-quality/ca2353): ненадежный набор данных или DataTable в типе Serializable
- [CA2354](/visualstudio/code-quality/ca2354): ненадежный набор данных или DataTable в графе десериализованных объектов может быть уязвим для атак удаленного выполнения кода
- [CA2355](/visualstudio/code-quality/ca2355): обнаружен ненадежный набор данных или тип DataTable в графе несериализуемых объектов
- [CA2356](/visualstudio/code-quality/ca2356): ненадежный набор данных или тип DataTable в графе веб-десериализуемых объектов
- [CA2361](/visualstudio/code-quality/ca2361): Убедитесь, что автоматически сформированный класс содержит DataSet. ReadXml () не используется с ненадежными данными
- [CA2362](/visualstudio/code-quality/ca2362): ненадежный набор данных или DataTable в автоматически созданном сериализуемым типе может быть уязвим для атак удаленного выполнения кода

Дополнительные сведения о настройке правил см. в статье [использование анализаторов кода](/visualstudio/code-quality/use-roslyn-analyzers).

Новые правила безопасности доступны в следующих пакетах NuGet:

- Microsoft. CodeAnalysis. Фкскопанализерс 3.3.0: для Visual Studio 2019 версии 16,3 или более поздней.
- Microsoft. CodeAnalysis. Фкскопанализерс 2.9.11: для Visual Studio 2017 версии 15,9 или более поздней.
