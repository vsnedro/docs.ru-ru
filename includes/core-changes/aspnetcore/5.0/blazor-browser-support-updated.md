---
ms.openlocfilehash: 584014572ab799e1e3ab2f02c9fbf4fe6b0c17e7
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2020
ms.locfileid: "91804934"
---
### <a name="blazor-updated-browser-support"></a>Blazor: Обновлен список поддерживаемых веб-браузеров

В ASP.NET Core 5.0 появились [новые функции Blazor](https://github.com/dotnet/aspnetcore/issues/21514), некоторые из которых несовместимы со старыми браузерами. Список браузеров, поддерживаемых Blazor в ASP.NET Core 5.0, обновлен соответствующим образом.

Обсуждение этого вопроса см. на странице GitHub [dotnet/aspnetcore#26475](https://github.com/dotnet/aspnetcore/issues/26475).

#### <a name="version-introduced"></a>Представленная версия

5.0

#### <a name="old-behavior"></a>Старое поведение

Blazor Server поддерживает Microsoft Internet Explorer 11 с достаточным количеством заполнений. Blazor Server и Blazor WebAssembly также работают в [устаревшей версии Microsoft Edge](https://support.microsoft.com/help/4533505/what-is-microsoft-edge-legacy).

#### <a name="new-behavior"></a>Новое поведение

Blazor Server в ASP.NET Core 5.0 не поддерживается в Microsoft Internet Explorer 11. Blazor Server и Blazor WebAssembly работают с ограниченной функциональностью в устаревшей версии Microsoft Edge.

#### <a name="reason-for-change"></a>Причина изменения

Новые функции Blazor в ASP.NET Core 5.0 несовместимы с этими старыми браузерами, кроме того, уровень их использования снижается. Дополнительные сведения см. в следующих ресурсах:

* [Поддержка Windows устаревшей версии Microsoft Edge также прекращается 9 марта 2021 г.](https://support.microsoft.com/help/4533505/what-is-microsoft-edge-legacy)
* [Приложения и службы Microsoft 365 перестанут поддерживать Microsoft Internet Explorer 11 17 августа 2021 г.](/lifecycle/announcements/m365-ie11-microsoft-edge-legacy)

#### <a name="recommended-action"></a>Рекомендованное действие

Обновите эти старые браузеры до [нового Microsoft Edge, основанного на Chromium](https://www.microsoft.com/edge). Для приложений Blazor, которым требуется поддержка этих старых браузеров, используйте ASP.NET Core 3.1. Список поддерживаемых браузеров для Blazor в ASP.NET Core 3.1 не изменился и описан в разделе о [поддерживаемых платформах](/aspnet/core/blazor/supported-platforms?view=aspnetcore-3.1).

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

None

<!--

#### Affected APIs

Not detectable via API analysis

-->
