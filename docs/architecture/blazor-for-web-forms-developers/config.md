---
title: Конфигурация приложения
description: Узнайте, как настроить Blazor приложения без использования ConfigurationManager.
author: csharpfritz
ms.author: jefritz
no-loc:
- Blazor
ms.date: 04/01/2020
ms.openlocfilehash: 6154b4f8c7a5bff42e603b12d5ef85468b80224e
ms.sourcegitcommit: 0100be20fcf23f61dab672deced70059ed71bb2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88267507"
---
# <a name="app-configuration"></a>Конфигурация приложения

Основной способ загрузки конфигурации приложения в веб-формы — с записями в *web.config* файле &mdash; либо на сервере, либо в связанном файле конфигурации, на который ссылается *web.config*. Статический объект можно использовать `ConfigurationManager` для взаимодействия с параметрами приложения, строками подключения репозитория данных и другими поставщиками расширенной конфигурации, добавленными в приложение. Обычно для просмотра взаимодействия с конфигурацией приложения отображается следующий код:

```csharp
var configurationValue = ConfigurationManager.AppSettings["ConfigurationSettingName"];
var connectionString = ConfigurationManager.ConnectionStrings["MyDatabaseConnectionName"].ConnectionString;
```

При использовании ASP.NET Core и на стороне сервера Blazor файл *web.config* может присутствовать, если приложение размещено на сервере Windows IIS. Однако `ConfigurationManager` взаимодействие с этой конфигурацией не требуется, и вы можете получить более структурированную конфигурацию приложения из других источников. Давайте посмотрим, как собирается конфигурация и как можно получить доступ к сведениям о конфигурации из файла *web.config* .

## <a name="configuration-sources"></a>Источники конфигураций

ASP.NET Core распознает множество источников конфигурации, которые вы можете использовать для приложения. Платформа пытается предложить наиболее подходящие из этих функций по умолчанию. Конфигурация считывается и объединяется из этих различных источников с помощью ASP.NET Core. Более поздние загруженные значения для одного и того же ключа конфигурации имеют приоритет над более ранними значениями.

ASP.NET Core была разработана для обеспечения работы в облаке и упрощения настройки приложений для операторов и разработчиков. ASP.NET Core работает с учетом среды и знает, работает ли она в `Production` `Development` среде или. Индикатор среды задается в `ASPNETCORE_ENVIRONMENT` системной переменной среды. Если значение не задано, приложение по умолчанию работает в `Production` среде.

Приложение может активировать и добавить конфигурацию из нескольких источников в зависимости от имени среды. По умолчанию конфигурация загружается из следующих ресурсов в указанном порядке.

1. *appsettings.jsв* файле, если он есть
1. *appSettings. Файл {ENVIRONMENT_NAME}. JSON* , если он есть
1. Файл секретов пользователя на диске, если он есть
1. Переменные среды
1. аргументов командной строки;

## <a name="appsettingsjson-format-and-access"></a>appsettings.jsк формату и доступу

*appsettings.jsв* файле могут быть иерархическими со значениями, структурированными как в следующем JSON:

```json
{
  "section0": {
    "key0": "value",
    "key1": "value"
  },
  "section1": {
    "key0": "value",
    "key1": "value"
  }
}
```

При отображении с помощью предыдущего JSON система конфигурации выравнивает дочерние значения и ссылается на полные иерархические пути. Символ двоеточия ( `:` ) разделяет каждое свойство в иерархии. Например, ключ конфигурации `section1:key0` обращается к `section1` значению объектного литерала `key0` .

## <a name="user-secrets"></a>Секреты пользователя

Секреты пользователя:

* Значения конфигурации, хранящиеся в JSON-файле на рабочей станции разработчика, за пределами папки разработки приложения.
* Загружается только при выполнении в `Development` среде.
* Связан с конкретным приложением.
* Управляется с помощью `user-secrets` команды .NET Core CLI.

Настройте приложение для хранения секретных данных, выполнив `user-secrets` команду:

```dotnetcli
dotnet user-secrets init
```

Предыдущая команда добавляет `UserSecretsId` элемент в файл проекта. Элемент содержит идентификатор GUID, который используется для связывания секретов с приложением. Затем можно определить секрет с помощью `set` команды. Например:

```dotnetcli
dotnet user-secrets set "Parent:ApiKey" "12345"
```

Предыдущая команда делает `Parent:ApiKey` ключ конфигурации доступным на рабочей станции разработчика со значением `12345` .

Дополнительные сведения о создании, хранении и управлении секретами пользователей см. в разделе [безопасного хранения секретов приложений в разработке в ASP.NET Core](/aspnet/core/security/app-secrets) документе.

## <a name="environment-variables"></a>Переменные среды

Следующий набор значений, загружаемых в конфигурацию приложения, — это переменные среды системы. Все параметры переменных среды системы теперь доступны через API настройки. При чтении внутри приложения иерархические значения преобразуются в плоские и разделяются символами двоеточия. Однако некоторые операционные системы не разрешают имена переменных среды с двоеточием. ASP.NET Core устраняет это ограничение, преобразуя значения с двойным подчеркиванием ( `__` ) в двоеточие при обращении к ним. `Parent:ApiKey`Значение из приведенного выше раздела секреты пользователя можно переопределить с помощью переменной среды `Parent__ApiKey` .

## <a name="command-line-arguments"></a>аргументов командной строки;

