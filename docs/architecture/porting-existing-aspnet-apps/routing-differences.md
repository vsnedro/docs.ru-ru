---
title: Различия маршрутизации между ASP.NET MVC и ASP.NET Core
description: Как определяется Маршрутизация и как она работает в среде выполнения в ASP.NET MVC? Чем маршрутизация отличается в ASP.NET Coreных приложениях?
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: d5c18948248f03a19c97461efe3df38a5be9360b
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401715"
---
# <a name="routing-differences-between-aspnet-mvc-and-aspnet-core"></a>Различия маршрутизации между ASP.NET MVC и ASP.NET Core

Маршрутизация отвечает за сопоставление входящих запросов браузера с определенными действиями контроллера (или обработчиками Razor Pages). В этом разделе описывается различие маршрутизации между ASP.NET MVC (и веб-API) и ASP.NET Core (MVC, Razor Pages и иным способом).

## <a name="routing-in-aspnet-mvc-and-web-api"></a>Маршрутизация в ASP.NET MVC и веб-API

ASP.NET MVC предлагает два подхода к маршрутизации:

1. Таблица маршрутов, которая представляет собой коллекцию маршрутов, которые можно использовать для сопоставления входящих запросов с действиями контроллера.
1. Маршрутизация атрибутов, которая выполняет ту же функцию, но достигается путем оформления самих действий, вместо изменения глобальной таблицы маршрутов.

## <a name="route-table"></a>Таблица маршрутов

Таблица маршрутов настраивается при запуске приложения. Как правило, вызов статического метода используется для настройки коллекции глобальных маршрутов следующим образом:

```csharp
public class MvcApplication : System.Web.HttpApplication
{
    public static void RegisterRoutes(RouteCollection routes)
    {
        routes.IgnoreRoute("{resource}.axd/{*pathInfo}");
        routes.MapRoute(
            name: "Default",
            url: "{controller}/{action}/{id}",
            defaults: new { controller = "Home", action = "Index", id = "" },
            constraints: new { id = "\\d+" }
        );
    }

    protected void Application_Start()
    {
        RegisterRoutes(RouteTable.Routes);
    }
}
```

В приведенном выше коде Управление таблицей маршрута осуществляется с помощью `RouteCollection` типа, который используется для добавления новых маршрутов с помощью `MapRoute` . Маршруты именуются и включают строку маршрута, которая может включать параметры для контроллеров, действий, областей и других заполнителей. Если приложение соответствует стандартному соглашению, большинство его действий может обрабатываться этим отдельным маршрутом по умолчанию, за исключением того, что это соглашение настроено с использованием дополнительных маршрутов.

### <a name="attribute-routing-in-aspnet-mvc"></a>Маршрутизация атрибутов в ASP.NET MVC

Маршруты, определенные с помощью их действий, могут быть проще в обнаружении и причинах, чем маршруты, определенные во внешнем расположении. При использовании маршрутизации атрибутов отдельный метод действия может иметь свой маршрут, определенный с помощью `[Route]` атрибута:

```csharp
public class ProductsController
{
    [Route("products")]
    public ActionResult Index()
    {
        return View();
    }

    [Route("products/{id}")]
    public ActionResult Details(int id)
    {
        return View();
    }
}
```

