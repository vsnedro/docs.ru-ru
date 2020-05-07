---
ms.openlocfilehash: 6deeb7debce9b731f3871b7de0ad8df8a8cdafea
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728302"
---
### <a name="localization-resourcemanagerwithculturestringlocalizer-class-and-withculture-interface-member-removed"></a><span data-ttu-id="04d07-101">Локализация. Удален класс ResourceManagerWithCultureStringLocalizer и элемент интерфейса WithCulture</span><span class="sxs-lookup"><span data-stu-id="04d07-101">Localization: ResourceManagerWithCultureStringLocalizer class and WithCulture interface member removed</span></span>

<span data-ttu-id="04d07-102">Класс [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) и метод [WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) удалены в .NET 5.0, предварительная версия 1.</span><span class="sxs-lookup"><span data-stu-id="04d07-102">The [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) class and [WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) method were removed in .NET 5.0 Preview 1.</span></span>

<span data-ttu-id="04d07-103">Контекст см. в разделах [aspnet/Announcements#346](https://github.com/aspnet/Announcements/issues/346) и [dotnet/aspnetcore#3324](https://github.com/dotnet/aspnetcore/issues/3324).</span><span class="sxs-lookup"><span data-stu-id="04d07-103">For context, see [aspnet/Announcements#346](https://github.com/aspnet/Announcements/issues/346) and [dotnet/aspnetcore#3324](https://github.com/dotnet/aspnetcore/issues/3324).</span></span> <span data-ttu-id="04d07-104">Обсуждение этого изменения см. на странице [dotnet/aspnetcore#7756](https://github.com/dotnet/aspnetcore/issues/7756).</span><span class="sxs-lookup"><span data-stu-id="04d07-104">For discussion on this change, see [dotnet/aspnetcore#7756](https://github.com/dotnet/aspnetcore/issues/7756).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="04d07-105">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="04d07-105">Version introduced</span></span>

<span data-ttu-id="04d07-106">5.0 Предварительная версия 1</span><span class="sxs-lookup"><span data-stu-id="04d07-106">5.0 Preview 1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="04d07-107">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="04d07-107">Old behavior</span></span>

<span data-ttu-id="04d07-108">Класс `ResourceManagerWithCultureStringLocalizer` и метод `ResourceManagerStringLocalizer.WithCulture` являются [устаревшими в .NET Core 3.0, предварительная версия 3, и более поздних версиях](/dotnet/core/compatibility/2.2-3.0#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete).</span><span class="sxs-lookup"><span data-stu-id="04d07-108">The `ResourceManagerWithCultureStringLocalizer` class and the `ResourceManagerStringLocalizer.WithCulture` method are [obsolete in .NET Core 3.0 Preview 3 and later](/dotnet/core/compatibility/2.2-3.0#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete).</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="04d07-109">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="04d07-109">New behavior</span></span>

<span data-ttu-id="04d07-110">Класс `ResourceManagerWithCultureStringLocalizer` и метод `ResourceManagerStringLocalizer.WithCulture` были удалены в .NET 5.0, предварительная версия 1.</span><span class="sxs-lookup"><span data-stu-id="04d07-110">The `ResourceManagerWithCultureStringLocalizer` class and the `ResourceManagerStringLocalizer.WithCulture` method have been removed in .NET 5.0 Preview 1.</span></span> <span data-ttu-id="04d07-111">Сведения о внесенных изменениях см. в запросе на вытягивание [dotnet/extensions#2562](https://github.com/dotnet/extensions/pull/2562/files).</span><span class="sxs-lookup"><span data-stu-id="04d07-111">For an inventory of the changes made, see the pull request at [dotnet/extensions#2562](https://github.com/dotnet/extensions/pull/2562/files).</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="04d07-112">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="04d07-112">Reason for change</span></span>

<span data-ttu-id="04d07-113">Класс [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) и метод [ResourceManagerStringLocalizer.WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) часто создают путаницу для пользователей локализации.</span><span class="sxs-lookup"><span data-stu-id="04d07-113">The [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) class and [ResourceManagerStringLocalizer.WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) method were often sources of confusion for users of localization.</span></span> <span data-ttu-id="04d07-114">Особенно это проявляется при создании пользовательской реализации <xref:Microsoft.Extensions.Localization.IStringLocalizer>.</span><span class="sxs-lookup"><span data-stu-id="04d07-114">The confusion was especially high when creating a custom <xref:Microsoft.Extensions.Localization.IStringLocalizer> implementation.</span></span> <span data-ttu-id="04d07-115">Этот класс и метод создают ощущение, что экземпляр `IStringLocalizer` должен существовать для каждого языка и ресурса.</span><span class="sxs-lookup"><span data-stu-id="04d07-115">This class and method give consumers the impression that an `IStringLocalizer` instance is expected to be "per-language, per-resource".</span></span> <span data-ttu-id="04d07-116">На самом деле экземпляры различаются только для ресурсов.</span><span class="sxs-lookup"><span data-stu-id="04d07-116">In reality, the instance should only be "per-resource".</span></span> <span data-ttu-id="04d07-117">Во время выполнения свойство <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> определяет используемый язык.</span><span class="sxs-lookup"><span data-stu-id="04d07-117">At run time, the <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> property determines the language to be used.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="04d07-118">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="04d07-118">Recommended action</span></span>

<span data-ttu-id="04d07-119">Прекратите использовать класс `ResourceManagerWithCultureStringLocalizer` и метод `ResourceManagerStringLocalizer.WithCulture`.</span><span class="sxs-lookup"><span data-stu-id="04d07-119">Stop using the `ResourceManagerWithCultureStringLocalizer` class and the `ResourceManagerStringLocalizer.WithCulture` method.</span></span>

#### <a name="category"></a><span data-ttu-id="04d07-120">Категория</span><span class="sxs-lookup"><span data-stu-id="04d07-120">Category</span></span>

<span data-ttu-id="04d07-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="04d07-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="04d07-122">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="04d07-122">Affected APIs</span></span>

- [<span data-ttu-id="04d07-123">ResourceManagerWithCultureStringLocalizer</span><span class="sxs-lookup"><span data-stu-id="04d07-123">ResourceManagerWithCultureStringLocalizer</span></span>](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1)
- [<span data-ttu-id="04d07-124">ResourceManagerStringLocalizer.WithCulture</span><span class="sxs-lookup"><span data-stu-id="04d07-124">ResourceManagerStringLocalizer.WithCulture</span></span>](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1)

<!--

#### Affected APIs

- `T:Microsoft.Extensions.Localization.ResourceManagerWithCultureStringLocalizer`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.WithCulture`

-->
