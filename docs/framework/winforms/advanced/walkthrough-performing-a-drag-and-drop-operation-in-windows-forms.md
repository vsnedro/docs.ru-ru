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
# <a name="walkthrough-performing-a-drag-and-drop-operation-in-windows-forms"></a><span data-ttu-id="0d00a-103">Пошаговое руководство. Выполнение операции перетаскивания в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0d00a-103">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>
<span data-ttu-id="0d00a-104">Для выполнения операций перетаскивания в приложениях на основе Windows необходимо выполнить обработку ряда событий, особенно <xref:System.Windows.Forms.Control.DragEnter> <xref:System.Windows.Forms.Control.DragLeave> событий, и <xref:System.Windows.Forms.Control.DragDrop> .</span><span class="sxs-lookup"><span data-stu-id="0d00a-104">To perform drag-and-drop operations within Windows-based applications you must handle a series of events, most notably the <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>, and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span> <span data-ttu-id="0d00a-105">Работая со сведениями, доступными через аргументы этих событий, можно значительно упростить операции перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="0d00a-105">By working with the information available in the event arguments of these events, you can easily facilitate drag-and-drop operations.</span></span>  
  
## <a name="dragging-data"></a><span data-ttu-id="0d00a-106">Перетаскивание данных</span><span class="sxs-lookup"><span data-stu-id="0d00a-106">Dragging Data</span></span>  
 <span data-ttu-id="0d00a-107">Все операции перетаскивания начинаются с переноса данных.</span><span class="sxs-lookup"><span data-stu-id="0d00a-107">All drag-and-drop operations begin with dragging.</span></span> <span data-ttu-id="0d00a-108">Функция, позволяющая собирать данные при начале перетаскивания, реализуется в <xref:System.Windows.Forms.Control.DoDragDrop%2A> методе.</span><span class="sxs-lookup"><span data-stu-id="0d00a-108">The functionality to enable data to be collected when dragging begins is implemented in the <xref:System.Windows.Forms.Control.DoDragDrop%2A> method.</span></span>  
  
 <span data-ttu-id="0d00a-109">В следующем примере <xref:System.Windows.Forms.Control.MouseDown> событие используется для запуска операции перетаскивания, поскольку она является наиболее интуитивно понятной (большинство действий по перетаскиванию начинается с нажатия кнопки мыши).</span><span class="sxs-lookup"><span data-stu-id="0d00a-109">In the following example, the <xref:System.Windows.Forms.Control.MouseDown> event is used to start the drag operation because it is the most intuitive (most drag-and-drop actions begin with the mouse button being depressed).</span></span> <span data-ttu-id="0d00a-110">Однако не забывайте, что любое событие может использоваться для инициализации процедуры перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="0d00a-110">However, remember that any event could be used to initiate a drag-and-drop procedure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0d00a-111">Некоторые элементы управления имеют собственные события перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="0d00a-111">Certain controls have custom drag-specific events.</span></span> <span data-ttu-id="0d00a-112"><xref:System.Windows.Forms.ListView> <xref:System.Windows.Forms.TreeView> Для элементов управления и, например, имеется <xref:System.Windows.Forms.TreeView.ItemDrag> событие.</span><span class="sxs-lookup"><span data-stu-id="0d00a-112">The <xref:System.Windows.Forms.ListView> and <xref:System.Windows.Forms.TreeView> controls, for example, have an <xref:System.Windows.Forms.TreeView.ItemDrag> event.</span></span>  
  
#### <a name="to-start-a-drag-operation"></a><span data-ttu-id="0d00a-113">Начало операции перетаскивания</span><span class="sxs-lookup"><span data-stu-id="0d00a-113">To start a drag operation</span></span>  
  
