---
ms.openlocfilehash: 972601874d80d82ebae8b79779acfed82e5570cb
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496563"
---
### <a name="calling-itemsrefresh-on-a-wpf-listbox-listview-or-datagrid-with-items-selected-can-cause-duplicate-items-to-appear-in-the-element"></a>Вызов Items.Refresh для ListBox, ListView или DataGrid в WPF с выбранным элементом может привести к появлению в элементе повторяющихся записей

#### <a name="details"></a>Подробнее

В .NET Framework 4.5 вызов ListBox.Items.Refresh из кода, когда элементы выбраны в <xref:System.Windows.Controls.ListBox?displayProperty=fullName>, может привести к дублированию выбранных элементов в списке. Аналогичная проблема возникает с <xref:System.Windows.Controls.ListView?displayProperty=fullName> и <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>. Эта проблема устранена в EntityFramework 4.6.

#### <a name="suggestion"></a>Предложение

Эту проблему можно решить с помощью программных средств, отменив выбор элементов до вызова метода <xref:System.Windows.Data.CollectionView.Refresh?displayProperty=fullName> и затем повторно выбрав их после завершения вызова. Кроме того, эта проблема была устранена в .NET Framework 4.6 и может быть решена путем обновления до этой версии платформы .NET Framework.

| name    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.5|
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Windows.Data.CollectionView.Refresh?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Data.CollectionView.Refresh`

-->
