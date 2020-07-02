---
title: Практическое руководство. Воспроизведение звука в Windows Forms
description: Узнайте, как воспроизвести звук из формы Windows в заданном пути во время выполнения. Кроме того, Узнайте о компиляции кода и платформы безопасности .NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- playing sounds [Windows Forms], Windows Forms
- sounds [Windows Forms], playing
- sounds
- My.Computer.Audio object [Windows Forms], playing sounds
- examples [Windows Forms], sounds
ms.assetid: 3d3350b7-1ebd-4e05-a738-48ca1160a19d
ms.openlocfilehash: beb17d994e224f41b2b590ecb1401988cdad314d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85613752"
---
# <a name="how-to-play-a-sound-from-a-windows-form"></a><span data-ttu-id="d7618-104">Практическое руководство. Воспроизведение звука в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d7618-104">How to: Play a Sound from a Windows Form</span></span>
<span data-ttu-id="d7618-105">В этом примере воспроизводится звук по заданному пути во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="d7618-105">This example plays a sound at a given path at run time.</span></span>

## <a name="example"></a><span data-ttu-id="d7618-106">Пример</span><span class="sxs-lookup"><span data-stu-id="d7618-106">Example</span></span>

```vb
Sub PlaySimpleSound()
    My.Computer.Audio.Play("c:\Windows\Media\chimes.wav")
End Sub
```

```csharp
private void playSimpleSound()
{
    SoundPlayer simpleSound = new SoundPlayer(@"c:\Windows\Media\chimes.wav");
    simpleSound.Play();
}
```

## <a name="compiling-the-code"></a><span data-ttu-id="d7618-107">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="d7618-107">Compiling the Code</span></span>
 <span data-ttu-id="d7618-108">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="d7618-108">This example requires:</span></span>

- <span data-ttu-id="d7618-109">замена имени файла `"c:\Windows\Media\chimes.wav"` на допустимое имя файла.</span><span class="sxs-lookup"><span data-stu-id="d7618-109">That you replace the file name `"c:\Windows\Media\chimes.wav"` with a valid file name.</span></span>

- <span data-ttu-id="d7618-110">См Ссылка на <xref:System.Media?displayProperty=nameWithType> пространство имен.</span><span class="sxs-lookup"><span data-stu-id="d7618-110">(C#) A reference to the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>

## <a name="robust-programming"></a><span data-ttu-id="d7618-111">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="d7618-111">Robust Programming</span></span>
 <span data-ttu-id="d7618-112">Операции с файлами должны быть включены в соответствующие структурированные блоки обработки исключений.</span><span class="sxs-lookup"><span data-stu-id="d7618-112">File operations should be enclosed within appropriate structured exception handling blocks.</span></span>

 <span data-ttu-id="d7618-113">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="d7618-113">The following conditions may cause an exception:</span></span>

- <span data-ttu-id="d7618-114">Недопустимое имя пути</span><span class="sxs-lookup"><span data-stu-id="d7618-114">The path name is malformed.</span></span> <span data-ttu-id="d7618-115">Например, оно содержит недопустимые символы или состоит из одних пробелов (класс <xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="d7618-115">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException> class).</span></span>

- <span data-ttu-id="d7618-116">Путь доступен только для чтения (класс <xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="d7618-116">The path is read-only (<xref:System.IO.IOException> class).</span></span>

- <span data-ttu-id="d7618-117">Имя пути — `null` (класс <xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="d7618-117">The path name is `null` (<xref:System.ArgumentNullException> class).</span></span>

- <span data-ttu-id="d7618-118">Указано слишком длинное имя пути (класс <xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="d7618-118">The path name is too long (<xref:System.IO.PathTooLongException> class).</span></span>

- <span data-ttu-id="d7618-119">Недопустимый путь (класс <xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="d7618-119">The path is invalid (<xref:System.IO.DirectoryNotFoundException> class).</span></span>

- <span data-ttu-id="d7618-120">Путь представляет собой только двоеточие, ":" ( <xref:System.NotSupportedException> класс).</span><span class="sxs-lookup"><span data-stu-id="d7618-120">The path is only a colon, ":" (<xref:System.NotSupportedException> class).</span></span>

## <a name="net-framework-security"></a><span data-ttu-id="d7618-121">Безопасность .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d7618-121">.NET Framework Security</span></span>
 <span data-ttu-id="d7618-122">По имени файла не всегда можно с уверенностью судить о его содержимом.</span><span class="sxs-lookup"><span data-stu-id="d7618-122">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="d7618-123">Например, файл с именем `Form1.vb` может вовсе не быть исходным файлом Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d7618-123">For example, the file `Form1.vb` may not be a Visual Basic source file.</span></span> <span data-ttu-id="d7618-124">Следует проверять все входные данные перед использованием их в приложении.</span><span class="sxs-lookup"><span data-stu-id="d7618-124">Verify all inputs before using the data in your application.</span></span>

## <a name="see-also"></a><span data-ttu-id="d7618-125">См. также</span><span class="sxs-lookup"><span data-stu-id="d7618-125">See also</span></span>

- <xref:System.Media.SoundPlayer>
- [<span data-ttu-id="d7618-126">Практическое руководство. Асинхронная загрузка звука в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d7618-126">How to: Load a Sound Asynchronously within a Windows Form</span></span>](how-to-load-a-sound-asynchronously-within-a-windows-form.md)
