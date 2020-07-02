---
title: Определение отмеченных элементов в элементе управления CheckedListBox
description: Узнайте, как определить отмеченные элементы в элементе управления Windows Forms CheckedListBox путем прохода по коллекции, хранящейся в свойстве Чеккедитемс.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- check boxes [Windows Forms], determining checked state
- CheckedListBox control [Windows Forms], determining checked state
ms.assetid: 178b477d-27c9-489c-8914-44a9623a4d41
ms.openlocfilehash: fd8845ef83da7406ff4f1468506a23e3f4d386a0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618354"
---
# <a name="how-to-determine-checked-items-in-the-windows-forms-checkedlistbox-control"></a>Практическое руководство. Определение отмеченных элементов в элементе управления CheckedListBox в Windows Forms
При представлении данных в <xref:System.Windows.Forms.CheckedListBox> элементе управления Windows Forms можно либо выполнить итерацию по коллекции, хранящейся в <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> свойстве, либо выполнить пошаговое выполнение списка с помощью <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> метода, чтобы определить, какие элементы отмечены флажками. <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A>Метод принимает номер индекса элемента в качестве аргумента и возвращает значение `true` или `false` . В отличие от того, что вы можете ожидать, <xref:System.Windows.Forms.ListBox.SelectedItems%2A> <xref:System.Windows.Forms.ListBox.SelectedIndices%2A> Свойства и не определяют, какие элементы отмечены. они определяют, какие элементы выделены.  
  
### <a name="to-determine-checked-items-in-a-checkedlistbox-control"></a>Определение отмеченных элементов в элементе управления CheckedListBox  
  
1. Выполните итерацию по <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> коллекции, начиная с 0, так как коллекция отсчитывается от нуля. Обратите внимание, что этот метод предоставит номер элемента в списке отмеченных элементов, а не в общем списке. Таким образом, если первый элемент в списке не установлен и второй элемент установлен, в приведенном ниже коде отображается текст, например "Checked Item 1 = MyListItem2".  
  
    ```vb  
    ' Determine if there are any items checked.  
    If CheckedListBox1.CheckedItems.Count <> 0 Then  
       ' If so, loop through all checked items and print results.  
       Dim x As Integer  
       Dim s As String = ""  
       For x = 0 To CheckedListBox1.CheckedItems.Count - 1  
          s = s & "Checked Item " & (x + 1).ToString & " = " & CheckedListBox1.CheckedItems(x).ToString & ControlChars.CrLf  
       Next x  
       MessageBox.Show(s)  
    End If  
    ```  
  
    ```csharp  
    // Determine if there are any items checked.  
    if(checkedListBox1.CheckedItems.Count != 0)  
    {  
       // If so, loop through all checked items and print results.  
       string s = "";  
       for(int x = 0; x < checkedListBox1.CheckedItems.Count ; x++)  
       {  
          s = s + "Checked Item " + (x+1).ToString() + " = " + checkedListBox1.CheckedItems[x].ToString() + "\n";  
       }  
       MessageBox.Show(s);  
    }  
    ```  
  
    ```cpp  
    // Determine if there are any items checked.  
    if(checkedListBox1->CheckedItems->Count != 0)  
    {  
       // If so, loop through all checked items and print results.  
       String ^ s = "";  
       for(int x = 0; x < checkedListBox1->CheckedItems->Count; x++)  
       {  
          s = String::Concat(s, "Checked Item ", (x+1).ToString(),  
             " = ", checkedListBox1->CheckedItems[x]->ToString(),  
             "\n");  
       }  
       MessageBox::Show(s);  
    }  
    ```  
  
     - или  
  
2. Пройдите по <xref:System.Windows.Forms.CheckedListBox.Items%2A> коллекции, начиная с 0, так как коллекция отсчитывается от нуля, и вызовите <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> метод для каждого элемента. Обратите внимание, что этот метод предоставит номер элемента в общем списке, поэтому, если первый элемент в списке не установлен и второй элемент установлен, он будет отображать нечто вроде "Item 2 = MyListItem2".  
  
    ```vb  
    Dim i As Integer  
    Dim s As String  
    s = "Checked Items:" & ControlChars.CrLf  
    For i = 0 To (CheckedListBox1.Items.Count - 1)  
       If CheckedListBox1.GetItemChecked(i) = True Then  
          s = s & "Item " & (i + 1).ToString & " = " & CheckedListBox1.Items(i).ToString & ControlChars.CrLf  
       End If  
    Next  
    MessageBox.Show(s)  
    ```  
  
    ```csharp  
    int i;  
    string s;
    s = "Checked items:\n" ;  
    for (i = 0; i <= (checkedListBox1.Items.Count-1); i++)  
    {  
       if (checkedListBox1.GetItemChecked(i))  
       {  
          s = s + "Item " + (i+1).ToString() + " = " + checkedListBox1.Items[i].ToString() + "\n";  
       }  
    }  
    MessageBox.Show (s);  
    ```  
  
    ```cpp  
    int i;  
    String ^ s;
    s = "Checked items:\n" ;  
    for (i = 0; i <= (checkedListBox1->Items->Count-1); i++)  
    {  
       if (checkedListBox1->GetItemChecked(i))  
       {  
          s = String::Concat(s, "Item ", (i+1).ToString(), " = ",  
             checkedListBox1->Item[i]->ToString(), "\n");  
       }  
    }  
    MessageBox::Show(s);  
    ```  
  
## <a name="see-also"></a>См. также

- [Создание списка для выбора элементов в Windows Forms](windows-forms-controls-used-to-list-options.md)
