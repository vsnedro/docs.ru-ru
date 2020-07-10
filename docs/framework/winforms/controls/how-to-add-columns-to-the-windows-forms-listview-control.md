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
# <a name="how-to-add-columns-to-the-windows-forms-listview-control"></a><span data-ttu-id="8970a-103">Практическое руководство. Добавление столбцов в элемент управления ListView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8970a-103">How to: Add Columns to the Windows Forms ListView Control</span></span>
<span data-ttu-id="8970a-104">В представлении Details <xref:System.Windows.Forms.ListView> элемент управления может отображать несколько столбцов для каждого элемента списка.</span><span class="sxs-lookup"><span data-stu-id="8970a-104">In the Details view, the <xref:System.Windows.Forms.ListView> control can display multiple columns for each list item.</span></span> <span data-ttu-id="8970a-105">Столбцы можно использовать для вывода нескольких типов сведений о каждом элементе списка.</span><span class="sxs-lookup"><span data-stu-id="8970a-105">You can use the columns to display to the user several types of information about each list item.</span></span> <span data-ttu-id="8970a-106">Например, список файлов может отображать имя файла, тип файла, размер и дату последнего изменения файла.</span><span class="sxs-lookup"><span data-stu-id="8970a-106">For example, a list of files could display the file name, file type, size, and date the file was last modified.</span></span> <span data-ttu-id="8970a-107">Сведения о заполнении столбцов после их создания см. в разделе [инструкции. Отображение подэлементов в столбцах с помощью элемента управления ListView Windows Forms](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).</span><span class="sxs-lookup"><span data-stu-id="8970a-107">For information about populating the columns after they are created, see [How to: Display Subitems in Columns with the Windows Forms ListView Control](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).</span></span>  
  
### <a name="to-add-columns-programmatically"></a><span data-ttu-id="8970a-108">Добавление столбцов программным способом</span><span class="sxs-lookup"><span data-stu-id="8970a-108">To add columns programmatically</span></span>  
  
1. <span data-ttu-id="8970a-109">Присвойте свойству элемента управления значение <xref:System.Windows.Forms.ListView.View%2A> <xref:System.Windows.Forms.View.Details> .</span><span class="sxs-lookup"><span data-stu-id="8970a-109">Set the control's <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>  
  
2. <span data-ttu-id="8970a-110">Используйте <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> метод свойства представления списка <xref:System.Windows.Forms.ListView.Columns%2A> .</span><span class="sxs-lookup"><span data-stu-id="8970a-110">Use the <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> method of the list view's <xref:System.Windows.Forms.ListView.Columns%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="8970a-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8970a-111">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- [<span data-ttu-id="8970a-112">Элемент управления ListView</span><span class="sxs-lookup"><span data-stu-id="8970a-112">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="8970a-113">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="8970a-113">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