[Маршрутизация атрибутов в ASP.NET MVC 5](https://devblogs.microsoft.com/aspnet/attribute-routing-in-asp-net-mvc-5/) также поддерживает значения по умолчанию и префиксы, которые могут быть добавлены на уровне контроллера (и применяются ко всем действиям в этом контроллере). Дополнительные сведения см. в документации.

Для настройки маршрутизации атрибутов необходимо добавить одну строку в конфигурацию таблицы маршрутов по умолчанию:

```csharp
routes.MapMvcAttributeRoutes();
```

Маршрутизация атрибутов может воспользоваться преимуществами ограничений маршрута, встроенных и пользовательских, и поддерживает именованные маршруты и области с помощью `[RouteArea]` атрибута. Если приложение использует области, необходимо настроить поддержку для них в коде регистрации маршрута, добавив еще одну строку:

```csharp
routes.MapMvcAttributeRoutes();

AreaRegistration.RegisterAllAreas();
```

### <a name="attribute-routing-in-aspnet-web-api-2"></a>Маршрутизация атрибутов в веб-API ASP.NET 2

[Маршрутизация атрибутов в веб-API ASP.NET 2](/aspnet/web-api/overview/web-api-routing-and-actions/attribute-routing-in-web-api-2) аналогична маршрутизации в ASP.NET MVC 5 с незначительными различиями. Настройка веб-API 2 обычно выполняется в собственном классе, который вызывается во время запуска приложения. Конфигурация маршрутизации атрибутов обрабатывается в этом классе:

```csharp
public static class WebApiConfig
{
    public static void Register(HttpConfiguration config)
    {
        // Attribute routing.
        config.MapHttpAttributeRoutes();

        // Convention-based routing.
        config.Routes.MapHttpRoute(
            name: "DefaultApi",
            routeTemplate: "api/{controller}/{id}",
            defaults: new { id = RouteParameter.Optional }
        );
    }
}
```

Как показано в приведенном выше коде, маршрутизация атрибутов может сочетаться с маршрутизацией на основе соглашений в приложениях веб-API.

Помимо маршрутизации атрибутов, [веб-API ASP.NET выбирает, какое действие следует вызвать](/aspnet/web-api/overview/web-api-routing-and-actions/routing-and-action-selection) на основе метода HTTP (например, Get или POST), `{action}` заполнителя в маршруте (если есть) и параметры действия. Во многих случаях имя действия поможет определить, соответствует ли оно, так как префикс имени действия "Get" или "Post" используется для сопоставления соответствующего метода HTTP. Кроме того, действия можно снабдить соответствующим атрибутом метода HTTP, например `[HttpGet]` , допуская использование имен действий, которые не имеют префикса с помощью метода HTTP.

```csharp
public class ProductsController : ApiController
{
    // matched by name and (lack of) parameters
    public IEnumerable<Product> GetAll() { }

    // matched by GET and string parameter
    [HttpGet]
    public IEnumerable<Product> FindProductsByName(string name) { }
}
```

В соответствии с указанным выше контроллером HTTP-запрос GET `localhost:123/products/` соответствует `GetAll` действию. Запрос HTTP GET, `localhost:123/products?name=ardalis` соответствующий `FindProductsByName` действию.

## <a name="routing-in-aspnet-core-31"></a>Маршрутизация в ASP.NET Core 3,1

В ASP.NET Core маршрутизация обрабатывается по промежуточного слоя маршрутизации, который соответствует URL-адресам входящих запросов на действия или другие конечные точки. Действия контроллера либо маршрутизируются, либо направляются с помощью атрибутов. Стандартная маршрутизация аналогична подходу таблицы маршрутов, используемому в ASP.NET MVC и веб-API. Независимо от того, используете ли вы стандартный, атрибут или оба, необходимо настроить приложение для использования по промежуточного слоя маршрутизации. Чтобы использовать по промежуточного слоя, добавьте в метод следующий код `Startup.Configure` :

```csharp
app.UseRouting();
```

### <a name="conventional-routing"></a>Маршрутизация на основе соглашений

При использовании обычной маршрутизации вы настраиваете одно или несколько соглашений, которые будут использоваться для сопоставления входящих URL-адресов с *конечными точками* в приложении. В ASP.NET Core эти конечные точки могут быть действиями контроллера, как в ASP.NET MVC или веб-API. Конечные точки также могут быть Razor Pages, проверки работоспособности или концентраторы SignalR. Все эти маршрутизируемые функции настраиваются аналогичным образом с помощью конечных точек:

```csharp
// in Startup.Configure()
app.UseEndpoints(endpoints =>
{
    endpoints.MapHealthChecks("/healthz").RequireAuthorization();
    endpoints.MapControllerRoute(
        name: "default",
        pattern: "{controller=Home}/{action=Index}/{id?}");
    endpoints.MapRazorPages();
});
```

Приведенный выше код используется (в дополнение к `UseRouting` ) для настройки различных конечных точек, включая проверки работоспособности, контроллеры и Razor Pages. Для контроллеров в приведенной выше конфигурации задано соглашение о маршрутизации по умолчанию. это довольно стандартный `{controller}/{action}/{id?}` шаблон, который рекомендуется использовать с первой версии ASP.NET MVC.

### <a name="attribute-routing"></a>Маршрутизация с помощью атрибутов

Маршрутизация атрибутов в ASP.NET Core является предпочтительным подходом для настройки маршрутизации в контроллерах. Если вы создаете API, `[ApiController]` атрибут должен применяться к контроллерам. Помимо прочего, этот атрибут требует использования маршрутизации атрибутов для действий в таких классах контроллеров.

Маршрутизация атрибутов в ASP.NET Core ведет себя аналогично в ASP.NET MVC и веб-API. Однако в дополнение к поддержке `[Route]` атрибута сведения о маршрутах также можно указать как часть атрибута метода HTTP:

```csharp
[HttpGet("api/products/{id}")]
public async ActionResult<Product> Details(int id)
{
    // ...
}
```

Как и в предыдущих версиях, можно указать маршрут по умолчанию с заполнителями и добавить его на уровне класса контроллера или даже в базовом классе. Для всех этих вариантов используется один и тот же `[Route]` атрибут. Например, базовый класс контроллера API может выглядеть следующим образом:

```csharp
[Route("api/{controller}/{action}/{id?:int}")]
public abstract class BaseApiController : ControllerBase, IApiController
{
    // ...
}
```

С помощью этого атрибута классы, наследующие от этого типа, будут маршрутизировать URL-адреса к действиям на основе имени контроллера, имени действия и необязательного целочисленного `id` параметра.

## <a name="references"></a>Ссылки

- [Общие сведения о маршрутизации в ASP.NET MVC](/aspnet/mvc/overview/older-versions-1/controllers-and-routing/asp-net-mvc-routing-overview-cs)
- [Маршрутизация атрибутов в ASP.NET MVC 5](https://devblogs.microsoft.com/aspnet/attribute-routing-in-asp-net-mvc-5/)
- [Маршрутизация атрибутов в веб-API ASP.NET 2](/aspnet/web-api/overview/web-api-routing-and-actions/attribute-routing-in-web-api-2)
- [Выбор маршрутизации и действий в веб-API ASP.NET](/aspnet/web-api/overview/web-api-routing-and-actions/routing-and-action-selection)
- [Маршрутизация в ASP.NET Core](/aspnet/core/fundamentals/routing)
- [Маршрутизация к действиям контроллера в ASP.NET Core MVC](/aspnet/core/mvc/controllers/routing)

>[!div class="step-by-step"]
>[Назад](configuration-differences.md)
>[Вперед](comparing-razor-pages-aspnet-mvc.md)
