---
ms.openlocfilehash: 2b88ab7cfdd7a0a0a770b305ecd0200afd9a9b4b
ms.sourcegitcommit: 2543a78be6e246aa010a01decf58889de53d1636
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/17/2020
ms.locfileid: "86441558"
---
### <a name="authorization-resource-in-endpoint-routing-is-httpcontext"></a>Авторизация. Для маршрутизации конечных точек используется ресурс HttpContext

При маршрутизации конечных точек в ASP.NET Core 3.1 в качестве ресурса для авторизации используется конечная точка. Такой подход не обеспечивал доступ к данным маршрута (<xref:Microsoft.AspNetCore.Routing.RouteData>). Ранее в MVC передавался ресурс <xref:Microsoft.AspNetCore.Http.HttpContext>, который обеспечивал доступ одновременно к конечной точке (<xref:Microsoft.AspNetCore.Http.Endpoint>) и данным маршрута. Это изменение гарантирует, что в качестве ресурса для авторизации всегда будет передаваться `HttpContext`.

#### <a name="version-introduced"></a>Представленная версия

5.0 (предварительная версия 7)

#### <a name="old-behavior"></a>Старое поведение

При использовании маршрутизации конечной точки и ПО промежуточного слоя авторизации (<xref:Microsoft.AspNetCore.Authorization.AuthorizationMiddleware>) или атрибутов [[Authorize]](xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute) в качестве ресурса для авторизации передается соответствующая конечная точка.

#### <a name="new-behavior"></a>Новое поведение

При маршрутизации конечной точки для авторизации передается `HttpContext`.

#### <a name="reason-for-change"></a>Причина изменения

Существует возможность перейти к конечной точке из `HttpContext`. Тем не менее, из конечной точки было невозможно получить информацию, например данные маршрута. Таким образом, утрачивались функциональные возможности из-за маршрутизации без конечной точки.

#### <a name="recommended-action"></a>Рекомендованное действие

Если в вашем приложении используется ресурс конечной точки вызовите <xref:Microsoft.AspNetCore.Http.EndpointHttpContextExtensions.GetEndpoint%2A> для `HttpContext`, чтобы сохранить доступ к конечной точке.

В ASP.NET Core 5.0 предварительной версии 8 и более поздних вы можете восстановить поведение предыдущих версий с использованием <xref:System.AppContext.SetSwitch%2A>. Пример:

```csharp
AppContext.SetSwitch(
    "Microsoft.AspNetCore.Authorization.SuppressUseHttpContextAsAuthorizationResource",
    isEnabled: true);
```

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

Отсутствуют

<!--

#### Affected APIs

Not detectable via API analysis

-->
