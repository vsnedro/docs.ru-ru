---
title: Отображение веб-ссылок с помощью элемента управления RichTextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- text boxes [Windows Forms], displaying Web links
- examples [Windows Forms], text boxes
- RichTextBox control [Windows Forms], linking to Web pages
ms.assetid: 95089a37-a202-4f7a-94ee-6ee312908851
ms.openlocfilehash: 06ed304e566bb437a2353dd330d7de5328f2a729
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144829"
---
# <a name="how-to-display-web-style-links-with-the-windows-forms-richtextbox-control"></a>Практическое руководство. Отображение ссылок веб-типа с помощью элемента управления RichTextBox в Windows Forms

<xref:System.Windows.Forms.RichTextBox>Элемент управления Windows Forms может отображать веб-ссылки как цветные и подчеркнутые. Можно написать код, открывающий окно браузера, в котором отображается веб-сайт, указанный в тексте ссылки при щелчке ссылки.

### <a name="to-link-to-a-web-page-with-the-richtextbox-control"></a>Ссылка на веб-страницу с помощью элемента управления RichTextBox

1. Задайте <xref:System.Windows.Forms.RichTextBox.Text%2A> для свойства строку, содержащую допустимый URL-адрес (например, " https://www.microsoft.com/ ").

2. Убедитесь, что <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> свойство имеет значение `true` (по умолчанию).

3. Создайте новый глобальный экземпляр <xref:System.Diagnostics.Process> объекта.

4. Напишите обработчик событий для <xref:System.Windows.Forms.RichTextBox.LinkClicked> события, которое отправляет браузеру нужный текст.

    В приведенном ниже примере <xref:System.Windows.Forms.RichTextBox.LinkClicked> событие открывает экземпляр Internet Explorer по URL-адресу, указанному в <xref:System.Windows.Forms.RichTextBox.Text%2A> свойстве <xref:System.Windows.Forms.RichTextBox> элемента управления. В этом примере предполагается наличие формы с <xref:System.Windows.Forms.RichTextBox> элементом управления.

    > [!IMPORTANT]
    > При вызове <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> метода возникает <xref:System.Security.SecurityException> исключение, если код выполняется в контексте частичного доверия из-за недостаточных привилегий. Дополнительные сведения см. в разделе [Code Access Security Basics](../../misc/code-access-security-basics.md).

    ```vb
    Public p As New System.Diagnostics.Process
    Private Sub RichTextBox1_LinkClicked _
       (ByVal sender As Object, ByVal e As _
       System.Windows.Forms.LinkClickedEventArgs) _
       Handles RichTextBox1.LinkClicked
          ' Call Process.Start method to open a browser
          ' with link text as URL.
          p = System.Diagnostics.Process.Start("IExplore.exe", e.LinkText)
    End Sub
    ```

    ```csharp
    public System.Diagnostics.Process p = new System.Diagnostics.Process();

    private void richTextBox1_LinkClicked(object sender,
    System.Windows.Forms.LinkClickedEventArgs e)
    {
       // Call Process.Start method to open a browser
       // with link text as URL.
       p = System.Diagnostics.Process.Start("IExplore.exe", e.LinkText);
    }
    ```

    ```cpp
    public:
       System::Diagnostics::Process ^ p;

    private:
       void richTextBox1_LinkClicked(System::Object ^  sender,
          System::Windows::Forms::LinkClickedEventArgs ^  e)
       {
          // Call Process.Start method to open a browser
          // with link text as URL.
          p = System::Diagnostics::Process::Start("IExplore.exe",
             e->LinkText);
       }
    ```

    (Visual C++) Для этого необходимо инициализировать процесс, добавив в `p` конструктор формы следующую инструкцию:

    ```cpp
    p = gcnew System::Diagnostics::Process();
    ```

    (Visual C#, Visual C++) Поместите следующий код в конструктор формы для регистрации обработчика событий.

    ```csharp
    this.richTextBox1.LinkClicked += new
       System.Windows.Forms.LinkClickedEventHandler
       (this.richTextBox1_LinkClicked);
    ```

    ```cpp
    this->richTextBox1->LinkClicked += gcnew
       System::Windows::Forms::LinkClickedEventHandler
       (this, &Form1::richTextBox1_LinkClicked);
    ```

    Важно немедленно завершить процесс, созданный после завершения работы с ним. При указании кода, приведенного выше, код для завершения процесса может выглядеть следующим образом:

    ```vb
    Public Sub StopWebProcess()
       p.Kill()
    End Sub
    ```

    ```csharp
    public void StopWebProcess()
    {
       p.Kill();
    }
    ```

    ```cpp
    public: void StopWebProcess()
    {
       p->Kill();
    }
    ```

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>
- <xref:System.Windows.Forms.RichTextBox.LinkClicked>
- <xref:System.Windows.Forms.RichTextBox>
- [Элемент управления RichTextBox](richtextbox-control-windows-forms.md)
- [Элементы управления для использования в формах Windows Forms](controls-to-use-on-windows-forms.md)
