---
ms.openlocfilehash: d23d7821e19b9d7f2db13a6bfdf868a8414cf721
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496443"
---
### <a name="item-scrolling-a-flat-list-with-items-of-different-pixel-height"></a><span data-ttu-id="ddb05-101">Поэлементная прокрутка плоского списка с элементами, имеющими различную высоту в пикселях</span><span class="sxs-lookup"><span data-stu-id="ddb05-101">Item-scrolling a flat list with items of different pixel-height</span></span>

#### <a name="details"></a><span data-ttu-id="ddb05-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="ddb05-102">Details</span></span>

<span data-ttu-id="ddb05-103">Когда <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> отображает коллекцию с помощью виртуализации (<code>IsVirtualizing=true</code>) и прокрутки элемента (<code>ScrollUnit=Item</code>) и когда элемент управления прокручивается для отображения элемента, высота которого в пикселях отличается о высоты соседних элементов, <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName> выполняет итерацию по всем элементам в коллекции.</span><span class="sxs-lookup"><span data-stu-id="ddb05-103">When an <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> displays a collection using virtualization (<code>IsVirtualizing=true</code>) and item- scrolling (<code>ScrollUnit=Item</code>), and when the control scrolls to display an item whose height in pixels differs from its neighbors, the <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName> iterates over all items in the collection.</span></span> <span data-ttu-id="ddb05-104">Пользовательский интерфейс не отвечает на запросы в ходе этой итерации; если коллекция большая, это может восприниматься как зависание.</span><span class="sxs-lookup"><span data-stu-id="ddb05-104">The UI is unresponsive during this iteration; if the collection is large, this can be perceived as a hang.</span></span> <span data-ttu-id="ddb05-105">Такая итерация происходит и в других ситуациях, даже в более ранних выпусках .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ddb05-105">The iteration occurs in other circumstances, even in previous .NET Framework releases.</span></span> <span data-ttu-id="ddb05-106">Например, она происходит при пиксельной прокрутке (<code>ScrollUnit=Pixel</code>) при обнаружении элемента другой высоты в пикселях, а также при поэлементной прокрутке иерархических данных (например, в элементе управления <xref:System.Windows.Controls.TreeView?displayProperty=fullName> или <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> с включенным группированием) при обнаружении элемента, число подчиненных элементов которого отличается от соседних элементов. Для поэлементной прокрутки элементов с разной высотой в пикселях эта итерация была представлена в .NET Framework 4.6.1, чтобы устранить ошибки, связанные с макетом иерархических данных.</span><span class="sxs-lookup"><span data-stu-id="ddb05-106">For example, it occurs when pixel-scrolling (<code>ScrollUnit=Pixel</code>) upon encountering an item with different pixel height, and when item-scrolling hierarchical data (such as a <xref:System.Windows.Controls.TreeView?displayProperty=fullName> or an <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> with grouping enabled) upon encountering an item with a different number of descendant items than its neighbors.For the case of item-scrolling and different pixel height, the iteration was introduced in .NET Framework 4.6.1 to fix bugs in the layout of hierarchical data.</span></span>  <span data-ttu-id="ddb05-107">Итерация не требуется, если данные не структурированы (без иерархии), и в этом случае .NET Framework 4.6.2 не выполняет ее.</span><span class="sxs-lookup"><span data-stu-id="ddb05-107">It is not needed if the data is flat (no hierarchy), and .NET Framework 4.6.2 does not do it in that case.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ddb05-108">Предложение</span><span class="sxs-lookup"><span data-stu-id="ddb05-108">Suggestion</span></span>

<span data-ttu-id="ddb05-109">Если итерация выполняется в .NET Framework 4.6.1, но не в более ранних выпусках, т. е. если <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> прокручивает поэлементно плоский список с элементами разной высоты в пикселях, то существует два решения:</span><span class="sxs-lookup"><span data-stu-id="ddb05-109">If the iteration occurs in .NET Framework 4.6.1 but not in earlier releases - that is, if the <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> is item- scrolling a flat list with items of different pixel height - there are two remedies:</span></span><ol><li><span data-ttu-id="ddb05-110">Установите .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="ddb05-110">Install .NET Framework 4.6.2.</span></span></li><li><span data-ttu-id="ddb05-111">Установите исправление HR 1605 для .NET Framework 4.6.1.</span><span class="sxs-lookup"><span data-stu-id="ddb05-111">Install hotfix HR 1605 for .NET Framework 4.6.1.</span></span></li></ol>

| <span data-ttu-id="ddb05-112">name</span><span class="sxs-lookup"><span data-stu-id="ddb05-112">Name</span></span>    | <span data-ttu-id="ddb05-113">Значение</span><span class="sxs-lookup"><span data-stu-id="ddb05-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ddb05-114">Область</span><span class="sxs-lookup"><span data-stu-id="ddb05-114">Scope</span></span>   |<span data-ttu-id="ddb05-115">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="ddb05-115">Minor</span></span>|
|<span data-ttu-id="ddb05-116">Version</span><span class="sxs-lookup"><span data-stu-id="ddb05-116">Version</span></span>|<span data-ttu-id="ddb05-117">4.6.1</span><span class="sxs-lookup"><span data-stu-id="ddb05-117">4.6.1</span></span>|
|<span data-ttu-id="ddb05-118">Type</span><span class="sxs-lookup"><span data-stu-id="ddb05-118">Type</span></span>|<span data-ttu-id="ddb05-119">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="ddb05-119">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="ddb05-120">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="ddb05-120">Affected APIs</span></span>

- <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Windows.Controls.VirtualizingStackPanel`

-->
