---
title: Сравнение контроллеров в ASP.NET MVC и ASP.NET Core
description: ASP.NET Core контроллеры MVC похожи на контроллеры ASP.NET MVC 5 и Web API 2, но существуют важные различия. В этом разделе рассматриваются различия и действия, необходимые для переноса приложений из ASP.NET MVC и Web API 2 в ASP.NET Core.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 2c2b7b848162a6ab9901ac9f7779787e2cc994ce
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401781"
---
# <a name="compare-controllers-in-aspnet-mvc-and-web-api-with-controllers-in-aspnet-core"></a>Сравнение контроллеров в ASP.NET MVC и веб-API с контроллерами в ASP.NET Core

В ASP.NET MVC 5 и Web API 2 существовали два разных `Controller` базовых типа. Контроллеры MVC, наследуемые от `Controller` ; Контроллеры веб-API, наследуемые от `ApiController` . В ASP.NET Core Эта иерархия объектов была объединена. Рекомендуется, чтобы контроллеры API в ASP.NET Core наследовались от `ControllerBase` и добавили `[ApiController]` атрибут. Стандартные контроллеры MVC, основанные на представлении, должны наследоваться от `Controller` .

В обеих платформах контроллеры используются для организации наборов методов действий. Фильтры и маршруты можно применять к уровню контроллера в дополнение к уровню действий. Эти соглашения можно дополнительно расширить, используя пользовательские базовые `Controller` типы с поведением по умолчанию и применяемыми к ним атрибутами.

В ASP.NET MVC согласование содержимого не поддерживается. Веб-API ASP.NET 2 поддерживает согласование содержимого, как это делает ASP.NET Core. При использовании [согласования содержимого](/aspnet/core/web-api/advanced/formatting)формат содержимого, возвращаемого в запрос, может определяться заголовками, которые клиент предоставляет, указывая предпочтительный способ получения содержимого.

При переносе контроллеров веб-API ASP.NET в ASP.NET Core необходимо изменить несколько компонентов, если они существуют. К ним относятся ссылки на `ApiController` базовый класс, `System.Web.Http` пространство имен и `IHttpActionResult` интерфейс. [Рекомендации по переносу указанных различий](/aspnet/core/migration/webapi)см. в документации. Обратите внимание, что предпочтительным типом возвращаемого значения для действий API в ASP.NET Core является `ActionResult<T>` .

Кроме того, `[ChildActionOnly]` атрибут не поддерживается в ASP.NET Core. В ASP.NET Core аналогичные функциональные возможности реализуются с помощью [компонентов представления](/aspnet/core/mvc/views/view-components).

ASP.NET Core включает два новых атрибута: [консумесаттрибуте](/dotnet/api/microsoft.aspnetcore.mvc.consumesattribute) и [продуцесаттрибуте](/dotnet/api/microsoft.aspnetcore.mvc.producesattribute). Они используются для указания типа, который потребляет или создает действие, что может быть полезно для маршрутизации и документирования API с помощью таких средств, как [Swagger и OpenAPI](/aspnet/core/tutorials/web-api-help-pages-using-swagger).

## <a name="references"></a>Ссылки

- [Форматирование данных отклика в веб-API ASP.NET Core](/aspnet/core/web-api/advanced/formatting)
- [Переход с веб-API ASP.NET на ASP.NET Core](/aspnet/core/migration/webapi)

>[!div class="step-by-step"]
>[Назад](identity-differences.md)
>[Вперед](razor-differences.md)
