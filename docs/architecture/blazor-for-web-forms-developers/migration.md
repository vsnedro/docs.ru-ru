---
title: Переход с веб-форм ASP.NET на Blazor
description: Узнайте, как подходить к переносу существующего приложения веб-форм ASP.NET в Blazor .
author: twsouthwick
ms.author: tasou
no-loc:
- Blazor
- WebAssembly
ms.date: 09/19/2019
ms.openlocfilehash: 853358fbf534ee7501412259c61efe054b4757a7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161208"
---
# <a name="migrate-from-aspnet-web-forms-to-no-locblazor"></a>Переход с веб-форм ASP.NET на Blazor

Миграция базы кода из веб-форм ASP.NET в Blazor является трудоемкой задачей, требующей планирования. В этой главе описывается процесс. Что может упростить переход — убедиться, что приложение соответствует *N-уровневой* архитектуре, где модель приложения (в нашем примере это веб-формы) отдельно от бизнес-логики. Это логическое разделение слоев делает ясно, что необходимо для перехода на .NET Core и Blazor .

В этом примере используется приложение Ешоп, доступное на сайте [GitHub](https://github.com/dotnet-architecture/eShopOnBlazor) . Ешоп — это служба каталога, которая предоставляет возможности CRUD посредством ввода форм и проверки.

Зачем следует выполнять миграцию рабочего приложения в Blazor ? Во многих случаях нет необходимости. Веб-формы ASP.NET продолжат поддерживаться в течение многих лет. Однако многие функции, Blazor предоставляемые, поддерживаются только в перенесенном приложении. К таким функциям относятся:

- Улучшения производительности в такой среде, как `Span<T>`
- Возможность запуска от имени WebAssembly
- Кросс-платформенная поддержка для Linux и macOS
- Локальное развертывание приложения или развертывание общей платформы без влияния на другие приложения

Если эти или другие новые функции являются достаточно привлекательными, может возникнуть значение в процессе миграции приложения. Миграция может принять другие формы. Это может быть все приложение или только определенные конечные точки, для которых требуются изменения. Решение о миграции в конечном итоге зависит от бизнес-задач, которые могут быть решены разработчиком.

## <a name="server-side-versus-client-side-hosting"></a>Размещение на стороне сервера и клиента

Как описано в главе « [модели размещения](hosting-models.md) », Blazor приложение может размещаться двумя разными способами: на стороне сервера и на стороне клиента. Модель на стороне сервера использует ASP.NET Coreные подключения SignalR для управления обновлениями DOM при выполнении любого фактического кода на сервере. Клиентская модель выполняется WebAssembly в браузере и не требует соединения с сервером. Существует ряд различий, которые могут повлиять на то, что лучше всего подходит для конкретного приложения:

- Запуск от имени WebAssembly продолжается в процессе разработки и может не поддерживать все функции (например, потоки) в текущем времени.
- Обмен данными между клиентом и сервером может вызвать проблемы задержки в режиме на стороне сервера
- Для доступа к базам данных и внутренним или защищенным службам требуется отдельная служба с размещением на стороне клиента.

На момент написания статьи модель на стороне сервера более похожа на веб-формы. Большая часть этой главы посвящена модели размещения на стороне сервера, так как она готова к производству.

## <a name="create-a-new-project"></a>Создание нового проекта

Этот этап начальной миграции заключается в создании нового проекта. Этот тип проекта основан на проектах стиля пакета SDK .NET Core и упрощает большую часть шаблона, который использовался в предыдущих форматах проекта. Дополнительные сведения см. в разделе [Структура проекта](project-structure.md).

После создания проекта установите библиотеки, которые использовались в предыдущем проекте. В более старых проектах Web Forms вы могли использовать файл *packages.config* для перечисления необходимых пакетов NuGet. В новом проекте типа SDK *packages.config* был заменен `<PackageReference>` элементами в файле проекта. Преимуществом этого подхода является то, что все зависимости устанавливаются транзитно. Вы перечислите только те зависимости верхнего уровня, которые вас интересуют.

Многие из зависимостей, которые вы используете, доступны для .NET Core, включая Entity Framework 6 и log4net. Если версия .NET Core или .NET Standard недоступна, часто можно использовать .NET Frameworkную версию. Расстояние может отличаться. Любой интерфейс API, недоступный в .NET Core, вызывает ошибку во время выполнения. Visual Studio уведомляет вас о таких пакетах. На узле **ссылки** проекта в **Обозреватель решений**появляется желтый значок.

В Blazor проекте ешоп на основе можно просмотреть установленные пакеты. Ранее файл *packages.config* указан в списке каждого пакета, используемого в проекте, что приводит к тому, что файл будет почти 50 строк. Фрагмент *packages.config* :

```xml
<?xml version="1.0" encoding="utf-8"?>
<packages>
  ...
  <package id="Microsoft.ApplicationInsights.Agent.Intercept" version="2.4.0" targetFramework="net472" />
  <package id="Microsoft.ApplicationInsights.DependencyCollector" version="2.9.1" targetFramework="net472" />
  <package id="Microsoft.ApplicationInsights.PerfCounterCollector" version="2.9.1" targetFramework="net472" />
  <package id="Microsoft.ApplicationInsights.Web" version="2.9.1" targetFramework="net472" />
  <package id="Microsoft.ApplicationInsights.WindowsServer" version="2.9.1" targetFramework="net472" />
  <package id="Microsoft.ApplicationInsights.WindowsServer.TelemetryChannel" version="2.9.1" targetFramework="net472" />
  <package id="Microsoft.AspNet.FriendlyUrls" version="1.0.2" targetFramework="net472" />
  <package id="Microsoft.AspNet.FriendlyUrls.Core" version="1.0.2" targetFramework="net472" />
  <package id="Microsoft.AspNet.ScriptManager.MSAjax" version="5.0.0" targetFramework="net472" />
  <package id="Microsoft.AspNet.ScriptManager.WebForms" version="5.0.0" targetFramework="net472" />
  ...
  <package id="System.Memory" version="4.5.1" targetFramework="net472" />
  <package id="System.Numerics.Vectors" version="4.4.0" targetFramework="net472" />
  <package id="System.Runtime.CompilerServices.Unsafe" version="4.5.0" targetFramework="net472" />
  <package id="System.Threading.Channels" version="4.5.0" targetFramework="net472" />
  <package id="System.Threading.Tasks.Extensions" version="4.5.1" targetFramework="net472" />
  <package id="WebGrease" version="1.6.0" targetFramework="net472" />
</packages>
```

`<packages>`Элемент включает все необходимые зависимости. Трудно обнаружить, какие из этих пакетов включены, так как они требуются. Некоторые `<package>` элементы перечислены просто для удовлетворения потребностей необходимых зависимостей.

BlazorПроект перечисляет зависимости, которые требуются в `<ItemGroup>` элементе файла проекта:

```xml
<ItemGroup>
    <PackageReference Include="Autofac" Version="4.9.3" />
    <PackageReference Include="EntityFramework" Version="6.3.0-preview9-19423-04" />
    <PackageReference Include="log4net" Version="2.0.8" />
</ItemGroup>
```

Одним пакетом NuGet, который упрощает жизнь разработчиков веб-форм, является [пакет обеспечения совместимости Windows](../../core/porting/windows-compat-pack.md). Несмотря на то, что .NET Core работает на разных платформах, некоторые функции доступны только в Windows. Функции Windows становятся доступными путем установки пакета обеспечения совместимости. Примеры таких функций включают в себя реестр, WMI и службы каталогов. Пакет добавляет около 20 000 API и активирует множество служб, с которыми вы, возможно, уже знакомы. Для проекта Ешоп не требуется пакет обеспечения совместимости; но если в проектах используются функции Windows, пакет упрощает миграцию.

## <a name="enable-startup-process"></a>Включить процесс запуска

Процесс запуска Blazor был изменен с веб-форм и соответствует аналогичной настройке для других служб ASP.NET Core. При размещении на стороне сервера Blazor компоненты запускаются как часть обычного ASP.NET Core приложения. При размещении в браузере с WebAssembly Blazor компонентом компоненты используют аналогичную модель размещения. Различие состоит в том, что компоненты запускаются как отдельная служба из любого внутреннего процесса. В любом случае запуск будет похожим.

Файл *Global.asax.CS* является страницей запуска по умолчанию для проектов веб-форм. В проекте Ешоп этот файл настраивает контейнер инверсии управления (IoC) и обрабатывает различные события жизненного цикла приложения или запроса. Некоторые из этих событий обрабатываются по промежуточного слоя (например, `Application_BeginRequest` ). Другие события нуждаются в переопределении конкретных служб посредством внедрения зависимостей (DI).

Например, файл *Global.asax.CS* для ешоп содержит следующий код:

```csharp
public class Global : HttpApplication, IContainerProviderAccessor
{
    private static readonly ILog _log = LogManager.GetLogger(System.Reflection.MethodBase.GetCurrentMethod().DeclaringType);

    static IContainerProvider _containerProvider;
    IContainer container;

    public IContainerProvider ContainerProvider
    {
        get { return _containerProvider; }
    }

    protected void Application_Start(object sender, EventArgs e)
    {
        // Code that runs on app startup
        RouteConfig.RegisterRoutes(RouteTable.Routes);
        BundleConfig.RegisterBundles(BundleTable.Bundles);
        ConfigureContainer();
        ConfigDataBase();
    }

    /// <summary>
    /// Track the machine name and the start time for the session inside the current session
    /// </summary>
    protected void Session_Start(Object sender, EventArgs e)
    {
        HttpContext.Current.Session["MachineName"] = Environment.MachineName;
        HttpContext.Current.Session["SessionStartTime"] = DateTime.Now;
    }

    /// <summary>
    /// https://autofaccn.readthedocs.io/en/latest/integration/webforms.html
    /// </summary>
    private void ConfigureContainer()
    {
        var builder = new ContainerBuilder();
        var mockData = bool.Parse(ConfigurationManager.AppSettings["UseMockData"]);
        builder.RegisterModule(new ApplicationModule(mockData));
        container = builder.Build();
        _containerProvider = new ContainerProvider(container);
    }

    private void ConfigDataBase()
    {
        var mockData = bool.Parse(ConfigurationManager.AppSettings["UseMockData"]);

        if (!mockData)
        {
            Database.SetInitializer<CatalogDBContext>(container.Resolve<CatalogDBInitializer>());
        }
    }

    protected void Application_BeginRequest(object sender, EventArgs e)
    {
        //set the property to our new object
        LogicalThreadContext.Properties["activityid"] = new ActivityIdHelper();

        LogicalThreadContext.Properties["requestinfo"] = new WebRequestInfo();

        _log.Debug("Application_BeginRequest");
    }
}
```

Предыдущий файл станет `Startup` классом на стороне сервера Blazor :

```csharp
public class Startup
{
    public Startup(IConfiguration configuration, IWebHostEnvironment env)
    {
        Configuration = configuration;
        Env = env;
    }

    public IConfiguration Configuration { get; }

    public IWebHostEnvironment Env { get; }

    // This method gets called by the runtime. Use this method to add services to the container.
    // For more information on how to configure your application, visit https://go.microsoft.com/fwlink/?LinkID=398940
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddRazorPages();
        services.AddServerSideBlazor();

        if (Configuration.GetValue<bool>("UseMockData"))
        {
            services.AddSingleton<ICatalogService, CatalogServiceMock>();
        }
        else
        {
            services.AddScoped<ICatalogService, CatalogService>();
            services.AddScoped<IDatabaseInitializer<CatalogDBContext>, CatalogDBInitializer>();
            services.AddSingleton<CatalogItemHiLoGenerator>();
            services.AddScoped(_ => new CatalogDBContext(Configuration.GetConnectionString("CatalogDBContext")));
        }
    }

    // This method gets called by the runtime. Use this method to configure the HTTP request pipeline.
    public void Configure(IApplicationBuilder app, ILoggerFactory loggerFactory)
    {
        loggerFactory.AddLog4Net("log4Net.xml");

        if (Env.IsDevelopment())
        {
            app.UseDeveloperExceptionPage();
        }
        else
        {
            app.UseExceptionHandler("/Home/Error");
        }

        // Middleware for Application_BeginRequest
        app.Use((ctx, next) =>
        {
            LogicalThreadContext.Properties["activityid"] = new ActivityIdHelper(ctx);
            LogicalThreadContext.Properties["requestinfo"] = new WebRequestInfo(ctx);
            return next();
        });

        app.UseStaticFiles();

        app.UseRouting();

        app.UseEndpoints(endpoints =>
        {
            endpoints.MapBlazorHub();
            endpoints.MapFallbackToPage("/_Host");
        });

        ConfigDataBase(app);
    }

    private void ConfigDataBase(IApplicationBuilder app)
    {
        using (var scope = app.ApplicationServices.CreateScope())
        {
            var initializer = scope.ServiceProvider.GetService<IDatabaseInitializer<CatalogDBContext>>();

            if (initializer != null)
            {
                Database.SetInitializer(initializer);
            }
        }
    }
}
```

Одно существенное изменение, которое можно заметить в Web Forms, является выразительностью внедрения. DI является принципом GUID в ASP.NET Coreном проектировании. Он поддерживает настройку почти всех аспектов ASP.NET Core Framework. Существует даже встроенный поставщик услуг, который можно использовать во многих сценариях. Если требуется дополнительная настройка, она может поддерживаться многими проектами сообщества. Например, вы можете переслать вложения библиотеки внедрения сторонних разработчиков.

В исходном приложении Ешоп существует определенная конфигурация управления сеансами. Так как сервер Blazor использует ASP.NET Core SignalR для связи, состояние сеанса не поддерживается, так как соединения могут происходить независимо от контекста HTTP. Для приложения, использующего состояние сеанса, требуется пересоздать архитектуру перед запуском в качестве Blazor приложения.

Дополнительные сведения о запуске приложения см. в разделе [Запуск приложения](app-startup.md).

## <a name="migrate-http-modules-and-handlers-to-middleware"></a>Перенос HTTP-модулей и обработчиков на по промежуточного слоя

HTTP-модули и обработчики — это общие шаблоны в Web Forms для управления конвейером HTTP-запросов. Классы, которые реализуют `IHttpModule` или `IHttpHandler` могут быть зарегистрированы и обрабатывали входящие запросы. Веб-формы настраивают модули и обработчики в файле *web.config* . Веб-формы также сильно основаны на обработке событий жизненного цикла приложения. Вместо этого ASP.NET Core использует по промежуточного слоя. По промежуточного слоя регистрируется в `Configure` методе `Startup` класса. Порядок выполнения по промежуточного слоя определяется порядком регистрации.

В разделе [Включение процесса запуска](#enable-startup-process) событие жизненного цикла было вызвано веб-формами в качестве `Application_BeginRequest` метода. Это событие недоступно в ASP.NET Core. Одним из способов добиться такого поведения является реализация по промежуточного слоя, как показано в примере файла *Startup.CS* . Это по промежуточного слоя выполняет ту же логику, а затем передает управление следующему обработчику в конвейере по промежуточного слоя.

Дополнительные сведения о миграции модулей и обработчиков см. [в разделе Миграция обработчиков и модулей HTTP в ASP.NET Core по промежуточного слоя](/aspnet/core/migration/http-modules).

## <a name="migrate-static-files"></a>Миграция статических файлов

Для обслуживания статических файлов (например, HTML, CSS, изображений и JavaScript) файлы должны предоставляться по промежуточного слоя. Вызов `UseStaticFiles` метода позволяет обслуживать статические файлы из корневого пути в Интернете. Корневой каталог веб-сайта по умолчанию — *wwwroot*, но его можно настроить. Как включается в `Configure` метод `Startup` класса ешоп:

```csharp
public void Configure(IApplicationBuilder app)
{
    ...

    app.UseStaticFiles();

    ...
}
```

Проект Ешоп обеспечивает базовый доступ к статическим файлам. Существует множество настроек, доступных для доступа к статическим файлам. Сведения о включении файлов по умолчанию или обозревателя файлов см. [в разделе статические файлы в ASP.NET Core](/aspnet/core/fundamentals/static-files).

## <a name="migrate-runtime-bundling-and-minification-setup"></a>Миграция объединения среды выполнения и установки минификации

Объединение и минификации — это методы оптимизации производительности, позволяющие сократить количество и размер запросов сервера для получения определенных типов файлов. JavaScript и CSS часто проводят некоторую форму объединения или минификации перед отправкой клиенту. В веб-формах ASP.NET эти оптимизации обрабатываются во время выполнения. Соглашения по оптимизации определяют App_Start файл */бундлеконфиг.КС* . В ASP.NET Core применяется более декларативный подход. Файл содержит список файлов, которые будут минифицированные, а также конкретные параметры минификации.

Дополнительные сведения о объединениях и минификации см. [в разделе статические ресурсы пакета и уменьшение в ASP.NET Core](/aspnet/core/client-side/bundling-and-minification).

## <a name="migrate-aspx-pages"></a>Перенос страниц ASPX

Страница в приложении Web Forms — это файл с расширением *. aspx* . Страница веб-форм часто может быть сопоставлена с компонентом в Blazor . BlazorКомпонент создан в файле с расширением *Razor* . Для проекта Ешоп пять страниц преобразуются в страницу Razor.

Например, представление Details состоит из трех файлов в проекте веб-форм: *Details. aspx*, *Details.aspx.CS*и *Details.aspx.Designer.CS*. При преобразовании в в Blazor код программной части и разметку объединяются в *Details. Razor*. Компиляция Razor (эквивалентная в *Designer.CS* -файлах) хранится в каталоге *obj* и не по умолчанию отображается в **Обозреватель решений**. Страница веб-форм состоит из следующей разметки:

```aspx-csharp
<%@ Page Title="Details" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true" CodeBehind="Details.aspx.cs" Inherits="eShopLegacyWebForms.Catalog.Details" %>

<asp:Content ID="Details" ContentPlaceHolderID="MainContent" runat="server">
    <h2 class="esh-body-title">Details</h2>

    <div class="container">
        <div class="row">
            <asp:Image runat="server" CssClass="col-md-6 esh-picture" ImageUrl='<%#"/Pics/" + product.PictureFileName%>' />
            <dl class="col-md-6 dl-horizontal">
                <dt>Name
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.Name%>' />
                </dd>

                <dt>Description
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.Description%>' />
                </dd>

                <dt>Brand
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.CatalogBrand.Brand%>' />
                </dd>

                <dt>Type
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.CatalogType.Type%>' />
                </dd>
                <dt>Price
                </dt>

                <dd>
                    <asp:Label CssClass="esh-price" runat="server" Text='<%#product.Price%>' />
                </dd>

                <dt>Picture name
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.PictureFileName%>' />
                </dd>

                <dt>Stock
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.AvailableStock%>' />
                </dd>

                <dt>Restock
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.RestockThreshold%>' />
                </dd>

                <dt>Max stock
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.MaxStockThreshold%>' />
                </dd>

            </dl>
        </div>

        <div class="form-actions no-color esh-link-list">
            <a runat="server" href='<%# GetRouteUrl("EditProductRoute", new {id =product.Id}) %>' class="esh-link-item">Edit
            </a>
            |
            <a runat="server" href="~" class="esh-link-item">Back to list
            </a>
        </div>

    </div>
</asp:Content>
```

Код программной части предыдущей разметки включает следующий код:

```csharp
using eShopLegacyWebForms.Models;
using eShopLegacyWebForms.Services;
using log4net;
using System;
using System.Web.UI;

namespace eShopLegacyWebForms.Catalog
{
    public partial class Details : System.Web.UI.Page
    {
        private static readonly ILog _log = LogManager.GetLogger(System.Reflection.MethodBase.GetCurrentMethod().DeclaringType);

        protected CatalogItem product;

        public ICatalogService CatalogService { get; set; }

        protected void Page_Load(object sender, EventArgs e)
        {
            var productId = Convert.ToInt32(Page.RouteData.Values["id"]);
            _log.Info($"Now loading... /Catalog/Details.aspx?id={productId}");
            product = CatalogService.FindCatalogItem(productId);

            this.DataBind();
        }
    }
}
```

При преобразовании на Blazor страницу веб-форм преобразуется в следующий код:

```razor
@page "/Catalog/Details/{id:int}"
@inject ICatalogService CatalogService
@inject ILogger<Details> Logger

<h2 class="esh-body-title">Details</h2>

<div class="container">
    <div class="row">
        <img class="col-md-6 esh-picture" src="@($"/Pics/{_item.PictureFileName}")">

        <dl class="col-md-6 dl-horizontal">
            <dt>
                Name
            </dt>

            <dd>
                @_item.Name
            </dd>

            <dt>
                Description
            </dt>

            <dd>
                @_item.Description
            </dd>

            <dt>
                Brand
            </dt>

            <dd>
                @_item.CatalogBrand.Brand
            </dd>

            <dt>
                Type
            </dt>

            <dd>
                @_item.CatalogType.Type
            </dd>
            <dt>
                Price
            </dt>

            <dd>
                @_item.Price
            </dd>

            <dt>
                Picture name
            </dt>

            <dd>
                @_item.PictureFileName
            </dd>

            <dt>
                Stock
            </dt>

            <dd>
                @_item.AvailableStock
            </dd>

            <dt>
                Restock
            </dt>

            <dd>
                @_item.RestockThreshold
            </dd>

            <dt>
                Max stock
            </dt>

            <dd>
                @_item.MaxStockThreshold
            </dd>

        </dl>
    </div>

    <div class="form-actions no-color esh-link-list">
        <a href="@($"/Catalog/Edit/{_item.Id}")" class="esh-link-item">
            Edit
        </a>
        |
        <a href="/" class="esh-link-item">
            Back to list
        </a>
    </div>

</div>

@code {
    private CatalogItem _item;

    [Parameter]
    public int Id { get; set; }

    protected override void OnInitialized()
    {
        Logger.LogInformation("Now loading... /Catalog/Details/{Id}", Id);

        _item = CatalogService.FindCatalogItem(Id);
    }
}
```

Обратите внимание, что код и разметка находятся в одном файле. Все необходимые службы становятся доступными с помощью `@inject` атрибута. Для каждой `@page` директивы Эта страница доступна по `Catalog/Details/{id}` маршруту. Значение `{id}` заполнителя маршрута ограничено целым числом. Как описано в разделе о [маршрутизации](pages-routing-layouts.md) , в отличие от веб-форм, компонент Razor явным образом указывает свой маршрут и все включенные параметры. Многие элементы управления веб-форм могут не иметь точных аналогов в Blazor . Часто существует эквивалентный фрагмент кода HTML, который будет использоваться в той же цели. Например, `<asp:Label />` элемент управления можно заменить на HTML- `<label>` элемент.

### <a name="model-validation-in-no-locblazor"></a>Проверка модели в Blazor

Если код веб-форм включает проверку, вы можете переносить многие из них с минимальными изменениями. Преимуществом работы в является то Blazor , что та же логика проверки может быть запущена без использования пользовательского кода JavaScript. Заметки к данным обеспечивают простую проверку модели.

Например, страница *Create. aspx* содержит форму ввода данных с проверкой. Пример фрагмента кода выглядит следующим образом:

```aspx
<div class="form-group">
    <label class="control-label col-md-2">Name</label>
    <div class="col-md-3">
        <asp:TextBox ID="Name" runat="server" CssClass="form-control"></asp:TextBox>
        <asp:RequiredFieldValidator runat="server" ControlToValidate="Name" Display="Dynamic"
            CssClass="field-validation-valid text-danger" ErrorMessage="The Name field is required." />
    </div>
</div>
```

В в Blazor файле *Create. Razor* указана Эквивалентная разметка:

```razor
<EditForm Model="_item" OnValidSubmit="@...">
    <DataAnnotationsValidator />

    <div class="form-group">
        <label class="control-label col-md-2">Name</label>
        <div class="col-md-3">
            <InputText class="form-control" @bind-Value="_item.Name" />
            <ValidationMessage For="(() => _item.Name)" />
        </div>
    </div>

    ...
</EditForm>
```

`EditForm`Контекст включает поддержку проверки и может быть заключен во входные данные. Заметки к данным являются обычным способом добавления проверки. Такая поддержка проверки может быть добавлена через `DataAnnotationsValidator` компонент. Дополнительные сведения об этом механизме см. в разделе [ASP.NET Core Blazor Forms and Validation](/aspnet/core/blazor/forms-validation).

## <a name="migrate-configuration"></a>Миграция конфигурации

В проекте веб-форм данные конфигурации чаще всего хранятся в файле *web.config* . Доступ к данным конфигурации осуществляется с помощью `ConfigurationManager` . Службам часто требовалось анализировать объекты. При использовании .NET Framework 4.7.2 компонуемости был добавлен в конфигурацию с помощью `ConfigurationBuilders` . Эти построители позволяли разработчикам добавлять различные источники для настройки, которые затем состоялись во время выполнения для получения необходимых значений.

ASP.NET Core представил гибкую систему конфигурации, позволяющую определить источник конфигурации или источники, используемые приложением и развертыванием. `ConfigurationBuilder`Инфраструктура, которую можно использовать в приложении веб-форм, была смоделирована после использования концепций, используемых в системе конфигурации ASP.NET Core.

В следующем фрагменте кода показано, как проект Web Forms Ешоп использует *web.config* для хранения значений конфигурации:

```xml
<configuration>
  <configSections>
    <section name="entityFramework" type="System.Data.Entity.Internal.ConfigFile.EntityFrameworkSection, EntityFramework, Version=6.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" requirePermission="false" />
  </configSections>
  <connectionStrings>
    <add name="CatalogDBContext" connectionString="Data Source=(localdb)\MSSQLLocalDB; Initial Catalog=Microsoft.eShopOnContainers.Services.CatalogDb; Integrated Security=True; MultipleActiveResultSets=True;" providerName="System.Data.SqlClient" />
  </connectionStrings>
  <appSettings>
    <add key="UseMockData" value="true" />
    <add key="UseCustomizationData" value="false" />
  </appSettings>
</configuration>
```

Обычно для секретов, таких как строки подключения к базе данных, они хранятся в *web.config*. Секреты неизбежно сохраняются в незащищенных расположениях, таких как система управления версиями. При использовании Blazor ASP.NET Core предыдущая конфигурация на основе XML заменяется следующим JSON:

```json
{
  "ConnectionStrings": {
    "CatalogDBContext": "Data Source=(localdb)\\MSSQLLocalDB; Initial Catalog=Microsoft.eShopOnContainers.Services.CatalogDb; Integrated Security=True; MultipleActiveResultSets=True;"
  },
  "UseMockData": true,
  "UseCustomizationData": false
}
```

JSON является форматом конфигурации по умолчанию; Однако ASP.NET Core поддерживает многие другие форматы, в том числе XML. Существует также несколько форматов, поддерживаемых сообществом.

Конструктор в Blazor `Startup` классе проекта принимает `IConfiguration` экземпляр с помощью метода di, известного как внедрение конструктора:

```csharp
public class Startup
{
    public Startup(IConfiguration configuration, IWebHostEnvironment env)
    {
        Configuration = configuration;
        Env = env;
    }

    ...
}
```

По умолчанию переменные среды, JSON-файлы (*appsettings.jsв* и *appSettings. { Environment}. JSON*) и параметры командной строки регистрируются в объекте конфигурации в качестве допустимых источников конфигурации. Доступ к источникам конфигурации можно получить с помощью `Configuration[key]` . Более сложная методика — привязать данные конфигурации к объектам с помощью шаблона параметров. Дополнительные сведения о конфигурации и шаблоне параметров см. в разделе [Конфигурация в ASP.NET Core](/aspnet/core/fundamentals/configuration/) и [шаблоне параметров в ASP.NET Core](/aspnet/core/fundamentals/configuration/options)соответственно.

## <a name="migrate-data-access"></a>Перенос доступа к данным

Доступ к данным является важным аспектом любого приложения. Проект Ешоп хранит сведения о каталоге в базе данных и извлекает их с помощью Entity Framework (EF) 6. Поскольку EF 6 поддерживается в .NET Core 3,0, проект может продолжать его использовать.

Для Ешоп были необходимы следующие изменения, связанные с EF:

- В .NET Framework `DbContext` объект принимает строку с *именем Form = ConnectionString* и использует строку подключения из `ConfigurationManager.AppSettings[ConnectionString]` для подключения. В .NET Core это не поддерживается. Необходимо указать строку подключения.
- Доступ к базе данных осуществлялся синхронно. Хотя это и работает, масштабируемость может снизиться. Эта логика должна быть перемещена в асинхронную модель.

Несмотря на то, что собственная поддержка привязки набора данных не поддерживается, Blazor обеспечивает гибкость и мощь с поддержкой C# на странице Razor. Например, можно выполнять вычисления и отображать результат. Дополнительные сведения о шаблонах данных в Blazor см. в разделе « [доступ к данным](data.md) ».

## <a name="architectural-changes"></a>Изменения архитектуры

Наконец, существуют некоторые важные архитектурные различия, которые следует учитывать при переходе на Blazor . Многие из этих изменений применимы к любому, основанному на .NET Core или ASP.NET Core.

Поскольку Blazor основана на .NET Core, существуют рекомендации по обеспечению поддержки в .NET Core. Некоторые из основных изменений включают удаление следующих компонентов:

- Несколько доменов AppDomain
- Удаленное взаимодействие
- CAS (Code Access Security — безопасность доступа кода)
- Прозрачность безопасности

Дополнительные сведения о методах, позволяющих определить необходимые изменения для поддержки в .NET Core, см. в разделе [Перенос кода из .NET Framework в .NET Core](../../core/porting/index.md).

ASP.NET Core является пересмотренной версией ASP.NET и содержит некоторые изменения, которые изначально не кажутся очевидными. Основные изменения:

- Нет контекста синхронизации, что означает отсутствие `HttpContext.Current` `Thread.CurrentPrincipal` статических методов доступа, или других.
- Без теневого копирования
- Нет очереди запросов

Многие операции в ASP.NET Core являются асинхронными, что позволяет упростить отгрузку задач, связанных с вводом-выводом. Важно никогда не блокировать с помощью `Task.Wait()` или `Task.GetResult()` , что позволяет быстро выпустить ресурсы пула потоков.

## <a name="migration-conclusion"></a>Заключение миграции

На этом этапе вы узнали много примеров того, что требуется для перемещения проекта веб-форм Blazor . Полный пример см. в разделе проект [ешопон Blazor ](https://github.com/dotnet-architecture/eShopOnBlazor) .

>[!div class="step-by-step"]
>[Назад](security-authentication-authorization.md)
