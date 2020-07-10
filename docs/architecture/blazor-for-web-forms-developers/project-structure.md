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
# <a name="project-structure-for-blazor-apps"></a><span data-ttu-id="52e99-103">Структура проекта для Blazor приложений</span><span class="sxs-lookup"><span data-stu-id="52e99-103">Project structure for Blazor apps</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="52e99-104">Несмотря на существенные различия в структуре проекта, ASP.NET веб-формы и Blazor совместно используют многие схожие концепции.</span><span class="sxs-lookup"><span data-stu-id="52e99-104">Despite their significant project structure differences, ASP.NET Web Forms and Blazor share many similar concepts.</span></span> <span data-ttu-id="52e99-105">Здесь мы рассмотрим структуру Blazor проекта и сравнив ее с проектом веб-форм ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="52e99-105">Here, we'll look at the structure of a Blazor project and compare it to an ASP.NET Web Forms project.</span></span>

<span data-ttu-id="52e99-106">Чтобы создать свое первое Blazor приложение, следуйте инструкциям в [ Blazor статье Приступая к работе](/aspnet/core/blazor/get-started).</span><span class="sxs-lookup"><span data-stu-id="52e99-106">To create your first Blazor app, follow the instructions in the [Blazor getting started steps](/aspnet/core/blazor/get-started).</span></span> <span data-ttu-id="52e99-107">Вы можете выполнить инструкции, чтобы создать Blazor серверное приложение или приложение, Blazor WebAssembly размещенное в ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="52e99-107">You can follow the instructions to create either a Blazor Server app or a Blazor WebAssembly app hosted in ASP.NET Core.</span></span> <span data-ttu-id="52e99-108">За исключением логики размещения для конкретной модели, большая часть кода в обоих проектах одинакова.</span><span class="sxs-lookup"><span data-stu-id="52e99-108">Except for the hosting model-specific logic, most of the code in both projects is the same.</span></span>

## <a name="project-file"></a><span data-ttu-id="52e99-109">Файл проекта</span><span class="sxs-lookup"><span data-stu-id="52e99-109">Project file</span></span>

Blazor<span data-ttu-id="52e99-110">Серверные приложения — это проекты .NET Core.</span><span class="sxs-lookup"><span data-stu-id="52e99-110"> Server apps are .NET Core projects.</span></span> <span data-ttu-id="52e99-111">Файл проекта для Blazor серверного приложения примерно так прост, как он может получить:</span><span class="sxs-lookup"><span data-stu-id="52e99-111">The project file for the Blazor Server app is about as simple as it can get:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.0</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="52e99-112">Файл проекта Blazor WebAssembly приложения выглядит немного подробнее (точный номер версии может отличаться):</span><span class="sxs-lookup"><span data-stu-id="52e99-112">The project file for a Blazor WebAssembly app looks slightly more involved (exact version numbers may vary):</span></span>

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

Blazor<span data-ttu-id="52e99-113">WebAssemblyпроекты нацелены .NET Standard вместо .NET Core, так как они выполняются в браузере в WebAssembly среде выполнения .NET на основе.</span><span class="sxs-lookup"><span data-stu-id="52e99-113"> WebAssembly projects target .NET Standard instead of .NET Core because they run in the browser on a WebAssembly-based .NET runtime.</span></span> <span data-ttu-id="52e99-114">Вы не можете установить .NET в веб-браузер, как на сервере или на компьютере разработчика.</span><span class="sxs-lookup"><span data-stu-id="52e99-114">You can't install .NET into a web browser like you can on a server or developer machine.</span></span> <span data-ttu-id="52e99-115">Следовательно, проект ссылается на Blazor платформу, используя отдельные ссылки на пакеты.</span><span class="sxs-lookup"><span data-stu-id="52e99-115">Consequently, the project references the Blazor framework using individual package references.</span></span>

