---
ms.openlocfilehash: 196b6a13d32c7767b858d6d68ca775eb49324805
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496294"
---
### <a name="listboxitem-isselected-binding-issue-with-observablecollectionlttgtmove"></a>Проблема с привязкой ListBoxItem IsSelected к ObservableCollection&lt;T&gt;.Move

#### <a name="details"></a>Подробнее

Вызов <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> или <xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)> для коллекции, привязанной к <xref:System.Windows.Controls.ListBox?displayProperty=fullName> с выделенными элементами, может привести к последующему выделению или отмене выделения элементов <xref:System.Windows.Controls.ListBox?displayProperty=fullName>.

#### <a name="suggestion"></a>Предложение

Чтобы обойти эту проблему, выполните вызов <xref:System.Collections.ObjectModel.Collection%601.Remove(%600)?displayProperty=fullName> и <xref:System.Collections.ObjectModel.Collection%601.Insert(System.Int32,%600)?displayProperty=fullName> вместо <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)>. Кроме того, эта проблема была устранена в .NET Framework 4.6 и может быть решена путем обновления до этой версии платформы .NET Framework.

| name    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.5|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)?displayProperty=nameWithType>

<!--

#### Affected APIs

- ``M:System.Collections.ObjectModel.ObservableCollection`1.Move(System.Int32,System.Int32)``
- ``M:System.Collections.ObjectModel.ObservableCollection`1.MoveItem(System.Int32,System.Int32)``

-->
