---
title: Структура проекта для Blazor приложений
description: Узнайте, как сравниваются структуры проекта веб-форм и Blazor проектов ASP.NET.
author: danroth27
ms.author: daroth
no-loc:
- Blazor
- WebAssembly
ms.date: 09/11/2019
ms.openlocfilehash: 473b708a9b58fa88844bc6f79a898943d5a7db71
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173046"
---
# <a name="project-structure-for-blazor-apps"></a>Структура проекта для Blazor приложений

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Несмотря на существенные различия в структуре проекта, ASP.NET веб-формы и Blazor совместно используют многие схожие концепции. Здесь мы рассмотрим структуру Blazor проекта и сравнив ее с проектом веб-форм ASP.NET.

Чтобы создать свое первое Blazor приложение, следуйте инструкциям в [ Blazor статье Приступая к работе](/aspnet/core/blazor/get-started). Вы можете выполнить инструкции, чтобы создать Blazor серверное приложение или приложение, Blazor WebAssembly размещенное в ASP.NET Core. За исключением логики размещения для конкретной модели, большая часть кода в обоих проектах одинакова.

## <a name="project-file"></a>Файл проекта

BlazorСерверные приложения — это проекты .NET Core. Файл проекта для Blazor серверного приложения примерно так прост, как он может получить:

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.0</TargetFramework>
  </PropertyGroup>

</Project>
```

Файл проекта Blazor WebAssembly приложения выглядит немного подробнее (точный номер версии может отличаться):

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
    <RazorLangVersion>3.0</RazorLangVersion>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Microsoft.AspNetCore.Blazor" Version="3.1.0" />
    <PackageReference Include="Microsoft.AspNetCore.Blazor.Build" Version="3.1.0" PrivateAssets="all" />
    <PackageReference Include="Microsoft.AspNetCore.Blazor.HttpClient" Version="3.1.0" />
    <PackageReference Include="Microsoft.AspNetCore.Blazor.DevServer" Version="3.1.0" PrivateAssets="all" />
  </ItemGroup>

  <ItemGroup>
    <ProjectReference Include="..\Shared\BlazorWebAssemblyApp1.Shared.csproj" />
  </ItemGroup>

</Project>
```

BlazorWebAssemblyпроекты нацелены .NET Standard вместо .NET Core, так как они выполняются в браузере в WebAssembly среде выполнения .NET на основе. Вы не можете установить .NET в веб-браузер, как на сервере или на компьютере разработчика. Следовательно, проект ссылается на Blazor платформу, используя отдельные ссылки на пакеты.

По сравнению, проект веб-форм ASP.NET по умолчанию включает в себя почти 300 строк XML в файле *. csproj* , большинство из которых явно задает в проекте различные файлы кода и содержимого. Многие упрощения в проектах на основе .NET Core и .NET Standard берутся из целевых объектов по умолчанию и свойств, импортированных с помощью ссылки на `Microsoft.NET.Sdk.Web` пакет SDK, часто называемого веб-пакетом SDK. Веб-пакет SDK включает подстановочные знаки и другие удобства, упрощающие включение файлов кода и содержимого в проект. Вам не нужно явно перечислять файлы. При разработке для .NET Core веб-пакет SDK также добавляет ссылки на платформы в общие платформы .NET Core и ASP.NET Core. Платформы отображаются в **Dependencies**  >  узле**инфраструктуры** зависимостей в окне **Обозреватель решений** . Общие платформы — это коллекции сборок, которые были установлены на компьютере при установке .NET Core.

Хотя они поддерживаются, отдельные ссылки на сборки менее распространены в проектах .NET Core. Большинство зависимостей проектов обрабатываются как ссылки на пакеты NuGet. В проектах .NET Core необходимо ссылаться только на зависимости пакетов верхнего уровня. Транзитивные зависимости включаются автоматически. Вместо того чтобы использовать файл *packages.config* , который часто встречаются в проектах веб-форм ASP.NET для ссылки на пакеты, ссылки на пакет добавляются в файл проекта с помощью `<PackageReference>` элемента.

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="12.0.2" />
</ItemGroup>
```

## <a name="entry-point"></a>Точка входа

BlazorТочка входа серверного приложения определяется в файле *Program.CS* , как показано в консольном приложении. При выполнении приложения он создает и запускает экземпляр веб-узла с использованием значений по умолчанию, относящихся к веб-приложениям. Веб-узел управляет Blazor жизненным циклом серверного приложения и настраивает службы на уровне узла. Примерами таких служб являются конфигурация, ведение журнала, внедрение зависимостей и HTTP-сервер. Этот код в основном является шаблоном, и часто остается без изменений.

```csharp
public class Program
{
    public static void Main(string[] args)
    {
        CreateHostBuilder(args).Build().Run();
    }

