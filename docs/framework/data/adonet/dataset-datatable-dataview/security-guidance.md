---
title: Набор данных и руководство по безопасности DataTable
ms.date: 07/14/2020
dev_langs:
- csharp
ms.openlocfilehash: 2fbac625ae0049fc4c363977dc1d3fbcfb376025
ms.sourcegitcommit: 3492dafceb5d4183b6b0d2f3bdf4a1abc4d5ed8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2020
ms.locfileid: "86416204"
---
# <a name="dataset-and-datatable-security-guidance"></a><span data-ttu-id="713e6-102">Набор данных и руководство по безопасности DataTable</span><span class="sxs-lookup"><span data-stu-id="713e6-102">DataSet and DataTable security guidance</span></span>

<span data-ttu-id="713e6-103">Эта статья относится к следующим продуктам:</span><span class="sxs-lookup"><span data-stu-id="713e6-103">This article applies to:</span></span>

* <span data-ttu-id="713e6-104">.NET Framework (все версии)</span><span class="sxs-lookup"><span data-stu-id="713e6-104">.NET Framework (all versions)</span></span>
* <span data-ttu-id="713e6-105">.NET Core и более поздние версии</span><span class="sxs-lookup"><span data-stu-id="713e6-105">.NET Core and later</span></span>
* <span data-ttu-id="713e6-106">.NET 5,0 и более поздние версии</span><span class="sxs-lookup"><span data-stu-id="713e6-106">.NET 5.0 and later</span></span>

<span data-ttu-id="713e6-107">Типы [DataSet](/dotnet/api/system.data.dataset) и [DataTable](/dotnet/api/system.data.datatable) являются устаревшими компонентами .NET, которые позволяют представлять наборы данных как управляемые объекты.</span><span class="sxs-lookup"><span data-stu-id="713e6-107">The [DataSet](/dotnet/api/system.data.dataset) and [DataTable](/dotnet/api/system.data.datatable) types are legacy .NET components that allow representing data sets as managed objects.</span></span> <span data-ttu-id="713e6-108">Эти компоненты появились в .NET 1,0 как часть исходной [инфраструктуры ADO.NET](/dotnet/framework/data/adonet/dataset-datatable-dataview/).</span><span class="sxs-lookup"><span data-stu-id="713e6-108">These components were introduced in .NET 1.0 as part of the original [ADO.NET infrastructure](/dotnet/framework/data/adonet/dataset-datatable-dataview/).</span></span> <span data-ttu-id="713e6-109">Их цель — предоставить управляемое представление по реляционному набору данных, чтобы отказаться от того, является ли базовый источник данных XML, SQL или другой технологией.</span><span class="sxs-lookup"><span data-stu-id="713e6-109">Their goal was to provide a managed view over a relational data set, abstracting away whether the underlying source of the data was XML, SQL, or another technology.</span></span>

<span data-ttu-id="713e6-110">Дополнительные сведения о ADO.NET, включая более современные парадигмы представления данных, см. [в документации по ADO.NET](/dotnet/framework/data/adonet/).</span><span class="sxs-lookup"><span data-stu-id="713e6-110">For more information on ADO.NET, including more modern data view paradigms, see [the ADO.NET documentation](/dotnet/framework/data/adonet/).</span></span>

## <a name="default-restrictions-when-deserializing-a-dataset-or-datatable-from-xml"></a><span data-ttu-id="713e6-111">Ограничения по умолчанию при десериализации набора данных или DataTable из XML</span><span class="sxs-lookup"><span data-stu-id="713e6-111">Default restrictions when deserializing a DataSet or DataTable from XML</span></span>

<span data-ttu-id="713e6-112">Во всех поддерживаемых версиях .NET Framework, .NET Core и .NET, а также `DataSet` `DataTable` накладываются следующие ограничения на типы объектов, которые могут присутствовать в десериализованных данных.</span><span class="sxs-lookup"><span data-stu-id="713e6-112">On all supported versions of .NET Framework, .NET Core, and .NET, `DataSet` and `DataTable` place the following restrictions on what types of objects may be present in the deserialized data.</span></span> <span data-ttu-id="713e6-113">По умолчанию этот список ограничен:</span><span class="sxs-lookup"><span data-stu-id="713e6-113">By default, this list is restricted to:</span></span>

* <span data-ttu-id="713e6-114">Примитивы и примитивные эквиваленты: `bool` , `char` , `sbyte` , `byte` , `short` , `ushort` , `int` , `uint` ,,, `long` `ulong` `float` `double` `decimal` `DateTime` `DateTimeOffset` `TimeSpan` `string` `Guid` `SqlBinary` `SqlBoolean` `SqlByte` `SqlBytes` `SqlChars` `SqlDateTime` `SqlDecimal` `SqlDouble` `SqlGuid` `SqlInt16` `SqlInt32` `SqlInt64` `SqlMoney` `SqlSingle` `SqlString` ,,,,,,,,,,,,,,,,,,,,,, и.</span><span class="sxs-lookup"><span data-stu-id="713e6-114">Primitives and primitive equivalents: `bool`, `char`, `sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, `decimal`, `DateTime`, `DateTimeOffset`, `TimeSpan`, `string`, `Guid`, `SqlBinary`, `SqlBoolean`, `SqlByte`, `SqlBytes`, `SqlChars`, `SqlDateTime`, `SqlDecimal`, `SqlDouble`, `SqlGuid`, `SqlInt16`, `SqlInt32`, `SqlInt64`, `SqlMoney`, `SqlSingle`, and `SqlString`.</span></span>
* <span data-ttu-id="713e6-115">Часто используемые не примитивы: `Type` , `Uri` и `BigInteger` .</span><span class="sxs-lookup"><span data-stu-id="713e6-115">Commonly used non-primitives: `Type`, `Uri`, and `BigInteger`.</span></span>
* <span data-ttu-id="713e6-116">Часто используемые типы _System. Drawing_ : `Color` , `Point` , `PointF` , `Rectangle` , `RectangleF` , `Size` и `SizeF` .</span><span class="sxs-lookup"><span data-stu-id="713e6-116">Commonly used _System.Drawing_ types: `Color`, `Point`, `PointF`, `Rectangle`, `RectangleF`, `Size`, and `SizeF`.</span></span>
* <span data-ttu-id="713e6-117">`Enum`типов.</span><span class="sxs-lookup"><span data-stu-id="713e6-117">`Enum` types.</span></span>
* <span data-ttu-id="713e6-118">Массивы и списки приведенных выше типов.</span><span class="sxs-lookup"><span data-stu-id="713e6-118">Arrays and lists of the above types.</span></span>

<span data-ttu-id="713e6-119">Если входящие XML-данные содержат объект, тип которого отсутствует в этом списке:</span><span class="sxs-lookup"><span data-stu-id="713e6-119">If the incoming XML data contains an object whose type is not in this list:</span></span>

* <span data-ttu-id="713e6-120">Возникает исключение.</span><span class="sxs-lookup"><span data-stu-id="713e6-120">An exception is thrown.</span></span>
* <span data-ttu-id="713e6-121">Операция десериализации завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="713e6-121">The deserialization operation fails.</span></span>

<span data-ttu-id="713e6-122">При загрузке XML в существующий `DataSet` экземпляр или `DataTable` можно учитывать существующие определения столбцов.</span><span class="sxs-lookup"><span data-stu-id="713e6-122">When loading XML into an existing `DataSet` or `DataTable` instance, the existing column definitions are also taken into account.</span></span> <span data-ttu-id="713e6-123">Если таблица уже содержит определение столбца пользовательского типа, этот тип временно добавляется в список разрешений на время выполнения операции десериализации XML.</span><span class="sxs-lookup"><span data-stu-id="713e6-123">If the table already contains a column definition of a custom type, that type is temporarily added to the allow list for the duration of the XML deserialization operation.</span></span>

```cs
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

