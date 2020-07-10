---
title: ComboBox и ListBox
description: Сведения об использовании Windows Forms ComboBox и Windows Forms ListBox, а также о том, как сообщить, когда одно или другое подходящее для задачи.
ms.date: 03/30/2017
helpviewer_keywords:
- ListBox control [Windows Forms], adding and removing items
- ListBox control [Windows Forms], vs. ComboBox
- bound controls [Windows Forms], combo boxes
- Windows Forms controls, data binding
- ComboBox control [Windows Forms], compared to ListBox
- combo boxes [Windows Forms], compared to list boxes
- ListBox control [Windows Forms], accessing items
- ListCount property
ms.assetid: 7bcaea58-1cfa-46db-9baf-b75a69d8f9ec
ms.openlocfilehash: ca6ad6bec2dbc30128ea09808af2806687b17a8c
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174423"
---
# <a name="when-to-use-a-windows-forms-combobox-instead-of-a-listbox"></a>Применение элемента управления ComboBox вместо элемента управления ListBox в Windows Forms
<xref:System.Windows.Forms.ComboBox> <xref:System.Windows.Forms.ListBox> Элементы управления и имеют похожие поведения, и в некоторых случаях они могут быть взаимозаменяемыми. Однако бывают ситуации, когда один из них более подходит для задачи.  
  
 Как правило, поле со списком подходит, если имеется список предлагаемых вариантов, и если необходимо ограничить входные данные на содержимое списка, то поле со списком подходит. Поле со списком содержит текстовое поле, поэтому варианты, отсутствующие в списке, можно вводить в. Исключением является то, что <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> свойство имеет значение <xref:System.Windows.Forms.ComboBoxStyle.DropDownList> . В этом случае элемент управления выберет элемент, если ввести его первую букву.  
  
 Кроме того, поля со списком сохраняют место в форме. Поскольку полный список не отображается до тех пор, пока пользователь не щелкнет стрелку вниз, поле со списком можно легко разместить в маленьком пространстве, в котором поле со списком не умещается. Исключением является то, что <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> свойство имеет значение <xref:System.Windows.Forms.ComboBoxStyle.Simple> : отображается полный список, и поле со списком занимает больше места, чем поле со списком.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [Практическое руководство. Добавление и удаление элементов, отображаемых в элементах управления ComboBox, ListBox и CheckedListBox в Windows Forms](add-and-remove-items-from-a-wf-combobox.md)
- [Практическое руководство. Сортировка содержимого элемента управления ComboBox, ListBox или CheckedListBox в Windows Forms](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [Создание списка для выбора элементов в Windows Forms](windows-forms-controls-used-to-list-options.md)
