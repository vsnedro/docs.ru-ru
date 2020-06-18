---
title: Создание текстового поля для ввода пароля с помощью элемента управления TextBox
description: Узнайте, как создание текст Windows Forms, отображающий символы-заместители, в то время как пользователь вводит строку.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], entering passwords
- password boxes [Windows Forms], creating
- PasswordChar property in text boxes
- passwords [Windows Forms], input mask
- passwords [Windows Forms], password text box
ms.assetid: d105d6b9-3d50-44cd-80d8-2c0e2f486727
ms.openlocfilehash: 6d7e61eefa44ce3152aa77e3922bde471a4aeaf3
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904316"
---
# <a name="how-to-create-a-password-text-box-with-the-windows-forms-textbox-control"></a><span data-ttu-id="5c7e5-103">Практическое руководство. Создание текстового поля для ввода пароля с помощью элемента управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5c7e5-103">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>

<span data-ttu-id="5c7e5-104">Поле пароля — это Windows Forms текстовое поле, которое отображает символы-заместители, когда пользователь вводит строку.</span><span class="sxs-lookup"><span data-stu-id="5c7e5-104">A password box is a Windows Forms text box that displays placeholder characters while a user types a string.</span></span>

### <a name="to-create-a-password-text-box"></a><span data-ttu-id="5c7e5-105">Создание текстового поля пароля</span><span class="sxs-lookup"><span data-stu-id="5c7e5-105">To create a password text box</span></span>

1. <span data-ttu-id="5c7e5-106">Задайте <xref:System.Windows.Forms.TextBox.PasswordChar%2A> <xref:System.Windows.Forms.TextBox> для свойства элемента управления конкретный символ.</span><span class="sxs-lookup"><span data-stu-id="5c7e5-106">Set the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property of the <xref:System.Windows.Forms.TextBox> control to a specific character.</span></span>

    <span data-ttu-id="5c7e5-107"><xref:System.Windows.Forms.TextBox.PasswordChar%2A>Свойство определяет символ, отображаемый в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="5c7e5-107">The <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property specifies the character displayed in the text box.</span></span> <span data-ttu-id="5c7e5-108">Например, если вы хотите, чтобы в поле пароль отображались звездочки, укажите \* для <xref:System.Windows.Forms.TextBox.PasswordChar%2A> свойства в окно свойств.</span><span class="sxs-lookup"><span data-stu-id="5c7e5-108">For example, if you want asterisks displayed in the password box, specify \* for the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property in the Properties window.</span></span> <span data-ttu-id="5c7e5-109">Затем, независимо от того, какой символ пользователь вводит в текстовое поле, отображается звездочка.</span><span class="sxs-lookup"><span data-stu-id="5c7e5-109">Then, regardless of what character a user types in the text box, an asterisk is displayed.</span></span>