<span data-ttu-id="713e6-124">Ограничения типа объекта также применяются при использовании `XmlSerializer` для десериализации экземпляра `DataSet` или `DataTable` .</span><span class="sxs-lookup"><span data-stu-id="713e6-124">The object type restrictions also apply when using `XmlSerializer` to deserialize an instance of `DataSet` or `DataTable`.</span></span> <span data-ttu-id="713e6-125">Однако они могут не применяться при использовании `BinaryFormatter` для десериализации экземпляра `DataSet` или `DataTable` .</span><span class="sxs-lookup"><span data-stu-id="713e6-125">However, they may not apply when using `BinaryFormatter` to deserialize an instance of `DataSet` or `DataTable`.</span></span>

<span data-ttu-id="713e6-126">Ограничения типа объекта не применяются при использовании `DataAdapter.Fill` , например при `DataTable` заполнении экземпляра непосредственно из базы данных без использования API-интерфейсов десериализации XML.</span><span class="sxs-lookup"><span data-stu-id="713e6-126">The object type restrictions don't apply when using `DataAdapter.Fill`, such as when a `DataTable` instance is populated directly from a database without using the XML deserialization APIs.</span></span>

### <a name="extend-the-list-of-allowed-types"></a><span data-ttu-id="713e6-127">Расширение списка разрешенных типов</span><span class="sxs-lookup"><span data-stu-id="713e6-127">Extend the list of allowed types</span></span>

<span data-ttu-id="713e6-128">Приложение может расширить список разрешенных типов, включив в него пользовательские типы, а также встроенные типы, перечисленные выше.</span><span class="sxs-lookup"><span data-stu-id="713e6-128">An app can extend the allowed types list to include custom types in addition to the built-in types listed above.</span></span> <span data-ttu-id="713e6-129">При расширении списка разрешенных типов изменение затрагивает _все_ `DataSet` `DataTable` экземпляры приложения и в нем.</span><span class="sxs-lookup"><span data-stu-id="713e6-129">If extending the allowed types list, the change affects _all_ `DataSet` and `DataTable` instances within the app.</span></span> <span data-ttu-id="713e6-130">Невозможно удалить типы из списка разрешенных типов.</span><span class="sxs-lookup"><span data-stu-id="713e6-130">Types cannot be removed from the built-in allowed types list.</span></span>

#### <a name="extend-through-configuration-net-framework-40---48"></a><span data-ttu-id="713e6-131">Расширение через конфигурацию (.NET Framework 4,0-4,8)</span><span class="sxs-lookup"><span data-stu-id="713e6-131">Extend through configuration (.NET Framework 4.0 - 4.8)</span></span>

<span data-ttu-id="713e6-132">_App.config_ можно использовать для расширения списка разрешенных типов.</span><span class="sxs-lookup"><span data-stu-id="713e6-132">_App.config_ can be used to extend the allowed types list.</span></span> <span data-ttu-id="713e6-133">Чтобы расширить список разрешенных типов, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="713e6-133">To extend the allowed types list:</span></span>

* <span data-ttu-id="713e6-134">Используйте `<configSections>` элемент, чтобы добавить ссылку на раздел конфигурации _System. Data_ .</span><span class="sxs-lookup"><span data-stu-id="713e6-134">Use the `<configSections>` element to add a reference to the _System.Data_ configuration section.</span></span>
* <span data-ttu-id="713e6-135">Используйте `<system.data.dataset.serialization>` / `<allowedTypes>` для указания дополнительных типов.</span><span class="sxs-lookup"><span data-stu-id="713e6-135">Use `<system.data.dataset.serialization>`/`<allowedTypes>` to specify additional types.</span></span>

<span data-ttu-id="713e6-136">Каждый `<add>` элемент должен указывать только один тип, используя полное имя типа сборки.</span><span class="sxs-lookup"><span data-stu-id="713e6-136">Each `<add>` element must specify only one type by using its assembly qualified type name.</span></span> <span data-ttu-id="713e6-137">Чтобы добавить дополнительные типы в список разрешенных типов, используйте несколько `<add>` элементов.</span><span class="sxs-lookup"><span data-stu-id="713e6-137">To add additional types to the allowed types list, use multiple `<add>` elements.</span></span>

<span data-ttu-id="713e6-138">В следующем примере показано расширение списка разрешенных типов путем добавления пользовательского типа `Fabrikam.CustomType` .</span><span class="sxs-lookup"><span data-stu-id="713e6-138">The following sample shows extending the allowed types list by adding the custom type `Fabrikam.CustomType`.</span></span>

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

<span data-ttu-id="713e6-139">Чтобы получить полное имя сборки типа, используйте свойство [Type. AssemblyQualifiedName](/dotnet/api/system.type.assemblyqualifiedname) , как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="713e6-139">To retrieve the assembly qualified name of a type, use the [Type.AssemblyQualifiedName](/dotnet/api/system.type.assemblyqualifiedname) property, as demonstrated in the following code.</span></span>

```cs
string assemblyQualifiedName = typeof(Fabrikam.CustomType).AssemblyQualifiedName;
```

<a name="etc"></a>

#### <a name="extend-through-configuration-net-framework-20---35"></a><span data-ttu-id="713e6-140">Расширение через конфигурацию (.NET Framework 2,0-3,5)</span><span class="sxs-lookup"><span data-stu-id="713e6-140">Extend through configuration (.NET Framework 2.0 - 3.5)</span></span>

<span data-ttu-id="713e6-141">Если приложение предназначено для .NET Framework 2,0 или 3,5, вы по-прежнему можете использовать описанный выше механизм _App.config_ для расширения списка разрешенных типов.</span><span class="sxs-lookup"><span data-stu-id="713e6-141">If your app targets .NET Framework 2.0 or 3.5, you can still use the above _App.config_ mechanism to extend the allowed types list.</span></span> <span data-ttu-id="713e6-142">Однако `<configSections>` элемент будет выглядеть немного иначе, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="713e6-142">However, your `<configSections>` element will look slightly different, as shown in the following code:</span></span>

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

#### <a name="extend-programmatically-net-framework-net-core-net-50"></a><span data-ttu-id="713e6-143">Расширение программным способом (.NET Framework, .NET Core, .NET 5.0 +)</span><span class="sxs-lookup"><span data-stu-id="713e6-143">Extend programmatically (.NET Framework, .NET Core, .NET 5.0+)</span></span>

<span data-ttu-id="713e6-144">Список разрешенных типов также можно расширить программно с помощью [AppDomain. SetData](/dotnet/api/system.appdomain.setdata) с хорошо известным ключом _System. Data. датасетдефаулталловедтипес_, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="713e6-144">The list of allowed types can also be extended programmatically by using [AppDomain.SetData](/dotnet/api/system.appdomain.setdata) with the well-known key _System.Data.DataSetDefaultAllowedTypes_, as shown in the following code.</span></span>