<span data-ttu-id="52e99-116">По сравнению, проект веб-форм ASP.NET по умолчанию включает в себя почти 300 строк XML в файле *. csproj* , большинство из которых явно задает в проекте различные файлы кода и содержимого.</span><span class="sxs-lookup"><span data-stu-id="52e99-116">By comparison, a default ASP.NET Web Forms project includes almost 300 lines of XML in its *.csproj* file, most of which is explicitly listing the various code and content files in the project.</span></span> <span data-ttu-id="52e99-117">Многие упрощения в проектах на основе .NET Core и .NET Standard берутся из целевых объектов по умолчанию и свойств, импортированных с помощью ссылки на `Microsoft.NET.Sdk.Web` пакет SDK, часто называемого веб-пакетом SDK.</span><span class="sxs-lookup"><span data-stu-id="52e99-117">Many of the simplifications in the .NET Core- and .NET Standard-based projects come from the default targets and properties imported by referencing the `Microsoft.NET.Sdk.Web` SDK, often referred to as simply the Web SDK.</span></span> <span data-ttu-id="52e99-118">Веб-пакет SDK включает подстановочные знаки и другие удобства, упрощающие включение файлов кода и содержимого в проект.</span><span class="sxs-lookup"><span data-stu-id="52e99-118">The Web SDK includes wildcards and other conveniences that simplify inclusion of code and content files in the project.</span></span> <span data-ttu-id="52e99-119">Вам не нужно явно перечислять файлы.</span><span class="sxs-lookup"><span data-stu-id="52e99-119">You don't need to list the files explicitly.</span></span> <span data-ttu-id="52e99-120">При разработке для .NET Core веб-пакет SDK также добавляет ссылки на платформы в общие платформы .NET Core и ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="52e99-120">When targeting .NET Core, the Web SDK also adds framework references to both the .NET Core and ASP.NET Core shared frameworks.</span></span> <span data-ttu-id="52e99-121">Платформы отображаются в **Dependencies**  >  узле**инфраструктуры** зависимостей в окне **Обозреватель решений** .</span><span class="sxs-lookup"><span data-stu-id="52e99-121">The frameworks are visible from the **Dependencies** > **Frameworks** node in the **Solution Explorer** window.</span></span> <span data-ttu-id="52e99-122">Общие платформы — это коллекции сборок, которые были установлены на компьютере при установке .NET Core.</span><span class="sxs-lookup"><span data-stu-id="52e99-122">The shared frameworks are collections of assemblies that were installed on the machine when installing .NET Core.</span></span>

