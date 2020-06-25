---
title: Добавление элементов управления
description: Научитесь нарисовать элемент управления в форме Windows Forms. Элемент управления — это компонент в форме, с помощью которого можно отображать сведения или принимать вводимые пользователем данные.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, adding to form
- controls [Windows Forms], adding
ms.assetid: 2af86001-9d62-4154-87fb-66db2c3cd9fd
ms.openlocfilehash: d9ab0d78fa0153cce20fb17d22f6e9e781229ece
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325880"
---
# <a name="how-to-add-controls-to-windows-forms"></a><span data-ttu-id="bb172-104">Практическое руководство. Добавление элементов управления в формы Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="bb172-104">How to: Add Controls to Windows Forms</span></span>

<span data-ttu-id="bb172-105">Большинство форм разрабатываются путем добавления элементов управления на поверхность формы для определения пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="bb172-105">Most forms are designed by adding controls to the surface of the form to define a user interface (UI).</span></span> <span data-ttu-id="bb172-106">*Элемент управления* — это компонент в форме, используемый для вывода информации или ввода данных пользователем.</span><span class="sxs-lookup"><span data-stu-id="bb172-106">A *control* is a component on a form used to display information or accept user input.</span></span> <span data-ttu-id="bb172-107">Дополнительные сведения об элементах управления см. в разделе [элементы управления Windows Forms](index.md).</span><span class="sxs-lookup"><span data-stu-id="bb172-107">For more information about controls, see [Windows Forms Controls](index.md).</span></span>

## <a name="to-draw-a-control-on-a-form"></a><span data-ttu-id="bb172-108">Рисование элемента управления в форме</span><span class="sxs-lookup"><span data-stu-id="bb172-108">To draw a control on a form</span></span>