```cs
Type[] extraAllowedTypes = new Type[]
{
    typeof(Fabrikam.CustomType),
    typeof(Contoso.AdditionalCustomType)
};

AppDomain.CurrentDomain.SetData("System.Data.DataSetDefaultAllowedTypes", extraAllowedTypes);
```

<span data-ttu-id="713e6-145">При использовании механизма расширения значение, связанное с ключом _System. Data. датасетдефаулталловедтипес_ , должно иметь тип `Type[]` .</span><span class="sxs-lookup"><span data-stu-id="713e6-145">If using the extension mechanism, the value associated with the key _System.Data.DataSetDefaultAllowedTypes_ must be of type `Type[]`.</span></span>

<span data-ttu-id="713e6-146">В .NET Framework список разрешенных типов можно расширить с помощью _App.config_ и `AppDomain.SetData` .</span><span class="sxs-lookup"><span data-stu-id="713e6-146">On .NET Framework, the list of allowed types may be extended both with _App.config_ and `AppDomain.SetData`.</span></span> <span data-ttu-id="713e6-147">В этом случае `DataSet` и `DataTable` позволяет десериализовать объект как часть данных, если его тип имеется в любом из списков.</span><span class="sxs-lookup"><span data-stu-id="713e6-147">In this case, `DataSet` and `DataTable` will allow an object to be deserialized as part of the data if its type is present in either list.</span></span>

### <a name="run-an-app-in-audit-mode-net-framework"></a><span data-ttu-id="713e6-148">Запуск приложения в режиме аудита (.NET Framework)</span><span class="sxs-lookup"><span data-stu-id="713e6-148">Run an app in audit mode (.NET Framework)</span></span>

<span data-ttu-id="713e6-149">В .NET Framework `DataSet` и `DataTable` Предоставьте возможность режима аудита.</span><span class="sxs-lookup"><span data-stu-id="713e6-149">In .NET Framework, `DataSet` and `DataTable` provide an audit mode capability.</span></span> <span data-ttu-id="713e6-150">Если включен режим аудита `DataSet` и `DataTable` Сравнение типов входящих объектов со списком разрешенных типов.</span><span class="sxs-lookup"><span data-stu-id="713e6-150">When audit mode is enabled, `DataSet` and `DataTable` compare the types of incoming objects against the allowed types list.</span></span> <span data-ttu-id="713e6-151">Однако если объект, тип которого не разрешен, отображается, исключение **не** создается.</span><span class="sxs-lookup"><span data-stu-id="713e6-151">However, if an object whose type is not allowed is seen, an exception is **not** thrown.</span></span> <span data-ttu-id="713e6-152">Вместо этого `DataSet` и `DataTable` уведомлять все подключенные `TraceListener` экземпляры о наличии подозрительного типа, позволяя `TraceListener` записывать эти сведения в журнал.</span><span class="sxs-lookup"><span data-stu-id="713e6-152">Instead, `DataSet` and `DataTable` notify any attached `TraceListener` instances that a suspicious type is present, allowing the `TraceListener` to log this information.</span></span> <span data-ttu-id="713e6-153">Исключение не создается, и Операция десериализации сохраняется.</span><span class="sxs-lookup"><span data-stu-id="713e6-153">No exception is thrown and the deserialization operation continues.</span></span>

