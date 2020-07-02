---
ms.openlocfilehash: 9131c91b34f4c24653dea37ea39af6be6e072287
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620631"
---
### <a name="enumerableemptylttresultgt-always-returns-cached-instance"></a><span data-ttu-id="2ea2e-101">Enumerable.Empty&lt;TResult&gt; всегда возвращает кэшированный экземпляр</span><span class="sxs-lookup"><span data-stu-id="2ea2e-101">Enumerable.Empty&lt;TResult&gt; always returns cached instance</span></span>

#### <a name="details"></a><span data-ttu-id="2ea2e-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="2ea2e-102">Details</span></span>

<span data-ttu-id="2ea2e-103">Начиная с версии .NET Framework 4.5 <xref:System.Linq.Enumerable.Empty%60%601> всегда возвращает кэшированный внутренний экземпляр <xref:System.Collections.Generic.IEnumerable%601>. Ранее <xref:System.Linq.Enumerable.Empty%60%601> кэшировал пустой <xref:System.Collections.Generic.IEnumerable%601> в момент вызова API, и в некоторых ситуациях, когда <xref:System.Linq.Enumerable.Empty%60%601> вызывался быстро и параллельно, для различных вызовов API могли возвращаться разные экземпляры типа.</span><span class="sxs-lookup"><span data-stu-id="2ea2e-103">Beginning in .NET Framework 4.5, <xref:System.Linq.Enumerable.Empty%60%601> always returns a cached internal instance <xref:System.Collections.Generic.IEnumerable%601>.Previously, <xref:System.Linq.Enumerable.Empty%60%601> would cache an empty <xref:System.Collections.Generic.IEnumerable%601> at the time the API was called, meaning that in some conditions in which <xref:System.Linq.Enumerable.Empty%60%601> was called rapidly and concurrently, different instances of the type could be returned for different calls to the API.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2ea2e-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="2ea2e-104">Suggestion</span></span>

<span data-ttu-id="2ea2e-105">Так как прежнее поведение было недетерминированным, код вряд ли зависит от него.</span><span class="sxs-lookup"><span data-stu-id="2ea2e-105">Because the previous behavior was non-deterministic, code is unlikely to depend on it.</span></span> <span data-ttu-id="2ea2e-106">Однако в том маловероятном случае, когда выполняется сравнение пустых перечислений и ожидается, что они будут неравными, следует создать явные пустые массивы (<code>new T[0]</code>) и не использовать <xref:System.Linq.Enumerable.Empty%60%601>.</span><span class="sxs-lookup"><span data-stu-id="2ea2e-106">However, in the unlikely case that empty enumerables are being compared and expected to sometimes be unequal, explicit empty arrays should be created (<code>new T[0]</code>) instead of using <xref:System.Linq.Enumerable.Empty%60%601>.</span></span>

| <span data-ttu-id="2ea2e-107">name</span><span class="sxs-lookup"><span data-stu-id="2ea2e-107">Name</span></span>    | <span data-ttu-id="2ea2e-108">Значение</span><span class="sxs-lookup"><span data-stu-id="2ea2e-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2ea2e-109">Область</span><span class="sxs-lookup"><span data-stu-id="2ea2e-109">Scope</span></span>   |<span data-ttu-id="2ea2e-110">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="2ea2e-110">Edge</span></span>|
|<span data-ttu-id="2ea2e-111">Version</span><span class="sxs-lookup"><span data-stu-id="2ea2e-111">Version</span></span>|<span data-ttu-id="2ea2e-112">4.5</span><span class="sxs-lookup"><span data-stu-id="2ea2e-112">4.5</span></span>|
|<span data-ttu-id="2ea2e-113">Type</span><span class="sxs-lookup"><span data-stu-id="2ea2e-113">Type</span></span>|<span data-ttu-id="2ea2e-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="2ea2e-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2ea2e-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="2ea2e-115">Affected APIs</span></span>

-<xref:System.Linq.Enumerable.Empty%60%601?displayProperty=nameWithType></li></ul>|
