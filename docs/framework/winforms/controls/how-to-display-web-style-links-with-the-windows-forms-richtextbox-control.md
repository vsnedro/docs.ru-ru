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
# <a name="how-to-display-web-style-links-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="af405-102">Практическое руководство. Отображение ссылок веб-типа с помощью элемента управления RichTextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="af405-102">How to: Display Web-Style Links with the Windows Forms RichTextBox Control</span></span>

<span data-ttu-id="af405-103"><xref:System.Windows.Forms.RichTextBox>Элемент управления Windows Forms может отображать веб-ссылки как цветные и подчеркнутые.</span><span class="sxs-lookup"><span data-stu-id="af405-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control can display Web links as colored and underlined.</span></span> <span data-ttu-id="af405-104">Можно написать код, открывающий окно браузера, в котором отображается веб-сайт, указанный в тексте ссылки при щелчке ссылки.</span><span class="sxs-lookup"><span data-stu-id="af405-104">You can write code that opens a browser window showing the Web site specified in the link text when the link is clicked.</span></span>

### <a name="to-link-to-a-web-page-with-the-richtextbox-control"></a><span data-ttu-id="af405-105">Ссылка на веб-страницу с помощью элемента управления RichTextBox</span><span class="sxs-lookup"><span data-stu-id="af405-105">To link to a Web page with the RichTextBox control</span></span>

1. <span data-ttu-id="af405-106">Задайте <xref:System.Windows.Forms.RichTextBox.Text%2A> для свойства строку, содержащую допустимый URL-адрес (например, " https://www.microsoft.com/ ").</span><span class="sxs-lookup"><span data-stu-id="af405-106">Set the <xref:System.Windows.Forms.RichTextBox.Text%2A> property to a string that includes a valid URL (for example, "https://www.microsoft.com/").</span></span>

2. <span data-ttu-id="af405-107">Убедитесь, что <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> свойство имеет значение `true` (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="af405-107">Make sure the <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> property is set to `true` (the default).</span></span>

3. <span data-ttu-id="af405-108">Создайте новый глобальный экземпляр <xref:System.Diagnostics.Process> объекта.</span><span class="sxs-lookup"><span data-stu-id="af405-108">Create a new global instance of the <xref:System.Diagnostics.Process> object.</span></span>

4. <span data-ttu-id="af405-109">Напишите обработчик событий для <xref:System.Windows.Forms.RichTextBox.LinkClicked> события, которое отправляет браузеру нужный текст.</span><span class="sxs-lookup"><span data-stu-id="af405-109">Write an event handler for the <xref:System.Windows.Forms.RichTextBox.LinkClicked> event that sends the browser the desired text.</span></span>

    <span data-ttu-id="af405-110">В приведенном ниже примере <xref:System.Windows.Forms.RichTextBox.LinkClicked> событие открывает экземпляр Internet Explorer по URL-адресу, указанному в <xref:System.Windows.Forms.RichTextBox.Text%2A> свойстве <xref:System.Windows.Forms.RichTextBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="af405-110">In the example below, the <xref:System.Windows.Forms.RichTextBox.LinkClicked> event opens an instance of Internet Explorer to the URL specified in the <xref:System.Windows.Forms.RichTextBox.Text%2A> property of the <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="af405-111">В этом примере предполагается наличие формы с <xref:System.Windows.Forms.RichTextBox> элементом управления.</span><span class="sxs-lookup"><span data-stu-id="af405-111">This example assumes a form with a <xref:System.Windows.Forms.RichTextBox> control.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="af405-112">При вызове <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> метода возникает <xref:System.Security.SecurityException> исключение, если код выполняется в контексте частичного доверия из-за недостаточных привилегий.</span><span class="sxs-lookup"><span data-stu-id="af405-112">In calling the <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> method, you will encounter a <xref:System.Security.SecurityException> exception if you are running the code in a partial-trust context because of insufficient privileges.</span></span> <span data-ttu-id="af405-113">Дополнительные сведения см. в разделе [Code Access Security Basics](../../misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="af405-113">For more information, see [Code Access Security Basics](../../misc/code-access-security-basics.md).</span></span>

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

    <span data-ttu-id="af405-114">(Visual C++) Для этого необходимо инициализировать процесс, добавив в `p` конструктор формы следующую инструкцию:</span><span class="sxs-lookup"><span data-stu-id="af405-114">(Visual C++) You must initialize process `p`, which you can do by including the following statement in the constructor of your form:</span></span>

    ```cpp
    p = gcnew System::Diagnostics::Process();
    ```

    <span data-ttu-id="af405-115">(Visual C#, Visual C++) Поместите следующий код в конструктор формы для регистрации обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="af405-115">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>

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

    <span data-ttu-id="af405-116">Важно немедленно завершить процесс, созданный после завершения работы с ним.</span><span class="sxs-lookup"><span data-stu-id="af405-116">It is important to immediately stop the process you have created once you have finished working with it.</span></span> <span data-ttu-id="af405-117">При указании кода, приведенного выше, код для завершения процесса может выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="af405-117">Referring to the code presented above, your code to stop the process might look like this:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="af405-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="af405-118">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>
- <xref:System.Windows.Forms.RichTextBox.LinkClicked>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="af405-119">Элемент управления RichTextBox</span><span class="sxs-lookup"><span data-stu-id="af405-119">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="af405-120">Элементы управления для использования в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="af405-120">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