Кроме того, конфигурацию можно указать в качестве аргументов командной строки при запуске приложения. Используйте двойное тире ( `--` ) или прямую косую черту ( `/` ), чтобы указать имя устанавливаемого значения конфигурации и значение, которое необходимо настроить. Синтаксис напоминает следующие команды:

```dotnetcli
dotnet run CommandLineKey1=value1 --CommandLineKey2=value2 /CommandLineKey3=value3
dotnet run --CommandLineKey1 value1 /CommandLineKey2 value2
dotnet run Parent:ApiKey=67890
```

## <a name="the-return-of-webconfig"></a>Возврат web.config

Если вы развернули приложение в Windows на IIS, файл *web.config* по-прежнему настраивает IIS для управления приложением. По умолчанию службы IIS добавляют ссылку на модуль ASP.NET Core (ANCM). ANCM — это собственный модуль IIS, в котором размещено приложение вместо веб-сервера Kestrel. Этот *web.config* раздел напоминает следующую XML-разметку:

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <location path="." inheritInChildApplications="false">
    <system.webServer>
      <handlers>
        <add name="aspNetCore" path="*" verb="*" modules="AspNetCoreModuleV2" resourceType="Unspecified" />
      </handlers>
      <aspNetCore processPath=".\MyApp.exe"
                  stdoutLogEnabled="false"
                  stdoutLogFile=".\logs\stdout"
                  hostingModel="inprocess" />
    </system.webServer>
  </location>
</configuration>
```

Конфигурация конкретного приложения может быть определена путем вложения `environmentVariables` элемента в `aspNetCore` элемент. Значения, определенные в этом разделе, представлены в ASP.NET Core приложении в виде переменных среды. Переменные среды загружаются соответствующим образом во время выполнения этого сегмента запуска приложения.

```xml
<aspNetCore processPath="dotnet"
      arguments=".\MyApp.dll"
      stdoutLogEnabled="false"
      stdoutLogFile=".\logs\stdout"
      hostingModel="inprocess">
  <environmentVariables>
    <environmentVariable name="ASPNETCORE_ENVIRONMENT" value="Development" />
    <environmentVariable name="Parent:ApiKey" value="67890" />
  </environmentVariables>
</aspNetCore>
```

## <a name="read-configuration-in-the-app"></a>Чтение конфигурации в приложении

ASP.NET Core предоставляет конфигурацию приложения через <xref:Microsoft.Extensions.Configuration.IConfiguration> интерфейс. Этот интерфейс конфигурации должен запрашиваться Blazor компонентами, Blazor страницами и любым другим управляемым ASP.NET Core классом, которым требуется доступ к конфигурации. Платформа ASP.NET Core автоматически заполнит этот интерфейс разрешенной конфигурацией, настроенной ранее. На Blazor странице или в разметке Razor компонента можно внедрить `IConfiguration` объект с `@inject` директивой, расположенной в верхней части файла *. Razor* следующим образом:

```razor
@inject IConfiguration Configuration
```

Приведенная выше инструкция делает `IConfiguration` объект доступным в качестве `Configuration` переменной на протяжении всего остального шаблона Razor.

Отдельные параметры конфигурации можно прочитать, указав иерархию параметров конфигурации, которую нужно использовать в качестве параметра индексатора:

```csharp
var mySetting = Configuration["section1:key0"];
```

Вы можете извлечь все разделы конфигурации с помощью <xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A> метода, чтобы получить коллекцию ключей в определенном месте с синтаксисом, аналогичным `GetSection("section1")` получению конфигурации для Section1 из предыдущего примера.

## <a name="strongly-typed-configuration"></a>Строго типизированная конфигурация

С помощью веб-форм можно было создать строго типизированный тип конфигурации, наследуемый от <xref:System.Configuration.ConfigurationSection> типа и связанных с ним типов. `ConfigurationSection`Вы можете настроить некоторые бизнес-правила и обработку для этих значений конфигурации.

В ASP.NET Core можно указать иерархию классов, которая будет принимать значения конфигурации. Следующие классы:

* Не нужно наследовать от родительского класса.
* Должны быть включены `public` свойства, соответствующие свойствам и ссылкам на типы для структуры конфигурации, которую вы хотите захватить.

Для предыдущих *appsettings.js* образца можно было определить следующие классы для записи значений:

```csharp
public class MyConfig
{
    public MyConfigSection section0 { get; set;}

    public MyConfigSection section1 { get; set;}
}

public class MyConfigSection
{
    public string key0 { get; set; }

    public string key1 { get; set; }
}
```

Эту иерархию классов можно заполнить, добавив следующую строку в `Startup.ConfigureServices` метод:

```csharp
services.Configure<MyConfig>(Configuration);
```

В оставшейся части приложения можно добавить входной параметр в классы или `@inject` директиву в шаблонах Razor типа `IOptions<MyConfig>` для получения строго типизированных параметров конфигурации. `IOptions<MyConfig>.Value`Свойство даст `MyConfig` значение, заполненное из параметров конфигурации.

```razor
@inject IOptions<MyConfig> options
@code {
    var MyConfiguration = options.Value;
    var theSetting = MyConfiguration.section1.key0;
}
```

Дополнительные сведения о функциях параметров можно найти в [шаблоне параметров в ASP.NET Core](/aspnet/core/fundamentals/configuration/options#options-interfaces) документе.

>[!div class="step-by-step"]
>[Назад](middleware.md)
>[Вперед](security-authentication-authorization.md)
