---
ms.openlocfilehash: 09bd2c6312493f8b6369d05d8f1c4e88e4c05ece
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497413"
---
### <a name="listsort-algorithm-changed"></a><span data-ttu-id="bf446-101">Изменен алгоритм List.Sort</span><span class="sxs-lookup"><span data-stu-id="bf446-101">List.Sort algorithm changed</span></span>

#### <a name="details"></a><span data-ttu-id="bf446-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="bf446-102">Details</span></span>

<span data-ttu-id="bf446-103">Начиная с версии .NET Framework 4.5, алгоритм сортировки <xref:System.Collections.Generic.List%601?displayProperty=fullName> был изменен и реализует интроспективную сортировку вместо быстрой.</span><span class="sxs-lookup"><span data-stu-id="bf446-103">Beginning in .NET Framework 4.5, <xref:System.Collections.Generic.List%601?displayProperty=fullName>'s sort algorithm has changed (to be an introspective sort instead of a quick sort).</span></span> <span data-ttu-id="bf446-104">Сортировка <xref:System.Collections.Generic.List%601?displayProperty=fullName> никогда не была стабильной, однако это изменение может привести к потере стабильности при сортировке в различных других сценариях.</span><span class="sxs-lookup"><span data-stu-id="bf446-104"><xref:System.Collections.Generic.List%601?displayProperty=fullName>'s sort has never been stable, but this change may cause different scenarios to sort in unstable ways.</span></span> <span data-ttu-id="bf446-105">Это означает, что эквивалентные элементы могут сортироваться в разном порядке при последовательных вызовах API.</span><span class="sxs-lookup"><span data-stu-id="bf446-105">That simply means that equivalent items may sort in different orders in subsequent calls of the API.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="bf446-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="bf446-106">Suggestion</span></span>

<span data-ttu-id="bf446-107">Поскольку старый алгоритм сортировки также был нестабилен (в несколько другом плане), не следует использовать код, который зависит от постоянства порядка сортировки эквивалентных элементов.</span><span class="sxs-lookup"><span data-stu-id="bf446-107">Because the old sort algorithm was also unstable (though in slightly different ways), there should be no code that depends on equivalent items always sorting in a particular order.</span></span> <span data-ttu-id="bf446-108">Если в коде присутствовала такая зависимость и он ранее выполнялся без ошибок, его следует обновить для использования компаратора, который будет осуществлять детерминированную сортировку элементов в необходимом порядке.</span><span class="sxs-lookup"><span data-stu-id="bf446-108">If there are instances of code depending upon that and being lucky with the old behavior, that code should be updated to use a comparer that will deterministically sort the items in the desired order.</span></span>

| <span data-ttu-id="bf446-109">name</span><span class="sxs-lookup"><span data-stu-id="bf446-109">Name</span></span>    | <span data-ttu-id="bf446-110">Значение</span><span class="sxs-lookup"><span data-stu-id="bf446-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="bf446-111">Область</span><span class="sxs-lookup"><span data-stu-id="bf446-111">Scope</span></span>   |<span data-ttu-id="bf446-112">Прозрачный</span><span class="sxs-lookup"><span data-stu-id="bf446-112">Transparent</span></span>|
|<span data-ttu-id="bf446-113">Version</span><span class="sxs-lookup"><span data-stu-id="bf446-113">Version</span></span>|<span data-ttu-id="bf446-114">4.5</span><span class="sxs-lookup"><span data-stu-id="bf446-114">4.5</span></span>|
|<span data-ttu-id="bf446-115">Type</span><span class="sxs-lookup"><span data-stu-id="bf446-115">Type</span></span>|<span data-ttu-id="bf446-116">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="bf446-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="bf446-117">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="bf446-117">Affected APIs</span></span>

- <xref:System.Collections.Generic.List%601.Sort?displayProperty=nameWithType>
- <xref:System.Collections.Generic.List%601.Sort(System.Collections.Generic.IComparer{%600})?displayProperty=nameWithType>
- <xref:System.Collections.Generic.List%601.Sort(System.Comparison{%600})?displayProperty=nameWithType>
- <xref:System.Collections.Generic.List%601.Sort(System.Int32,System.Int32,System.Collections.Generic.IComparer{%600})?displayProperty=nameWithType>

<!--

#### Affected APIs

- ``M:System.Collections.Generic.List`1.Sort``
- ``M:System.Collections.Generic.List`1.Sort(System.Collections.Generic.IComparer{`0})``
- ``M:System.Collections.Generic.List`1.Sort(System.Comparison{`0})``
- ``M:System.Collections.Generic.List`1.Sort(System.Int32,System.Int32,System.Collections.Generic.IComparer{`0})``

-->
