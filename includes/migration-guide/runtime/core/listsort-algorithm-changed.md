---
ms.openlocfilehash: 9dada93c3330331064b7a944d97d61edb4dea299
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620582"
---
### <a name="listsort-algorithm-changed"></a><span data-ttu-id="586bf-101">Изменен алгоритм List.Sort</span><span class="sxs-lookup"><span data-stu-id="586bf-101">List.Sort algorithm changed</span></span>

#### <a name="details"></a><span data-ttu-id="586bf-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="586bf-102">Details</span></span>

<span data-ttu-id="586bf-103">Начиная с версии .NET Framework 4.5, алгоритм сортировки <xref:System.Collections.Generic.List%601?displayProperty=fullName> был изменен и реализует интроспективную сортировку вместо быстрой.</span><span class="sxs-lookup"><span data-stu-id="586bf-103">Beginning in .NET Framework 4.5, <xref:System.Collections.Generic.List%601?displayProperty=fullName>'s sort algorithm has changed (to be an introspective sort instead of a quick sort).</span></span> <span data-ttu-id="586bf-104">Сортировка <xref:System.Collections.Generic.List%601?displayProperty=fullName> никогда не была стабильной, однако это изменение может привести к потере стабильности при сортировке в различных других сценариях.</span><span class="sxs-lookup"><span data-stu-id="586bf-104"><xref:System.Collections.Generic.List%601?displayProperty=fullName>'s sort has never been stable, but this change may cause different scenarios to sort in unstable ways.</span></span> <span data-ttu-id="586bf-105">Это означает, что эквивалентные элементы могут сортироваться в разном порядке при последовательных вызовах API.</span><span class="sxs-lookup"><span data-stu-id="586bf-105">That simply means that equivalent items may sort in different orders in subsequent calls of the API.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="586bf-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="586bf-106">Suggestion</span></span>

<span data-ttu-id="586bf-107">Поскольку старый алгоритм сортировки также был нестабилен (в несколько другом плане), не следует использовать код, который зависит от постоянства порядка сортировки эквивалентных элементов.</span><span class="sxs-lookup"><span data-stu-id="586bf-107">Because the old sort algorithm was also unstable (though in slightly different ways), there should be no code that depends on equivalent items always sorting in a particular order.</span></span> <span data-ttu-id="586bf-108">Если в коде присутствовала такая зависимость и он ранее выполнялся без ошибок, его следует обновить для использования компаратора, который будет осуществлять детерминированную сортировку элементов в необходимом порядке.</span><span class="sxs-lookup"><span data-stu-id="586bf-108">If there are instances of code depending upon that and being lucky with the old behavior, that code should be updated to use a comparer that will deterministically sort the items in the desired order.</span></span>

| <span data-ttu-id="586bf-109">name</span><span class="sxs-lookup"><span data-stu-id="586bf-109">Name</span></span>    | <span data-ttu-id="586bf-110">Значение</span><span class="sxs-lookup"><span data-stu-id="586bf-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="586bf-111">Область</span><span class="sxs-lookup"><span data-stu-id="586bf-111">Scope</span></span>   |<span data-ttu-id="586bf-112">Прозрачный</span><span class="sxs-lookup"><span data-stu-id="586bf-112">Transparent</span></span>|
|<span data-ttu-id="586bf-113">Version</span><span class="sxs-lookup"><span data-stu-id="586bf-113">Version</span></span>|<span data-ttu-id="586bf-114">4.5</span><span class="sxs-lookup"><span data-stu-id="586bf-114">4.5</span></span>|
|<span data-ttu-id="586bf-115">Type</span><span class="sxs-lookup"><span data-stu-id="586bf-115">Type</span></span>|<span data-ttu-id="586bf-116">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="586bf-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="586bf-117">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="586bf-117">Affected APIs</span></span>

-<xref:System.Collections.Generic.List%601.Sort?displayProperty=nameWithType></li><li><xref:System.Collections.Generic.List%601.Sort(System.Collections.Generic.IComparer{%600})?displayProperty=nameWithType></li><li><xref:System.Collections.Generic.List%601.Sort(System.Comparison{%600})?displayProperty=nameWithType></li><li><xref:System.Collections.Generic.List%601.Sort(System.Int32,System.Int32,System.Collections.Generic.IComparer{%600})?displayProperty=nameWithType></li></ul>|