1. <span data-ttu-id="0d00a-114">В <xref:System.Windows.Forms.Control.MouseDown> событии для элемента управления, в котором начнется перетаскивание, используйте `DoDragDrop` метод, чтобы задать перетаскиваемые данные и разрешить перетаскивание разрешенных эффектов.</span><span class="sxs-lookup"><span data-stu-id="0d00a-114">In the <xref:System.Windows.Forms.Control.MouseDown> event for the control where the drag will begin, use the `DoDragDrop` method to set the data to be dragged and the allowed effect dragging will have.</span></span> <span data-ttu-id="0d00a-115">Дополнительные сведения см. в разделах <xref:System.Windows.Forms.DragEventArgs.Data%2A> и <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.</span><span class="sxs-lookup"><span data-stu-id="0d00a-115">For more information, see <xref:System.Windows.Forms.DragEventArgs.Data%2A> and <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.</span></span>  
  
     <span data-ttu-id="0d00a-116">В следующем примере показан запуск операции перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="0d00a-116">The following example shows how to initiate a drag operation.</span></span> <span data-ttu-id="0d00a-117">Элемент управления, в котором начинается перетаскивание <xref:System.Windows.Forms.Button> , является элементом управления, перетаскиваемые данные — это строка, представляющая <xref:System.Windows.Forms.Control.Text%2A> свойство <xref:System.Windows.Forms.Button> элемента управления, и разрешенные эффекты можно копировать или перемещать.</span><span class="sxs-lookup"><span data-stu-id="0d00a-117">The control where the drag begins is a <xref:System.Windows.Forms.Button> control, the data being dragged is the string representing the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control, and the allowed effects are either copying or moving.</span></span>  
  
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
    > <span data-ttu-id="0d00a-118">В качестве параметра в методе можно использовать любые данные `DoDragDrop` . в приведенном выше примере <xref:System.Windows.Forms.Control.Text%2A> <xref:System.Windows.Forms.Button> используется свойство элемента управления (вместо жесткого кодирования значения или извлечения данных из набора данных), поскольку свойство было связано с расположением, которое перетаскивается из ( <xref:System.Windows.Forms.Button> элемент управления).</span><span class="sxs-lookup"><span data-stu-id="0d00a-118">Any data can be used as a parameter in the `DoDragDrop` method; in the example above, the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control was used (rather than hard-coding a value or retrieving data from a dataset) because the property was related to the location being dragged from (the <xref:System.Windows.Forms.Button> control).</span></span> <span data-ttu-id="0d00a-119">Учитывайте это при реализации операций перетаскивания в приложениях Windows.</span><span class="sxs-lookup"><span data-stu-id="0d00a-119">Keep this in mind as you incorporate drag-and-drop operations into your Windows-based applications.</span></span>  
  
 <span data-ttu-id="0d00a-120">Пока действует операция перетаскивания, можно выполнить обработку <xref:System.Windows.Forms.Control.QueryContinueDrag> события, которое "запрашивает разрешение" системы, чтобы продолжить операцию перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="0d00a-120">While a drag operation is in effect, you can handle the <xref:System.Windows.Forms.Control.QueryContinueDrag> event, which "asks permission" of the system to continue the drag operation.</span></span> <span data-ttu-id="0d00a-121">При обработке этого метода также является подходящая точка для вызова методов, которые влияют на операцию перетаскивания, например, расширение объекта <xref:System.Windows.Forms.TreeNode> в <xref:System.Windows.Forms.TreeView> элементе управления при наведении курсора мыши на него.</span><span class="sxs-lookup"><span data-stu-id="0d00a-121">When handling this method, it is also the appropriate point for you to call methods that will have an effect on the drag operation, such as expanding a <xref:System.Windows.Forms.TreeNode> in a <xref:System.Windows.Forms.TreeView> control when the cursor hovers over it.</span></span>  
  
## <a name="dropping-data"></a><span data-ttu-id="0d00a-122">Завершение перетаскивания данных</span><span class="sxs-lookup"><span data-stu-id="0d00a-122">Dropping Data</span></span>  
 <span data-ttu-id="0d00a-123">После начала перетаскивания данных из расположения в форме Windows Forms или элементе управления их требуется куда-то поместить.</span><span class="sxs-lookup"><span data-stu-id="0d00a-123">Once you have begun dragging data from a location on a Windows Form or control, you will naturally want to drop it somewhere.</span></span> <span data-ttu-id="0d00a-124">При попадании курсора в область формы или элемента управления, которые правильно настроены для размещения данных, вид курсора изменится.</span><span class="sxs-lookup"><span data-stu-id="0d00a-124">The cursor will change when it crosses an area of a form or control that is correctly configured for dropping data.</span></span> <span data-ttu-id="0d00a-125">Любая область внутри формы или элемента управления Windows может быть сделана для приема пропущенных данных путем установки <xref:System.Windows.Forms.Control.AllowDrop%2A> Свойства и обработки <xref:System.Windows.Forms.Control.DragEnter> <xref:System.Windows.Forms.Control.DragDrop> событий и.</span><span class="sxs-lookup"><span data-stu-id="0d00a-125">Any area within a Windows Form or control can be made to accept dropped data by setting the <xref:System.Windows.Forms.Control.AllowDrop%2A> property and handling the <xref:System.Windows.Forms.Control.DragEnter> and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span>  
  
#### <a name="to-perform-a-drop"></a><span data-ttu-id="0d00a-126">Завершение операции перетаскивания</span><span class="sxs-lookup"><span data-stu-id="0d00a-126">To perform a drop</span></span>  
  
1. <span data-ttu-id="0d00a-127">Присвойте <xref:System.Windows.Forms.Control.AllowDrop%2A> свойству значение true.</span><span class="sxs-lookup"><span data-stu-id="0d00a-127">Set the <xref:System.Windows.Forms.Control.AllowDrop%2A> property to true.</span></span>  
  
