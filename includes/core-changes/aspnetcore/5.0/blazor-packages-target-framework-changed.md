---
ms.openlocfilehash: 17a167e5245914329195d61ab45ae2d8ecb617d6
ms.sourcegitcommit: 3492dafceb5d4183b6b0d2f3bdf4a1abc4d5ed8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2020
ms.locfileid: "86416282"
---
### <a name="blazor-target-framework-of-nuget-packages-changed"></a><span data-ttu-id="f9989-101">Blazor: Изменена целевая платформа для пакетов NuGet</span><span class="sxs-lookup"><span data-stu-id="f9989-101">Blazor: Target framework of NuGet packages changed</span></span>

<span data-ttu-id="f9989-102">Ранее проекты Blazor 3.2 WebAssembly компилировались для целевой платформы .NET Standard 2.1 (`<TargetFramework>netstandard2.1</TargetFramework>`).</span><span class="sxs-lookup"><span data-stu-id="f9989-102">Blazor 3.2 WebAssembly projects were compiled to target .NET Standard 2.1 (`<TargetFramework>netstandard2.1</TargetFramework>`).</span></span> <span data-ttu-id="f9989-103">В ASP.NET Core 5.0 целевой платформой для проектов Blazor Server и Blazor WebAssembly является .NET 5.0 (`<TargetFramework>net5.0</TargetFramework>`).</span><span class="sxs-lookup"><span data-stu-id="f9989-103">In ASP.NET Core 5.0, both Blazor Server and Blazor WebAssembly projects target .NET 5.0 (`<TargetFramework>net5.0</TargetFramework>`).</span></span> <span data-ttu-id="f9989-104">В соответствии с изменением целевой платформы следующие пакеты Blazor также больше не предназначены для платформы .NET Standard 2.1:</span><span class="sxs-lookup"><span data-stu-id="f9989-104">To better align with the target framework change, the following Blazor packages no longer target .NET Standard 2.1:</span></span>

* <span data-ttu-id="f9989-105">[Microsoft.AspNetCore.Components](https://www.nuget.org/packages/Microsoft.AspNetCore.Components);</span><span class="sxs-lookup"><span data-stu-id="f9989-105">[Microsoft.AspNetCore.Components](https://www.nuget.org/packages/Microsoft.AspNetCore.Components)</span></span>
* [<span data-ttu-id="f9989-106">Microsoft.AspNetCore.Components.Authorization</span><span class="sxs-lookup"><span data-stu-id="f9989-106">Microsoft.AspNetCore.Components.Authorization</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Authorization)
* [<span data-ttu-id="f9989-107">Microsoft.AspNetCore.Components.Forms</span><span class="sxs-lookup"><span data-stu-id="f9989-107">Microsoft.AspNetCore.Components.Forms</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Forms)
* <span data-ttu-id="f9989-108">[Microsoft.AspNetCore.Components.Web](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web).</span><span class="sxs-lookup"><span data-stu-id="f9989-108">[Microsoft.AspNetCore.Components.Web](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web)</span></span>
* [<span data-ttu-id="f9989-109">Microsoft.AspNetCore.Components.WebAssembly</span><span class="sxs-lookup"><span data-stu-id="f9989-109">Microsoft.AspNetCore.Components.WebAssembly</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.WebAssembly)
* [<span data-ttu-id="f9989-110">Microsoft.AspNetCore.Components.WebAssembly.Authentication</span><span class="sxs-lookup"><span data-stu-id="f9989-110">Microsoft.AspNetCore.Components.WebAssembly.Authentication</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.WebAssembly.Authentication)
* [<span data-ttu-id="f9989-111">Microsoft.JSInterop</span><span class="sxs-lookup"><span data-stu-id="f9989-111">Microsoft.JSInterop</span></span>](https://www.nuget.org/packages/Microsoft.JSInterop)
* [<span data-ttu-id="f9989-112">Microsoft.JSInterop.WebAssembly</span><span class="sxs-lookup"><span data-stu-id="f9989-112">Microsoft.JSInterop.WebAssembly</span></span>](https://www.nuget.org/packages/Microsoft.JSInterop.WebAssembly)
* [<span data-ttu-id="f9989-113">Microsoft.Authentication.WebAssembly.Msal</span><span class="sxs-lookup"><span data-stu-id="f9989-113">Microsoft.Authentication.WebAssembly.Msal</span></span>](https://www.nuget.org/packages/Microsoft.Authentication.WebAssembly.Msal)

<span data-ttu-id="f9989-114">Обсуждение этого вопроса см. на странице GitHub [dotnet/aspnetcore#23424](https://github.com/dotnet/aspnetcore/issues/23424).</span><span class="sxs-lookup"><span data-stu-id="f9989-114">For discussion, see GitHub issue [dotnet/aspnetcore#23424](https://github.com/dotnet/aspnetcore/issues/23424).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f9989-115">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="f9989-115">Version introduced</span></span>

<span data-ttu-id="f9989-116">5.0 (предварительная версия 7)</span><span class="sxs-lookup"><span data-stu-id="f9989-116">5.0 Preview 7</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="f9989-117">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="f9989-117">Old behavior</span></span>

<span data-ttu-id="f9989-118">В Blazor 3.1 и 3.2 пакеты были предназначены для платформ .NET Standard 2.1 и .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="f9989-118">In Blazor 3.1 and 3.2, packages target .NET Standard 2.1 and .NET Core 3.1.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="f9989-119">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="f9989-119">New behavior</span></span>

<span data-ttu-id="f9989-120">В ASP.NET Core 5.0 пакеты предназначены для платформы .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="f9989-120">In ASP.NET Core 5.0, packages target .NET 5.0.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="f9989-121">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="f9989-121">Reason for change</span></span>

<span data-ttu-id="f9989-122">Эти изменения были внесены в соответствии с требованиями к целевой платформе .NET.</span><span class="sxs-lookup"><span data-stu-id="f9989-122">The change was made to better align with .NET target framework requirements.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f9989-123">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="f9989-123">Recommended action</span></span>

<span data-ttu-id="f9989-124">Для проектов Blazor 3.2 WebAssembly следует задавать .NET 5.0 в качестве целевой платформы в рамках обновления ссылок на пакеты до версии 5.x.x.</span><span class="sxs-lookup"><span data-stu-id="f9989-124">Blazor 3.2 WebAssembly projects should target .NET 5.0 as part of updating their package references to 5.x.x.</span></span> <span data-ttu-id="f9989-125">Библиотеки, ссылающиеся на эти пакеты, могут быть предназначены для .NET 5.0 или сразу для нескольких платформ в зависимости от требований.</span><span class="sxs-lookup"><span data-stu-id="f9989-125">Libraries that reference one of these packages can either target .NET 5.0 or multi-target depending on their requirements.</span></span>

#### <a name="category"></a><span data-ttu-id="f9989-126">Категория</span><span class="sxs-lookup"><span data-stu-id="f9989-126">Category</span></span>

<span data-ttu-id="f9989-127">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f9989-127">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f9989-128">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="f9989-128">Affected APIs</span></span>

<span data-ttu-id="f9989-129">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="f9989-129">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
