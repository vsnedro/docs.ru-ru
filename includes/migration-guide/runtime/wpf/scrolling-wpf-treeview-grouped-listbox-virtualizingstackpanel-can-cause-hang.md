---
ms.openlocfilehash: 31ada197db36be192317e32a37a353d375d9cc65
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497015"
---
### <a name="scrolling-a-wpf-treeview-or-grouped-listbox-in-a-virtualizingstackpanel-can-cause-a-hang"></a><span data-ttu-id="840ce-101">Прокрутка TreeView в WPF или сгруппированный ListBox в VirtualizingStackPanel может привести к зависанию</span><span class="sxs-lookup"><span data-stu-id="840ce-101">Scrolling a WPF TreeView or grouped ListBox in a VirtualizingStackPanel can cause a hang</span></span>

#### <a name="details"></a><span data-ttu-id="840ce-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="840ce-102">Details</span></span>

<span data-ttu-id="840ce-103">В версии .NET Framework 4.5 прокрутка <xref:System.Windows.Controls.TreeView?displayProperty=fullName> WPF на панели виртуализированного стека может привести к зависанию при наличии полей в области просмотра (между элементами в <xref:System.Windows.Controls.TreeView?displayProperty=fullName>, например, или в элементе ItemsPresenter).</span><span class="sxs-lookup"><span data-stu-id="840ce-103">In the .NET Framework v4.5, scrolling a WPF <xref:System.Windows.Controls.TreeView?displayProperty=fullName> in a virtualized stack panel can cause hangs if there are margins in the viewport (between the items in the <xref:System.Windows.Controls.TreeView?displayProperty=fullName>, for example, or on an ItemsPresenter element).</span></span> <span data-ttu-id="840ce-104">Кроме того, в некоторых случаях элементы разных размеров в представлении могут привести к нестабильности даже при отсутствии полей.</span><span class="sxs-lookup"><span data-stu-id="840ce-104">Additionally, in some cases, different sized items in the view can cause instability even if there are no margins.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="840ce-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="840ce-105">Suggestion</span></span>

<span data-ttu-id="840ce-106">Этой ошибки можно избежать путем обновления до .NET Framework 4.5.1.</span><span class="sxs-lookup"><span data-stu-id="840ce-106">This bug can be avoided by upgrading to .NET Framework 4.5.1.</span></span> <span data-ttu-id="840ce-107">Кроме того, можно удалить поля из коллекций представлений (таких как <xref:System.Windows.Controls.TreeView?displayProperty=fullName>) на панелях виртуализированных стеков, если все содержащиеся в них элементы имеют одинаковый размер.</span><span class="sxs-lookup"><span data-stu-id="840ce-107">Alternatively, margins can be removed from view collections (like <xref:System.Windows.Controls.TreeView?displayProperty=fullName>s) within virtualized stack panels if all contained items are the same size.</span></span>

| <span data-ttu-id="840ce-108">name</span><span class="sxs-lookup"><span data-stu-id="840ce-108">Name</span></span>    | <span data-ttu-id="840ce-109">Значение</span><span class="sxs-lookup"><span data-stu-id="840ce-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="840ce-110">Область</span><span class="sxs-lookup"><span data-stu-id="840ce-110">Scope</span></span>   |<span data-ttu-id="840ce-111">Значительно</span><span class="sxs-lookup"><span data-stu-id="840ce-111">Major</span></span>|
|<span data-ttu-id="840ce-112">Version</span><span class="sxs-lookup"><span data-stu-id="840ce-112">Version</span></span>|<span data-ttu-id="840ce-113">4.5</span><span class="sxs-lookup"><span data-stu-id="840ce-113">4.5</span></span>|
|<span data-ttu-id="840ce-114">Type</span><span class="sxs-lookup"><span data-stu-id="840ce-114">Type</span></span>|<span data-ttu-id="840ce-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="840ce-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="840ce-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="840ce-116">Affected APIs</span></span>

- <xref:System.Windows.Controls.VirtualizingStackPanel.SetIsVirtualizing(System.Windows.DependencyObject,System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Controls.VirtualizingStackPanel.SetIsVirtualizing(System.Windows.DependencyObject,System.Boolean)`

-->
