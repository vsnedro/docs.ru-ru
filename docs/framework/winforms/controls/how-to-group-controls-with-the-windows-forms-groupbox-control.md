---
title: Группирование элементов управления с помощью элемента управления GroupBox
description: Узнайте, как группировать элементы управления с помощью элемента управления Windows Forms GroupBox, чтобы можно было создать визуальное группирование связанных элементов.
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], grouping
- GroupBox control [Windows Forms], grouping controls
- Windows Forms controls, grouping
ms.assetid: 0bda316d-bd2a-43aa-ac73-342453303169
ms.openlocfilehash: f84c495a18f4ae5e04367f024a1e2849f1ed59f9
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618068"
---
# <a name="how-to-group-controls-with-the-windows-forms-groupbox-control"></a>Практическое руководство. Группировка элементов управления с помощью элемента управления GroupBox в формах Windows Forms
<xref:System.Windows.Forms.GroupBox>Элементы управления Windows Forms используются для группирования других элементов управления. Существуют три причины группировки элементов управления.  
  
- Для создания визуального группирования связанных элементов формы для простого пользовательского интерфейса.  
  
- Для создания программного группирования (например, для переключателей).  
  
- Для перемещения элементов управления как единицы во время разработки.  
  
### <a name="to-create-a-group-of-controls"></a>Создание группы элементов управления  
  
1. Рисование <xref:System.Windows.Forms.GroupBox> элемента управления в форме.  
  
2. Добавьте в поле группы другие элементы управления, нарисовав их внутри поля группы.  
  
     При наличии существующих элементов управления, которые необходимо заключать в поле группы, можно выбрать все элементы управления, вырезать их в буфер обмена, выбрать <xref:System.Windows.Forms.GroupBox> элемент управления и вставить их в поле Группа. Их также можно перетащить в поле Группа.  
  
3. Задайте <xref:System.Windows.Forms.GroupBox.Text%2A> для свойства поля Группа соответствующий заголовок.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.GroupBox>
- [Элемент управления GroupBox](groupbox-control-windows-forms.md)
