---
title: Как открыть файлы с помощью компонента OpenFileDialog
ms.date: 02/11/2019
description: Узнайте, как использовать компонент OpenFileDialog, чтобы открыть диалоговое окно Windows для обзора и выбора файлов.
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], opening files
- OpenFile method [Windows Forms], OpenFileDialog component
- files [Windows Forms], opening with OpenFileDialog component
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
ms.openlocfilehash: d571885011b0f0c723c73a417f294f30f96952f4
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904433"
---
# <a name="how-to-open-files-with-the-openfiledialog"></a><span data-ttu-id="75f47-103">Как открыть файлы с помощью OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="75f47-103">How to: Open files with the OpenFileDialog</span></span>

<span data-ttu-id="75f47-104"><xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType>Компонент открывает диалоговое окно Windows для обзора и выбора файлов.</span><span class="sxs-lookup"><span data-stu-id="75f47-104">The <xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType> component opens the Windows dialog box for browsing and selecting files.</span></span> <span data-ttu-id="75f47-105">Чтобы открыть и прочитать выбранные файлы, можно использовать <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType> метод или создать экземпляр <xref:System.IO.StreamReader?displayProperty=nameWithType> класса.</span><span class="sxs-lookup"><span data-stu-id="75f47-105">To open and read the selected files, you can use the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType> method, or create an instance of the <xref:System.IO.StreamReader?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="75f47-106">В следующих примерах показаны оба подхода.</span><span class="sxs-lookup"><span data-stu-id="75f47-106">The following examples show both approaches.</span></span>

<span data-ttu-id="75f47-107">В .NET Framework для получения или задания <xref:System.Windows.Forms.FileDialog.FileName%2A> свойства требуется уровень привилегий, предоставляемый <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> классом.</span><span class="sxs-lookup"><span data-stu-id="75f47-107">In .NET Framework, to get or set the <xref:System.Windows.Forms.FileDialog.FileName%2A> property requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="75f47-108">В примерах выполняется <xref:System.Security.Permissions.FileIOPermission> Проверка разрешений и может вызываться исключение из-за недостаточных привилегий при выполнении в контексте частичного доверия.</span><span class="sxs-lookup"><span data-stu-id="75f47-108">The examples run a <xref:System.Security.Permissions.FileIOPermission> permission check, and can throw an exception due to insufficient privileges if run in a partial-trust context.</span></span> <span data-ttu-id="75f47-109">Дополнительные сведения см. в статье [основы управления доступом для кода](../../misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="75f47-109">For more information, see [Code access security basics](../../misc/code-access-security-basics.md).</span></span>

<span data-ttu-id="75f47-110">Вы можете собрать и запустить эти примеры как .NET Framework приложения из командной строки C# или Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="75f47-110">You can build and run these examples as .NET Framework apps from the C# or Visual Basic command line.</span></span> <span data-ttu-id="75f47-111">Дополнительные сведения см. в разделе [Построение из командной строки с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) или [Сборка из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="75f47-111">For more information, see [Command-line building with csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) or [Build from the command line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span>

<span data-ttu-id="75f47-112">Начиная с .NET Core 3,0, можно также создавать и запускать примеры как приложения Windows .NET Core из папки с файлом проекта .NET Core Windows Forms \* \<folder name> . csproj\* .</span><span class="sxs-lookup"><span data-stu-id="75f47-112">Starting with .NET Core 3.0, you can also build and run the examples as Windows .NET Core apps from a folder that has a .NET Core Windows Forms *\<folder name>.csproj* project file.</span></span>

## <a name="example-read-a-file-as-a-stream-with-streamreader"></a><span data-ttu-id="75f47-113">Пример. чтение файла в виде потока с помощью StreamReader</span><span class="sxs-lookup"><span data-stu-id="75f47-113">Example: Read a file as a stream with StreamReader</span></span>  
  
<span data-ttu-id="75f47-114">В следующем примере используется <xref:System.Windows.Forms.Button> обработчик событий Windows Forms элемента управления <xref:System.Windows.Forms.Control.Click> для открытия <xref:System.Windows.Forms.OpenFileDialog> с помощью <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> метода.</span><span class="sxs-lookup"><span data-stu-id="75f47-114">The following example uses the Windows Forms <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler to open the <xref:System.Windows.Forms.OpenFileDialog> with the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span> <span data-ttu-id="75f47-115">После того как пользователь выберет файл и нажмет **кнопку ОК**, экземпляр <xref:System.IO.StreamReader> класса считывает файл и отображает его содержимое в текстовом поле формы.</span><span class="sxs-lookup"><span data-stu-id="75f47-115">After the user chooses a file and selects **OK**, an instance of the <xref:System.IO.StreamReader> class reads the file and displays its contents in the form's text box.</span></span> <span data-ttu-id="75f47-116">Дополнительные сведения о чтении из файловых потоков см <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> . в разделе и <xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="75f47-116">For more information about reading from file streams, see <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> and <xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType>.</span></span>  

 [!code-csharp[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/vb/Form1.vb)]  

## <a name="example-open-a-file-from-a-filtered-selection-with-openfile"></a><span data-ttu-id="75f47-117">Пример. Открытие файла из отфильтрованного выделенного фрагмента с помощью OpenFile</span><span class="sxs-lookup"><span data-stu-id="75f47-117">Example: Open a file from a filtered selection with OpenFile</span></span>

<span data-ttu-id="75f47-118">В следующем примере <xref:System.Windows.Forms.Button> обработчик событий элемента управления используется <xref:System.Windows.Forms.Control.Click> для открытия <xref:System.Windows.Forms.OpenFileDialog> с фильтром, который отображает только текстовые файлы.</span><span class="sxs-lookup"><span data-stu-id="75f47-118">The following example uses the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler to open the <xref:System.Windows.Forms.OpenFileDialog> with a filter that shows only text files.</span></span> <span data-ttu-id="75f47-119">После того как пользователь выберет текстовый файл и нажмет **кнопку ОК**, <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> для открытия файла в блокноте используется метод.</span><span class="sxs-lookup"><span data-stu-id="75f47-119">After the user chooses a text file and selects **OK**, the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method is used to open the file in Notepad.</span></span>

 [!code-csharp[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/vb/Form1.vb)]  

## <a name="see-also"></a><span data-ttu-id="75f47-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="75f47-120">See also</span></span>

- <xref:System.Windows.Forms.OpenFileDialog>
- [<span data-ttu-id="75f47-121">Компонент OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="75f47-121">OpenFileDialog component</span></span>](openfiledialog-component-windows-forms.md)
