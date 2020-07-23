---
ms.openlocfilehash: d75dc2caa3a002b9d34ac74f2c5c5e192281c0df
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281314"
---
### <a name="default-activityidformat-is-w3c"></a><span data-ttu-id="cd71c-101">По умолчанию ActivityIdFormat имеет значение W3C</span><span class="sxs-lookup"><span data-stu-id="cd71c-101">Default ActivityIdFormat is W3C</span></span>

<span data-ttu-id="cd71c-102">По умолчанию в качестве формата идентификатора действия (<xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType>) теперь используется <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cd71c-102">The default identifier format for activity (<xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType>) is now <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="cd71c-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="cd71c-103">Change description</span></span>

<span data-ttu-id="cd71c-104">Формат идентификатора действия W3C был представлен в .NET Core 3.0 в качестве альтернативы иерархическому формату идентификатора.</span><span class="sxs-lookup"><span data-stu-id="cd71c-104">The W3C activity ID format was introduced in .NET Core 3.0 as an alternative to the hierarchical ID format.</span></span> <span data-ttu-id="cd71c-105">Тем не менее, чтобы обеспечить совместимость, вплоть до версии .NET 5.0 формат W3C не использовался по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cd71c-105">However, to preserve compatibility, the W3C format wasn't made the default until .NET 5.0.</span></span> <span data-ttu-id="cd71c-106">В .NET 5.0 значение по умолчанию было изменено в связи с [ратификацией формата W3C](https://www.w3.org/TR/trace-context/) для применения в различных реализациях языка.</span><span class="sxs-lookup"><span data-stu-id="cd71c-106">The default was changed in .NET 5.0 because the [W3C format has been ratified](https://www.w3.org/TR/trace-context/) and gained traction across multiple language implementations.</span></span>

<span data-ttu-id="cd71c-107">Если ваше приложение предназначено не для платформы .NET 5.0 или более поздней версии, в нем будет применяться поведение предшествующих версий, в которых по умолчанию использовался формат <xref:System.Diagnostics.ActivityIdFormat.Hierarchical>.</span><span class="sxs-lookup"><span data-stu-id="cd71c-107">If your app targets a platform other than .NET 5.0 or later, it will experience the old behavior, where <xref:System.Diagnostics.ActivityIdFormat.Hierarchical> is the default format.</span></span> <span data-ttu-id="cd71c-108">Это значение по умолчанию применяется для платформ net45+, netstandard1.1+ и netcoreapp (1.x, 2.x и 3.x).</span><span class="sxs-lookup"><span data-stu-id="cd71c-108">This default applies to platforms net45+, netstandard1.1+, and netcoreapp (1.x, 2.x, and 3.x).</span></span> <span data-ttu-id="cd71c-109">В .NET 5.0 и более поздних версий <xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType> имеет значение <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cd71c-109">In .NET 5.0 and later, <xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType> is set to <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType>.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="cd71c-110">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="cd71c-110">Version introduced</span></span>

<span data-ttu-id="cd71c-111">5.0 (предварительная версия 7)</span><span class="sxs-lookup"><span data-stu-id="cd71c-111">5.0 Preview 7</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="cd71c-112">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="cd71c-112">Recommended action</span></span>

<span data-ttu-id="cd71c-113">Если в вашем приложении не используется идентификатор для распределенной трассировки, никаких действий не требуется.</span><span class="sxs-lookup"><span data-stu-id="cd71c-113">If your application is agnostic to the identifier that's used for distributed tracing, no action is needed.</span></span> <span data-ttu-id="cd71c-114">Такие библиотеки, как ASP.NET Core и <xref:System.Net.Http.HttpClient>, могут использовать и распространять обе версии <xref:System.Diagnostics.ActivityIdFormat>.</span><span class="sxs-lookup"><span data-stu-id="cd71c-114">Libraries such as ASP.NET Core and <xref:System.Net.Http.HttpClient> can consume or propagate both versions of the <xref:System.Diagnostics.ActivityIdFormat>.</span></span>

<span data-ttu-id="cd71c-115">Если вам необходимо обеспечить совместимость с существующими системами, или в текущих системах учитывается формат идентификатора, вы можете сохранить старое поведение, установив для <xref:System.Diagnostics.Activity.DefaultIdFormat> значение <xref:System.Diagnostics.ActivityIdFormat.Hierarchical?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cd71c-115">If you require interoperability with existing systems, or current systems rely on the format of the identifier, you can preserve the old behavior by setting <xref:System.Diagnostics.Activity.DefaultIdFormat> to <xref:System.Diagnostics.ActivityIdFormat.Hierarchical?displayProperty=nameWithType>.</span></span> <span data-ttu-id="cd71c-116">Кроме того, вы можете задать параметр AppContext одним из трех способов:</span><span class="sxs-lookup"><span data-stu-id="cd71c-116">Alternatively, you can set an AppContext switch in one of three ways:</span></span>

- <span data-ttu-id="cd71c-117">В файле проекта.</span><span class="sxs-lookup"><span data-stu-id="cd71c-117">In the project file.</span></span>

  ```xml
  <ItemGroup>
    <RuntimeHostConfigurationOption Include="System.Diagnostics.DefaultActivityIdFormatIsHierarchial" Value="true" />
  </ItemGroup>
  ```

- <span data-ttu-id="cd71c-118">В файле *runtimeconfig.json*.</span><span class="sxs-lookup"><span data-stu-id="cd71c-118">In the *runtimeconfig.json* file.</span></span>

  ```json
  {
      "runtimeOptions": {
          "configProperties": {
              "System.Diagnostics.DefaultActivityIdFormatIsHierarchial": true
          }
      }
  }
  ```

- <span data-ttu-id="cd71c-119">С помощью переменной среды.</span><span class="sxs-lookup"><span data-stu-id="cd71c-119">Through an environment variable.</span></span>

  <span data-ttu-id="cd71c-120">Задайте для `DOTNET_SYSTEM_DIAGNOSTICS_DEFAULTACTIVITYIDFORMATISHIERARCHIAL` значение `true` или 1.</span><span class="sxs-lookup"><span data-stu-id="cd71c-120">Set `DOTNET_SYSTEM_DIAGNOSTICS_DEFAULTACTIVITYIDFORMATISHIERARCHIAL` to `true` or 1.</span></span>

#### <a name="category"></a><span data-ttu-id="cd71c-121">Категория</span><span class="sxs-lookup"><span data-stu-id="cd71c-121">Category</span></span>

<span data-ttu-id="cd71c-122">Библиотеки Core .NET</span><span class="sxs-lookup"><span data-stu-id="cd71c-122">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="cd71c-123">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="cd71c-123">Affected APIs</span></span>

- <xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Diagnostics.Activity.DefaultIdFormat`

-->
