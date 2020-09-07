---
ms.openlocfilehash: 25ce391f917bd270d4d9a75f608e4a8ec763d15c
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497691"
---
### <a name="itemsclear-does-not-remove-duplicates-from-selecteditems"></a><span data-ttu-id="ad98a-101">Items.Clear не удаляет дубликаты из SelectedItems</span><span class="sxs-lookup"><span data-stu-id="ad98a-101">Items.Clear does not remove duplicates from SelectedItems</span></span>

#### <a name="details"></a><span data-ttu-id="ad98a-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="ad98a-102">Details</span></span>

<span data-ttu-id="ad98a-103">Если в элементе Selector, поддерживающем выбор нескольких элементов, в коллекции <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> присутствуют дубликаты, один и тот же элемент присутствует несколько раз.</span><span class="sxs-lookup"><span data-stu-id="ad98a-103">Suppose a Selector (with multiple selection enabled) has duplicates in its <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> collection - the same item appears more than once.</span></span>  <span data-ttu-id="ad98a-104">Удаление этих элементов из источника данных (например, путем вызова Items.Clear) не приведет к их удалению из коллекции <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName>. Будет удален только первый экземпляр.</span><span class="sxs-lookup"><span data-stu-id="ad98a-104">Removing those items from the data source (e.g. by calling Items.Clear) fails to remove them from <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName>; only the first instance is removed.</span></span> <span data-ttu-id="ad98a-105">Более того, последующее использование коллекции <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName>, например вызов SelectedItems.Clear(), может вызвать проблемы, например исключение <xref:System.ArgumentException?displayProperty=fullName>, так как коллекция <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> содержит элементы, которые отсутствуют в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="ad98a-105">Furthermore, subsequent use of <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> (e.g. SelectedItems.Clear()) can encounter problems such as <xref:System.ArgumentException?displayProperty=fullName>, because <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> contains items that are no longer in the data source.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ad98a-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="ad98a-106">Suggestion</span></span>

<span data-ttu-id="ad98a-107">По возможности выполните обновление до .NET 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="ad98a-107">Upgrade if possible to .NET Framework 4.6.2.</span></span>

| <span data-ttu-id="ad98a-108">name</span><span class="sxs-lookup"><span data-stu-id="ad98a-108">Name</span></span>    | <span data-ttu-id="ad98a-109">Значение</span><span class="sxs-lookup"><span data-stu-id="ad98a-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ad98a-110">Область</span><span class="sxs-lookup"><span data-stu-id="ad98a-110">Scope</span></span>   |<span data-ttu-id="ad98a-111">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="ad98a-111">Minor</span></span>|
|<span data-ttu-id="ad98a-112">Version</span><span class="sxs-lookup"><span data-stu-id="ad98a-112">Version</span></span>|<span data-ttu-id="ad98a-113">4.5</span><span class="sxs-lookup"><span data-stu-id="ad98a-113">4.5</span></span>|
|<span data-ttu-id="ad98a-114">Type</span><span class="sxs-lookup"><span data-stu-id="ad98a-114">Type</span></span>|<span data-ttu-id="ad98a-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="ad98a-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="ad98a-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="ad98a-116">Affected APIs</span></span>

- <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Windows.Controls.Primitives.MultiSelector.SelectedItems`

-->
