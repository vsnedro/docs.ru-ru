---
ms.openlocfilehash: d7a93cb539baee6a70f75d3afe52fd7546ac2399
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2020
ms.locfileid: "82507101"
---
### <a name="extensions-package-reference-changes-affecting-some-nuget-packages"></a><span data-ttu-id="ae453-101">Расширения. Изменения ссылок на пакеты, затрагивающие некоторые пакеты NuGet</span><span class="sxs-lookup"><span data-stu-id="ae453-101">Extensions: Package reference changes affecting some NuGet packages</span></span>

<span data-ttu-id="ae453-102">При переносе некоторых пакетов NuGet `Microsoft.Extensions.*` из репозитория [dotnet/extensions](https://github.com/dotnet/extensions) в [dotnet/runtime](https://github.com/dotnet/runtime), как описано на странице [aspnet/Announcements#411](https://github.com/aspnet/Announcements/issues/411), изменения в пакетах применяются к некоторым перенесенным пакетам.</span><span class="sxs-lookup"><span data-stu-id="ae453-102">With the migration of some `Microsoft.Extensions.*` NuGet packages from the [dotnet/extensions](https://github.com/dotnet/extensions) repository to [dotnet/runtime](https://github.com/dotnet/runtime), as described in [aspnet/Announcements#411](https://github.com/aspnet/Announcements/issues/411), packaging changes are being applied to some of the migrated packages.</span></span> <span data-ttu-id="ae453-103">Обсуждение этого вопроса см. на странице [dotnet/aspnetcore#21033](https://github.com/dotnet/aspnetcore/issues/21033).</span><span class="sxs-lookup"><span data-stu-id="ae453-103">For discussion on this issue, see [dotnet/aspnetcore#21033](https://github.com/dotnet/aspnetcore/issues/21033).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ae453-104">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="ae453-104">Version introduced</span></span>

<span data-ttu-id="ae453-105">5.0, предварительная версия 4</span><span class="sxs-lookup"><span data-stu-id="ae453-105">5.0 Preview 4</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="ae453-106">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="ae453-106">Old behavior</span></span>

<span data-ttu-id="ae453-107">Некоторые пакеты `Microsoft.Extensions.*` включают ссылки на пакеты для API, использовавшиеся приложением.</span><span class="sxs-lookup"><span data-stu-id="ae453-107">Some `Microsoft.Extensions.*` packages included package references for APIs on which your app relied.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="ae453-108">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="ae453-108">New behavior</span></span>

<span data-ttu-id="ae453-109">Приложению может потребоваться добавить зависимости пакета `Microsoft.Extensions.*`.</span><span class="sxs-lookup"><span data-stu-id="ae453-109">Your app may have to add `Microsoft.Extensions.*` package dependencies.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="ae453-110">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="ae453-110">Reason for change</span></span>

<span data-ttu-id="ae453-111">Политики упаковки были обновлены для согласованности с репозиторием *dotnet/runtime*.</span><span class="sxs-lookup"><span data-stu-id="ae453-111">Packaging policies were updated to better align with the *dotnet/runtime* repository.</span></span> <span data-ttu-id="ae453-112">В новой политике неиспользуемые ссылки на пакеты удаляются из файлов *NUPKG* во время упаковки.</span><span class="sxs-lookup"><span data-stu-id="ae453-112">Under the new policy, unused package references are removed from *.nupkg* files during packaging.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ae453-113">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="ae453-113">Recommended action</span></span>

<span data-ttu-id="ae453-114">Пользователи затронутых пакетов должны добавить прямую зависимость от удаленной зависимости пакета в своем проекте, если используются API из удаленной зависимости пакета.</span><span class="sxs-lookup"><span data-stu-id="ae453-114">Consumers of the affected packages should add a direct dependency on the removed package dependency in their project if APIs from removed package dependency are used.</span></span> <span data-ttu-id="ae453-115">В следующей таблице перечислены затронутые пакеты и соответствующие изменения.</span><span class="sxs-lookup"><span data-stu-id="ae453-115">The following table lists the affected packages and the corresponding changes.</span></span>

|<span data-ttu-id="ae453-116">Имя пакета</span><span class="sxs-lookup"><span data-stu-id="ae453-116">Package name</span></span>|<span data-ttu-id="ae453-117">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="ae453-117">Change description</span></span>|
|------------|------------------|
|[<span data-ttu-id="ae453-118">Microsoft.Extensions.Configuration.Binder</span><span class="sxs-lookup"><span data-stu-id="ae453-118">Microsoft.Extensions.Configuration.Binder</span></span>](https://nuget.org/packages/Microsoft.Extensions.Configuration.Binder)|<span data-ttu-id="ae453-119">Удалена ссылка на `Microsoft.Extensions.Configuration`</span><span class="sxs-lookup"><span data-stu-id="ae453-119">Removed reference to `Microsoft.Extensions.Configuration`</span></span>|
|[<span data-ttu-id="ae453-120">Microsoft.Extensions.Configuration.Json</span><span class="sxs-lookup"><span data-stu-id="ae453-120">Microsoft.Extensions.Configuration.Json</span></span>](https://nuget.org/packages/Microsoft.Extensions.Configuration.Json)    |<span data-ttu-id="ae453-121">Удалена ссылка на `System.Threading.Tasks.Extensions`</span><span class="sxs-lookup"><span data-stu-id="ae453-121">Removed reference to `System.Threading.Tasks.Extensions`</span></span>|
|[<span data-ttu-id="ae453-122">Microsoft.Extensions.Hosting.Abstractions</span><span class="sxs-lookup"><span data-stu-id="ae453-122">Microsoft.Extensions.Hosting.Abstractions</span></span>](https://nuget.org/packages/Microsoft.Extensions.Hosting.Abstractions)|<span data-ttu-id="ae453-123">Удалена ссылка на `Microsoft.Extensions.Logging.Abstractions`</span><span class="sxs-lookup"><span data-stu-id="ae453-123">Removed reference to `Microsoft.Extensions.Logging.Abstractions`</span></span>|
|[<span data-ttu-id="ae453-124">Microsoft.Extensions.Logging</span><span class="sxs-lookup"><span data-stu-id="ae453-124">Microsoft.Extensions.Logging</span></span>](https://nuget.org/packages/Microsoft.Extensions.Logging)                          |<span data-ttu-id="ae453-125">Удалена ссылка на `Microsoft.Extensions.Configuration.Binder`</span><span class="sxs-lookup"><span data-stu-id="ae453-125">Removed reference to `Microsoft.Extensions.Configuration.Binder`</span></span>|
|[<span data-ttu-id="ae453-126">Microsoft.Extensions.Logging.Console</span><span class="sxs-lookup"><span data-stu-id="ae453-126">Microsoft.Extensions.Logging.Console</span></span>](https://nuget.org/packages/Microsoft.Extensions.Logging.Console)          |<span data-ttu-id="ae453-127">Удалена ссылка на `Microsoft.Extensions.Configuration.Abstractions`</span><span class="sxs-lookup"><span data-stu-id="ae453-127">Removed reference to `Microsoft.Extensions.Configuration.Abstractions`</span></span>|
|[<span data-ttu-id="ae453-128">Microsoft.Extensions.Logging.EventLog</span><span class="sxs-lookup"><span data-stu-id="ae453-128">Microsoft.Extensions.Logging.EventLog</span></span>](https://nuget.org/packages/Microsoft.Extensions.Logging.EventLog)        |<span data-ttu-id="ae453-129">Удалена ссылка на `System.Diagnostics.EventLog` для моникера целевой платформы .NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="ae453-129">Removed reference to `System.Diagnostics.EventLog` for the .NET Framework 4.6.1 target framework moniker</span></span>|
|[<span data-ttu-id="ae453-130">Microsoft.Extensions.Logging.EventSource</span><span class="sxs-lookup"><span data-stu-id="ae453-130">Microsoft.Extensions.Logging.EventSource</span></span>](https://nuget.org/packages/Microsoft.Extensions.Logging.EventSource)  |<span data-ttu-id="ae453-131">Удалена ссылка на `System.Threading.Tasks.Extensions`</span><span class="sxs-lookup"><span data-stu-id="ae453-131">Removed reference to `System.Threading.Tasks.Extensions`</span></span>|
|[<span data-ttu-id="ae453-132">Microsoft.Extensions.Options</span><span class="sxs-lookup"><span data-stu-id="ae453-132">Microsoft.Extensions.Options</span></span>](https://nuget.org/packages/Microsoft.Extensions.Options)                          |<span data-ttu-id="ae453-133">Удалена ссылка на `System.ComponentModel.Annotations`</span><span class="sxs-lookup"><span data-stu-id="ae453-133">Removed reference to `System.ComponentModel.Annotations`</span></span>|

<span data-ttu-id="ae453-134">Например, ссылка на пакет `Microsoft.Extensions.Configuration` была удалена из `Microsoft.Extensions.Configuration.Binder`.</span><span class="sxs-lookup"><span data-stu-id="ae453-134">For example, the package reference to `Microsoft.Extensions.Configuration` was removed from `Microsoft.Extensions.Configuration.Binder`.</span></span> <span data-ttu-id="ae453-135">В пакете не использовался API из зависимости.</span><span class="sxs-lookup"><span data-stu-id="ae453-135">No API from the dependency was used in the package.</span></span> <span data-ttu-id="ae453-136">Пользователи `Microsoft.Extensions.Configuration.Binder`, которые зависят от API из `Microsoft.Extensions.Configuration`, должны добавить прямую ссылку на него в своем проекте.</span><span class="sxs-lookup"><span data-stu-id="ae453-136">Users of `Microsoft.Extensions.Configuration.Binder` who depend on APIs from `Microsoft.Extensions.Configuration` should add a direct reference to it in their project.</span></span>

#### <a name="category"></a><span data-ttu-id="ae453-137">Категория</span><span class="sxs-lookup"><span data-stu-id="ae453-137">Category</span></span>

<span data-ttu-id="ae453-138">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ae453-138">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ae453-139">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="ae453-139">Affected APIs</span></span>

<span data-ttu-id="ae453-140">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="ae453-140">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
