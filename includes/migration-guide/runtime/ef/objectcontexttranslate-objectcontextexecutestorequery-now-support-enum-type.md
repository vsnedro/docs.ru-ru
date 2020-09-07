---
ms.openlocfilehash: 81992e57d7e92b4df92ce68870c0272d6cd5b220
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497174"
---
### <a name="objectcontexttranslate-and-objectcontextexecutestorequery-now-support-enum-type"></a><span data-ttu-id="d6e8a-101">ObjectContext.Translate и ObjectContext.ExecuteStoreQuery теперь поддерживают тип перечисления</span><span class="sxs-lookup"><span data-stu-id="d6e8a-101">ObjectContext.Translate and ObjectContext.ExecuteStoreQuery now support enum type</span></span>

#### <a name="details"></a><span data-ttu-id="d6e8a-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="d6e8a-102">Details</span></span>

<span data-ttu-id="d6e8a-103">В .NET Framework 4.0 универсальный параметр <code>T</code> методов <code>ObjectContext.Translate</code> и <code>ObjectContext.ExecuteStoreQuery</code> не мог иметь тип перечисления.</span><span class="sxs-lookup"><span data-stu-id="d6e8a-103">In .NET Framework 4.0, the generic parameter <code>T</code> of <code>ObjectContext.Translate</code> and <code>ObjectContext.ExecuteStoreQuery</code> methods could not be an enum.</span></span> <span data-ttu-id="d6e8a-104">Теперь этот сценарий поддерживается.</span><span class="sxs-lookup"><span data-stu-id="d6e8a-104">That scenario is now supported.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d6e8a-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="d6e8a-105">Suggestion</span></span>

<span data-ttu-id="d6e8a-106">Если метод Translate или ExecuteStoreQuery вызывался для типа перечисления в .NET Framework 4.0, возвращалось значение "0".</span><span class="sxs-lookup"><span data-stu-id="d6e8a-106">If Translate or ExecuteStoreQuery was called on an enum type in .NET Framework 4.0, '0' was returned.</span></span> <span data-ttu-id="d6e8a-107">Если такое поведение было желательным, вызовы следовало заменять константой 0 (или его эквивалентом перечисления).</span><span class="sxs-lookup"><span data-stu-id="d6e8a-107">If that behavior was desirable, the calls should be replaced with a constant 0 (or the enum equivalent of it).</span></span>

| <span data-ttu-id="d6e8a-108">name</span><span class="sxs-lookup"><span data-stu-id="d6e8a-108">Name</span></span>    | <span data-ttu-id="d6e8a-109">Значение</span><span class="sxs-lookup"><span data-stu-id="d6e8a-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d6e8a-110">Область</span><span class="sxs-lookup"><span data-stu-id="d6e8a-110">Scope</span></span>   |<span data-ttu-id="d6e8a-111">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="d6e8a-111">Edge</span></span>|
|<span data-ttu-id="d6e8a-112">Version</span><span class="sxs-lookup"><span data-stu-id="d6e8a-112">Version</span></span>|<span data-ttu-id="d6e8a-113">4.5</span><span class="sxs-lookup"><span data-stu-id="d6e8a-113">4.5</span></span>|
|<span data-ttu-id="d6e8a-114">Type</span><span class="sxs-lookup"><span data-stu-id="d6e8a-114">Type</span></span>|<span data-ttu-id="d6e8a-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="d6e8a-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="d6e8a-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="d6e8a-116">Affected APIs</span></span>

- <xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader)?displayProperty=nameWithType>
- <xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader,System.String,System.Data.Objects.MergeOption)?displayProperty=nameWithType>
- <xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.Object[])?displayProperty=nameWithType>
- <xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.String,System.Data.Objects.MergeOption,System.Object[])?displayProperty=nameWithType></li></ul>|

<!--

#### Affected APIs

- ``M:System.Data.Objects.ObjectContext.Translate``1(System.Data.Common.DbDataReader)``
- ``M:System.Data.Objects.ObjectContext.Translate``1(System.Data.Common.DbDataReader,System.String,System.Data.Objects.MergeOption)``
- ``M:System.Data.Objects.ObjectContext.ExecuteStoreQuery``1(System.String,System.Object[])``
- ``M:System.Data.Objects.ObjectContext.ExecuteStoreQuery``1(System.String,System.String,System.Data.Objects.MergeOption,System.Object[])``

-->
