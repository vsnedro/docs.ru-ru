---
title: Сравнение проверки подлинности и авторизации между ASP.NET MVC и ASP.NET Core
description: Сводка различий проверки подлинности и авторизации между ASP.NET MVC и ASP.NET Core.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: c8f3314186b7408e40d3a79cbc922a29eb75c5d2
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401817"
---
# <a name="compare-authentication-and-authorization-between-aspnet-mvc-and-aspnet-core"></a>Сравнение проверки подлинности и авторизации между ASP.NET MVC и ASP.NET Core

В ASP.NET MVC 5 Проверка подлинности настраивается в *Startup.auth.CS* в папке *App_Start* . В ASP.NET Core MVC эта конфигурация происходит в `Startup.cs` . Проверка подлинности и авторизация выполняются с помощью по промежуточного слоя, добавленного в конвейер запросов в `ConfigureServices` .

```csharp
// inside Startup.ConfigureServices

app.UseRouting();

app.UseAuthentication();
app.UseAuthorization();

app.UseEndpoints(endpoints =>
{
    endpoints.MapControllerRoute(
        name: "default",
        pattern: "{controller=Home}/{action=Index}/{id?}");
    endpoints.MapRazorPages();
});
```

Важно добавить по промежуточного слоя проверки подлинности в соответствующем порядке в конвейере по промежуточного слоя. Только запросы, которые делают его по промежуточного слоя, будут затронуты. Например, если вызов метода `UseStaticFiles()` был помещен выше показанного здесь кода, он не будет защищен проверкой подлинности и авторизацией.

В ASP.NET MVC и веб-API приложения часто обращаются к текущему пользователю с помощью `ClaimsPrincipal.Current` Свойства. Это свойство не задано в ASP.NET Core, и любое поведение в приложении, которое зависит от него, должно быть [перенесено из ClaimsPrincipal. Current](/aspnet/core/migration/claimsprincipal-current) с помощью `User` свойства в `ControllerBase` или получения доступа к текущему `HttpContext` свойству и ссылки на его `User` свойство. Если ни одно из этих решений не является параметром, службы могут запросить пользователя в качестве аргумента, в этом случае он должен быть указан в любом расположении в приложении, а также `IHttpContextAccessor` может быть запрошен и использован для получения `HttpContext` .

## <a name="authorization"></a>Авторизация

Авторизация определяет, что может делать данный пользователь в приложении. Это отдельно от проверки подлинности, что очень важно для идентификации пользователя. ASP.NET Core предоставляет простую, декларативную роль и многофункциональную модель на основе политик для авторизации. Чтобы указать, что ресурсу требуется авторизация, часто достаточно просто добавить `[Authorize]` атрибут к действию или контроллеру. Если выполняется миграция на Razor Pages из представлений MVC, необходимо [указать соглашения для авторизации при настройке Razor Pages при запуске](/aspnet/core/security/authorization/razor-pages-authorization).

Авторизация в ASP.NET Core может быть такой же простой, как запрет анонимных пользователей, разрешая пользователям, прошедшим проверку подлинности. Кроме того, можно увеличить масштаб для поддержки подходов авторизации на основе ролей, основанных на утверждениях или политик. Дополнительные сведения об этих подходах см. в документации по [авторизации в ASP.NET Core](/aspnet/core/security/authorization/introduction). Скорее всего, вы обнаружите, что один из них тесно соответствует текущему подходу авторизации.

## <a name="references"></a>Ссылки

- [Безопасность, проверка подлинности и авторизация с помощью ASP.NET MVC](/aspnet/mvc/overview/security/)
- [Перенесите проверку подлинности и удостоверение в ASP.NET Core](/aspnet/mvc/overview/security/)
- [Миграция из ClaimsPrincipal. Current](/aspnet/core/migration/claimsprincipal-current)
- [Общие сведения об авторизации в ASP.NET Core](/aspnet/core/security/authorization/introduction)

>[!div class="step-by-step"]
>[Назад](webapi-differences.md)
>[Вперед](identity-differences.md)