<span data-ttu-id="52e99-123">Хотя они поддерживаются, отдельные ссылки на сборки менее распространены в проектах .NET Core.</span><span class="sxs-lookup"><span data-stu-id="52e99-123">Although they're supported, individual assembly references are less common in .NET Core projects.</span></span> <span data-ttu-id="52e99-124">Большинство зависимостей проектов обрабатываются как ссылки на пакеты NuGet.</span><span class="sxs-lookup"><span data-stu-id="52e99-124">Most project dependencies are handled as NuGet package references.</span></span> <span data-ttu-id="52e99-125">В проектах .NET Core необходимо ссылаться только на зависимости пакетов верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="52e99-125">You only need to reference top-level package dependencies in .NET Core projects.</span></span> <span data-ttu-id="52e99-126">Транзитивные зависимости включаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="52e99-126">Transitive dependencies are included automatically.</span></span> <span data-ttu-id="52e99-127">Вместо того чтобы использовать файл *packages.config* , который часто встречаются в проектах веб-форм ASP.NET для ссылки на пакеты, ссылки на пакет добавляются в файл проекта с помощью `<PackageReference>` элемента.</span><span class="sxs-lookup"><span data-stu-id="52e99-127">Instead of using the *packages.config* file commonly found in ASP.NET Web Forms projects to reference packages, package references are added to the project file using the `<PackageReference>` element.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="12.0.2" />
</ItemGroup>
```

## <a name="entry-point"></a><span data-ttu-id="52e99-128">Точка входа</span><span class="sxs-lookup"><span data-stu-id="52e99-128">Entry point</span></span>

<span data-ttu-id="52e99-129">BlazorТочка входа серверного приложения определяется в файле *Program.CS* , как показано в консольном приложении.</span><span class="sxs-lookup"><span data-stu-id="52e99-129">The Blazor Server app's entry point is defined in the *Program.cs* file, as you would see in a Console app.</span></span> <span data-ttu-id="52e99-130">При выполнении приложения он создает и запускает экземпляр веб-узла с использованием значений по умолчанию, относящихся к веб-приложениям.</span><span class="sxs-lookup"><span data-stu-id="52e99-130">When the app executes, it creates and runs a web host instance using defaults specific to web apps.</span></span> <span data-ttu-id="52e99-131">Веб-узел управляет Blazor жизненным циклом серверного приложения и настраивает службы на уровне узла.</span><span class="sxs-lookup"><span data-stu-id="52e99-131">The web host manages the Blazor Server app's lifecycle and sets up host-level services.</span></span> <span data-ttu-id="52e99-132">Примерами таких служб являются конфигурация, ведение журнала, внедрение зависимостей и HTTP-сервер.</span><span class="sxs-lookup"><span data-stu-id="52e99-132">Examples of such services are configuration, logging, dependency injection, and the HTTP server.</span></span> <span data-ttu-id="52e99-133">Этот код в основном является шаблоном, и часто остается без изменений.</span><span class="sxs-lookup"><span data-stu-id="52e99-133">This code is mostly boilerplate and is often left unchanged.</span></span>

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

Blazor<span data-ttu-id="52e99-134">WebAssemblyприложения также определяют точку входа в *Program.CS*.</span><span class="sxs-lookup"><span data-stu-id="52e99-134"> WebAssembly apps also define an entry point in *Program.cs*.</span></span> <span data-ttu-id="52e99-135">Код выглядит немного иначе.</span><span class="sxs-lookup"><span data-stu-id="52e99-135">The code looks slightly different.</span></span> <span data-ttu-id="52e99-136">Код аналогичен тому, что настраивает узел приложения для предоставления приложению тех же служб уровня узла.</span><span class="sxs-lookup"><span data-stu-id="52e99-136">The code is similar in that it's setting up the app host to provide the same host-level services to the app.</span></span> <span data-ttu-id="52e99-137">WebAssemblyУзел приложения, однако, не настраивает HTTP-сервер, так как он выполняется непосредственно в браузере.</span><span class="sxs-lookup"><span data-stu-id="52e99-137">The WebAssembly app host doesn't, however, set up an HTTP server because it executes directly in the browser.</span></span>

Blazor<span data-ttu-id="52e99-138">приложения имеют `Startup` класс, а не файл *Global. asax* для определения логики запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="52e99-138"> apps have a `Startup` class instead of a *Global.asax* file to define the startup logic for the app.</span></span> <span data-ttu-id="52e99-139">`Startup`Класс используется для настройки приложения и всех служб, зависящих от приложения.</span><span class="sxs-lookup"><span data-stu-id="52e99-139">The `Startup` class is used to configure the app and any app-specific services.</span></span> <span data-ttu-id="52e99-140">В Blazor серверном приложении `Startup` класс используется для настройки конечной точки для соединения в режиме реального времени, используемого Blazor между клиентскими браузерами и сервером.</span><span class="sxs-lookup"><span data-stu-id="52e99-140">In the Blazor Server app, the `Startup` class is used to set up the endpoint for the real-time connection used by Blazor between the client browsers and the server.</span></span> <span data-ttu-id="52e99-141">В Blazor WebAssembly приложении `Startup` класс определяет корневые компоненты приложения и место, где они должны быть подготовлены к просмотру.</span><span class="sxs-lookup"><span data-stu-id="52e99-141">In the Blazor WebAssembly app, the `Startup` class defines the root components for the app and where they should be rendered.</span></span> <span data-ttu-id="52e99-142">Мы подробнее рассмотрим `Startup` класс в разделе [Запуск приложения](./app-startup.md) .</span><span class="sxs-lookup"><span data-stu-id="52e99-142">We'll take a deeper look at the `Startup` class in the [App startup](./app-startup.md) section.</span></span>

## <a name="static-files"></a><span data-ttu-id="52e99-143">Статические веб-сайты</span><span class="sxs-lookup"><span data-stu-id="52e99-143">Static files</span></span>

<span data-ttu-id="52e99-144">В отличие от проектов веб-форм ASP.NET, не все файлы Blazor проекта могут запрашиваться как статические файлы.</span><span class="sxs-lookup"><span data-stu-id="52e99-144">Unlike ASP.NET Web Forms projects, not all files in a Blazor project can be requested as static files.</span></span> <span data-ttu-id="52e99-145">Веб-адресацией могут быть только файлы в папке *wwwroot* .</span><span class="sxs-lookup"><span data-stu-id="52e99-145">Only the files in the *wwwroot* folder are web-addressable.</span></span> <span data-ttu-id="52e99-146">Эта папка называется "корневым веб-приложением".</span><span class="sxs-lookup"><span data-stu-id="52e99-146">This folder is referred to the app's "web root".</span></span> <span data-ttu-id="52e99-147">Все, что находится за пределами корневого веб-узла приложения, *не является* веб-адресацией.</span><span class="sxs-lookup"><span data-stu-id="52e99-147">Anything outside of the app's web root *isn't* web-addressable.</span></span> <span data-ttu-id="52e99-148">Эта установка обеспечивает дополнительный уровень безопасности, который предотвращает случайное предоставление файлов проекта через Интернет.</span><span class="sxs-lookup"><span data-stu-id="52e99-148">This setup provides an additional level of security that prevents accidental exposing of project files over the web.</span></span>

## <a name="configuration"></a><span data-ttu-id="52e99-149">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="52e99-149">Configuration</span></span>

<span data-ttu-id="52e99-150">Конфигурация в приложениях ASP.NET Web Forms обычно обрабатывается с помощью одного или нескольких файлов *web.config* .</span><span class="sxs-lookup"><span data-stu-id="52e99-150">Configuration in ASP.NET Web Forms apps is typically handled using one or more *web.config* files.</span></span> Blazor<span data-ttu-id="52e99-151">приложения обычно не имеют *web.config* файлов.</span><span class="sxs-lookup"><span data-stu-id="52e99-151"> apps don't typically have *web.config* files.</span></span> <span data-ttu-id="52e99-152">В противном случае файл будет использоваться только для настройки параметров IIS при размещении в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="52e99-152">If they do, the file is only used to configure IIS-specific settings when hosted on IIS.</span></span> <span data-ttu-id="52e99-153">Вместо этого Blazor серверные приложения используют абстракции конфигурации ASP.NET Core ( Blazor WebAssembly приложения в настоящее время не поддерживают одни и те же абстракции конфигурации, но это может быть функция, добавленная в будущем).</span><span class="sxs-lookup"><span data-stu-id="52e99-153">Instead, Blazor Server apps use the ASP.NET Core configuration abstractions (Blazor WebAssembly apps don't currently support the same configuration abstractions, but that may be a feature added in the future).</span></span> <span data-ttu-id="52e99-154">Например, Blazor серверное приложение по умолчанию хранит некоторые параметры в *appsettings.js*.</span><span class="sxs-lookup"><span data-stu-id="52e99-154">For example, the default Blazor Server app stores some settings in *appsettings.json*.</span></span>

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

<span data-ttu-id="52e99-155">Дополнительные сведения о конфигурации в ASP.NET Core проектах см. в разделе [конфигурации](./config.md) .</span><span class="sxs-lookup"><span data-stu-id="52e99-155">We'll learn more about configuration in ASP.NET Core projects in the [Configuration](./config.md) section.</span></span>

## <a name="razor-components"></a><span data-ttu-id="52e99-156">Компоненты Razor</span><span class="sxs-lookup"><span data-stu-id="52e99-156">Razor components</span></span>

<span data-ttu-id="52e99-157">Большинство файлов в Blazor проектах являются файлами *. Razor* .</span><span class="sxs-lookup"><span data-stu-id="52e99-157">Most files in Blazor projects are *.razor* files.</span></span> <span data-ttu-id="52e99-158">Razor — это язык шаблонов, основанный на HTML и C#, который используется для динамического создания пользовательского веб-интерфейса.</span><span class="sxs-lookup"><span data-stu-id="52e99-158">Razor is a templating language based on HTML and C# that is used to dynamically generate web UI.</span></span> <span data-ttu-id="52e99-159">Файлы *. Razor* определяют компоненты, составляющие пользовательский интерфейс приложения.</span><span class="sxs-lookup"><span data-stu-id="52e99-159">The *.razor* files define components that make up the UI of the app.</span></span> <span data-ttu-id="52e99-160">В большинстве случаев компоненты идентичны как для Blazor сервера, так и для Blazor WebAssembly приложений.</span><span class="sxs-lookup"><span data-stu-id="52e99-160">For the most part, the components are identical for both the Blazor Server and Blazor WebAssembly apps.</span></span> <span data-ttu-id="52e99-161">Компоненты в Blazor являются аналогом пользовательских элементов управления в веб-формах ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="52e99-161">Components in Blazor are analogous to user controls in ASP.NET Web Forms.</span></span>

<span data-ttu-id="52e99-162">Каждый файл компонента Razor компилируется в класс .NET при построении проекта.</span><span class="sxs-lookup"><span data-stu-id="52e99-162">Each Razor component file is compiled into a .NET class when the project is built.</span></span> <span data-ttu-id="52e99-163">Созданный класс захватывает состояние компонента, логику отрисовки, методы жизненного цикла, обработчики событий и другую логику.</span><span class="sxs-lookup"><span data-stu-id="52e99-163">The generated class captures the component's state, rendering logic, lifecycle methods, event handlers, and other logic.</span></span> <span data-ttu-id="52e99-164">Мы рассмотрим создание компонентов [пользовательского интерфейса с возможностью повторного использования с помощью Blazor ](./components.md) раздела.</span><span class="sxs-lookup"><span data-stu-id="52e99-164">We'll look at authoring components in the [Building reusable UI components with Blazor](./components.md) section.</span></span>

<span data-ttu-id="52e99-165">Файлы *_Imports. Razor* не являются файлами компонентов Razor.</span><span class="sxs-lookup"><span data-stu-id="52e99-165">The *_Imports.razor* files aren't Razor component files.</span></span> <span data-ttu-id="52e99-166">Вместо этого они определяют набор директив Razor для импорта в другие файлы *Razor* в той же папке и ее вложенных папках.</span><span class="sxs-lookup"><span data-stu-id="52e99-166">Instead, they define a set of Razor directives to import into other *.razor* files within the same folder and in its subfolders.</span></span> <span data-ttu-id="52e99-167">Например, файл *_Imports. Razor* — это стандартный способ добавления `using` директив для часто используемых пространств имен:</span><span class="sxs-lookup"><span data-stu-id="52e99-167">For example, a *_Imports.razor* file is a conventional way to add `using` directives for commonly used namespaces:</span></span>

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

## <a name="pages"></a><span data-ttu-id="52e99-168">Pages (Страницы)</span><span class="sxs-lookup"><span data-stu-id="52e99-168">Pages</span></span>

<span data-ttu-id="52e99-169">Где находятся страницы в Blazor приложениях?</span><span class="sxs-lookup"><span data-stu-id="52e99-169">Where are the pages in the Blazor apps?</span></span> Blazor<span data-ttu-id="52e99-170">не определяет отдельное расширение файла для адресных страниц, например *ASPX* -файлы в ASP.NET Web Forms.</span><span class="sxs-lookup"><span data-stu-id="52e99-170"> doesn't define a separate file extension for addressable pages, like the *.aspx* files in ASP.NET Web Forms apps.</span></span> <span data-ttu-id="52e99-171">Вместо этого страницы определяются путем назначения маршрутов компонентам.</span><span class="sxs-lookup"><span data-stu-id="52e99-171">Instead, pages are defined by assigning routes to components.</span></span> <span data-ttu-id="52e99-172">Маршрут обычно назначается с помощью `@page` директивы Razor.</span><span class="sxs-lookup"><span data-stu-id="52e99-172">A route is typically assigned using the `@page` Razor directive.</span></span> <span data-ttu-id="52e99-173">Например, компонент, `Counter` созданный в файле *pages/Counter. Razor* , определяет следующий маршрут:</span><span class="sxs-lookup"><span data-stu-id="52e99-173">For example, the `Counter` component authored in the *Pages/Counter.razor* file defines the following route:</span></span>

```razor
@page "/counter"
```

<span data-ttu-id="52e99-174">Маршрутизация в Blazor обрабатывается на стороне клиента, а не на сервере.</span><span class="sxs-lookup"><span data-stu-id="52e99-174">Routing in Blazor is handled client-side, not on the server.</span></span> <span data-ttu-id="52e99-175">При переходе пользователя в браузере Blazor перехватывает навигацию, а затем отображает компонент с соответствующим маршрутом.</span><span class="sxs-lookup"><span data-stu-id="52e99-175">As the user navigates in the browser, Blazor intercepts the navigation and then renders the component with the matching route.</span></span>

<span data-ttu-id="52e99-176">Маршруты к компонентам в настоящее время не выводятся расположением файлов компонента, как и страницы *ASPX* .</span><span class="sxs-lookup"><span data-stu-id="52e99-176">The component routes aren't currently inferred by the component's file location like they are with *.aspx* pages.</span></span> <span data-ttu-id="52e99-177">Эта функция может быть добавлена в будущем.</span><span class="sxs-lookup"><span data-stu-id="52e99-177">This feature may be added in the future.</span></span> <span data-ttu-id="52e99-178">Каждый маршрут должен быть явно указан в компоненте.</span><span class="sxs-lookup"><span data-stu-id="52e99-178">Each route must be specified explicitly on the component.</span></span> <span data-ttu-id="52e99-179">Хранение маршрутизируемых компонентов в папке *pages* не имеет особого смысла и является исключительно Соглашением.</span><span class="sxs-lookup"><span data-stu-id="52e99-179">Storing routable components in a *Pages* folder has no special meaning and is purely a convention.</span></span>

<span data-ttu-id="52e99-180">Мы более подробно рассмотрим маршрутизацию в Blazor разделе [страницы, маршрутизация и макеты](./pages-routing-layouts.md) .</span><span class="sxs-lookup"><span data-stu-id="52e99-180">We'll look in greater detail at routing in Blazor in the [Pages, routing, and layouts](./pages-routing-layouts.md) section.</span></span>

## <a name="layout"></a><span data-ttu-id="52e99-181">Макет</span><span class="sxs-lookup"><span data-stu-id="52e99-181">Layout</span></span>

<span data-ttu-id="52e99-182">В приложениях веб-форм ASP.NET общий макет страницы обрабатывается с помощью главных страниц (*site. master*).</span><span class="sxs-lookup"><span data-stu-id="52e99-182">In ASP.NET Web Forms apps, common page layout is handled using master pages (*Site.Master*).</span></span> <span data-ttu-id="52e99-183">В Blazor приложениях макет страницы обрабатывается с помощью компонентов макета (*Shared/маинлайаут. Razor*).</span><span class="sxs-lookup"><span data-stu-id="52e99-183">In Blazor apps, page layout is handled using layout components (*Shared/MainLayout.razor*).</span></span> <span data-ttu-id="52e99-184">Компоненты макета будут обсуждаться более подробно в разделе [страница, маршрутизация и макеты](./pages-routing-layouts.md) .</span><span class="sxs-lookup"><span data-stu-id="52e99-184">Layout components will be discussed in more detail in [Page, routing, and layouts](./pages-routing-layouts.md) section.</span></span>

## <a name="bootstrap-blazor"></a><span data-ttu-id="52e99-185">ЗагрузкеBlazor</span><span class="sxs-lookup"><span data-stu-id="52e99-185">Bootstrap Blazor</span></span>

<span data-ttu-id="52e99-186">Для начальной загрузки Blazor приложение должно:</span><span class="sxs-lookup"><span data-stu-id="52e99-186">To bootstrap Blazor, the app must:</span></span>

- <span data-ttu-id="52e99-187">Укажите, где на странице следует визуализировать корневой компонент (*app. Razor*).</span><span class="sxs-lookup"><span data-stu-id="52e99-187">Specify where on the page the root component (*App.Razor*) should be rendered.</span></span>
- <span data-ttu-id="52e99-188">Добавьте соответствующий Blazor скрипт платформы.</span><span class="sxs-lookup"><span data-stu-id="52e99-188">Add the corresponding Blazor framework script.</span></span>

<span data-ttu-id="52e99-189">В Blazor серверном приложении страница узла корневого компонента определена в файле *_Host. cshtml* .</span><span class="sxs-lookup"><span data-stu-id="52e99-189">In the Blazor Server app, the root component's host page is defined in the *_Host.cshtml* file.</span></span> <span data-ttu-id="52e99-190">Этот файл определяет страницу Razor, а не компонент.</span><span class="sxs-lookup"><span data-stu-id="52e99-190">This file defines a Razor Page, not a component.</span></span> <span data-ttu-id="52e99-191">Razor Pages использовать синтаксис Razor для определения серверной страницы, которая во многом аналогична странице *. aspx* .</span><span class="sxs-lookup"><span data-stu-id="52e99-191">Razor Pages use Razor syntax to define a server-addressable page, very much like an *.aspx* page.</span></span> <span data-ttu-id="52e99-192">`Html.RenderComponentAsync<TComponent>(RenderMode)`Метод используется для определения места, где должен быть визуализирован компонент корневого уровня.</span><span class="sxs-lookup"><span data-stu-id="52e99-192">The `Html.RenderComponentAsync<TComponent>(RenderMode)` method is used to define where a root-level component should be rendered.</span></span> <span data-ttu-id="52e99-193">`RenderMode`Параметр указывает способ подготовки компонента к просмотру.</span><span class="sxs-lookup"><span data-stu-id="52e99-193">The `RenderMode` option indicates the manner in which the component should be rendered.</span></span> <span data-ttu-id="52e99-194">В следующей таблице приведены поддерживаемые `RenderMode` Параметры.</span><span class="sxs-lookup"><span data-stu-id="52e99-194">The following table outlines the supported `RenderMode` options.</span></span>

|<span data-ttu-id="52e99-195">Параметр</span><span class="sxs-lookup"><span data-stu-id="52e99-195">Option</span></span>                        |<span data-ttu-id="52e99-196">Описание</span><span class="sxs-lookup"><span data-stu-id="52e99-196">Description</span></span>       |
|------------------------------|------------------|
|`RenderMode.Server`           |<span data-ttu-id="52e99-197">Интерактивный просмотр после установки соединения с браузером</span><span class="sxs-lookup"><span data-stu-id="52e99-197">Rendered interactively once a connection with the browser is established</span></span>|
|`RenderMode.ServerPrerendered`|<span data-ttu-id="52e99-198">Первая предварительно визуализированная и отображаемая в интерактивном режиме</span><span class="sxs-lookup"><span data-stu-id="52e99-198">First prerendered and then rendered interactively</span></span>|
|`RenderMode.Static`           |<span data-ttu-id="52e99-199">Отображается как статическое содержимое</span><span class="sxs-lookup"><span data-stu-id="52e99-199">Rendered as static content</span></span>|

<span data-ttu-id="52e99-200">Ссылка на скрипт для *_framework/blazor.server.js* устанавливает подключение к серверу в режиме реального времени, а затем обрабатывает все взаимодействия с пользователем и обновления пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="52e99-200">The script reference to *_framework/blazor.server.js* establishes the real-time connection with the server and then deals with all user interactions and UI updates.</span></span>

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

<span data-ttu-id="52e99-201">В Blazor WebAssembly приложении страница узла представляет собой простой статический HTML-файл в каталоге *wwwroot/index.html*.</span><span class="sxs-lookup"><span data-stu-id="52e99-201">In the Blazor WebAssembly app, the host page is a simple static HTML file under *wwwroot/index.html*.</span></span> <span data-ttu-id="52e99-202">`<app>`Элемент используется для указания места, где должен быть визуализирован корневой компонент.</span><span class="sxs-lookup"><span data-stu-id="52e99-202">The `<app>` element is used to indicate where the root component should be rendered.</span></span>

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

<span data-ttu-id="52e99-203">Конкретный компонент для подготовки к просмотру настраивается в `Startup.Configure` методе приложения с соответствующим селектором CSS, указывающим, где должен быть визуализирован компонент.</span><span class="sxs-lookup"><span data-stu-id="52e99-203">The specific component to render is configured in the app's `Startup.Configure` method with a corresponding CSS selector indicating where the component should be rendered.</span></span>

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

## <a name="build-output"></a><span data-ttu-id="52e99-204">Выходные данные при создании</span><span class="sxs-lookup"><span data-stu-id="52e99-204">Build output</span></span>

<span data-ttu-id="52e99-205">При Blazor сборке проекта все файлы компонента и кода Razor компилируются в одну сборку.</span><span class="sxs-lookup"><span data-stu-id="52e99-205">When a Blazor project is built, all Razor component and code files are compiled into a single assembly.</span></span> <span data-ttu-id="52e99-206">В отличие от проектов веб-форм ASP.NET Blazor не поддерживает компиляцию логики пользовательского интерфейса во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="52e99-206">Unlike ASP.NET Web Forms projects, Blazor doesn't support runtime compilation of the UI logic.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="52e99-207">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="52e99-207">Run the app</span></span>

<span data-ttu-id="52e99-208">Чтобы запустить Blazor серверное приложение, нажмите `F5` в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="52e99-208">To run the Blazor Server app, press `F5` in Visual Studio.</span></span> Blazor<span data-ttu-id="52e99-209">приложения не поддерживают компиляцию во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="52e99-209"> apps don't support runtime compilation.</span></span> <span data-ttu-id="52e99-210">Чтобы просмотреть результаты изменений разметки кода и компонентов, перестройте и перезапустите приложение с подключенным отладчиком.</span><span class="sxs-lookup"><span data-stu-id="52e99-210">To see the results of code and component markup changes, rebuild and restart the app with the debugger attached.</span></span> <span data-ttu-id="52e99-211">Если запустить без отладчика ( `Ctrl+F5` ), Visual Studio следит за изменениями файлов и перезапускает приложение при внесении изменений.</span><span class="sxs-lookup"><span data-stu-id="52e99-211">If you run without the debugger attached (`Ctrl+F5`), Visual Studio watches for file changes and restarts the app as changes are made.</span></span> <span data-ttu-id="52e99-212">Вы вручную обновляете браузер по мере внесения изменений.</span><span class="sxs-lookup"><span data-stu-id="52e99-212">You manually refresh the browser as changes are made.</span></span>

<span data-ttu-id="52e99-213">Чтобы запустить Blazor WebAssembly приложение, выберите один из следующих подходов:</span><span class="sxs-lookup"><span data-stu-id="52e99-213">To run the Blazor WebAssembly app, choose one of the following approaches:</span></span>

- <span data-ttu-id="52e99-214">Запустите клиентский проект непосредственно с помощью сервера разработки.</span><span class="sxs-lookup"><span data-stu-id="52e99-214">Run the client project directly using the development server.</span></span>
- <span data-ttu-id="52e99-215">Запустите серверный проект при размещении приложения с ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="52e99-215">Run the server project when hosting the app with ASP.NET Core.</span></span>

Blazor<span data-ttu-id="52e99-216">WebAssemblyприложения не поддерживают отладку с помощью Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="52e99-216"> WebAssembly apps don't support debugging using Visual Studio.</span></span> <span data-ttu-id="52e99-217">Чтобы запустить приложение, используйте `Ctrl+F5` вместо `F5` .</span><span class="sxs-lookup"><span data-stu-id="52e99-217">To run the app, use `Ctrl+F5` instead of `F5`.</span></span> <span data-ttu-id="52e99-218">Вместо этого можно отлаживать Blazor WebAssembly приложения непосредственно в браузере.</span><span class="sxs-lookup"><span data-stu-id="52e99-218">You can instead debug Blazor WebAssembly apps directly in the browser.</span></span> <span data-ttu-id="52e99-219">Дополнительные сведения см. в разделе [ASP.NET Core Blazor отладки](/aspnet/core/blazor/debug) .</span><span class="sxs-lookup"><span data-stu-id="52e99-219">See [Debug ASP.NET Core Blazor](/aspnet/core/blazor/debug) for details.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="52e99-220">[Назад](hosting-models.md)
>[Вперед](app-startup.md)</span><span class="sxs-lookup"><span data-stu-id="52e99-220">[Previous](hosting-models.md)
[Next](app-startup.md)</span></span>
