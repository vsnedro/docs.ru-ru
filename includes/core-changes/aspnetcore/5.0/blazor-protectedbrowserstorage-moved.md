---
ms.openlocfilehash: a9545c66d3873b5114fe66e13c77ddc28e20020e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077609"
---
### <a name="blazor-protectedbrowserstorage-feature-moved-to-shared-framework"></a>Blazor: Функция ProtectedBrowserStorage перемещена на общую платформу

В ASP.NET Core 5.0 RC2 функция `ProtectedBrowserStorage` перемещена в общую платформу ASP.NET Core.

#### <a name="version-introduced"></a>Представленная версия

5.0 RC2

#### <a name="old-behavior"></a>Старое поведение

В ASP.NET Core 5.0 предварительной версии 8 эта функция доступна в составе пакета [Microsoft.AspNetCore.Components.Web.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web.Extensions), но ее можно использовать только в Blazor WebAssembly.

В ASP.NET Core 5.0 RC1 эта функция доступна как часть пакета [Microsoft.AspNetCore.Components.ProtectedBrowserStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.ProtectedBrowserStorage), который ссылается на общую платформу `Microsoft.AspNetCore.App`.

#### <a name="new-behavior"></a>Новое поведение

В ASP.NET Core 5.0 RC2 ссылка на пакет NuGet больше не требуется для обращения к этой функции и ее использования.

#### <a name="reason-for-change"></a>Причина изменения

Переход на общую платформу больше соответствует ожиданиям клиентов.

#### <a name="recommended-action"></a>Рекомендованное действие

При обновлении с ASP.NET Core 5.0 RC1 выполните следующие действия:

1. удалите ссылку на пакет `Microsoft.AspNetCore.Components.ProtectedBrowserStorage` из проекта;
1. Замените `using Microsoft.AspNetCore.Components.ProtectedBrowserStorage;` на `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.
1. удалите вызов `AddProtectedBrowserStorage` из класса `Startup`.

При обновлении с ASP.NET Core 5.0 предварительной версии 8 выполните следующие действия:

1. удалите ссылку на пакет `Microsoft.AspNetCore.Components.Web.Extensions` из проекта;
1. Замените `using Microsoft.AspNetCore.Components.Web.Extensions;` на `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.
1. удалите вызов `AddProtectedBrowserStorage` из класса `Startup`.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

None

<!--

#### Affected APIs

Not detectable via API analysis

-->
