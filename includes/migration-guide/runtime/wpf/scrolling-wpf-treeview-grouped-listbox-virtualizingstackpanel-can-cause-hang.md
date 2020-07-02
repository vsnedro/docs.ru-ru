---
ms.openlocfilehash: 1be68c2968d0eaa9024007bcf37abf9e44c36f1c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622150"
---
### <a name="scrolling-a-wpf-treeview-or-grouped-listbox-in-a-virtualizingstackpanel-can-cause-a-hang"></a>Прокрутка TreeView в WPF или сгруппированный ListBox в VirtualizingStackPanel может привести к зависанию

#### <a name="details"></a>Подробнее

В версии .NET Framework 4.5 прокрутка <xref:System.Windows.Controls.TreeView?displayProperty=fullName> WPF на панели виртуализированного стека может привести к зависанию при наличии полей в области просмотра (между элементами в <xref:System.Windows.Controls.TreeView?displayProperty=fullName>, например, или в элементе ItemsPresenter). Кроме того, в некоторых случаях элементы разных размеров в представлении могут привести к нестабильности даже при отсутствии полей.

#### <a name="suggestion"></a>Предложение

Этой ошибки можно избежать путем обновления до .NET Framework 4.5.1. Кроме того, можно удалить поля из коллекций представлений (таких как <xref:System.Windows.Controls.TreeView?displayProperty=fullName>) на панелях виртуализированных стеков, если все содержащиеся в них элементы имеют одинаковый размер.

| name    | Значение       |
|:--------|:------------|
| Область   |Значительно|
|Version|4.5|
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

-<xref:System.Windows.Controls.VirtualizingStackPanel.SetIsVirtualizing(System.Windows.DependencyObject,System.Boolean)?displayProperty=nameWithType></li></ul>|
