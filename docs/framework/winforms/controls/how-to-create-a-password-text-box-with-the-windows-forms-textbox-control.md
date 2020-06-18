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
# <a name="how-to-create-a-password-text-box-with-the-windows-forms-textbox-control"></a>Практическое руководство. Создание текстового поля для ввода пароля с помощью элемента управления TextBox в Windows Forms

Поле пароля — это Windows Forms текстовое поле, которое отображает символы-заместители, когда пользователь вводит строку.

### <a name="to-create-a-password-text-box"></a>Создание текстового поля пароля

1. Задайте <xref:System.Windows.Forms.TextBox.PasswordChar%2A> <xref:System.Windows.Forms.TextBox> для свойства элемента управления конкретный символ.

    <xref:System.Windows.Forms.TextBox.PasswordChar%2A>Свойство определяет символ, отображаемый в текстовом поле. Например, если вы хотите, чтобы в поле пароль отображались звездочки, укажите * для <xref:System.Windows.Forms.TextBox.PasswordChar%2A> свойства в окно свойств. Затем, независимо от того, какой символ пользователь вводит в текстовое поле, отображается звездочка.

2. Используемых Задайте <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A> свойство. Свойство определяет, сколько символов можно ввести в текстовое поле. Если превышена максимальная длина, система выдает звуковой сигнал, и текстовое поле не принимает больше символов. Обратите внимание, что это может быть нежелательно, так как максимальная длина пароля может быть использована хакерами, пытающимися угадать пароль.

    В следующем примере кода показано, как инициализировать текстовое поле, которое будет принимать строку длиной до 14 символов и отображать звездочки вместо строки. `InitializeMyControl`Процедура не будет выполнена автоматически; ее необходимо вызвать.

    > [!IMPORTANT]
    > Использование <xref:System.Windows.Forms.TextBox.PasswordChar%2A> свойства в текстовом поле позволяет гарантировать, что другие пользователи не смогут определить пароль пользователя, если он следит за его вводом. Эта мера безопасности не охватывает никаких операций хранения или передачи пароля, которые могут возникать из-за логики приложения. Поскольку введенный текст не шифруется каким-либо образом, его следует обрабатывать так же, как любые другие конфиденциальные данные. Несмотря на то, что он не отображается, пароль по-прежнему обрабатывается как обычный текст (если не была реализована дополнительная мера безопасности).

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

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.TextBox>
- [Общие сведения об элементе управления TextBox](textbox-control-overview-windows-forms.md)
- [Практическое руководство. Управление положением курсора в элементе управления TextBox в Windows Forms](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Практическое руководство. Создание текстового поля только для чтения](how-to-create-a-read-only-text-box-windows-forms.md)
- [Практическое руководство. Добавление кавычек в строку](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Практическое руководство. Выделение текста в элементе управления TextBox в Windows Forms](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Практическое руководство. Многострочные элементы управления TextBox в Windows Forms](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [Элемент управления TextBox](textbox-control-windows-forms.md)