    public static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureWebHostDefaults(webBuilder =>
            {
                webBuilder.UseStartup<Startup>();
            });
}
```

BlazorWebAssemblyприложения также определяют точку входа в *Program.CS*. Код выглядит немного иначе. Код аналогичен тому, что настраивает узел приложения для предоставления приложению тех же служб уровня узла. WebAssemblyУзел приложения, однако, не настраивает HTTP-сервер, так как он выполняется непосредственно в браузере.

Blazorприложения имеют `Startup` класс, а не файл *Global. asax* для определения логики запуска приложения. `Startup`Класс используется для настройки приложения и всех служб, зависящих от приложения. В Blazor серверном приложении `Startup` класс используется для настройки конечной точки для соединения в режиме реального времени, используемого Blazor между клиентскими браузерами и сервером. В Blazor WebAssembly приложении `Startup` класс определяет корневые компоненты приложения и место, где они должны быть подготовлены к просмотру. Мы подробнее рассмотрим `Startup` класс в разделе [Запуск приложения](./app-startup.md) .

## <a name="static-files"></a>Статические веб-сайты

В отличие от проектов веб-форм ASP.NET, не все файлы Blazor проекта могут запрашиваться как статические файлы. Веб-адресацией могут быть только файлы в папке *wwwroot* . Эта папка называется "корневым веб-приложением". Все, что находится за пределами корневого веб-узла приложения, *не является* веб-адресацией. Эта установка обеспечивает дополнительный уровень безопасности, который предотвращает случайное предоставление файлов проекта через Интернет.

## <a name="configuration"></a>Конфигурация

Конфигурация в приложениях ASP.NET Web Forms обычно обрабатывается с помощью одного или нескольких файлов *web.config* . Blazorприложения обычно не имеют *web.config* файлов. В противном случае файл будет использоваться только для настройки параметров IIS при размещении в службах IIS. Вместо этого Blazor серверные приложения используют абстракции конфигурации ASP.NET Core ( Blazor WebAssembly приложения в настоящее время не поддерживают одни и те же абстракции конфигурации, но это может быть функция, добавленная в будущем). Например, Blazor серверное приложение по умолчанию хранит некоторые параметры в *appsettings.js*.

```json
{
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft": "Warning",
      "Microsoft.Hosting.Lifetime": "Information"
    }
  },
  "AllowedHosts": "*"
}
```

Дополнительные сведения о конфигурации в ASP.NET Core проектах см. в разделе [конфигурации](./config.md) .

## <a name="razor-components"></a>Компоненты Razor

Большинство файлов в Blazor проектах являются файлами *. Razor* . Razor — это язык шаблонов, основанный на HTML и C#, который используется для динамического создания пользовательского веб-интерфейса. Файлы *. Razor* определяют компоненты, составляющие пользовательский интерфейс приложения. В большинстве случаев компоненты идентичны как для Blazor сервера, так и для Blazor WebAssembly приложений. Компоненты в Blazor являются аналогом пользовательских элементов управления в веб-формах ASP.NET.

Каждый файл компонента Razor компилируется в класс .NET при построении проекта. Созданный класс захватывает состояние компонента, логику отрисовки, методы жизненного цикла, обработчики событий и другую логику. Мы рассмотрим создание компонентов [пользовательского интерфейса с возможностью повторного использования с помощью Blazor ](./components.md) раздела.

Файлы *_Imports. Razor* не являются файлами компонентов Razor. Вместо этого они определяют набор директив Razor для импорта в другие файлы *Razor* в той же папке и ее вложенных папках. Например, файл *_Imports. Razor* — это стандартный способ добавления `using` директив для часто используемых пространств имен:

```razor
@using System.Net.Http
@using Microsoft.AspNetCore.Authorization
@using Microsoft.AspNetCore.Components.Authorization
@using Microsoft.AspNetCore.Components.Forms
@using Microsoft.AspNetCore.Components.Routing
@using Microsoft.AspNetCore.Components.Web
@using Microsoft.JSInterop
@using BlazorApp1
@using BlazorApp1.Shared
```

## <a name="pages"></a>Pages (Страницы)

Где находятся страницы в Blazor приложениях? Blazorне определяет отдельное расширение файла для адресных страниц, например *ASPX* -файлы в ASP.NET Web Forms. Вместо этого страницы определяются путем назначения маршрутов компонентам. Маршрут обычно назначается с помощью `@page` директивы Razor. Например, компонент, `Counter` созданный в файле *pages/Counter. Razor* , определяет следующий маршрут:

```razor
@page "/counter"
```

Маршрутизация в Blazor обрабатывается на стороне клиента, а не на сервере. При переходе пользователя в браузере Blazor перехватывает навигацию, а затем отображает компонент с соответствующим маршрутом.

Маршруты к компонентам в настоящее время не выводятся расположением файлов компонента, как и страницы *ASPX* . Эта функция может быть добавлена в будущем. Каждый маршрут должен быть явно указан в компоненте. Хранение маршрутизируемых компонентов в папке *pages* не имеет особого смысла и является исключительно Соглашением.

Мы более подробно рассмотрим маршрутизацию в Blazor разделе [страницы, маршрутизация и макеты](./pages-routing-layouts.md) .

## <a name="layout"></a>Макет

В приложениях веб-форм ASP.NET общий макет страницы обрабатывается с помощью главных страниц (*site. master*). В Blazor приложениях макет страницы обрабатывается с помощью компонентов макета (*Shared/маинлайаут. Razor*). Компоненты макета будут обсуждаться более подробно в разделе [страница, маршрутизация и макеты](./pages-routing-layouts.md) .

## <a name="bootstrap-blazor"></a>ЗагрузкеBlazor

Для начальной загрузки Blazor приложение должно:

- Укажите, где на странице следует визуализировать корневой компонент (*app. Razor*).
- Добавьте соответствующий Blazor скрипт платформы.

В Blazor серверном приложении страница узла корневого компонента определена в файле *_Host. cshtml* . Этот файл определяет страницу Razor, а не компонент. Razor Pages использовать синтаксис Razor для определения серверной страницы, которая во многом аналогична странице *. aspx* . `Html.RenderComponentAsync<TComponent>(RenderMode)`Метод используется для определения места, где должен быть визуализирован компонент корневого уровня. `RenderMode`Параметр указывает способ подготовки компонента к просмотру. В следующей таблице приведены поддерживаемые `RenderMode` Параметры.

|Параметр                        |Описание       |
|------------------------------|------------------|
|`RenderMode.Server`           |Интерактивный просмотр после установки соединения с браузером|
|`RenderMode.ServerPrerendered`|Первая предварительно визуализированная и отображаемая в интерактивном режиме|
|`RenderMode.Static`           |Отображается как статическое содержимое|

Ссылка на скрипт для *_framework/blazor.server.js* устанавливает подключение к серверу в режиме реального времени, а затем обрабатывает все взаимодействия с пользователем и обновления пользовательского интерфейса.

```razor
@page "/"
@namespace BlazorApp1.Pages
@addTagHelper *, Microsoft.AspNetCore.Mvc.TagHelpers

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>BlazorApp1</title>
    <base href="~/" />
    <link rel="stylesheet" href="css/bootstrap/bootstrap.min.css" />
    <link href="css/site.css" rel="stylesheet" />
