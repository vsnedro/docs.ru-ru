---
title: Руководство по программированию на C#. Вызов неуправляемого кода для воспроизведения WAV-файла
description: В этом примере кода C# показано, как использовать службы вызова неуправляемого кода для воспроизведения звуковых WAV-файлов в ОС Windows.
ms.date: 07/20/2015
helpviewer_keywords:
- platform invoke, sound files
- interoperability [C#], playing WAV files using pinvoke
- wav files
- .wav files
ms.assetid: f7f62f53-e026-4c40-b221-3a26adb0c2c5
ms.openlocfilehash: b30cb08e2dcde0eb85e8d88a690ae24bf7ae7f22
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302988"
---
# <a name="how-to-use-platform-invoke-to-play-a-wav-file-c-programming-guide"></a><span data-ttu-id="9cd13-103">Руководство по программированию на C#. Вызов неуправляемого кода для воспроизведения WAV-файла</span><span class="sxs-lookup"><span data-stu-id="9cd13-103">How to use platform invoke to play a WAV file (C# Programming Guide)</span></span>

<span data-ttu-id="9cd13-104">В следующем примере кода C# показано, как использовать службы вызова неуправляемого кода для воспроизведения звуковых WAV-файлов в ОС Windows.</span><span class="sxs-lookup"><span data-stu-id="9cd13-104">The following C# code example illustrates how to use platform invoke services to play a WAV sound file on the Windows operating system.</span></span>

## <a name="example"></a><span data-ttu-id="9cd13-105">Пример</span><span class="sxs-lookup"><span data-stu-id="9cd13-105">Example</span></span>

<span data-ttu-id="9cd13-106">В этом примере <xref:System.Runtime.InteropServices.DllImportAttribute> используется для импорта точки входа метода `PlaySound` файла `winmm.dll` как `Form1 PlaySound()`.</span><span class="sxs-lookup"><span data-stu-id="9cd13-106">This example code uses <xref:System.Runtime.InteropServices.DllImportAttribute> to import `winmm.dll`'s `PlaySound` method entry point as `Form1 PlaySound()`.</span></span> <span data-ttu-id="9cd13-107">Пример включает простую форму Windows с кнопкой.</span><span class="sxs-lookup"><span data-stu-id="9cd13-107">The example has a simple Windows Form with a button.</span></span> <span data-ttu-id="9cd13-108">При нажатии кнопки открывается стандартное диалоговое окно Windows <xref:System.Windows.Forms.OpenFileDialog>, позволяющее выбрать файл для воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="9cd13-108">Clicking the button opens a standard windows <xref:System.Windows.Forms.OpenFileDialog> dialog box so that you can open a file to play.</span></span> <span data-ttu-id="9cd13-109">Выбранный WAV-файл воспроизводится с помощью метода `PlaySound()` из метода библиотеки *winmm.dll*.</span><span class="sxs-lookup"><span data-stu-id="9cd13-109">When a wave file is selected, it is played by using the `PlaySound()` method of the *winmm.dll* library.</span></span> <span data-ttu-id="9cd13-110">Дополнительные сведения об этом методе см. в разделе [Использование функции PlaySound со звуковыми WAV-файлами](https://docs.microsoft.com/windows/desktop/multimedia/using-playsound-to-play-waveform-audio-files).</span><span class="sxs-lookup"><span data-stu-id="9cd13-110">For more information about this method, see [Using the PlaySound function with Waveform-Audio Files](https://docs.microsoft.com/windows/desktop/multimedia/using-playsound-to-play-waveform-audio-files).</span></span> <span data-ttu-id="9cd13-111">Найдите и выберите файл с расширением WAV и нажмите кнопку **Открыть**, чтобы воспроизвести этот WAV-файл, используя вызов неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="9cd13-111">Browse and select a file that has a .wav extension, and then click **Open** to play the wave file by using platform invoke.</span></span> <span data-ttu-id="9cd13-112">В текстовом поле отображается полный путь к выбранному файлу.</span><span class="sxs-lookup"><span data-stu-id="9cd13-112">A text box shows the full path of the file selected.</span></span>

<span data-ttu-id="9cd13-113">За счет указанных ниже настроек в диалоговом окне **Открыть файлы** отображаются только файлы с расширением WAV:</span><span class="sxs-lookup"><span data-stu-id="9cd13-113">The **Open Files** dialog box is filtered to show only files that have a .wav extension through the filter settings:</span></span>

[!code-csharp[csProgGuideInterop#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#5)]

[!code-csharp[csProgGuideInterop#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#3)]

## <a name="compiling-the-code"></a><span data-ttu-id="9cd13-114">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="9cd13-114">Compiling the code</span></span>

1. <span data-ttu-id="9cd13-115">Создайте проект приложения Windows Forms на C# в Visual Studio и назовите его **WinSound**.</span><span class="sxs-lookup"><span data-stu-id="9cd13-115">Create a new C# Windows Forms Application project in Visual Studio and name it **WinSound**.</span></span>

2. <span data-ttu-id="9cd13-116">Скопируйте указанный выше код и вставьте его поверх содержимого файла *Form1.cs*.</span><span class="sxs-lookup"><span data-stu-id="9cd13-116">Copy the code above, and paste it over the contents of the *Form1.cs* file.</span></span>

3. <span data-ttu-id="9cd13-117">Скопируйте следующий код и вставьте его в файл *Form1.Designer.cs* в метод `InitializeComponent()` после существующего кода.</span><span class="sxs-lookup"><span data-stu-id="9cd13-117">Copy the following code, and paste it in the *Form1.Designer.cs* file, in the `InitializeComponent()` method, after any existing code.</span></span>

     [!code-csharp[csProgGuideInterop#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#4)]

4. <span data-ttu-id="9cd13-118">Скомпилируйте и запустите код.</span><span class="sxs-lookup"><span data-stu-id="9cd13-118">Compile and run the code.</span></span>

## <a name="see-also"></a><span data-ttu-id="9cd13-119">См. также</span><span class="sxs-lookup"><span data-stu-id="9cd13-119">See also</span></span>

- [<span data-ttu-id="9cd13-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="9cd13-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="9cd13-121">Общие сведения о взаимодействии</span><span class="sxs-lookup"><span data-stu-id="9cd13-121">Interoperability Overview</span></span>](interoperability-overview.md)
- [<span data-ttu-id="9cd13-122">Подробный обзор вызова неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="9cd13-122">A Closer Look at Platform Invoke</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [<span data-ttu-id="9cd13-123">Маршалинг данных при вызове неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="9cd13-123">Marshaling Data with Platform Invoke</span></span>](../../../framework/interop/marshaling-data-with-platform-invoke.md)
