---
ms.openlocfilehash: c78122a2fe69c78625d6cb7fa9ddf41c49c2e737
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496106"
---
### <a name="calling-datagridcommitedit-from-a-celleditending-handler-drops-focus"></a>Вызов метода DataGrid.CommitEdit из обработчика CellEditEnding удаляет фокус

#### <a name="details"></a>Подробнее

Вызов метода <xref:System.Windows.Controls.DataGrid.CommitEdit> из одного из обработчиков событий <xref:System.Windows.Controls.DataGrid?displayProperty=fullName><xref:System.Windows.Controls.DataGrid.CellEditEnding?displayProperty=fullName> приводит к потере фокуса для <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>.

#### <a name="suggestion"></a>Предложение

Это ошибка исправлена в .NET Framework 4.5.2, поэтому ее можно избежать путем обновления .NET Framework. Кроме того, ее можно избежать, явным образом повторно выбрав <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> после вызова <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=fullName>.

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.5|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=nameWithType>
- <xref:System.Windows.Controls.DataGrid.CommitEdit(System.Windows.Controls.DataGridEditingUnit,System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Controls.DataGrid.CommitEdit`
- `M:System.Windows.Controls.DataGrid.CommitEdit(System.Windows.Controls.DataGridEditingUnit,System.Boolean)`

-->
