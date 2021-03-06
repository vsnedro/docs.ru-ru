---
title: Дополнительные сценарии миграции
description: В этом разделе описываются дополнительные сценарии и методы миграции платформа .NET Framework приложений в .NET Core и .NET 5.
author: ardalis
ms.date: 02/11/2021
ms.openlocfilehash: fa1b756d8852854e50127ae3e7443e2949cceaa8
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401726"
---
# <a name="more-migration-scenarios"></a>Дополнительные сценарии миграции

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

В этом разделе описываются несколько различных сценариев приложений ASP.NET и приводятся конкретные методы решения каждого из них. С помощью этого раздела можно определить сценарии, применимые к приложению, и оценить, какие методы будут работать для приложения и его среды размещения.

## <a name="migrate-aspnet-mvc-5-and-webapi-2-to-aspnet-core-mvc"></a>Миграция ASP.NET MVC 5 и WebApi 2 на ASP.NET Core MVC

Распространенным сценарием для приложений ASP.NET MVC 5 и Web API 2 было установка обоих продуктов в одном и том же приложении. Это поддерживаемый и относительно распространенный подход, используемый многими группами, но поскольку эти два продукта используют разные абстракции, требуются некоторые избыточные усилия. Например, Настройка маршрутов для ASP.NET MVC выполняется с помощью методов в `RouteCollection` , таких как `MapMvcAttributeRoutes()` и `MapRoute()` . Но веб-API ASP.NET 2 маршрутизация управляется с помощью `HttpConfiguration` методов и, таких как `MapHttpAttributeRoutes()` и `MapHttpRoute()` .

`eShopLegacyMVC`Приложение включает в себя ASP.NET MVC и веб-API, а также методы в своей `App_Start` папке для настройки маршрутов для обоих. Он также поддерживает внедрение зависимостей с помощью Autofac, что также требует двух наборов аналогичной работы для настройки:

```csharp
protected IContainer RegisterContainer()
{
    var builder = new ContainerBuilder();

    var thisAssembly = Assembly.GetExecutingAssembly();
    builder.RegisterControllers(thisAssembly);      // MVC controllers
    builder.RegisterApiControllers(thisAssembly);   // Web API controllers

    var mockData = bool.Parse(ConfigurationManager.AppSettings["UseMockData"]);
    builder.RegisterModule(new ApplicationModule(mockData));

    var container = builder.Build();

    // set mvc resolver
    DependencyResolver.SetResolver(new AutofacDependencyResolver(container));

    // set webapi resolver
    var resolver = new AutofacWebApiDependencyResolver(container);
    GlobalConfiguration.Configuration.DependencyResolver = resolver;

    return container;
}
```

При обновлении этих приложений для использования ASP.NET Core эти дублирующие усилия и путаница, которые иногда прилагается к ней, устраняются. ASP.NET Core MVC — это единая платформа с одним набором правил для маршрутизации, фильтров и многого другого. Внедрение зависимостей встроено в .NET Core. Все это можно настроить в `Startup.cs` , как показано в `eShopPorted` приложении в примере.

## <a name="migrate-httpresponsemessage-to-aspnet-core"></a>Миграция HttpResponseMessage в ASP.NET Core

Некоторые веб-API ASP.NET приложения могут иметь методы действий, возвращающие `HttpResponseMessage` . Этот тип не существует в ASP.NET Core. Ниже приведен пример использования в `Delete` методе действия с помощью `ResponseMessage` вспомогательного метода в базе `ApiController` :

```csharp
// DELETE api/<controller>/5
[HttpDelete]
public IHttpActionResult Delete(int id)
{
    var brandToDelete = _service.GetCatalogBrands().FirstOrDefault(x => x.Id == id);
    if (brandToDelete == null)
    {
        return ResponseMessage(new HttpResponseMessage(HttpStatusCode.NotFound));
    }

    // demo only - don't actually delete
    return ResponseMessage(new HttpResponseMessage(HttpStatusCode.OK));
}
```

В ASP.NET Core MVC доступны вспомогательные методы для всех распространенных кодов состояния ответа HTTP, поэтому приведенный выше метод будет перенесен в следующий код:

```csharp
[HttpDelete("{id}")]
public IActionResult Delete(int id)
{
    var brandToDelete = _service.GetCatalogBrands().FirstOrDefault(x => x.Id == id);
    if (brandToDelete == null)
    {
        return NotFound();
    }

    // demo only - don't actually delete
    return Ok();
}
```

Если вы обнаружите, что вам нужно вернуть пользовательский код состояния, для которого не существует вспомогательного приложения, всегда можно использовать `return StatusCode(int statusCode)` для возврата любого числового кода.

## <a name="migrate-content-negotiation-from-aspnet-web-api-to-aspnet-core"></a>Перенос согласования содержимого из веб-API ASP.NET в ASP.NET Core

Веб-API ASP.NET 2 поддерживает [Согласование содержимого](/aspnet/web-api/overview/formats-and-model-binding/content-negotiation) изначально. Пример приложения включает в себя `BrandsController` , который демонстрирует эту поддержку путем перечисления результатов в формате XML или JSON. Он основан на `Accept` заголовке запроса и изменяется, когда он включает `application/xml` или `application/json` .

В приложениях ASP.NET MVC 5 не встроена поддержка согласования содержимого.

Согласование содержимого предпочтительнее, чем возврат определенного типа кодирования, так как он является более гибким и делает API доступным для большего числа клиентов. Если в данный момент у вас есть методы действий, возвращающие конкретный формат, рекомендуется изменить их, чтобы возвратить тип результата, поддерживающий согласование содержимого при переносе кода в ASP.NET Core.

Следующий код возвращает данные в формате JSON независимо от `Accept` содержимого заголовка клиента:

```csharp
[HttpGet]
public ActionResult Index()
{
    return Json(new { Message = "Hello World!" });
}
```

[ASP.NET Core MVC поддерживает согласование содержимого в собственном](/aspnet/core/web-api/advanced/formatting)режиме, при условии, что используется соответствующий [тип возвращаемого](/aspnet/core/web-api/action-return-types) значения. Согласование содержимого реализуется с помощью [Обжектресулт], который возвращается результатами действий, связанными с кодом состояния, возвращаемыми вспомогательными методами контроллера. Предыдущий метод действия, реализованный в ASP.NET Core MVC с использованием согласования содержимого, будет выглядеть следующим образом:

```csharp
public IActionResult Index()
{
    return Ok(new { Message = "Hello World!"} );
}
```

Это по умолчанию будет возвращать данные в формате JSON. XML и другие форматы будут использоваться, [Если приложение настроено с использованием соответствующего модуля форматирования](/aspnet/core/web-api/advanced/formatting).

## <a name="references"></a>Ссылки

- [Согласование содержимого веб-API ASP.NET](/aspnet/web-api/overview/formats-and-model-binding/content-negotiation)
- [Форматирование данных отклика в веб-API ASP.NET Core](/aspnet/core/web-api/advanced/formatting)

>[!div class="step-by-step"]
>[Назад](example-migration-eshop.md)
>[Вперед](deployment-scenarios.md)
