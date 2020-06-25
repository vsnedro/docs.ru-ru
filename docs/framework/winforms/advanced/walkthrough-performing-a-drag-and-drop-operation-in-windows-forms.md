---
title: Пошаговое руководство. выполнение операции перетаскивания
description: Узнайте, как выполнить операцию перетаскивания в Windows Forms путем обработки ряда событий, особенно в событиях DragEnter, DragLeave и DragDrop.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drag and drop operations
- drag and drop [Windows Forms], Windows Forms
ms.assetid: eb66f6bf-4a7d-4c2d-b276-40fefb2d3b6c
ms.openlocfilehash: 83bfda875e2fdec3981bbcb8f8f7be00db342440
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325823"
---
# <a name="walkthrough-performing-a-drag-and-drop-operation-in-windows-forms"></a>Пошаговое руководство. Выполнение операции перетаскивания в Windows Forms
Для выполнения операций перетаскивания в приложениях на основе Windows необходимо выполнить обработку ряда событий, особенно <xref:System.Windows.Forms.Control.DragEnter> <xref:System.Windows.Forms.Control.DragLeave> событий, и <xref:System.Windows.Forms.Control.DragDrop> . Работая со сведениями, доступными через аргументы этих событий, можно значительно упростить операции перетаскивания.  
  
## <a name="dragging-data"></a>Перетаскивание данных  
 Все операции перетаскивания начинаются с переноса данных. Функция, позволяющая собирать данные при начале перетаскивания, реализуется в <xref:System.Windows.Forms.Control.DoDragDrop%2A> методе.  
  
 В следующем примере <xref:System.Windows.Forms.Control.MouseDown> событие используется для запуска операции перетаскивания, поскольку она является наиболее интуитивно понятной (большинство действий по перетаскиванию начинается с нажатия кнопки мыши). Однако не забывайте, что любое событие может использоваться для инициализации процедуры перетаскивания.  
  
> [!NOTE]
> Некоторые элементы управления имеют собственные события перетаскивания. <xref:System.Windows.Forms.ListView> <xref:System.Windows.Forms.TreeView> Для элементов управления и, например, имеется <xref:System.Windows.Forms.TreeView.ItemDrag> событие.  
  
#### <a name="to-start-a-drag-operation"></a>Начало операции перетаскивания  
  
1. В <xref:System.Windows.Forms.Control.MouseDown> событии для элемента управления, в котором начнется перетаскивание, используйте `DoDragDrop` метод, чтобы задать перетаскиваемые данные и разрешить перетаскивание разрешенных эффектов. Дополнительные сведения см. в разделах <xref:System.Windows.Forms.DragEventArgs.Data%2A> и <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.  
  
     В следующем примере показан запуск операции перетаскивания. Элемент управления, в котором начинается перетаскивание <xref:System.Windows.Forms.Button> , является элементом управления, перетаскиваемые данные — это строка, представляющая <xref:System.Windows.Forms.Control.Text%2A> свойство <xref:System.Windows.Forms.Button> элемента управления, и разрешенные эффекты можно копировать или перемещать.  
  
    ```vb  
    Private Sub Button1_MouseDown(ByVal sender As Object, ByVal e As System.Windows.Forms.MouseEventArgs) Handles Button1.MouseDown  
       Button1.DoDragDrop(Button1.Text, DragDropEffects.Copy Or DragDropEffects.Move)  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_MouseDown(object sender,
    System.Windows.Forms.MouseEventArgs e)  
    {  
       button1.DoDragDrop(button1.Text, DragDropEffects.Copy |
          DragDropEffects.Move);  
    }  
    ```  
  
    > [!NOTE]
    > В качестве параметра в методе можно использовать любые данные `DoDragDrop` . в приведенном выше примере <xref:System.Windows.Forms.Control.Text%2A> <xref:System.Windows.Forms.Button> используется свойство элемента управления (вместо жесткого кодирования значения или извлечения данных из набора данных), поскольку свойство было связано с расположением, которое перетаскивается из ( <xref:System.Windows.Forms.Button> элемент управления). Учитывайте это при реализации операций перетаскивания в приложениях Windows.  
  
 Пока действует операция перетаскивания, можно выполнить обработку <xref:System.Windows.Forms.Control.QueryContinueDrag> события, которое "запрашивает разрешение" системы, чтобы продолжить операцию перетаскивания. При обработке этого метода также является подходящая точка для вызова методов, которые влияют на операцию перетаскивания, например, расширение объекта <xref:System.Windows.Forms.TreeNode> в <xref:System.Windows.Forms.TreeView> элементе управления при наведении курсора мыши на него.  
  
