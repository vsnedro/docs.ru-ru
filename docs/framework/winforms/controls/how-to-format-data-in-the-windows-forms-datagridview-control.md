---
title: Форматирование данных в элементе управления DataGridView
description: Узнайте, как форматировать значения ячеек с помощью свойства DefaultCellStyle элемента управления DataGridView Windows Forms и конкретных столбцов в элементе управления.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- data [Windows Forms], formatting in DataGridView control
- data grids [Windows Forms], enabling wordwrap
- currency values [Windows Forms], formatting in data grids
- data grids [Windows Forms], currency values
- data grids [Windows Forms], formatting data
- data grids [Windows Forms], text alignment
- data grids [Windows Forms], date values
- cells [Windows Forms], text alignment
ms.assetid: 8c33543c-9c08-4636-a65a-fdf714a529b7
ms.openlocfilehash: d6105c1d1120876f854332e7a10106cc1caf6276
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622813"
---
# <a name="how-to-format-data-in-the-windows-forms-datagridview-control"></a>Практическое руководство. Форматирование данных элемента управления DataGridView в Windows Forms
Следующие процедуры демонстрируют базовое форматирование значений ячеек с помощью <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> свойства <xref:System.Windows.Forms.DataGridView> элемента управления и конкретных столбцов в элементе управления. Дополнительные сведения о расширенном форматировании данных см. в разделе [инструкции. Настройка форматирования данных в элементе управления Windows Forms DataGridView](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
### <a name="to-format-currency-and-date-values"></a>Форматирование значений денежной единицы и даты  
  
- Задайте свойство <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> элемента <xref:System.Windows.Forms.DataGridViewCellStyle>. В следующем примере кода задается формат для конкретных столбцов с помощью <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> свойства столбцов. Значения в `UnitPrice` столбце отображаются в текущем формате валюты, зависящем от языка и региональных параметров, с отрицательными значениями, заключенными в круглые скобки. Значения в `ShipDate` столбце отображаются в кратком формате даты, соответствующем языку и региональным параметрам. Дополнительные сведения о <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> значениях см. в разделе [Типы форматирования](../../../standard/base-types/formatting-types.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#071](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#071)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#071](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#071)]  
  
### <a name="to-customize-the-display-of-null-database-values"></a>Настройка вывода значений NULL для базы данных  
  
- Задайте свойство <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> элемента <xref:System.Windows.Forms.DataGridViewCellStyle>. В следующем примере кода свойство используется <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> для вывода "без записи" во всех ячейках, содержащих значения, равные <xref:System.DBNull.Value?displayProperty=nameWithType> .  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#073](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#073)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#073](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#073)]  
  
### <a name="to-enable-wordwrap-in-text-based-cells"></a>Включение переноса слов в текстовых ячейках  
  
- Установите <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> свойство объекта в <xref:System.Windows.Forms.DataGridViewCellStyle> одно из <xref:System.Windows.Forms.DataGridViewTriState> значений перечисления. В следующем примере кода свойство используется <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> для задания режима переноса для всего элемента управления.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#074](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#074)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#074](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#074)]  
  
### <a name="to-specify-the-text-alignment-of-datagridview-cells"></a>Указание выравнивания текста для ячеек DataGridView  
  
- Установите <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A> свойство объекта в <xref:System.Windows.Forms.DataGridViewCellStyle> одно из <xref:System.Windows.Forms.DataGridViewContentAlignment> значений перечисления. В следующем примере кода устанавливается выравнивание для определенного столбца с помощью <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> Свойства столбца.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#072](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#072)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#072](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#072)]  
  
## <a name="example"></a>Пример  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#070](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#070)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#070](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#070)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этих примеров требуются:  
  
- <xref:System.Windows.Forms.DataGridView>Элемент управления с именем, `dataGridView1` содержащий столбец с именем, `UnitPrice` столбец с именем `ShipDate` и столбец с именем `CustomerName` .  
  
- ссылки на сборки <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Для обеспечения максимальной масштабируемости необходимо совместно использовать <xref:System.Windows.Forms.DataGridViewCellStyle> объекты в нескольких строках, столбцах или ячейках, использующих одни и те же стили, а не задавать свойства стиля для каждого элемента отдельно. Подробнее см. в разделе [Масштабирование элемента управления DataGridView в Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [Базовое форматирование и оформление элемента управления DataGridView в Windows Forms](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Стили ячеек элемента управления DataGridView в Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Форматирование данных в элементе управления DataGridView в Windows Forms](data-formatting-in-the-windows-forms-datagridview-control.md)
- [Практическое руководство. Настройка форматирования данных элемента управления DataGridView в Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
- [Типы форматирования](../../../standard/base-types/formatting-types.md)
