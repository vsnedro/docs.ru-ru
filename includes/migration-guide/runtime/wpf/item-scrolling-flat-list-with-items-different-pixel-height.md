---
ms.openlocfilehash: d23d7821e19b9d7f2db13a6bfdf868a8414cf721
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496443"
---
### <a name="item-scrolling-a-flat-list-with-items-of-different-pixel-height"></a>Поэлементная прокрутка плоского списка с элементами, имеющими различную высоту в пикселях

#### <a name="details"></a>Подробнее

Когда <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> отображает коллекцию с помощью виртуализации (<code>IsVirtualizing=true</code>) и прокрутки элемента (<code>ScrollUnit=Item</code>) и когда элемент управления прокручивается для отображения элемента, высота которого в пикселях отличается о высоты соседних элементов, <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName> выполняет итерацию по всем элементам в коллекции. Пользовательский интерфейс не отвечает на запросы в ходе этой итерации; если коллекция большая, это может восприниматься как зависание. Такая итерация происходит и в других ситуациях, даже в более ранних выпусках .NET Framework. Например, она происходит при пиксельной прокрутке (<code>ScrollUnit=Pixel</code>) при обнаружении элемента другой высоты в пикселях, а также при поэлементной прокрутке иерархических данных (например, в элементе управления <xref:System.Windows.Controls.TreeView?displayProperty=fullName> или <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> с включенным группированием) при обнаружении элемента, число подчиненных элементов которого отличается от соседних элементов. Для поэлементной прокрутки элементов с разной высотой в пикселях эта итерация была представлена в .NET Framework 4.6.1, чтобы устранить ошибки, связанные с макетом иерархических данных.  Итерация не требуется, если данные не структурированы (без иерархии), и в этом случае .NET Framework 4.6.2 не выполняет ее.

#### <a name="suggestion"></a>Предложение

Если итерация выполняется в .NET Framework 4.6.1, но не в более ранних выпусках, т. е. если <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> прокручивает поэлементно плоский список с элементами разной высоты в пикселях, то существует два решения:<ol><li>Установите .NET Framework 4.6.2.</li><li>Установите исправление HR 1605 для .NET Framework 4.6.1.</li></ol>

| name    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.6.1|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Windows.Controls.VirtualizingStackPanel`

-->