## <a name="dropping-data"></a>Завершение перетаскивания данных  
 После начала перетаскивания данных из расположения в форме Windows Forms или элементе управления их требуется куда-то поместить. При попадании курсора в область формы или элемента управления, которые правильно настроены для размещения данных, вид курсора изменится. Любая область внутри формы или элемента управления Windows может быть сделана для приема пропущенных данных путем установки <xref:System.Windows.Forms.Control.AllowDrop%2A> Свойства и обработки <xref:System.Windows.Forms.Control.DragEnter> <xref:System.Windows.Forms.Control.DragDrop> событий и.  
  
#### <a name="to-perform-a-drop"></a>Завершение операции перетаскивания  
  
1. Присвойте <xref:System.Windows.Forms.Control.AllowDrop%2A> свойству значение true.  
  
2. В `DragEnter` событии для элемента управления, в котором будет выполняться перетаскивание, убедитесь, что перетаскиваемые данные имеют допустимый тип (в данном случае <xref:System.Windows.Forms.Control.Text%2A> ). Затем код задает результат, который будет выполняться при выполнении перетаскивания в значение в <xref:System.Windows.Forms.DragDropEffects> перечислении. Для получения дополнительной информации см. <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.  
  
    ```vb  
    Private Sub TextBox1_DragEnter(ByVal sender As Object, ByVal e As System.Windows.Forms.DragEventArgs) Handles TextBox1.DragEnter  
       If (e.Data.GetDataPresent(DataFormats.Text)) Then  
         e.Effect = DragDropEffects.Copy  
       Else  
         e.Effect = DragDropEffects.None  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_DragEnter(object sender,
    System.Windows.Forms.DragEventArgs e)  
    {  
       if (e.Data.GetDataPresent(DataFormats.Text))
          e.Effect = DragDropEffects.Copy;  
       else  
          e.Effect = DragDropEffects.None;  
    }  
    ```  
  
    > [!NOTE]
    > Вы можете определить собственное <xref:System.Windows.Forms.DataFormats> , указав собственный объект в качестве <xref:System.Object> параметра <xref:System.Windows.Forms.DataObject.SetData%2A> метода. При этом необходимо убедиться, что указанный объект является сериализуемым. Для получения дополнительной информации см. <xref:System.Runtime.Serialization.ISerializable>.  
  
3. В <xref:System.Windows.Forms.Control.DragDrop> событии для элемента управления, в котором будет выполняться удаление, используйте <xref:System.Windows.Forms.DataObject.GetData%2A> метод для получения перетаскиваемых данных. Для получения дополнительной информации см. <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.  
  
     В приведенном ниже примере элемент <xref:System.Windows.Forms.TextBox> управления — это элемент управления, к которому выполняется перетаскивание (где произойдет удаление). Код задает <xref:System.Windows.Forms.Control.Text%2A> свойство <xref:System.Windows.Forms.TextBox> элемента управления, равное перетаскиваемых данным.  
  
    ```vb  
    Private Sub TextBox1_DragDrop(ByVal sender As Object, ByVal e As System.Windows.Forms.DragEventArgs) Handles TextBox1.DragDrop  
       TextBox1.Text = e.Data.GetData(DataFormats.Text).ToString  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_DragDrop(object sender,
    System.Windows.Forms.DragEventArgs e)  
    {  
       textBox1.Text = e.Data.GetData(DataFormats.Text).ToString();  
    }  
    ```  
  
    > [!NOTE]
    > Кроме того, можно работать со <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> свойством, чтобы, в зависимости от нажатых клавиш во время операции перетаскивания, были выполнены определенные эффекты (например, для копирования перетаскиваемых данных при нажатии клавиши CTRL).  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Добавление данных в буфер обмена](how-to-add-data-to-the-clipboard.md)
- [Практическое руководство. Извлечение данных из буфера обмена](how-to-retrieve-data-from-the-clipboard.md)
- [Операции перетаскивания и поддержка буфера обмена](drag-and-drop-operations-and-clipboard-support.md)
