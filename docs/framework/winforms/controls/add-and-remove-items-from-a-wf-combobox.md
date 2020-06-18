---
title: Добавление и удаление элементов из элемента управления ComboBox, ListBox или CheckedListBox
ms.date: 03/30/2017
description: Узнайте, как добавлять и удалять элементы управления ComboBox, ListBox и CheckedListBox Windows Forms просто и без привязки данных.
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- combo boxes [Windows Forms], adding items
- list boxes [Windows Forms], removing items
- ComboBox control [Windows Forms], adding and removing items
- ListBox control [Windows Forms], adding and removing items
- list boxes [Windows Forms], adding items
- combo boxes [Windows Forms], removing items
- CheckedListBox control [Windows Forms], adding and removing items
ms.assetid: 7224c8d2-4118-443e-ae1e-d7c17d1e69ee
ms.openlocfilehash: f3701257bbe410bf03c4c21700705e87b581bf2e
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904446"
---
# <a name="how-to-add-and-remove-items-from-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="8cfd8-103">Практическое руководство. Добавление и удаление элементов, отображаемых в элементах управления ComboBox, ListBox и CheckedListBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8cfd8-103">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="8cfd8-104">Элементы могут быть добавлены в Windows Forms поле со списком, списком или списком флажков различными способами, поскольку эти элементы управления могут быть привязаны к различным источникам данных.</span><span class="sxs-lookup"><span data-stu-id="8cfd8-104">Items can be added to a Windows Forms combo box, list box, or checked list box in a variety of ways, because these controls can be bound to a variety of data sources.</span></span> <span data-ttu-id="8cfd8-105">Однако в этом разделе демонстрируется простейший метод и не требуется привязка данных.</span><span class="sxs-lookup"><span data-stu-id="8cfd8-105">However, this topic demonstrates the simplest method and requires no data binding.</span></span> <span data-ttu-id="8cfd8-106">Отображаемые элементы обычно являются строками. Однако можно использовать любой объект.</span><span class="sxs-lookup"><span data-stu-id="8cfd8-106">The items displayed are usually strings; however, any object can be used.</span></span> <span data-ttu-id="8cfd8-107">Текст, отображаемый в элементе управления, является значением, возвращаемым `ToString` методом объекта.</span><span class="sxs-lookup"><span data-stu-id="8cfd8-107">The text that is displayed in the control is the value returned by the object's `ToString` method.</span></span>  
  
### <a name="to-add-items"></a><span data-ttu-id="8cfd8-108">Добавление элементов</span><span class="sxs-lookup"><span data-stu-id="8cfd8-108">To add items</span></span>  
  
1. <span data-ttu-id="8cfd8-109">Добавьте строку или объект в список с помощью `Add` метода `ObjectCollection` класса.</span><span class="sxs-lookup"><span data-stu-id="8cfd8-109">Add the string or object to the list by using the `Add` method of the `ObjectCollection` class.</span></span> <span data-ttu-id="8cfd8-110">Ссылка на коллекцию осуществляется с помощью `Items` Свойства:</span><span class="sxs-lookup"><span data-stu-id="8cfd8-110">The collection is referenced using the `Items` property:</span></span>  
  
    ```vb  
    ComboBox1.Items.Add("Tokyo")  
    ```  
  
    ```csharp  
    comboBox1.Items.Add("Tokyo");  
    ```  
  
    ```cpp  
    comboBox1->Items->Add("Tokyo");  
    ```  
  
     - <span data-ttu-id="8cfd8-111">или</span><span class="sxs-lookup"><span data-stu-id="8cfd8-111">or -</span></span>  
  
2. <span data-ttu-id="8cfd8-112">Вставьте строку или объект в нужную точку списка с помощью `Insert` метода:</span><span class="sxs-lookup"><span data-stu-id="8cfd8-112">Insert the string or object at the desired point in the list with the `Insert` method:</span></span>  
  
    ```vb  
    CheckedListBox1.Items.Insert(0, "Copenhagen")  
    ```  
  
    ```csharp  
    checkedListBox1.Items.Insert(0, "Copenhagen");  
    ```  
  
    ```cpp  
    checkedListBox1->Items->Insert(0, "Copenhagen");  
    ```  
  
     - <span data-ttu-id="8cfd8-113">или</span><span class="sxs-lookup"><span data-stu-id="8cfd8-113">or -</span></span>  
  
