---
title: Добавление столбцов в элемент управления ListView
description: Узнайте, как добавить столбцы в Windows Forms элемент управления ListView для отображения нескольких типов сведений о каждом элементе списка.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
- list views [Windows Forms], adding columns
ms.assetid: 79174274-12ee-4a5d-80db-6ec02976d010
ms.openlocfilehash: 7ca4e86ca3a9679876f2525c49596534f175096a
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174566"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control"></a>Практическое руководство. Добавление столбцов в элемент управления ListView в Windows Forms
В представлении Details <xref:System.Windows.Forms.ListView> элемент управления может отображать несколько столбцов для каждого элемента списка. Столбцы можно использовать для вывода нескольких типов сведений о каждом элементе списка. Например, список файлов может отображать имя файла, тип файла, размер и дату последнего изменения файла. Сведения о заполнении столбцов после их создания см. в разделе [инструкции. Отображение подэлементов в столбцах с помощью элемента управления ListView Windows Forms](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).  
  
### <a name="to-add-columns-programmatically"></a>Добавление столбцов программным способом  
  
1. Присвойте свойству элемента управления значение <xref:System.Windows.Forms.ListView.View%2A> <xref:System.Windows.Forms.View.Details> .  
  
2. Используйте <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> метод свойства представления списка <xref:System.Windows.Forms.ListView.Columns%2A> .  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.ListView>
- [Элемент управления ListView](listview-control-windows-forms.md)
- [Общие сведения об элементе управления ListView](listview-control-overview-windows-forms.md)