> [!WARNING]
> <span data-ttu-id="713e6-154">Запуск приложения в режиме аудита должен быть только временной мерой, используемой для тестирования.</span><span class="sxs-lookup"><span data-stu-id="713e6-154">Running an app in "audit mode" should only be a temporary measure used for testing.</span></span> <span data-ttu-id="713e6-155">Если включен режим аудита `DataSet` и `DataTable` не применяются ограничения типа, что может вызвать брешь в системе безопасности в приложении.</span><span class="sxs-lookup"><span data-stu-id="713e6-155">When audit mode is enabled, `DataSet` and `DataTable` do not enforce type restrictions, which can introduce a security hole inside your app.</span></span> <span data-ttu-id="713e6-156">Дополнительные сведения см. в разделах [Удаление всех ограничений на типы](#ratr) и [безопасность с учетом ненадежных входных данных](#swr).</span><span class="sxs-lookup"><span data-stu-id="713e6-156">For more information, see the sections titled [Removing all type restrictions](#ratr) and [Safety with regard to untrusted input](#swr).</span></span>

<span data-ttu-id="713e6-157">Режим аудита можно включить с помощью _App.config_:</span><span class="sxs-lookup"><span data-stu-id="713e6-157">Audit mode can be enabled through _App.config_:</span></span>

* <span data-ttu-id="713e6-158">Сведения о правильном значении для размещения элемента см. в разделе [расширение конфигурации](#etc) в этом документе `<configSections>` .</span><span class="sxs-lookup"><span data-stu-id="713e6-158">See the [Extending through configuration](#etc) section in this document for information on the proper value to put for the `<configSections>` element.</span></span>
* <span data-ttu-id="713e6-159">Используйте `<allowedTypes auditOnly="true">` для включения режима аудита, как показано в следующей разметке.</span><span class="sxs-lookup"><span data-stu-id="713e6-159">Use `<allowedTypes auditOnly="true">` to enable audit mode, as shown in the following markup.</span></span>

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

<span data-ttu-id="713e6-160">После включения режима аудита можно использовать _App.config_ , чтобы подключиться к `TraceListener` `DataSet` встроенному `TraceSource.` источнику трассировки по имени _System. Data. DataSet_.</span><span class="sxs-lookup"><span data-stu-id="713e6-160">Once audit mode is enabled, you can use _App.config_ to connect your preferred `TraceListener` to the `DataSet` built-in `TraceSource.` The name of the built-in trace source is _System.Data.DataSet_.</span></span> <span data-ttu-id="713e6-161">В следующем примере демонстрируется запись событий трассировки в консоль _и_ в файл журнала на диске.</span><span class="sxs-lookup"><span data-stu-id="713e6-161">The following sample demonstrates writing trace events to the console _and_ to a log file on disk.</span></span>

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

<span data-ttu-id="713e6-162">Дополнительные сведения о `TraceSource` и см `TraceListener` . в документе [практические руководства. использование TraceSource и фильтров с прослушивателями трассировки](../../../debug-trace-profile/how-to-use-tracesource-and-filters-with-trace-listeners.md).</span><span class="sxs-lookup"><span data-stu-id="713e6-162">For more information on `TraceSource` and `TraceListener`, see the document [How to: Use TraceSource and Filters with Trace Listeners](../../../debug-trace-profile/how-to-use-tracesource-and-filters-with-trace-listeners.md).</span></span>

> [!NOTE]
> <span data-ttu-id="713e6-163">Запуск приложения в режиме аудита недоступен в .NET Core или .NET 5,0 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="713e6-163">Running an app in audit mode is not available in .NET Core or in .NET 5.0 and later.</span></span>

<a name="ratr"></a>

### <a name="remove-all-type-restrictions"></a><span data-ttu-id="713e6-164">Удалить все ограничения типа</span><span class="sxs-lookup"><span data-stu-id="713e6-164">Remove all type restrictions</span></span>

<span data-ttu-id="713e6-165">Если приложение должно удалить все ограничения, ограничивающие тип `DataSet` , в и `DataTable` :</span><span class="sxs-lookup"><span data-stu-id="713e6-165">If an app must remove all type limiting restrictions from `DataSet` and `DataTable`:</span></span>

* <span data-ttu-id="713e6-166">Существует несколько вариантов отключения ограничений типа.</span><span class="sxs-lookup"><span data-stu-id="713e6-166">There are several options to suppress type limiting restrictions.</span></span>
* <span data-ttu-id="713e6-167">Доступные параметры зависят от платформы, для которой предназначено приложение.</span><span class="sxs-lookup"><span data-stu-id="713e6-167">The options available depend on the framework the app targets.</span></span>

> [!WARNING]
> <span data-ttu-id="713e6-168">Удаление всех ограничений типа может вызвать брешь в системе безопасности внутри приложения.</span><span class="sxs-lookup"><span data-stu-id="713e6-168">Removing all type restrictions can introduce a security hole inside the app.</span></span> <span data-ttu-id="713e6-169">При использовании этого механизма убедитесь, что приложение не **использует** `DataSet` или `DataTable` для чтения недоверенных входных данных.</span><span class="sxs-lookup"><span data-stu-id="713e6-169">When using this mechanism, ensure the app does **not** use `DataSet` or `DataTable` to read untrusted input.</span></span> <span data-ttu-id="713e6-170">Дополнительные сведения см. в статье [CVE-2020-1147](https://portal.msrc.microsoft.com/en-us/security-guidance/advisory/CVE-2020-1147) и следующем разделе [безопасность с учетом ненадежных входов](#swr).</span><span class="sxs-lookup"><span data-stu-id="713e6-170">For more information, see [CVE-2020-1147](https://portal.msrc.microsoft.com/en-us/security-guidance/advisory/CVE-2020-1147) and the following section titled [Safety with regard to untrusted input](#swr).</span></span>

#### <a name="through-appcontext-configuration-net-framework-46---48-net-core-21-and-later-net-50-and-later"></a><span data-ttu-id="713e6-171">Через AppContext Configuration (.NET Framework 4,6-4,8, .NET Core 2,1 и более поздних версий, .NET 5,0 и более поздние версии)</span><span class="sxs-lookup"><span data-stu-id="713e6-171">Through AppContext configuration (.NET Framework 4.6 - 4.8, .NET Core 2.1 and later, .NET 5.0 and later)</span></span>

<span data-ttu-id="713e6-172">`AppContext`Параметр, `Switch.System.Data.AllowArbitraryDataSetTypeInstantiation` при установке которого `true` удаляет все ограничения, ограничивающие типы `DataSet` , от и `DataTable` .</span><span class="sxs-lookup"><span data-stu-id="713e6-172">The `AppContext` switch, `Switch.System.Data.AllowArbitraryDataSetTypeInstantiation`, when set to `true` removes all type limiting restrictions from `DataSet` and `DataTable`.</span></span>

<span data-ttu-id="713e6-173">В .NET Framework этот коммутатор можно включить с помощью _App.config_, как показано в следующей конфигурации:</span><span class="sxs-lookup"><span data-stu-id="713e6-173">In .NET Framework, this switch can be enabled via _App.config_, as shown in the following configuration:</span></span>

```xml
<configuration>
   <runtime>
      <!-- Warning: setting the following switch can introduce a security problem. -->
      <AppContextSwitchOverrides value="Switch.System.Data.AllowArbitraryDataSetTypeInstantiation=true" />
   </runtime>
</configuration>
```

<span data-ttu-id="713e6-174">В ASP.NET `<AppContextSwitchOverrides>` элемент недоступен.</span><span class="sxs-lookup"><span data-stu-id="713e6-174">In ASP.NET, the `<AppContextSwitchOverrides>` element is not available.</span></span> <span data-ttu-id="713e6-175">Вместо этого коммутатор можно включить с помощью _Web.config_, как показано в следующей конфигурации:</span><span class="sxs-lookup"><span data-stu-id="713e6-175">Instead, the switch can be enabled via _Web.config_, as shown in the following configuration:</span></span>

```xml
<configuration>
    <appSettings>
        <!-- Warning: setting the following switch can introduce a security problem. -->
        <add key="AppContext.SetSwitch:Switch.System.Data.AllowArbitraryDataSetTypeInstantiation" value="true" />
    </appSettings>
</configuration>
```

<span data-ttu-id="713e6-176">Дополнительные сведения см. в описании [\<AppContextSwitchOverrides>](../../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="713e6-176">For more information, see the [\<AppContextSwitchOverrides>](../../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element.</span></span>

<span data-ttu-id="713e6-177">В .NET Core, .NET 5 и ASP.NET Core этот параметр управляется _runtimeconfig.jsв_, как показано в следующем примере JSON:</span><span class="sxs-lookup"><span data-stu-id="713e6-177">In .NET Core, .NET 5, and ASP.NET Core, this setting is controlled by _runtimeconfig.json_, as shown in the following JSON:</span></span>

```json
{
  "runtimeOptions": {
    "configProperties": {
      "Switch.System.Data.AllowArbitraryDataSetTypeInstantiation": true
    }
  }
}
```

<span data-ttu-id="713e6-178">Дополнительные сведения см. в разделе ["параметры конфигурации среды выполнения .NET Core"](/dotnet/core/run-time-config/).</span><span class="sxs-lookup"><span data-stu-id="713e6-178">For more information, see [".NET Core run-time configuration settings"](/dotnet/core/run-time-config/).</span></span>

<span data-ttu-id="713e6-179">`AllowArbitraryDataSetTypeInstantiation`также можно задать программно с помощью [AppContext. сетсвитч](/dotnet/api/system.appcontext.setswitch) вместо файла конфигурации, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="713e6-179">`AllowArbitraryDataSetTypeInstantiation` can also be set programmatically via [AppContext.SetSwitch](/dotnet/api/system.appcontext.setswitch) instead of using a configuration file, as shown in the following code:</span></span>

```cs
// Warning: setting the following switch can introduce a security problem.
AppContext.SetSwitch("Switch.System.Data.AllowArbitraryDataSetTypeInstantiation", true);
```

 <span data-ttu-id="713e6-180">При выборе предыдущего программного подхода вызов метода `AppContext.SetSwitch` должен выполняться на раннем этапе запуска приложений.</span><span class="sxs-lookup"><span data-stu-id="713e6-180">If you choose the preceding programmatic approach, the call to `AppContext.SetSwitch` should occur early in the apps startup.</span></span>

#### <a name="through-the-machine-wide-registry-net-framework-20---48"></a><span data-ttu-id="713e6-181">Через реестр на уровне компьютера (.NET Framework 2,0-4,8);</span><span class="sxs-lookup"><span data-stu-id="713e6-181">Through the machine-wide registry (.NET Framework 2.0 - 4.8)</span></span>

<span data-ttu-id="713e6-182">Если параметр `AppContext` недоступен, проверка ограничений типов может быть отключена с помощью реестра Windows:</span><span class="sxs-lookup"><span data-stu-id="713e6-182">If `AppContext` is not available, type limiting checks can be disabled with the Windows registry:</span></span>

* <span data-ttu-id="713e6-183">Администратор должен настроить реестр.</span><span class="sxs-lookup"><span data-stu-id="713e6-183">An administrator must configure the registry.</span></span>
* <span data-ttu-id="713e6-184">Использование реестра является изменением на уровне компьютера и влияет на _все_ приложения, выполняющиеся на компьютере.</span><span class="sxs-lookup"><span data-stu-id="713e6-184">Using the registry is a machine-wide change and will affect _all_ apps running on the machine.</span></span>

| <span data-ttu-id="713e6-185">Тип</span><span class="sxs-lookup"><span data-stu-id="713e6-185">Type</span></span>  |  <span data-ttu-id="713e6-186">Значение</span><span class="sxs-lookup"><span data-stu-id="713e6-186">Value</span></span> |
|---|---|
| <span data-ttu-id="713e6-187">**Раздел реестра**</span><span class="sxs-lookup"><span data-stu-id="713e6-187">**Registry key**</span></span> | `HKLM\SOFTWARE\Microsoft\.NETFramework\AppContext` |
| <span data-ttu-id="713e6-188">**Имя значения**</span><span class="sxs-lookup"><span data-stu-id="713e6-188">**Value name**</span></span> | `Switch.System.Data.AllowArbitraryDataSetTypeInstantiation` |
| <span data-ttu-id="713e6-189">**Тип значения**</span><span class="sxs-lookup"><span data-stu-id="713e6-189">**Value type**</span></span> | `REG_SZ` |
| <span data-ttu-id="713e6-190">**Данные**</span><span class="sxs-lookup"><span data-stu-id="713e6-190">**Value data**</span></span> | `true` |

<span data-ttu-id="713e6-191">В 64-разрядной операционной системе это значение необходимо добавить как для 64-разрядного ключа (показанного выше), так и для ключа 32-bit.</span><span class="sxs-lookup"><span data-stu-id="713e6-191">On a 64-bit operating system, this value my need to be added for both the 64-bit key (shown above) and the 32-bit key.</span></span> <span data-ttu-id="713e6-192">32-разрядный ключ находится в папке `HKLM\SOFTWARE\WOW6432Node\Microsoft\.NETFramework\AppContext` .</span><span class="sxs-lookup"><span data-stu-id="713e6-192">The 32-bit key is located at `HKLM\SOFTWARE\WOW6432Node\Microsoft\.NETFramework\AppContext`.</span></span>

<span data-ttu-id="713e6-193">Дополнительные сведения об использовании реестра для настройки `AppContext` см. в разделе [«AppContext для потребителей библиотек»](/dotnet/api/system.appcontext#appcontext-for-library-consumers).</span><span class="sxs-lookup"><span data-stu-id="713e6-193">For more information on using the registry to configure `AppContext`, see ["AppContext for library consumers"](/dotnet/api/system.appcontext#appcontext-for-library-consumers).</span></span>

<a name="swr"></a>

## <a name="safety-with-regard-to-untrusted-input"></a><span data-ttu-id="713e6-194">Безопасность в отношении ненадежных входных данных</span><span class="sxs-lookup"><span data-stu-id="713e6-194">Safety with regard to untrusted input</span></span>

<span data-ttu-id="713e6-195">Хотя `DataSet` и `DataTable` накладывают ограничения по умолчанию на типы, которые могут присутствовать при ДЕСЕРИАЛИЗАЦИИ XML-полезных данных, __ `DataSet` и `DataTable` в общем случае ненадежны при заполнении недоверенными входными данными.__</span><span class="sxs-lookup"><span data-stu-id="713e6-195">While `DataSet` and `DataTable` do impose default limitations on the types that are allowed to be present while deserializing XML payloads, __`DataSet` and `DataTable` are in general not safe when populated with untrusted input.__</span></span> <span data-ttu-id="713e6-196">Ниже приведен неисчерпывающий список способов, с помощью которых `DataSet` `DataTable` экземпляр или может считывать ненадежные входные данные.</span><span class="sxs-lookup"><span data-stu-id="713e6-196">The following is a non-exhaustive list of ways that a `DataSet` or `DataTable` instance might read untrusted input.</span></span>

* <span data-ttu-id="713e6-197">Объект `DataAdapter` ссылается на базу данных, а `DataAdapter.Fill` метод используется для заполнения `DataSet` с помощью содержимого запроса к базе данных.</span><span class="sxs-lookup"><span data-stu-id="713e6-197">A `DataAdapter` references a database, and the `DataAdapter.Fill` method is used to populate a `DataSet` with the contents of a database query.</span></span>
* <span data-ttu-id="713e6-198">`DataSet.ReadXml`Метод или `DataTable.ReadXml` используется для чтения XML-файла, содержащего сведения о столбцах и строках.</span><span class="sxs-lookup"><span data-stu-id="713e6-198">The `DataSet.ReadXml` or `DataTable.ReadXml` method is used to read an XML file containing column and row information.</span></span>
* <span data-ttu-id="713e6-199">`DataSet`Экземпляр или `DataTable` сериализуется как часть ASP.NET (SOAP) веб-служб или КОНЕЧНОЙ точки WCF.</span><span class="sxs-lookup"><span data-stu-id="713e6-199">A `DataSet` or `DataTable` instance is serialized as part of a ASP.NET (SOAP) web services or WCF endpoint.</span></span>
* <span data-ttu-id="713e6-200">Сериализатор, такой как `XmlSerializer` , используется для десериализации `DataSet` `DataTable` экземпляра или из потока XML.</span><span class="sxs-lookup"><span data-stu-id="713e6-200">A serializer such as `XmlSerializer` is used to deserialize a `DataSet` or `DataTable` instance from an XML stream.</span></span>
* <span data-ttu-id="713e6-201">Сериализатор, такой как `JsonConvert` , используется для десериализации `DataSet` `DataTable` экземпляра или из потока JSON.</span><span class="sxs-lookup"><span data-stu-id="713e6-201">A serializer such as `JsonConvert` is used to deserialize a `DataSet` or `DataTable` instance from a JSON stream.</span></span> <span data-ttu-id="713e6-202">`JsonConvert`— Это метод в популярном [Newtonsoft.Jsе](https://www.newtonsoft.com/json) стороннего производителя для библиотеки.</span><span class="sxs-lookup"><span data-stu-id="713e6-202">`JsonConvert` is a method in the popular third-party [Newtonsoft.Json](https://www.newtonsoft.com/json) library.</span></span>
* <span data-ttu-id="713e6-203">Сериализатор, такой как `BinaryFormatter` , используется для десериализации `DataSet` `DataTable` экземпляра или из потока необработанных байтов.</span><span class="sxs-lookup"><span data-stu-id="713e6-203">A serializer such as `BinaryFormatter` is used to deserialize a `DataSet` or `DataTable` instance from a raw byte stream.</span></span>

<span data-ttu-id="713e6-204">В этом документе обсуждаются вопросы безопасности в предыдущих сценариях.</span><span class="sxs-lookup"><span data-stu-id="713e6-204">This document discusses safety considerations for the preceding scenarios.</span></span>

## <a name="use-dataadapterfill-to-populate-a-dataset-from-an-untrusted-data-source"></a><span data-ttu-id="713e6-205">Использование `DataAdapter.Fill` для заполнения `DataSet` из ненадежного источника данных</span><span class="sxs-lookup"><span data-stu-id="713e6-205">Use `DataAdapter.Fill` to populate a `DataSet` from an untrusted data source</span></span>

<span data-ttu-id="713e6-206">`DataSet`Экземпляр можно заполнить с помощью `DataAdapter` [ `DataAdapter.Fill` метода](/dotnet/api/system.data.common.dataadapter.fill), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="713e6-206">A `DataSet` instance can be populated from a `DataAdapter` by using [the `DataAdapter.Fill` method](/dotnet/api/system.data.common.dataadapter.fill), as shown in the following example.</span></span>

```cs
// Assumes that connection is a valid SqlConnection object.  
string queryString =
  "SELECT CustomerID, CompanyName FROM dbo.Customers";  
SqlDataAdapter adapter = new SqlDataAdapter(queryString, connection);  
  
DataSet customers = new DataSet();  
adapter.Fill(customers, "Customers");
```

<span data-ttu-id="713e6-207">(Приведенный выше пример кода является частью более крупного примера, найденного при [заполнении набора данных из DataAdapter](../populating-a-dataset-from-a-dataadapter.md).)</span><span class="sxs-lookup"><span data-stu-id="713e6-207">(The code sample above is part of a larger sample found at [Populating a DataSet from a DataAdapter](../populating-a-dataset-from-a-dataadapter.md).)</span></span>

> <span data-ttu-id="713e6-208">Большинство приложений могут упростить и предположить, что их уровень базы данных является доверенным.</span><span class="sxs-lookup"><span data-stu-id="713e6-208">Most apps can simplify and assume that their database layer is trusted.</span></span> <span data-ttu-id="713e6-209">Тем не менее, если вы в привычке [моделирования угроз](https://www.microsoft.com/securityengineering/sdl/threatmodeling) для приложений, модель угроз может считать, что между приложением (клиентом) и уровнем базы данных (сервер) есть граница доверия.</span><span class="sxs-lookup"><span data-stu-id="713e6-209">However, if you are in the habit of [threat modeling](https://www.microsoft.com/securityengineering/sdl/threatmodeling) your apps, your threat model may consider there to be a trust boundary between the application (client) and database layer (server).</span></span> <span data-ttu-id="713e6-210">Использование [взаимной проверки подлинности](/sql/relational-databases/native-client/features/service-principal-name-spn-support-in-client-connections) или [проверки подлинности AAD](/azure/azure-sql/database/authentication-aad-overview) между клиентом и сервером является одним из способов помочь в устранении рисков, связанных с этим.</span><span class="sxs-lookup"><span data-stu-id="713e6-210">Using [mutual authentication](/sql/relational-databases/native-client/features/service-principal-name-spn-support-in-client-connections) or [AAD authentication](/azure/azure-sql/database/authentication-aad-overview) between client and server is one way to help address the risks associated with this.</span></span> <span data-ttu-id="713e6-211">Оставшаяся часть этого раздела посвящена возможному результату подключения клиента к серверу, который не является доверенным.</span><span class="sxs-lookup"><span data-stu-id="713e6-211">The remainder of this section discusses the possible result of a client connecting to an untrusted server.</span></span>

<span data-ttu-id="713e6-212">Последствия, указывающие на `DataAdapter` ненадежный источник данных, зависят от реализации `DataAdapter` самого себя.</span><span class="sxs-lookup"><span data-stu-id="713e6-212">The consequences of pointing a `DataAdapter` at an untrusted data source depend on the implementation of the `DataAdapter` itself.</span></span>

### <a name="sqldataadapter"></a><span data-ttu-id="713e6-213">SqlDataAdapter;</span><span class="sxs-lookup"><span data-stu-id="713e6-213">SqlDataAdapter</span></span>

<span data-ttu-id="713e6-214">Для встроенного типа [SqlDataAdapter](/dotnet/api/microsoft.data.sqlclient.sqldataadapter)ссылка на ненадежный источник данных может привести к атаке типа "отказ в обслуживании" (DOS).</span><span class="sxs-lookup"><span data-stu-id="713e6-214">For the built-in type [SqlDataAdapter](/dotnet/api/microsoft.data.sqlclient.sqldataadapter), referencing an untrusted data source could result in a denial of service (DoS) attack.</span></span> <span data-ttu-id="713e6-215">Атака с помощью DoS может привести к тому, что приложение перестанет отвечать или аварийно завершить работу.</span><span class="sxs-lookup"><span data-stu-id="713e6-215">The DoS attack could result in the app becoming unresponsive or crashing.</span></span> <span data-ttu-id="713e6-216">Если злоумышленник может разместить библиотеку DLL вместе с приложением, он также может обеспечить возможность выполнения локального кода.</span><span class="sxs-lookup"><span data-stu-id="713e6-216">If an attacker can plant a DLL alongside the app, they may also be able to achieve local code execution.</span></span>

### <a name="other-dataadapter-types"></a><span data-ttu-id="713e6-217">Другие типы DataAdapter</span><span class="sxs-lookup"><span data-stu-id="713e6-217">Other DataAdapter types</span></span>

<span data-ttu-id="713e6-218">Сторонние `DataAdapter` реализации должны самостоятельно выполнять оценку того, какие гарантии безопасности они предоставляют в ненадежных входных данных.</span><span class="sxs-lookup"><span data-stu-id="713e6-218">Third-party `DataAdapter` implementations must make their own assessments about what security guarantees they provide in the face of untrusted inputs.</span></span> <span data-ttu-id="713e6-219">.NET не может предоставлять гарантии безопасности в отношении этих реализаций.</span><span class="sxs-lookup"><span data-stu-id="713e6-219">.NET cannot make any safety guarantees regarding these implementations.</span></span>

<a name="dsrdtr"></a>

## <a name="datasetreadxml-and-datatablereadxml"></a><span data-ttu-id="713e6-220">DataSet. ReadXml и DataTable. ReadXml</span><span class="sxs-lookup"><span data-stu-id="713e6-220">DataSet.ReadXml and DataTable.ReadXml</span></span>

<span data-ttu-id="713e6-221">`DataSet.ReadXml`Методы и `DataTable.ReadXml` не являются надежными при использовании с ненадежными входными данными.</span><span class="sxs-lookup"><span data-stu-id="713e6-221">The `DataSet.ReadXml` and `DataTable.ReadXml` methods are not safe when used with untrusted input.</span></span> <span data-ttu-id="713e6-222">Мы настоятельно рекомендуем пользователям использовать один из вариантов, описанных далее в этом документе.</span><span class="sxs-lookup"><span data-stu-id="713e6-222">We strongly recommend that consumers instead consider using one of the alternatives outlined later in this document.</span></span>

<span data-ttu-id="713e6-223">Реализации `DataSet.ReadXml` и `DataTable.ReadXml` изначально были созданы до того, как уязвимые места сериализации были хорошо понятными категориями угроз.</span><span class="sxs-lookup"><span data-stu-id="713e6-223">The implementations of `DataSet.ReadXml` and `DataTable.ReadXml` were originally created before serialization vulnerabilities were a well-understood threat category.</span></span> <span data-ttu-id="713e6-224">В результате код не соответствует текущим рекомендациям по обеспечению безопасности.</span><span class="sxs-lookup"><span data-stu-id="713e6-224">As a result, the code does not follow current security best practices.</span></span> <span data-ttu-id="713e6-225">Эти API-интерфейсы можно использовать в качестве векторов, чтобы злоумышленники могли совершать атаки через DoS в отношении приложений.</span><span class="sxs-lookup"><span data-stu-id="713e6-225">These APIs can be used as vectors for attackers to perform DoS attacks against web apps.</span></span> <span data-ttu-id="713e6-226">Эти атаки могут привести к невозможности отклика веб-службы или вызвать непредвиденное завершение процесса.</span><span class="sxs-lookup"><span data-stu-id="713e6-226">These attacks might render the web service unresponsive or result in unexpected process termination.</span></span> <span data-ttu-id="713e6-227">Платформа не обеспечивает устранение рисков для этих категорий атак, и .NET считает это поведение «по разработке».</span><span class="sxs-lookup"><span data-stu-id="713e6-227">The framework does not provide mitigations for these attack categories and .NET considers this behavior "by design".</span></span>

<span data-ttu-id="713e6-228">.NET выпускает обновления для системы безопасности, чтобы устранить некоторые проблемы, такие как раскрытие информации или удаленное выполнение кода в `DataSet.ReadXml` и `DataTable.ReadXml` .</span><span class="sxs-lookup"><span data-stu-id="713e6-228">.NET has released security updates to mitigate some issues such as information disclosure or remote code execution in `DataSet.ReadXml` and `DataTable.ReadXml`.</span></span> <span data-ttu-id="713e6-229">Обновления для системы безопасности .NET могут не обеспечивать полную защиту от этих категорий угроз.</span><span class="sxs-lookup"><span data-stu-id="713e6-229">The .NET security updates may not provide complete protection against these threat categories.</span></span> <span data-ttu-id="713e6-230">Потребители должны оценивать отдельные сценарии и рассматривают их потенциальные угрозы.</span><span class="sxs-lookup"><span data-stu-id="713e6-230">Consumers should assess their individual scenarios and consider their potential exposure to these risks.</span></span>

<span data-ttu-id="713e6-231">Потребители должны учитывать, что обновления безопасности этих API могут повлиять на совместимость приложений в некоторых ситуациях.</span><span class="sxs-lookup"><span data-stu-id="713e6-231">Consumers should be aware that security updates to these APIs may impact application compatibility in some situations.</span></span> <span data-ttu-id="713e6-232">Кроме того, существует вероятность того, что в этих API будет обнаружена романская уязвимость, для которой .NET не может фактически публиковать обновление для системы безопасности.</span><span class="sxs-lookup"><span data-stu-id="713e6-232">Furthermore, the possibility exists that a novel vulnerability in these APIs will be discovered for which .NET can't practically publish a security update.</span></span>

<span data-ttu-id="713e6-233">Рекомендуется, чтобы потребители этих API были:</span><span class="sxs-lookup"><span data-stu-id="713e6-233">We recommend that consumers of these APIs either:</span></span>

* <span data-ttu-id="713e6-234">Попробуйте использовать один из вариантов, описанных далее в этом документе.</span><span class="sxs-lookup"><span data-stu-id="713e6-234">Consider using one of the alternatives outlined later in this document.</span></span>
* <span data-ttu-id="713e6-235">Выполните оценку отдельных рисков для своих приложений.</span><span class="sxs-lookup"><span data-stu-id="713e6-235">Perform individual risk assessments on their apps.</span></span>

<span data-ttu-id="713e6-236">Это единственная обязанность потребителя, позволяющая определить, следует ли использовать эти API.</span><span class="sxs-lookup"><span data-stu-id="713e6-236">It is the consumer's sole responsibility to determine whether to utilize these APIs.</span></span> <span data-ttu-id="713e6-237">Потребители должны оценивать любые вопросы безопасности, технические и юридические риски, включая нормативные требования, которые могут сопровождаться использованием этих API.</span><span class="sxs-lookup"><span data-stu-id="713e6-237">Consumers should assess any security, technical, and legal risks, including regulatory requirements, that may accompany using these APIs.</span></span>

## <a name="dataset-and-datatable-via-aspnet-web-services-or-wcf"></a><span data-ttu-id="713e6-238">DataSet и DataTable через веб-службы ASP.NET или WCF</span><span class="sxs-lookup"><span data-stu-id="713e6-238">DataSet and DataTable via ASP.NET web services or WCF</span></span>

<span data-ttu-id="713e6-239">Можно принять `DataSet` или `DataTable` экземпляр в веб-службе ASP.NET (SOAP), как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="713e6-239">It is possible to accept a `DataSet` or a `DataTable` instance in an ASP.NET (SOAP) web service, as demonstrated in the following code:</span></span>

```cs
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

<span data-ttu-id="713e6-240">Вариация в этом случае не принимает `DataSet` или не `DataTable` напрямую в качестве параметра, а принимает его как часть общего сериализованного графа объектов SOAP, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="713e6-240">A variation on this is not to accept `DataSet` or `DataTable` directly as a parameter, but instead to accept it as part of the overall SOAP serialized object graph, as shown in the following code:</span></span>

```cs
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

<span data-ttu-id="713e6-241">Или используйте WCF вместо веб-служб ASP.NET:</span><span class="sxs-lookup"><span data-stu-id="713e6-241">Or, using WCF instead of ASP.NET web services:</span></span>

```cs
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

<span data-ttu-id="713e6-242">Во всех этих случаях модель угроз и гарантии безопасности аналогичны [разделам DataSet. ReadXml и DataTable. ReadXml](#dsrdtr).</span><span class="sxs-lookup"><span data-stu-id="713e6-242">In all of these cases, the threat model and security guarantees are the same as the [DataSet.ReadXml and DataTable.ReadXml section](#dsrdtr).</span></span>

## <a name="deserialize-a-dataset-or-datatable-via-xmlserializer"></a><span data-ttu-id="713e6-243">Десериализация набора данных или DataTable через XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="713e6-243">Deserialize a DataSet or DataTable via XmlSerializer</span></span>

<span data-ttu-id="713e6-244">Разработчики могут использовать `XmlSerializer` для десериализации `DataSet` и `DataTable` экземпляров, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="713e6-244">Developers can use `XmlSerializer` to deserialize `DataSet` and `DataTable` instances, as shown in the following code:</span></span>

```cs
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

<span data-ttu-id="713e6-245">В таких случаях модель угроз и гарантии безопасности совпадают с [разделом DataSet. ReadXml и DataTable. ReadXml.](#dsrdtr)</span><span class="sxs-lookup"><span data-stu-id="713e6-245">In these cases, the threat model and security guarantees are the same as the [DataSet.ReadXml and DataTable.ReadXml section](#dsrdtr)</span></span>

## <a name="deserialize-a-dataset-or-datatable-via-jsonconvert"></a><span data-ttu-id="713e6-246">Десериализация набора данных или DataTable через JsonConvert</span><span class="sxs-lookup"><span data-stu-id="713e6-246">Deserialize a DataSet or DataTable via JsonConvert</span></span>

<span data-ttu-id="713e6-247">Популярную библиотеку [JSON.NET](https://www.newtonsoft.com/json) сторонних производителей Newtonsoft можно использовать для десериализации `DataSet` и `DataTable` экземпляров, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="713e6-247">The popular third-party Newtonsoft library [JSON.NET](https://www.newtonsoft.com/json) can be used to deserialize `DataSet` and `DataTable` instances, as shown in the following code:</span></span>

```cs
using System.Data;
using Newtonsoft.Json;

public DataSet PerformDeserialization1(string json) {
    return JsonConvert.DeserializeObect<DataSet>(data);
}

public MyClass PerformDeserialization2(string json) {
    return JsonConvert.DeserializeObect<MyClass>(data);
}

public class MyClass
{
    // Property of type DataTable, automatically serialized and
    // deserialized as part of the overall MyClass payload.
    public DataTable MyDataTable { get; set; }
}
```

<span data-ttu-id="713e6-248">Десериализация `DataSet` или `DataTable` таким образом из ненадежного BLOB-объекта JSON небезопасно.</span><span class="sxs-lookup"><span data-stu-id="713e6-248">Deserializing a `DataSet` or `DataTable` in this manner from an untrusted JSON blob is not safe.</span></span> <span data-ttu-id="713e6-249">Этот шаблон уязвим для атак типа "отказ в обслуживании".</span><span class="sxs-lookup"><span data-stu-id="713e6-249">This pattern is vulnerable to a denial of service attack.</span></span> <span data-ttu-id="713e6-250">Такая атака может привести к сбою приложения или отрисовывать его, не реагируя на запросы.</span><span class="sxs-lookup"><span data-stu-id="713e6-250">Such an attack could crash the app or render it unresponsive.</span></span>

> [!NOTE]
> <span data-ttu-id="713e6-251">Корпорация Майкрософт не гарантирует или не поддерживает реализацию сторонних библиотек, таких как _Newtonsoft.Js_.</span><span class="sxs-lookup"><span data-stu-id="713e6-251">Microsoft does not warrant or support the implementation of third-party libraries like _Newtonsoft.Json_.</span></span> <span data-ttu-id="713e6-252">Эти сведения предоставляются для полноты и являются точными на момент написания этой статьи.</span><span class="sxs-lookup"><span data-stu-id="713e6-252">This information is provided for completeness and is accurate as of the time of this writing.</span></span>

## <a name="deserialize-a-dataset-or-datatable-via-binaryformatter"></a><span data-ttu-id="713e6-253">Десериализация набора данных или DataTable через BinaryFormatter</span><span class="sxs-lookup"><span data-stu-id="713e6-253">Deserialize a DataSet or DataTable via BinaryFormatter</span></span>

<span data-ttu-id="713e6-254">Разработчики никогда не должны использовать `BinaryFormatter` , `NetDataContractSerializer` , `SoapFormatter` или связанные ***ненадежные*** модули форматирования для десериализации `DataSet` `DataTable` экземпляра или из ненадежных полезных данных:</span><span class="sxs-lookup"><span data-stu-id="713e6-254">Developers must never use `BinaryFormatter`, `NetDataContractSerializer`, `SoapFormatter`, or related ***unsafe*** formatters to deserialize a `DataSet` or `DataTable` instance from an untrusted payload:</span></span>

* <span data-ttu-id="713e6-255">Это является уязвимым для полной атаки удаленного выполнения кода.</span><span class="sxs-lookup"><span data-stu-id="713e6-255">This is susceptible to a full remote code execution attack.</span></span>
* <span data-ttu-id="713e6-256">Использование пользовательской функции недостаточно `SerializationBinder` для предотвращения такой атаки.</span><span class="sxs-lookup"><span data-stu-id="713e6-256">Using a custom `SerializationBinder` is not sufficient to prevent such an attack.</span></span>

## <a name="safe-replacements"></a><span data-ttu-id="713e6-257">Защищенные замены</span><span class="sxs-lookup"><span data-stu-id="713e6-257">Safe replacements</span></span>

<span data-ttu-id="713e6-258">Для приложений, которые:</span><span class="sxs-lookup"><span data-stu-id="713e6-258">For apps that either:</span></span>

* <span data-ttu-id="713e6-259">Принимают или променяйте `DataSet` `DataTable` конечную точку SOAP. asmx или конечную точку WCF.</span><span class="sxs-lookup"><span data-stu-id="713e6-259">Accept `DataSet` or `DataTable` through an .asmx SOAP endpoint or a WCF endpoint.</span></span>
* <span data-ttu-id="713e6-260">Десериализация непроверенных данных в экземпляр `DataSet` или `DataTable` .</span><span class="sxs-lookup"><span data-stu-id="713e6-260">Deserialize untrusted data into an instance of `DataSet` or `DataTable`.</span></span>

<span data-ttu-id="713e6-261">Рассмотрите возможность замены объектной модели для использования [Entity Framework](/ef).</span><span class="sxs-lookup"><span data-stu-id="713e6-261">Consider replacing the object model to use [Entity Framework](/ef).</span></span> <span data-ttu-id="713e6-262">Entity Framework:</span><span class="sxs-lookup"><span data-stu-id="713e6-262">Entity Framework:</span></span>

* <span data-ttu-id="713e6-263">— Это полнофункциональная, современная, объектно-ориентированная платформа, которая может представлять реляционные данные.</span><span class="sxs-lookup"><span data-stu-id="713e6-263">Is a rich, modern, object-oriented framework that can represent relational data.</span></span>
* <span data-ttu-id="713e6-264">Предоставляет [обширную экосистему](/ef/core/providers/) поставщиков баз данных, облегчающих проецирование запросов к базам данных с помощью объектных моделей Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="713e6-264">Brings [a diverse ecosystem](/ef/core/providers/) of database providers to make it easy to project database queries via your Entity Framework object models.</span></span>
* <span data-ttu-id="713e6-265">Предлагает встроенные средства защиты при десериализации данных из ненадежных источников.</span><span class="sxs-lookup"><span data-stu-id="713e6-265">Offers built-in protections when deserializing data from untrusted sources.</span></span>

<span data-ttu-id="713e6-266">Для приложений, использующих `.aspx` конечные точки SOAP, рассмотрите возможность изменения этих конечных точек для использования [WCF](/dotnet/framework/wcf/).</span><span class="sxs-lookup"><span data-stu-id="713e6-266">For apps that use `.aspx` SOAP endpoints, consider changing those endpoints to use [WCF](/dotnet/framework/wcf/).</span></span> <span data-ttu-id="713e6-267">WCF — это наиболее полнофункциональная замена `.asmx` веб-служб.</span><span class="sxs-lookup"><span data-stu-id="713e6-267">WCF is a more fully featured replacement for `.asmx` web services.</span></span> <span data-ttu-id="713e6-268">Конечные точки WCF [могут быть предоставлены через SOAP](../../../wcf/feature-details/how-to-expose-a-contract-to-soap-and-web-clients.md) для совместимости с существующими вызывающими объектами.</span><span class="sxs-lookup"><span data-stu-id="713e6-268">WCF endpoints [can be exposed via SOAP](../../../wcf/feature-details/how-to-expose-a-contract-to-soap-and-web-clients.md) for compatibility with existing callers.</span></span>
