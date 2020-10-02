---
ms.openlocfilehash: a9545c66d3873b5114fe66e13c77ddc28e20020e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077609"
---
### <a name="blazor-protectedbrowserstorage-feature-moved-to-shared-framework"></a><span data-ttu-id="52338-101">Blazor: Функция ProtectedBrowserStorage перемещена на общую платформу</span><span class="sxs-lookup"><span data-stu-id="52338-101">Blazor: ProtectedBrowserStorage feature moved to shared framework</span></span>

<span data-ttu-id="52338-102">В ASP.NET Core 5.0 RC2 функция `ProtectedBrowserStorage` перемещена в общую платформу ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="52338-102">As part of the ASP.NET Core 5.0 RC2 release, the `ProtectedBrowserStorage` feature moved to the ASP.NET Core shared framework.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="52338-103">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="52338-103">Version introduced</span></span>

<span data-ttu-id="52338-104">5.0 RC2</span><span class="sxs-lookup"><span data-stu-id="52338-104">5.0 RC2</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="52338-105">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="52338-105">Old behavior</span></span>

<span data-ttu-id="52338-106">В ASP.NET Core 5.0 предварительной версии 8 эта функция доступна в составе пакета [Microsoft.AspNetCore.Components.Web.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web.Extensions), но ее можно использовать только в Blazor WebAssembly.</span><span class="sxs-lookup"><span data-stu-id="52338-106">In ASP.NET Core 5.0 Preview 8, the feature is available as a part of the [Microsoft.AspNetCore.Components.Web.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web.Extensions) package but was only usable in Blazor WebAssembly.</span></span>

<span data-ttu-id="52338-107">В ASP.NET Core 5.0 RC1 эта функция доступна как часть пакета [Microsoft.AspNetCore.Components.ProtectedBrowserStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.ProtectedBrowserStorage), который ссылается на общую платформу `Microsoft.AspNetCore.App`.</span><span class="sxs-lookup"><span data-stu-id="52338-107">In ASP.NET Core 5.0 RC1, the feature is available as part of the [Microsoft.AspNetCore.Components.ProtectedBrowserStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.ProtectedBrowserStorage) package, which references the `Microsoft.AspNetCore.App` shared framework.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="52338-108">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="52338-108">New behavior</span></span>

<span data-ttu-id="52338-109">В ASP.NET Core 5.0 RC2 ссылка на пакет NuGet больше не требуется для обращения к этой функции и ее использования.</span><span class="sxs-lookup"><span data-stu-id="52338-109">In ASP.NET Core 5.0 RC2, a NuGet package reference is no longer needed to reference and use the feature.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="52338-110">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="52338-110">Reason for change</span></span>

<span data-ttu-id="52338-111">Переход на общую платформу больше соответствует ожиданиям клиентов.</span><span class="sxs-lookup"><span data-stu-id="52338-111">The move to the shared framework is a better fit for the user experience customers expect.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="52338-112">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="52338-112">Recommended action</span></span>

<span data-ttu-id="52338-113">При обновлении с ASP.NET Core 5.0 RC1 выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="52338-113">If upgrading from ASP.NET Core 5.0 RC1, complete the following steps:</span></span>

1. <span data-ttu-id="52338-114">удалите ссылку на пакет `Microsoft.AspNetCore.Components.ProtectedBrowserStorage` из проекта;</span><span class="sxs-lookup"><span data-stu-id="52338-114">Remove the `Microsoft.AspNetCore.Components.ProtectedBrowserStorage` package reference from the project.</span></span>
1. <span data-ttu-id="52338-115">Замените `using Microsoft.AspNetCore.Components.ProtectedBrowserStorage;` на `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.</span><span class="sxs-lookup"><span data-stu-id="52338-115">Replace `using Microsoft.AspNetCore.Components.ProtectedBrowserStorage;` with `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.</span></span>
1. <span data-ttu-id="52338-116">удалите вызов `AddProtectedBrowserStorage` из класса `Startup`.</span><span class="sxs-lookup"><span data-stu-id="52338-116">Remove the call to `AddProtectedBrowserStorage` from your `Startup` class.</span></span>

<span data-ttu-id="52338-117">При обновлении с ASP.NET Core 5.0 предварительной версии 8 выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="52338-117">If upgrading from ASP.NET Core 5.0 Preview 8, complete the following steps:</span></span>

1. <span data-ttu-id="52338-118">удалите ссылку на пакет `Microsoft.AspNetCore.Components.Web.Extensions` из проекта;</span><span class="sxs-lookup"><span data-stu-id="52338-118">Remove the `Microsoft.AspNetCore.Components.Web.Extensions` package reference from the project.</span></span>
1. <span data-ttu-id="52338-119">Замените `using Microsoft.AspNetCore.Components.Web.Extensions;` на `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.</span><span class="sxs-lookup"><span data-stu-id="52338-119">Replace `using Microsoft.AspNetCore.Components.Web.Extensions;` with `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.</span></span>
1. <span data-ttu-id="52338-120">удалите вызов `AddProtectedBrowserStorage` из класса `Startup`.</span><span class="sxs-lookup"><span data-stu-id="52338-120">Remove the call to `AddProtectedBrowserStorage` from your `Startup` class.</span></span>

#### <a name="category"></a><span data-ttu-id="52338-121">Категория</span><span class="sxs-lookup"><span data-stu-id="52338-121">Category</span></span>

<span data-ttu-id="52338-122">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="52338-122">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="52338-123">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="52338-123">Affected APIs</span></span>

<span data-ttu-id="52338-124">None</span><span class="sxs-lookup"><span data-stu-id="52338-124">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