2. <span data-ttu-id="5c7e5-110">Используемых Задайте <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="5c7e5-110">(Optional) Set the <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A> property.</span></span> <span data-ttu-id="5c7e5-111">Свойство определяет, сколько символов можно ввести в текстовое поле.</span><span class="sxs-lookup"><span data-stu-id="5c7e5-111">The property determines how many characters can be typed in the text box.</span></span> <span data-ttu-id="5c7e5-112">Если превышена максимальная длина, система выдает звуковой сигнал, и текстовое поле не принимает больше символов.</span><span class="sxs-lookup"><span data-stu-id="5c7e5-112">If the maximum length is exceeded, the system emits a beep and the text box does not accept any more characters.</span></span> <span data-ttu-id="5c7e5-113">Обратите внимание, что это может быть нежелательно, так как максимальная длина пароля может быть использована хакерами, пытающимися угадать пароль.</span><span class="sxs-lookup"><span data-stu-id="5c7e5-113">Note that you may not wish to do this as the maximum length of a password may be of use to hackers who are trying to guess the password.</span></span>

    <span data-ttu-id="5c7e5-114">В следующем примере кода показано, как инициализировать текстовое поле, которое будет принимать строку длиной до 14 символов и отображать звездочки вместо строки.</span><span class="sxs-lookup"><span data-stu-id="5c7e5-114">The following code example shows how to initialize a text box that will accept a string up to 14 characters long and display asterisks in place of the string.</span></span> <span data-ttu-id="5c7e5-115">`InitializeMyControl`Процедура не будет выполнена автоматически; ее необходимо вызвать.</span><span class="sxs-lookup"><span data-stu-id="5c7e5-115">The `InitializeMyControl` procedure will not execute automatically; it must be called.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="5c7e5-116">Использование <xref:System.Windows.Forms.TextBox.PasswordChar%2A> свойства в текстовом поле позволяет гарантировать, что другие пользователи не смогут определить пароль пользователя, если он следит за его вводом.</span><span class="sxs-lookup"><span data-stu-id="5c7e5-116">Using the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property on a text box can help ensure that other people will not be able to determine a user's password if they observe the user entering it.</span></span> <span data-ttu-id="5c7e5-117">Эта мера безопасности не охватывает никаких операций хранения или передачи пароля, которые могут возникать из-за логики приложения.</span><span class="sxs-lookup"><span data-stu-id="5c7e5-117">This security measure does not cover any sort of storage or transmission of the password that can occur due to your application logic.</span></span> <span data-ttu-id="5c7e5-118">Поскольку введенный текст не шифруется каким-либо образом, его следует обрабатывать так же, как любые другие конфиденциальные данные.</span><span class="sxs-lookup"><span data-stu-id="5c7e5-118">Because the text entered is not encrypted in any way, you should treat it as you would any other confidential data.</span></span> <span data-ttu-id="5c7e5-119">Несмотря на то, что он не отображается, пароль по-прежнему обрабатывается как обычный текст (если не была реализована дополнительная мера безопасности).</span><span class="sxs-lookup"><span data-stu-id="5c7e5-119">Even though it does not appear as such, the password is still being treated as a plain-text string (unless you have implemented some additional security measure).</span></span>

    ```vb
    Private Sub InitializeMyControl()
       ' Set to no text.
       TextBox1.Text = ""
       ' The password character is an asterisk.
       TextBox1.PasswordChar = "*"
       ' The control will allow no more than 14 characters.
       TextBox1.MaxLength = 14
    End Sub
    ```

    ```csharp
    private void InitializeMyControl()
    {
       // Set to no text.
       textBox1.Text = "";
       // The password character is an asterisk.
       textBox1.PasswordChar = '*';
       // The control will allow no more than 14 characters.
       textBox1.MaxLength = 14;
    }
    ```

    ```cpp
    private:
       void InitializeMyControl()
       {
          // Set to no text.
          textBox1->Text = "";
          // The password character is an asterisk.
          textBox1->PasswordChar = '*';
          // The control will allow no more than 14 characters.
          textBox1->MaxLength = 14;
       }
    ```

## <a name="see-also"></a><span data-ttu-id="5c7e5-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5c7e5-120">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="5c7e5-121">Общие сведения об элементе управления TextBox</span><span class="sxs-lookup"><span data-stu-id="5c7e5-121">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="5c7e5-122">Практическое руководство. Управление положением курсора в элементе управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5c7e5-122">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="5c7e5-123">Практическое руководство. Создание текстового поля только для чтения</span><span class="sxs-lookup"><span data-stu-id="5c7e5-123">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="5c7e5-124">Практическое руководство. Добавление кавычек в строку</span><span class="sxs-lookup"><span data-stu-id="5c7e5-124">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="5c7e5-125">Практическое руководство. Выделение текста в элементе управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5c7e5-125">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="5c7e5-126">Практическое руководство. Многострочные элементы управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5c7e5-126">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="5c7e5-127">Элемент управления TextBox</span><span class="sxs-lookup"><span data-stu-id="5c7e5-127">TextBox Control</span></span>](textbox-control-windows-forms.md)
