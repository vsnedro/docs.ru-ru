---
ms.openlocfilehash: 62a5f56bb7fffc453623a2c3202f288a19110158
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539515"
---
### <a name="localization-pubternal-apis-removed"></a><span data-ttu-id="edede-101">Локализация. Удалены API-интерфейсы Pubternal</span><span class="sxs-lookup"><span data-stu-id="edede-101">Localization: "Pubternal" APIs removed</span></span>

<span data-ttu-id="edede-102">Чтобы сохранить порядок в среде общедоступных API на платформе ASP.NET Core, некоторые API локализации :::no-loc text="\"pubternal\""::: были удалены.</span><span class="sxs-lookup"><span data-stu-id="edede-102">To better maintain the public API surface of ASP.NET Core, some :::no-loc text="\"pubternal\""::: localization APIs were removed.</span></span> <span data-ttu-id="edede-103">API :::no-loc text="\"pubternal\""::: имеет модификатор доступа `public` и определен в пространстве имен, предполагающем использование намерения [internal](../../../../docs/csharp/language-reference/keywords/internal.md).</span><span class="sxs-lookup"><span data-stu-id="edede-103">A :::no-loc text="\"pubternal\""::: API has a `public` access modifier and is defined in a namespace that implies an [internal](../../../../docs/csharp/language-reference/keywords/internal.md) intent.</span></span>

<span data-ttu-id="edede-104">Обсуждение этого вопроса см. на странице [dotnet/aspnetcore#22291](https://github.com/dotnet/aspnetcore/issues/22291).</span><span class="sxs-lookup"><span data-stu-id="edede-104">For discussion, see [dotnet/aspnetcore#22291](https://github.com/dotnet/aspnetcore/issues/22291).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="edede-105">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="edede-105">Version introduced</span></span>

<span data-ttu-id="edede-106">5.0, предварительная версия 6</span><span class="sxs-lookup"><span data-stu-id="edede-106">5.0 Preview 6</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="edede-107">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="edede-107">Old behavior</span></span>

<span data-ttu-id="edede-108">Следующие API были `public`:</span><span class="sxs-lookup"><span data-stu-id="edede-108">The following APIs were `public`:</span></span>

- `Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- <span data-ttu-id="edede-109">Перегрузки конструктора `Microsoft.Extensions.Localization.ResourceManagerStringLocalizer`, принимающие один из следующих типов параметров:</span><span class="sxs-lookup"><span data-stu-id="edede-109">`Microsoft.Extensions.Localization.ResourceManagerStringLocalizer` constructor overloads accepting either of the following parameter types:</span></span>
  - `AssemblyWrapper`
  - `IResourceStringProvider`

#### <a name="new-behavior"></a><span data-ttu-id="edede-110">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="edede-110">New behavior</span></span>

<span data-ttu-id="edede-111">В следующем списке перечислены изменения.</span><span class="sxs-lookup"><span data-stu-id="edede-111">The following list outlines the changes:</span></span>

- <span data-ttu-id="edede-112">`Microsoft.Extensions.Localization.Internal.AssemblyWrapper` стал `Microsoft.Extensions.Localization.AssemblyWrapper` и теперь является `internal`.</span><span class="sxs-lookup"><span data-stu-id="edede-112">`Microsoft.Extensions.Localization.Internal.AssemblyWrapper` became `Microsoft.Extensions.Localization.AssemblyWrapper` and is now `internal`.</span></span>
- <span data-ttu-id="edede-113">`Microsoft.Extensions.Localization.Internal.IResourceStringProvider` стал `Microsoft.Extensions.Localization.Internal.IResourceStringProvider` и теперь является `internal`.</span><span class="sxs-lookup"><span data-stu-id="edede-113">`Microsoft.Extensions.Localization.Internal.IResourceStringProvider` became `Microsoft.Extensions.Localization.Internal.IResourceStringProvider` and is now `internal`.</span></span>
- <span data-ttu-id="edede-114">Перегрузки конструктора `Microsoft.Extensions.Localization.ResourceManagerStringLocalizer`, принимающие один из следующих типов параметров, теперь являются `internal`:</span><span class="sxs-lookup"><span data-stu-id="edede-114">`Microsoft.Extensions.Localization.ResourceManagerStringLocalizer` constructor overloads accepting either of the following parameter types are now `internal`:</span></span>
  - `AssemblyWrapper`
  - `IResourceStringProvider`

#### <a name="reason-for-change"></a><span data-ttu-id="edede-115">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="edede-115">Reason for change</span></span>

<span data-ttu-id="edede-116">Более подробное описание приведено на странице [aspnet/Announcements#377](https://github.com/aspnet/Announcements/issues/377#issue-473651882), типы :::no-loc text="\"pubternal\""::: были удалены из области API `public`.</span><span class="sxs-lookup"><span data-stu-id="edede-116">Explained more thoroughly at [aspnet/Announcements#377](https://github.com/aspnet/Announcements/issues/377#issue-473651882), :::no-loc text="\"pubternal\""::: types were removed from the `public` API surface.</span></span> <span data-ttu-id="edede-117">В соответствии с этими изменениями в процесс разработки можно включить больше классов.</span><span class="sxs-lookup"><span data-stu-id="edede-117">These changes adapt more classes to that design decision.</span></span> <span data-ttu-id="edede-118">Рассматриваемые классы предназначались для использования в качестве точек расширения для внутреннего тестирования команды.</span><span class="sxs-lookup"><span data-stu-id="edede-118">The classes in question were intended as extension points for the team's internal testing.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="edede-119">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="edede-119">Recommended action</span></span>

<span data-ttu-id="edede-120">Хотя это маловероятно, некоторые приложения могут намеренно или случайно зависеть от типов :::no-loc text="\"pubternal\"":::.</span><span class="sxs-lookup"><span data-stu-id="edede-120">Although it's unlikely, some apps may intentionally or accidentally depend upon the :::no-loc text="\"pubternal\""::: types.</span></span> <span data-ttu-id="edede-121">Сведения о переходе с конкретных типов см. в разделах [Новое поведение](#new-behavior).</span><span class="sxs-lookup"><span data-stu-id="edede-121">See the [New behavior](#new-behavior) sections to determine how to migrate away from the types.</span></span>

<span data-ttu-id="edede-122">Если возникла ситуация, в которой общедоступный API можно было использовать до этого изменения, а сейчас нельзя, разместите вопрос о проблеме на странице [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues).</span><span class="sxs-lookup"><span data-stu-id="edede-122">If you've identified a scenario which the public API allowed before this change but doesn't now, file an issue at [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues).</span></span>

#### <a name="category"></a><span data-ttu-id="edede-123">Категория</span><span class="sxs-lookup"><span data-stu-id="edede-123">Category</span></span>

<span data-ttu-id="edede-124">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="edede-124">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="edede-125">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="edede-125">Affected APIs</span></span>

- `Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- <xref:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.%23ctor%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `T:Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.#ctor`

-->
