---
ms.openlocfilehash: 961ca545560a53fc2c1d52722b68ae460de66877
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497516"
---
### <a name="datagridcellspanelbringindexintoview-throws-argumentoutofrangeexception"></a>DataGridCellsPanel.BringIndexIntoView создает исключение ArgumentOutOfRangeException

#### <a name="details"></a>Подробнее

Метод <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> будет выполняться асинхронно, если виртуализация столбцов включена, но ширина столбцов еще не определена.  Если столбцы удаляются до завершения асинхронной операции, может возникнуть исключение <xref:System.ArgumentOutOfRangeException?displayProperty=fullName>.

#### <a name="suggestion"></a>Предложение

Выполните одно из следующих действий:<ol><li>Выполните обновление до .NET Framework 4.7.</li><li>Установите последнее служебное исправление для .NET Framework 4.6.2.</li><li>Избегать удаления столбцов до завершения асинхронного ответа на метод <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)>.</li></ol>

| Имя    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.6.2|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)?displayProperty=nameWithType>
- <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object,System.Windows.Controls.DataGridColumn)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)`
- `M:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object,System.Windows.Controls.DataGridColumn)`

-->
