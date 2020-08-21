---
ms.openlocfilehash: 950c69199219cca615e403c6515239de8864d35d
ms.sourcegitcommit: d3c09791297f0edc468a4849a5f11ef62e0e90fd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/12/2020
ms.locfileid: "88137478"
---
### <a name="complexity-of-linq-orderbyfirstordefault-increased"></a><span data-ttu-id="cace3-101">Увеличена сложность LINQ OrderBy.First{OrDefault}</span><span class="sxs-lookup"><span data-stu-id="cace3-101">Complexity of LINQ OrderBy.First{OrDefault} increased</span></span>

<span data-ttu-id="cace3-102">Реализация <xref:System.Linq.Enumerable.OrderBy%2A>`.`<xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> и <xref:System.Linq.Enumerable.OrderBy%2A>`.`<xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> изменилась, что привело к увеличению сложности операции.</span><span class="sxs-lookup"><span data-stu-id="cace3-102">The implementation of <xref:System.Linq.Enumerable.OrderBy%2A>`.`<xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> and <xref:System.Linq.Enumerable.OrderBy%2A>`.`<xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> has changed, resulting in increased complexity for the operation.</span></span>

#### <a name="change-description"></a><span data-ttu-id="cace3-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="cace3-103">Change description</span></span>

<span data-ttu-id="cace3-104">В .NET Core версий 1.x–3.x вызов <xref:System.Linq.Enumerable.OrderBy%2A> или <xref:System.Linq.Enumerable.OrderByDescending%2A>, за которым следовал вызов <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> или <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})>, выполнялся с уровнем сложности `O(N)`.</span><span class="sxs-lookup"><span data-stu-id="cace3-104">In .NET Core 1.x - 3.x, calling <xref:System.Linq.Enumerable.OrderBy%2A> or <xref:System.Linq.Enumerable.OrderByDescending%2A> followed by <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> or <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> operates with `O(N)` complexity.</span></span> <span data-ttu-id="cace3-105">Так как требуется только первый элемент (элемент по умолчанию), для его поиска требуется только одно перечисление.</span><span class="sxs-lookup"><span data-stu-id="cace3-105">Since only the first (or default) element is required, only one enumeration is required to find it.</span></span> <span data-ttu-id="cace3-106">Однако предикат, передаваемый в <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> или <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})>, вызывается ровно `N` раз, где `N` — длина последовательности.</span><span class="sxs-lookup"><span data-stu-id="cace3-106">However, the predicate that's supplied to <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> or <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> is invoked exactly `N` times, where `N` is the length of the sequence.</span></span>

<span data-ttu-id="cace3-107">В .NET 5.0 и более поздних версиях было [внесено изменение](https://github.com/dotnet/runtime/pull/36643), вследствие которого вызов <xref:System.Linq.Enumerable.OrderBy%2A> или <xref:System.Linq.Enumerable.OrderByDescending%2A>, за которым следует <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> или <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})>, выполняется с уровнем сложности `O(N log N)`, а не `O(N)`.</span><span class="sxs-lookup"><span data-stu-id="cace3-107">In .NET 5.0 and later versions, a [change was made](https://github.com/dotnet/runtime/pull/36643) such that calling <xref:System.Linq.Enumerable.OrderBy%2A> or <xref:System.Linq.Enumerable.OrderByDescending%2A> followed by <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> or <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> operates with `O(N log N)` complexity instead of `O(N)` complexity.</span></span> <span data-ttu-id="cace3-108">Однако предикат, который передается в <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> или <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})>, может вызываться *менее* чем `N` раз, что более важно для общей производительности.</span><span class="sxs-lookup"><span data-stu-id="cace3-108">However, the predicate that's supplied to <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> or <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> may be invoked *less* than `N` times, which is more important for overall performance.</span></span>

> [!NOTE]
> <span data-ttu-id="cace3-109">Это изменение соответствует реализации и сложности операции в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cace3-109">This change matches the implementation and complexity of the operation in .NET Framework.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="cace3-110">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="cace3-110">Reason for change</span></span>

<span data-ttu-id="cace3-111">Преимущество вызова предиката меньшее число раз перевешивает общее снижение сложности, поэтому реализация, появившаяся в .NET Core 1.0, была отменена.</span><span class="sxs-lookup"><span data-stu-id="cace3-111">The benefit of invoking the predicate fewer times outweighs a lower overall complexity, so the implementation that was introduced in .NET Core 1.0 was reverted.</span></span> <span data-ttu-id="cace3-112">Дополнительные сведения в описании [этой проблемы dotnet/runtime](https://github.com/dotnet/runtime/issues/31554).</span><span class="sxs-lookup"><span data-stu-id="cace3-112">For more information, see [this dotnet/runtime issue](https://github.com/dotnet/runtime/issues/31554).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="cace3-113">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="cace3-113">Version introduced</span></span>

<span data-ttu-id="cace3-114">5.0</span><span class="sxs-lookup"><span data-stu-id="cace3-114">5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="cace3-115">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="cace3-115">Recommended action</span></span>

<span data-ttu-id="cace3-116">От разработчика не требуется никаких действий.</span><span class="sxs-lookup"><span data-stu-id="cace3-116">No action is required on the developer's part.</span></span>

#### <a name="category"></a><span data-ttu-id="cace3-117">Категория</span><span class="sxs-lookup"><span data-stu-id="cace3-117">Category</span></span>

<span data-ttu-id="cace3-118">Библиотеки Core .NET</span><span class="sxs-lookup"><span data-stu-id="cace3-118">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="cace3-119">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="cace3-119">Affected APIs</span></span>

- <xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=fullName>
- <xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=fullName>
- <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})?displayProperty=fullName>
- <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Linq.Enumerable.OrderBy`
- `Overload:System.Linq.Enumerable.OrderByDescending`
- `M:System.Linq.Enumerable.First``1(System.Collections.Generic.IEnumerable{``0},System.Func{``0,System.Boolean})`
- `M:System.Linq.Enumerable.FirstOrDefault``1(System.Collections.Generic.IEnumerable{``0},System.Func{``0,System.Boolean})`

-->