1. <span data-ttu-id="bb172-109">Откройте форму.</span><span class="sxs-lookup"><span data-stu-id="bb172-109">Open the form.</span></span> <span data-ttu-id="bb172-110">Дополнительные сведения см. в разделе [инструкции. отображение Windows Forms в конструкторе](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="bb172-110">For more information, see [How to: Display Windows Forms in the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span></span>

2. <span data-ttu-id="bb172-111">В **области элементов**щелкните элемент управления, который необходимо добавить в форму.</span><span class="sxs-lookup"><span data-stu-id="bb172-111">In the **Toolbox**, click the control you want to add to your form.</span></span>

3. <span data-ttu-id="bb172-112">В форме щелкните место, где должен располагаться левый верхний угол элемента управления, и перетащите его в то место, где должен располагаться правый нижний угол элемента управления.</span><span class="sxs-lookup"><span data-stu-id="bb172-112">On the form, click where you want the upper-left corner of the control to be located, and drag to where you want the lower-right corner of the control to be located.</span></span>

    <span data-ttu-id="bb172-113">Элемент управления добавляется в форму с указанными расположением и размером.</span><span class="sxs-lookup"><span data-stu-id="bb172-113">The control is added to the form with the specified location and size.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bb172-114">Для каждого элемента управления определен размер по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bb172-114">Each control has a default size defined.</span></span> <span data-ttu-id="bb172-115">Можно добавить элемент управления в форму в размер элемента управления по умолчанию, перетащив его из **области элементов** в форму.</span><span class="sxs-lookup"><span data-stu-id="bb172-115">You can add a control to your form in the control's default size by dragging it from the **Toolbox** to the form.</span></span>

## <a name="to-drag-a-control-to-a-form"></a><span data-ttu-id="bb172-116">Перетаскивание элемента управления в форму</span><span class="sxs-lookup"><span data-stu-id="bb172-116">To drag a control to a form</span></span>

1. <span data-ttu-id="bb172-117">Откройте форму.</span><span class="sxs-lookup"><span data-stu-id="bb172-117">Open the form.</span></span> <span data-ttu-id="bb172-118">Дополнительные сведения см. в разделе [инструкции. отображение Windows Forms в конструкторе](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="bb172-118">For more information, see [How to: Display Windows Forms in the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span></span>

2. <span data-ttu-id="bb172-119">На **панели элементов**щелкните нужный элемент управления и перетащите его в форму.</span><span class="sxs-lookup"><span data-stu-id="bb172-119">In the **Toolbox**, click the control you want and drag it to your form.</span></span>

    <span data-ttu-id="bb172-120">Элемент управления добавляется в форму в указанном расположении в его размер по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bb172-120">The control is added to the form at the specified location in its default size.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bb172-121">Можно дважды щелкнуть элемент управления на **панели элементов** , чтобы добавить его в левый верхний угол формы в его размер по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bb172-121">You can double-click a control in the **Toolbox** to add it to the upper-left corner of the form in its default size.</span></span>

    <span data-ttu-id="bb172-122">Кроме того, можно динамически добавлять элементы управления в форму во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="bb172-122">You can also add controls dynamically to a form at run time.</span></span> <span data-ttu-id="bb172-123">В следующем примере кода <xref:System.Windows.Forms.TextBox> элемент управления будет добавлен в форму при <xref:System.Windows.Forms.Button> щелчке элемента управления.</span><span class="sxs-lookup"><span data-stu-id="bb172-123">In the following code example, a <xref:System.Windows.Forms.TextBox> control will be added to the form when a <xref:System.Windows.Forms.Button> control is clicked.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bb172-124">Следующая процедура требует наличия формы с элементом управления **Button** , `Button1` уже размещенным в ней.</span><span class="sxs-lookup"><span data-stu-id="bb172-124">The following procedure requires the existence of a form with a **Button** control, `Button1`, already placed on it.</span></span>

## <a name="to-add-a-control-to-a-form-programmatically"></a><span data-ttu-id="bb172-125">Добавление элемента управления в форму программным способом</span><span class="sxs-lookup"><span data-stu-id="bb172-125">To add a control to a form programmatically</span></span>

1. <span data-ttu-id="bb172-126">В методе, обрабатывающем событие кнопки `Click` в классе формы, вставьте код, аналогичный приведенному ниже, чтобы добавить ссылку на переменную элемента управления, задать элемент управления `Location` и добавить элемент управления.</span><span class="sxs-lookup"><span data-stu-id="bb172-126">In the method that handles the button's `Click` event within your form's class, insert code similar to the following to add a reference to your control variable, set the control's `Location`, and add the control.</span></span>

    ```vb
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click
       Dim MyText As New TextBox()
       MyText.Location = New Point(25, 25)
       Me.Controls.Add(MyText)
    End Sub
    ```

    ```csharp
    private void button1_Click(object sender, System.EventArgs e)
    {
       TextBox myText = new TextBox();
       myText.Location = new Point(25,25);
       this.Controls.Add (myText);
    }
    ```

    ```cpp
    private:
      System::Void button1_Click(System::Object ^  sender,
        System::EventArgs ^  e)
      {
        TextBox ^ myText = gcnew TextBox();
        myText->Location = Point(25,25);
        this->Controls->Add(myText);
      }
    ```

    > [!NOTE]
    > <span data-ttu-id="bb172-127">Можно также добавить код для инициализации других свойств элемента управления.</span><span class="sxs-lookup"><span data-stu-id="bb172-127">You can also add code to initialize other properties of the control.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="bb172-128">Вы можете предоставить локальному компьютеру угрозу безопасности через сеть, обратившись к вредоносной программе `UserControl` .</span><span class="sxs-lookup"><span data-stu-id="bb172-128">You might expose your local computer to a security risk through the network by referencing a malicious `UserControl`.</span></span> <span data-ttu-id="bb172-129">Это будет проблемой только в случае, если злоумышленник создает вредоносный пользовательский элемент управления, а затем добавляет его в проект по ошибке.</span><span class="sxs-lookup"><span data-stu-id="bb172-129">This would only be a concern in the case of a malicious person creating a damaging custom control, followed by you mistakenly adding it to your project.</span></span>

## <a name="see-also"></a><span data-ttu-id="bb172-130">См. также</span><span class="sxs-lookup"><span data-stu-id="bb172-130">See also</span></span>

- [<span data-ttu-id="bb172-131">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bb172-131">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="bb172-132">Практическое руководство. Изменение размера элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bb172-132">How to: Resize Controls on Windows Forms</span></span>](how-to-resize-controls-on-windows-forms.md)
- [<span data-ttu-id="bb172-133">Практическое руководство. Определение текста, отображаемого элементом управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bb172-133">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="bb172-134">Элементы управления для использования в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bb172-134">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
