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
# <a name="when-to-use-a-windows-forms-combobox-instead-of-a-listbox"></a><span data-ttu-id="53898-103">Применение элемента управления ComboBox вместо элемента управления ListBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="53898-103">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>
<span data-ttu-id="53898-104"><xref:System.Windows.Forms.ComboBox> <xref:System.Windows.Forms.ListBox> Элементы управления и имеют похожие поведения, и в некоторых случаях они могут быть взаимозаменяемыми.</span><span class="sxs-lookup"><span data-stu-id="53898-104">The <xref:System.Windows.Forms.ComboBox> and the <xref:System.Windows.Forms.ListBox> controls have similar behaviors, and in some cases may be interchangeable.</span></span> <span data-ttu-id="53898-105">Однако бывают ситуации, когда один из них более подходит для задачи.</span><span class="sxs-lookup"><span data-stu-id="53898-105">There are times, however, when one or the other is more appropriate to a task.</span></span>  
  
 <span data-ttu-id="53898-106">Как правило, поле со списком подходит, если имеется список предлагаемых вариантов, и если необходимо ограничить входные данные на содержимое списка, то поле со списком подходит.</span><span class="sxs-lookup"><span data-stu-id="53898-106">Generally, a combo box is appropriate when there is a list of suggested choices, and a list box is appropriate when you want to limit input to what is on the list.</span></span> <span data-ttu-id="53898-107">Поле со списком содержит текстовое поле, поэтому варианты, отсутствующие в списке, можно вводить в.</span><span class="sxs-lookup"><span data-stu-id="53898-107">A combo box contains a text box field, so choices not on the list can be typed in.</span></span> <span data-ttu-id="53898-108">Исключением является то, что <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> свойство имеет значение <xref:System.Windows.Forms.ComboBoxStyle.DropDownList> .</span><span class="sxs-lookup"><span data-stu-id="53898-108">The exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>.</span></span> <span data-ttu-id="53898-109">В этом случае элемент управления выберет элемент, если ввести его первую букву.</span><span class="sxs-lookup"><span data-stu-id="53898-109">In that case, the control will select an item if you type its first letter.</span></span>  
  
 <span data-ttu-id="53898-110">Кроме того, поля со списком сохраняют место в форме.</span><span class="sxs-lookup"><span data-stu-id="53898-110">In addition, combo boxes save space on a form.</span></span> <span data-ttu-id="53898-111">Поскольку полный список не отображается до тех пор, пока пользователь не щелкнет стрелку вниз, поле со списком можно легко разместить в маленьком пространстве, в котором поле со списком не умещается.</span><span class="sxs-lookup"><span data-stu-id="53898-111">Because the full list is not displayed until the user clicks the down arrow, a combo box can easily fit in a small space where a list box would not fit.</span></span> <span data-ttu-id="53898-112">Исключением является то, что <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> свойство имеет значение <xref:System.Windows.Forms.ComboBoxStyle.Simple> : отображается полный список, и поле со списком занимает больше места, чем поле со списком.</span><span class="sxs-lookup"><span data-stu-id="53898-112">An exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.Simple>: the full list is displayed, and the combo box takes up more room than a list box would.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53898-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="53898-113">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [<span data-ttu-id="53898-114">Практическое руководство. Добавление и удаление элементов, отображаемых в элементах управления ComboBox, ListBox и CheckedListBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="53898-114">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](add-and-remove-items-from-a-wf-combobox.md)
- [<span data-ttu-id="53898-115">Практическое руководство. Сортировка содержимого элемента управления ComboBox, ListBox или CheckedListBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="53898-115">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [<span data-ttu-id="53898-116">Создание списка для выбора элементов в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="53898-116">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
