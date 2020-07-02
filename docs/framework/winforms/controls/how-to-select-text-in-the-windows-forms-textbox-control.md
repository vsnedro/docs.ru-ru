---
title: Выбор текста в элементе управления TextBox
description: Узнайте, как программным способом выбрать текст в элементе управления TextBox Windows Forms. Также Узнайте, как визуально оповещать читателя о положении найденной строки.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], selecting text programmatically
- text boxes [Windows Forms], selecting text programmatically
- text [Windows Forms], selecting in text boxes programmatically
ms.assetid: 8c591546-6a01-45c7-8e03-f78431f903b1
ms.openlocfilehash: b8fdaff76461c4d6766dfc6afaef5e814d982834
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621565"
---
# <a name="how-to-select-text-in-the-windows-forms-textbox-control"></a><span data-ttu-id="06ce4-104">Практическое руководство. Выделение текста в элементе управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="06ce4-104">How to: Select Text in the Windows Forms TextBox Control</span></span>
<span data-ttu-id="06ce4-105">Текст можно выбрать программным способом в <xref:System.Windows.Forms.TextBox> элементе управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="06ce4-105">You can select text programmatically in the Windows Forms <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="06ce4-106">Например, при создании функции, выполняющей поиск определенной строки в тексте, можно выбрать текст, чтобы визуально предупредить читателя о положении найденной строки.</span><span class="sxs-lookup"><span data-stu-id="06ce4-106">For example, if you create a function that searches text for a particular string, you can select the text to visually alert the reader of the found string's position.</span></span>  
  
### <a name="to-select-text-programmatically"></a><span data-ttu-id="06ce4-107">Выбор текста программным способом</span><span class="sxs-lookup"><span data-stu-id="06ce4-107">To select text programmatically</span></span>  
  
1. <span data-ttu-id="06ce4-108">Задайте <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> для свойства начало текста, который необходимо выбрать.</span><span class="sxs-lookup"><span data-stu-id="06ce4-108">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property to the beginning of the text you want to select.</span></span>  
  
     <span data-ttu-id="06ce4-109"><xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A>Свойство является числом, указывающим точку вставки в текстовой строке, а 0 — самое левое положение.</span><span class="sxs-lookup"><span data-stu-id="06ce4-109">The <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property is a number that indicates the insertion point within the string of text, with 0 being the left-most position.</span></span> <span data-ttu-id="06ce4-110">Если <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> для свойства задано значение, равное числу символов в текстовом поле или больше, то точка вставки помещается после последнего символа.</span><span class="sxs-lookup"><span data-stu-id="06ce4-110">If the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property is set to a value equal to or greater than the number of characters in the text box, the insertion point is placed after the last character.</span></span>  
  
2. <span data-ttu-id="06ce4-111">Задайте <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> для свойства длину текста, который необходимо выбрать.</span><span class="sxs-lookup"><span data-stu-id="06ce4-111">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property to the length of the text you want to select.</span></span>  
  
     <span data-ttu-id="06ce4-112"><xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A>Свойство является числовым значением, которое задает ширину точки вставки.</span><span class="sxs-lookup"><span data-stu-id="06ce4-112">The <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property is a numeric value that sets the width of the insertion point.</span></span> <span data-ttu-id="06ce4-113">Если задать <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> для параметра значение больше 0, будет выбрано количество символов, начиная с текущей точки вставки.</span><span class="sxs-lookup"><span data-stu-id="06ce4-113">Setting the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> to a number greater than 0 causes that number of characters to be selected, starting from the current insertion point.</span></span>  
  
3. <span data-ttu-id="06ce4-114">Используемых Доступ к выбранному тексту осуществляется через <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="06ce4-114">(Optional) Access the selected text through the <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A> property.</span></span>  
  
     <span data-ttu-id="06ce4-115">Приведенный ниже код выбирает содержимое текстового поля при <xref:System.Windows.Forms.Control.Enter> возникновении события элемента управления.</span><span class="sxs-lookup"><span data-stu-id="06ce4-115">The code below selects the contents of a text box when the control's <xref:System.Windows.Forms.Control.Enter> event occurs.</span></span> <span data-ttu-id="06ce4-116">В этом примере проверяется, имеет ли текстовое поле значение для <xref:System.Windows.Forms.TextBox.Text%2A> свойства, которое не равно `null` или является пустой строкой.</span><span class="sxs-lookup"><span data-stu-id="06ce4-116">This example checks if the text box has a value for the <xref:System.Windows.Forms.TextBox.Text%2A> property that is not `null` or an empty string.</span></span> <span data-ttu-id="06ce4-117">Когда текстовое поле получает фокус, выделяется текущий текст в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="06ce4-117">When the text box receives the focus, the current text in the text box is selected.</span></span> <span data-ttu-id="06ce4-118">`TextBox1_Enter`Обработчик событий должен быть привязан к элементу управления. Дополнительные сведения см. [в разделе как создавать обработчики событий во время выполнения для Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="06ce4-118">The `TextBox1_Enter` event handler must be bound to the control; for more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
     <span data-ttu-id="06ce4-119">Чтобы протестировать этот пример, нажимайте клавишу TAB, пока текстовое поле не найдет фокус.</span><span class="sxs-lookup"><span data-stu-id="06ce4-119">To test this example, press the Tab key until the text box has the focus.</span></span> <span data-ttu-id="06ce4-120">Если щелкнуть в текстовом поле, то текст не будет выбран.</span><span class="sxs-lookup"><span data-stu-id="06ce4-120">If you click in the text box, the text is unselected.</span></span>  
  
    ```vb  
    Private Sub TextBox1_Enter(ByVal sender As Object, ByVal e As System.EventArgs) Handles TextBox1.Enter  
       If (Not String.IsNullOrEmpty(TextBox1.Text)) Then  
          TextBox1.SelectionStart = 0  
          TextBox1.SelectionLength = TextBox1.Text.Length  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_Enter(object sender, System.EventArgs e){  
       if (!String.IsNullOrEmpty(textBox1.Text))  
       {  
          textBox1.SelectionStart = 0;  
          textBox1.SelectionLength = textBox1.Text.Length;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void textBox1_Enter(System::Object ^ sender,  
          System::EventArgs ^ e) {  
       if (!System::String::IsNullOrEmpty(textBox1->Text))  
       {  
          textBox1->SelectionStart = 0;  
          textBox1->SelectionLength = textBox1->Text->Length;  
       }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="06ce4-121">См. также</span><span class="sxs-lookup"><span data-stu-id="06ce4-121">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="06ce4-122">Общие сведения об элементе управления TextBox</span><span class="sxs-lookup"><span data-stu-id="06ce4-122">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="06ce4-123">Практическое руководство. Управление положением курсора в элементе управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="06ce4-123">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="06ce4-124">Практическое руководство. Создание текстового поля для ввода пароля с помощью элемента управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="06ce4-124">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="06ce4-125">Практическое руководство. Создание текстового поля только для чтения</span><span class="sxs-lookup"><span data-stu-id="06ce4-125">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="06ce4-126">Практическое руководство. Добавление кавычек в строку</span><span class="sxs-lookup"><span data-stu-id="06ce4-126">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="06ce4-127">Практическое руководство. Многострочные элементы управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="06ce4-127">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="06ce4-128">Элемент управления TextBox</span><span class="sxs-lookup"><span data-stu-id="06ce4-128">TextBox Control</span></span>](textbox-control-windows-forms.md)
