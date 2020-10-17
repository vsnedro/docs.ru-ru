---
ms.openlocfilehash: 584014572ab799e1e3ab2f02c9fbf4fe6b0c17e7
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2020
ms.locfileid: "91804934"
---
### <a name="blazor-updated-browser-support"></a><span data-ttu-id="86f1e-101">Blazor: Обновлен список поддерживаемых веб-браузеров</span><span class="sxs-lookup"><span data-stu-id="86f1e-101">Blazor: Updated browser support</span></span>

<span data-ttu-id="86f1e-102">В ASP.NET Core 5.0 появились [новые функции Blazor](https://github.com/dotnet/aspnetcore/issues/21514), некоторые из которых несовместимы со старыми браузерами.</span><span class="sxs-lookup"><span data-stu-id="86f1e-102">ASP.NET Core 5.0 introduces [new Blazor features](https://github.com/dotnet/aspnetcore/issues/21514), some of which are incompatible with older browsers.</span></span> <span data-ttu-id="86f1e-103">Список браузеров, поддерживаемых Blazor в ASP.NET Core 5.0, обновлен соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="86f1e-103">The list of browsers supported by Blazor in ASP.NET Core 5.0 has been updated accordingly.</span></span>

<span data-ttu-id="86f1e-104">Обсуждение этого вопроса см. на странице GitHub [dotnet/aspnetcore#26475](https://github.com/dotnet/aspnetcore/issues/26475).</span><span class="sxs-lookup"><span data-stu-id="86f1e-104">For discussion, see GitHub issue [dotnet/aspnetcore#26475](https://github.com/dotnet/aspnetcore/issues/26475).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="86f1e-105">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="86f1e-105">Version introduced</span></span>

<span data-ttu-id="86f1e-106">5.0</span><span class="sxs-lookup"><span data-stu-id="86f1e-106">5.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="86f1e-107">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="86f1e-107">Old behavior</span></span>

<span data-ttu-id="86f1e-108">Blazor Server поддерживает Microsoft Internet Explorer 11 с достаточным количеством заполнений.</span><span class="sxs-lookup"><span data-stu-id="86f1e-108">Blazor Server supports Microsoft Internet Explorer 11 with sufficient polyfills.</span></span> <span data-ttu-id="86f1e-109">Blazor Server и Blazor WebAssembly также работают в [устаревшей версии Microsoft Edge](https://support.microsoft.com/help/4533505/what-is-microsoft-edge-legacy).</span><span class="sxs-lookup"><span data-stu-id="86f1e-109">Blazor Server and Blazor WebAssembly are also functional in [Microsoft Edge Legacy](https://support.microsoft.com/help/4533505/what-is-microsoft-edge-legacy).</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="86f1e-110">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="86f1e-110">New behavior</span></span>

<span data-ttu-id="86f1e-111">Blazor Server в ASP.NET Core 5.0 не поддерживается в Microsoft Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="86f1e-111">Blazor Server in ASP.NET Core 5.0 isn't supported with Microsoft Internet Explorer 11.</span></span> <span data-ttu-id="86f1e-112">Blazor Server и Blazor WebAssembly работают с ограниченной функциональностью в устаревшей версии Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="86f1e-112">Blazor Server and Blazor WebAssembly aren't fully functional in Microsoft Edge Legacy.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="86f1e-113">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="86f1e-113">Reason for change</span></span>

<span data-ttu-id="86f1e-114">Новые функции Blazor в ASP.NET Core 5.0 несовместимы с этими старыми браузерами, кроме того, уровень их использования снижается.</span><span class="sxs-lookup"><span data-stu-id="86f1e-114">New Blazor features in ASP.NET Core 5.0 are incompatible with these older browsers, and use of these older browsers is diminishing.</span></span> <span data-ttu-id="86f1e-115">Дополнительные сведения см. в следующих ресурсах:</span><span class="sxs-lookup"><span data-stu-id="86f1e-115">For more information, see the following resources:</span></span>

* [<span data-ttu-id="86f1e-116">Поддержка Windows устаревшей версии Microsoft Edge также прекращается 9 марта 2021 г.</span><span class="sxs-lookup"><span data-stu-id="86f1e-116">Windows support for Microsoft Edge Legacy is also ending on March 9, 2021</span></span>](https://support.microsoft.com/help/4533505/what-is-microsoft-edge-legacy)
* [<span data-ttu-id="86f1e-117">Приложения и службы Microsoft 365 перестанут поддерживать Microsoft Internet Explorer 11 17 августа 2021 г.</span><span class="sxs-lookup"><span data-stu-id="86f1e-117">Microsoft 365 apps and services will end support for Microsoft Internet Explorer 11 by August 17, 2021</span></span>](/lifecycle/announcements/m365-ie11-microsoft-edge-legacy)

#### <a name="recommended-action"></a><span data-ttu-id="86f1e-118">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="86f1e-118">Recommended action</span></span>

<span data-ttu-id="86f1e-119">Обновите эти старые браузеры до [нового Microsoft Edge, основанного на Chromium](https://www.microsoft.com/edge).</span><span class="sxs-lookup"><span data-stu-id="86f1e-119">Upgrade from these older browsers to the [new, Chromium-based Microsoft Edge](https://www.microsoft.com/edge).</span></span> <span data-ttu-id="86f1e-120">Для приложений Blazor, которым требуется поддержка этих старых браузеров, используйте ASP.NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="86f1e-120">For Blazor apps that need to support these older browsers, use ASP.NET Core 3.1.</span></span> <span data-ttu-id="86f1e-121">Список поддерживаемых браузеров для Blazor в ASP.NET Core 3.1 не изменился и описан в разделе о [поддерживаемых платформах](/aspnet/core/blazor/supported-platforms?view=aspnetcore-3.1).</span><span class="sxs-lookup"><span data-stu-id="86f1e-121">The supported browsers list for Blazor in ASP.NET Core 3.1 hasn't changed and is documented at [Supported platforms](/aspnet/core/blazor/supported-platforms?view=aspnetcore-3.1).</span></span>

#### <a name="category"></a><span data-ttu-id="86f1e-122">Категория</span><span class="sxs-lookup"><span data-stu-id="86f1e-122">Category</span></span>

<span data-ttu-id="86f1e-123">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="86f1e-123">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="86f1e-124">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="86f1e-124">Affected APIs</span></span>

<span data-ttu-id="86f1e-125">None</span><span class="sxs-lookup"><span data-stu-id="86f1e-125">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