3. <span data-ttu-id="8cfd8-114">Назначьте весь массив `Items` коллекции:</span><span class="sxs-lookup"><span data-stu-id="8cfd8-114">Assign an entire array to the `Items` collection:</span></span>  
  
    ```vb  
    Dim ItemObject(9) As System.Object  
    Dim i As Integer  
       For i = 0 To 9  
       ItemObject(i) = "Item" & i  
    Next i  
    ListBox1.Items.AddRange(ItemObject)  
    ```  
  
    ```csharp  
    System.Object[] ItemObject = new System.Object[10];  
    for (int i = 0; i <= 9; i++)  
    {  
       ItemObject[i] = "Item" + i;  
    }  
    listBox1.Items.AddRange(ItemObject);  
    ```  
  
    ```cpp  
    Array<System::Object^>^ ItemObject = gcnew Array<System::Object^>(10);  
    for (int i = 0; i <= 9; i++)  
    {  
       ItemObject[i] = String::Concat("Item", i.ToString());  
    }  
    listBox1->Items->AddRange(ItemObject);  
    ```  
  
### <a name="to-remove-an-item"></a><span data-ttu-id="8cfd8-115">Удаление элемента</span><span class="sxs-lookup"><span data-stu-id="8cfd8-115">To remove an item</span></span>  
  
1. <span data-ttu-id="8cfd8-116">Вызовите `Remove` метод или, `RemoveAt` чтобы удалить элементы.</span><span class="sxs-lookup"><span data-stu-id="8cfd8-116">Call the `Remove` or `RemoveAt` method to delete items.</span></span>  
  
     <span data-ttu-id="8cfd8-117">`Remove`содержит один аргумент, указывающий удаляемый элемент.`RemoveAt`</span><span class="sxs-lookup"><span data-stu-id="8cfd8-117">`Remove` has one argument that specifies the item to remove.`RemoveAt`</span></span> <span data-ttu-id="8cfd8-118">Удаляет элемент с указанным номером индекса.</span><span class="sxs-lookup"><span data-stu-id="8cfd8-118">removes the item with the specified index number.</span></span>  
  
    ```vb  
    ' To remove item with index 0:  
    ComboBox1.Items.RemoveAt(0)  
    ' To remove currently selected item:  
    ComboBox1.Items.Remove(ComboBox1.SelectedItem)  
    ' To remove "Tokyo" item:  
    ComboBox1.Items.Remove("Tokyo")  
    ```  
  
    ```csharp  
    // To remove item with index 0:  
    comboBox1.Items.RemoveAt(0);  
    // To remove currently selected item:  
    comboBox1.Items.Remove(comboBox1.SelectedItem);  
    // To remove "Tokyo" item:  
    comboBox1.Items.Remove("Tokyo");  
    ```  
  
    ```cpp  
    // To remove item with index 0:  
    comboBox1->Items->RemoveAt(0);  
    // To remove currently selected item:  
    comboBox1->Items->Remove(comboBox1->SelectedItem);  
    // To remove "Tokyo" item:  
    comboBox1->Items->Remove("Tokyo");  
    ```  
  
### <a name="to-remove-all-items"></a><span data-ttu-id="8cfd8-119">Удаление всех элементов</span><span class="sxs-lookup"><span data-stu-id="8cfd8-119">To remove all items</span></span>  
  
1. <span data-ttu-id="8cfd8-120">Вызовите `Clear` метод, чтобы удалить все элементы из коллекции:</span><span class="sxs-lookup"><span data-stu-id="8cfd8-120">Call the `Clear` method to remove all items from the collection:</span></span>  
  
    ```vb  
    ListBox1.Items.Clear()  
    ```  
  
    ```csharp  
    listBox1.Items.Clear();  
    ```  
  
    ```cpp  
    listBox1->Items->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="8cfd8-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8cfd8-121">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [<span data-ttu-id="8cfd8-122">Практическое руководство. Сортировка содержимого элемента управления ComboBox, ListBox или CheckedListBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8cfd8-122">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [<span data-ttu-id="8cfd8-123">Применение элемента управления ComboBox вместо элемента управления ListBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8cfd8-123">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [<span data-ttu-id="8cfd8-124">Создание списка для выбора элементов в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8cfd8-124">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
