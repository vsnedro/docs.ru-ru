---
ms.openlocfilehash: d78d083b16ac034c6c393dbc0f6094ee4c6c63c0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622380"
---
### <a name="datagridcellspanelbringindexintoview-throws-argumentoutofrangeexception"></a>DataGridCellsPanel.BringIndexIntoView создает исключение ArgumentOutOfRangeException

#### <a name="details"></a>Подробнее

Метод <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> будет выполняться асинхронно, если виртуализация столбцов включена, но ширина столбцов еще не определена.  Если столбцы удаляются до завершения асинхронной операции, может возникнуть исключение <xref:System.ArgumentOutOfRangeException?displayProperty=fullName>.

#### <a name="suggestion"></a>Предложение

Выполните одно из следующих действий:<ol><li>Выполните обновление до .NET Framework 4.7.</li><li>Установите последнее служебное исправление для .NET Framework 4.6.2.</li><li>Избегать удаления столбцов до завершения асинхронного ответа на метод <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)>.</li></ol>

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.6.2|
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

-<xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object,System.Windows.Controls.DataGridColumn)?displayProperty=nameWithType></li></ul>|
