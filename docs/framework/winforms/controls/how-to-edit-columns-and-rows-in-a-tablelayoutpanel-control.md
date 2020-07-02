---
title: Практическое руководство. Изменение столбцов и строк в элементе управления TableLayoutPanel
description: Узнайте, как использовать диалоговое окно Стили столбцов и строк для изменения строк и столбцов элементов управления Windows Forms.
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor
helpviewer_keywords:
- columns [Windows Forms], editing
- TableLayoutPanel control [Windows Forms], editing
- rows [Windows Forms], editing
ms.assetid: c367ed43-40dc-49eb-9e0f-ba70e83dfec0
ms.openlocfilehash: cfd2ca4be5d5a2658a9a129d911f1dba9670ccfd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619355"
---
# <a name="how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control"></a>Практическое руководство. Изменение столбцов и строк в элементе управления TableLayoutPanel

<xref:System.Windows.Forms.TableLayoutPanel>Для изменения строк и столбцов элементов управления можно использовать редактор коллекций элемента управления, называемый диалоговым окном **стили столбцов и строк** .

> [!NOTE]
> Если требуется, чтобы элемент управления занимал несколько строк или столбцов, установите `RowSpan` Свойства и `ColumnSpan` в элементе управления. Для получения дополнительной информации см. [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).
>
> Если необходимо выстроить элемент управления в пределах ячейки или нужно растянуть элемент управления внутри ячейки, используйте свойство элемента управления <xref:System.Windows.Forms.Control.Anchor%2A> . Для получения дополнительной информации см. [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).

## <a name="to-edit-rows-and-columns"></a>Изменение строк и столбцов

1. Перетащите элемент управления <xref:System.Windows.Forms.TableLayoutPanel> из **панели элементов** в свою форму.

2. Щелкните <xref:System.Windows.Forms.TableLayoutPanel> глиф действий конструктора элементов управления ( ![ маленькая черная стрелка ](./media/designer-actions-glyph.gif) ) и выберите **изменить строки и столбцы** , чтобы открыть диалоговое окно **стили столбцов и строк** . Можно также щелкнуть правой кнопкой мыши <xref:System.Windows.Forms.TableLayoutPanel> элемент управления и выбрать пункт **изменить строки и столбцы** из контекстного меню.

3. Чтобы добавить или удалить столбцы, выберите **столбцы** из раскрывающегося списка **тип элемента** .

4. Чтобы добавить или удалить строки, выберите **строки** из раскрывающегося списка **тип элемента** .

5. Нажмите кнопку **Добавить** , чтобы добавить строку или столбец в конец списка **элементов** .

6. Нажмите кнопку **Вставить** , чтобы добавить строку или столбец перед текущим выбранным элементом в списке.

7. При добавлении строки или столбца выберите **Тип размера** для новой строки или столбца. Для получения дополнительной информации см. <xref:System.Windows.Forms.SizeType>.

8. Чтобы удалить строку или столбец, нажмите кнопку **Удалить** , чтобы удалить текущий выбранный элемент в списке **элементов** .

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.SizeType>
- [Элемент управления TableLayoutPanel](tablelayoutpanel-control-windows-forms.md)