</head>
<body>
    <app>
        @(await Html.RenderComponentAsync<App>(RenderMode.ServerPrerendered))
    </app>

    <script src="_framework/blazor.server.js"></script>
</body>
</html>
```

В Blazor WebAssembly приложении страница узла представляет собой простой статический HTML-файл в каталоге *wwwroot/index.html*. `<app>`Элемент используется для указания места, где должен быть визуализирован корневой компонент.

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width" />
    <title>BlazorApp2</title>
    <base href="/" />
    <link href="css/bootstrap/bootstrap.min.css" rel="stylesheet" />
    <link href="css/site.css" rel="stylesheet" />
</head>
<body>
    <app>Loading...</app>

    <script src="_framework/blazor.webassembly.js"></script>
</body>
</html>
```

Конкретный компонент для подготовки к просмотру настраивается в `Startup.Configure` методе приложения с соответствующим селектором CSS, указывающим, где должен быть визуализирован компонент.

```csharp
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
    }

    public void Configure(IComponentsApplicationBuilder app)
    {
        app.AddComponent<App>("app");
    }
}
```

## <a name="build-output"></a>Выходные данные при создании

При Blazor сборке проекта все файлы компонента и кода Razor компилируются в одну сборку. В отличие от проектов веб-форм ASP.NET Blazor не поддерживает компиляцию логики пользовательского интерфейса во время выполнения.

## <a name="run-the-app"></a>Запуск приложения

Чтобы запустить Blazor серверное приложение, нажмите `F5` в Visual Studio. Blazorприложения не поддерживают компиляцию во время выполнения. Чтобы просмотреть результаты изменений разметки кода и компонентов, перестройте и перезапустите приложение с подключенным отладчиком. Если запустить без отладчика ( `Ctrl+F5` ), Visual Studio следит за изменениями файлов и перезапускает приложение при внесении изменений. Вы вручную обновляете браузер по мере внесения изменений.

Чтобы запустить Blazor WebAssembly приложение, выберите один из следующих подходов:

- Запустите клиентский проект непосредственно с помощью сервера разработки.
- Запустите серверный проект при размещении приложения с ASP.NET Core.

BlazorWebAssemblyприложения не поддерживают отладку с помощью Visual Studio. Чтобы запустить приложение, используйте `Ctrl+F5` вместо `F5` . Вместо этого можно отлаживать Blazor WebAssembly приложения непосредственно в браузере. Дополнительные сведения см. в разделе [ASP.NET Core Blazor отладки](/aspnet/core/blazor/debug) .

>[!div class="step-by-step"]
>[Назад](hosting-models.md)
>[Вперед](app-startup.md)