2. <span data-ttu-id="0d00a-128">В `DragEnter` событии для элемента управления, в котором будет выполняться перетаскивание, убедитесь, что перетаскиваемые данные имеют допустимый тип (в данном случае <xref:System.Windows.Forms.Control.Text%2A> ).</span><span class="sxs-lookup"><span data-stu-id="0d00a-128">In the `DragEnter` event for the control where the drop will occur, ensure that the data being dragged is of an acceptable type (in this case, <xref:System.Windows.Forms.Control.Text%2A>).</span></span> <span data-ttu-id="0d00a-129">Затем код задает результат, который будет выполняться при выполнении перетаскивания в значение в <xref:System.Windows.Forms.DragDropEffects> перечислении.</span><span class="sxs-lookup"><span data-stu-id="0d00a-129">The code then sets the effect that will happen when the drop occurs to a value in the <xref:System.Windows.Forms.DragDropEffects> enumeration.</span></span> <span data-ttu-id="0d00a-130">Для получения дополнительной информации см. <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.</span><span class="sxs-lookup"><span data-stu-id="0d00a-130">For more information, see <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.</span></span>  
  
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
    > <span data-ttu-id="0d00a-131">Вы можете определить собственное <xref:System.Windows.Forms.DataFormats> , указав собственный объект в качестве <xref:System.Object> параметра <xref:System.Windows.Forms.DataObject.SetData%2A> метода.</span><span class="sxs-lookup"><span data-stu-id="0d00a-131">You can define your own <xref:System.Windows.Forms.DataFormats> by specifying your own object as the <xref:System.Object> parameter of the <xref:System.Windows.Forms.DataObject.SetData%2A> method.</span></span> <span data-ttu-id="0d00a-132">При этом необходимо убедиться, что указанный объект является сериализуемым.</span><span class="sxs-lookup"><span data-stu-id="0d00a-132">Be sure, when doing this, that the object specified is serializable.</span></span> <span data-ttu-id="0d00a-133">Для получения дополнительной информации см. <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="0d00a-133">For more information, see <xref:System.Runtime.Serialization.ISerializable>.</span></span>  
  
3. <span data-ttu-id="0d00a-134">В <xref:System.Windows.Forms.Control.DragDrop> событии для элемента управления, в котором будет выполняться удаление, используйте <xref:System.Windows.Forms.DataObject.GetData%2A> метод для получения перетаскиваемых данных.</span><span class="sxs-lookup"><span data-stu-id="0d00a-134">In the <xref:System.Windows.Forms.Control.DragDrop> event for the control where the drop will occur, use the <xref:System.Windows.Forms.DataObject.GetData%2A> method to retrieve the data being dragged.</span></span> <span data-ttu-id="0d00a-135">Для получения дополнительной информации см. <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.</span><span class="sxs-lookup"><span data-stu-id="0d00a-135">For more information, see <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.</span></span>  
  
     <span data-ttu-id="0d00a-136">В приведенном ниже примере элемент <xref:System.Windows.Forms.TextBox> управления — это элемент управления, к которому выполняется перетаскивание (где произойдет удаление).</span><span class="sxs-lookup"><span data-stu-id="0d00a-136">In the example below, a <xref:System.Windows.Forms.TextBox> control is the control being dragged to (where the drop will occur).</span></span> <span data-ttu-id="0d00a-137">Код задает <xref:System.Windows.Forms.Control.Text%2A> свойство <xref:System.Windows.Forms.TextBox> элемента управления, равное перетаскиваемых данным.</span><span class="sxs-lookup"><span data-stu-id="0d00a-137">The code sets the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.TextBox> control equal to the data being dragged.</span></span>  
  
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
    > <span data-ttu-id="0d00a-138">Кроме того, можно работать со <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> свойством, чтобы, в зависимости от нажатых клавиш во время операции перетаскивания, были выполнены определенные эффекты (например, для копирования перетаскиваемых данных при нажатии клавиши CTRL).</span><span class="sxs-lookup"><span data-stu-id="0d00a-138">Additionally, you can work with the <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> property, so that, depending on keys depressed during the drag-and-drop operation, certain effects occur (for example, it is standard to copy the dragged data when the CTRL key is pressed).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d00a-139">См. также</span><span class="sxs-lookup"><span data-stu-id="0d00a-139">See also</span></span>

- [<span data-ttu-id="0d00a-140">Практическое руководство. Добавление данных в буфер обмена</span><span class="sxs-lookup"><span data-stu-id="0d00a-140">How to: Add Data to the Clipboard</span></span>](how-to-add-data-to-the-clipboard.md)
- [<span data-ttu-id="0d00a-141">Практическое руководство. Извлечение данных из буфера обмена</span><span class="sxs-lookup"><span data-stu-id="0d00a-141">How to: Retrieve Data from the Clipboard</span></span>](how-to-retrieve-data-from-the-clipboard.md)
- [<span data-ttu-id="0d00a-142">Операции перетаскивания и поддержка буфера обмена</span><span class="sxs-lookup"><span data-stu-id="0d00a-142">Drag-and-Drop Operations and Clipboard Support</span></span>](drag-and-drop-operations-and-clipboard-support.md)
