---
title: Получение и задание текущей ячейки в элементе управления DataGridView
description: Узнайте, как программным способом определить, какая ячейка активна в данный момент, путем получения и установки текущей ячейки в элементе управления Windows Forms DataGridView.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], getting current cell
- DataGridView control [Windows Forms], setting current cell
- cells [Windows Forms], getting and setting current
ms.assetid: b0e41e57-493a-4bd0-9376-a6f76723540c
ms.openlocfilehash: 1651ca9c8fa0329f9435a70ce777bce68f15ff63
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622215"
---
# <a name="how-to-get-and-set-the-current-cell-in-the-windows-forms-datagridview-control"></a>Практическое руководство. Считывание и установка значения текущей ячейки элемента управления DataGridView в Windows Forms
Для взаимодействия с <xref:System.Windows.Forms.DataGridView> часто требуется программно определить, какая ячейка активна в данный момент. Также может потребоваться изменить текущую ячейку. Эти задачи можно выполнить с помощью <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> Свойства.  
  
> [!NOTE]
> Нельзя задать текущую ячейку в строке или столбце, <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> для свойства которого задано значение `false` .  
  
 В зависимости от <xref:System.Windows.Forms.DataGridView> режима выбора элемента управления изменение текущей ячейки может изменить выбор. Дополнительные сведения см. [в разделе Режимы выделения в элементе управления Windows Forms DataGridView](selection-modes-in-the-windows-forms-datagridview-control.md).  
  
### <a name="to-get-the-current-cell-programmatically"></a>Получение текущей ячейки программным способом  
  
- Используйте <xref:System.Windows.Forms.DataGridView> свойство элемента управления <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> .  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#080)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#080)]  
  
### <a name="to-set-the-current-cell-programmatically"></a>Задание текущей ячейки программным способом  
  
- Задайте <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> свойство <xref:System.Windows.Forms.DataGridView> элемента управления. В следующем примере кода текущей ячейке присваивается значение строка 0, столбец 1.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#085)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#085)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- <xref:System.Windows.Forms.Button>элементы управления с именами `getCurrentCellButton` и `setCurrentCellButton` . В Visual C# <xref:System.Windows.Forms.Control.Click> события для каждой кнопки необходимо прикрепить к соответствующему обработчику событий в примере кода.  
  
- элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;  
  
- ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CurrentCell%2A?displayProperty=nameWithType>
- [Базовые характеристики столбцов, строк и ячеек элемента управления DataGridView в Windows Forms](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [Режимы выделения содержимого элемента управления DataGridView в Windows Forms](selection-modes-in-the-windows-forms-datagridview-control.md)
