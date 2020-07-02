---
ms.openlocfilehash: 1be68c2968d0eaa9024007bcf37abf9e44c36f1c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622150"
---
### <a name="scrolling-a-wpf-treeview-or-grouped-listbox-in-a-virtualizingstackpanel-can-cause-a-hang"></a><span data-ttu-id="c6fce-101">Прокрутка TreeView в WPF или сгруппированный ListBox в VirtualizingStackPanel может привести к зависанию</span><span class="sxs-lookup"><span data-stu-id="c6fce-101">Scrolling a WPF TreeView or grouped ListBox in a VirtualizingStackPanel can cause a hang</span></span>

#### <a name="details"></a><span data-ttu-id="c6fce-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="c6fce-102">Details</span></span>

<span data-ttu-id="c6fce-103">В версии .NET Framework 4.5 прокрутка <xref:System.Windows.Controls.TreeView?displayProperty=fullName> WPF на панели виртуализированного стека может привести к зависанию при наличии полей в области просмотра (между элементами в <xref:System.Windows.Controls.TreeView?displayProperty=fullName>, например, или в элементе ItemsPresenter).</span><span class="sxs-lookup"><span data-stu-id="c6fce-103">In the .NET Framework v4.5, scrolling a WPF <xref:System.Windows.Controls.TreeView?displayProperty=fullName> in a virtualized stack panel can cause hangs if there are margins in the viewport (between the items in the <xref:System.Windows.Controls.TreeView?displayProperty=fullName>, for example, or on an ItemsPresenter element).</span></span> <span data-ttu-id="c6fce-104">Кроме того, в некоторых случаях элементы разных размеров в представлении могут привести к нестабильности даже при отсутствии полей.</span><span class="sxs-lookup"><span data-stu-id="c6fce-104">Additionally, in some cases, different sized items in the view can cause instability even if there are no margins.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c6fce-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="c6fce-105">Suggestion</span></span>

<span data-ttu-id="c6fce-106">Этой ошибки можно избежать путем обновления до .NET Framework 4.5.1.</span><span class="sxs-lookup"><span data-stu-id="c6fce-106">This bug can be avoided by upgrading to .NET Framework 4.5.1.</span></span> <span data-ttu-id="c6fce-107">Кроме того, можно удалить поля из коллекций представлений (таких как <xref:System.Windows.Controls.TreeView?displayProperty=fullName>) на панелях виртуализированных стеков, если все содержащиеся в них элементы имеют одинаковый размер.</span><span class="sxs-lookup"><span data-stu-id="c6fce-107">Alternatively, margins can be removed from view collections (like <xref:System.Windows.Controls.TreeView?displayProperty=fullName>s) within virtualized stack panels if all contained items are the same size.</span></span>

| <span data-ttu-id="c6fce-108">name</span><span class="sxs-lookup"><span data-stu-id="c6fce-108">Name</span></span>    | <span data-ttu-id="c6fce-109">Значение</span><span class="sxs-lookup"><span data-stu-id="c6fce-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c6fce-110">Область</span><span class="sxs-lookup"><span data-stu-id="c6fce-110">Scope</span></span>   |<span data-ttu-id="c6fce-111">Значительно</span><span class="sxs-lookup"><span data-stu-id="c6fce-111">Major</span></span>|
|<span data-ttu-id="c6fce-112">Version</span><span class="sxs-lookup"><span data-stu-id="c6fce-112">Version</span></span>|<span data-ttu-id="c6fce-113">4.5</span><span class="sxs-lookup"><span data-stu-id="c6fce-113">4.5</span></span>|
|<span data-ttu-id="c6fce-114">Type</span><span class="sxs-lookup"><span data-stu-id="c6fce-114">Type</span></span>|<span data-ttu-id="c6fce-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="c6fce-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c6fce-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="c6fce-116">Affected APIs</span></span>

-<xref:System.Windows.Controls.VirtualizingStackPanel.SetIsVirtualizing(System.Windows.DependencyObject,System.Boolean)?displayProperty=nameWithType></li></ul>|
