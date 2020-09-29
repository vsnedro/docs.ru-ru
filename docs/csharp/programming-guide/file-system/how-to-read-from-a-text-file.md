---
title: Руководство по программированию на C#. Чтение из текстового файла
description: Узнайте, как считывать данные из текстового файла, используя статические методы из класса File. Изучите пример кода и ознакомьтесь с дополнительными ресурсами.
ms.date: 07/20/2015
f1_keywords:
- StreamReader.ReadToEnd
helpviewer_keywords:
- text files, writing to
- reading text files
- reading data, text files
- text files, reading
ms.assetid: 92246c5b-e819-4eea-9370-1a9460e12de3
ms.openlocfilehash: 64ac99ec0a72ba7df120f6732edccf160a351738
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201841"
---
# <a name="how-to-read-from-a-text-file-c-programming-guide"></a><span data-ttu-id="22e2b-104">Руководство по программированию на C#. Чтение из текстового файла</span><span class="sxs-lookup"><span data-stu-id="22e2b-104">How to read from a text file (C# Programming Guide)</span></span>

<span data-ttu-id="22e2b-105">В этом примере считывается содержимое текстового файла с помощью статических методов <xref:System.IO.File.ReadAllText%2A> и <xref:System.IO.File.ReadAllLines%2A> из класса <xref:System.IO.File?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="22e2b-105">This example reads the contents of a text file by using the static methods <xref:System.IO.File.ReadAllText%2A> and <xref:System.IO.File.ReadAllLines%2A> from the <xref:System.IO.File?displayProperty=nameWithType> class.</span></span>  
  
<span data-ttu-id="22e2b-106">См. пример использования <xref:System.IO.StreamReader> в руководстве по [построчному чтению текстового файла](./how-to-read-a-text-file-one-line-at-a-time.md).</span><span class="sxs-lookup"><span data-stu-id="22e2b-106">For an example that uses <xref:System.IO.StreamReader>, see [How to read a text file one line at a time](./how-to-read-a-text-file-one-line-at-a-time.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="22e2b-107">Файлы, которые используются в этом примере, созданы в руководстве по [записи в текстовый файл](./how-to-write-to-a-text-file.md).</span><span class="sxs-lookup"><span data-stu-id="22e2b-107">The files that are used in this example are created in the topic [How to write to a text file](./how-to-write-to-a-text-file.md).</span></span>
  
## <a name="example"></a><span data-ttu-id="22e2b-108">Пример</span><span class="sxs-lookup"><span data-stu-id="22e2b-108">Example</span></span>  

 [!code-csharp[csFilesandFolders#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#4)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="22e2b-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="22e2b-109">Compiling the Code</span></span>  

 <span data-ttu-id="22e2b-110">Скопируйте код и вставьте его в консольное приложение C#.</span><span class="sxs-lookup"><span data-stu-id="22e2b-110">Copy the code and paste it into a C# console application.</span></span>  
  
<span data-ttu-id="22e2b-111">Если вы не используете текстовые файлы из руководства по [записи в текстовый файл](./how-to-write-to-a-text-file.md), замените аргумент `ReadAllText` и `ReadAllLines` соответствующими путем и именем файла на компьютере.</span><span class="sxs-lookup"><span data-stu-id="22e2b-111">If you are not using the text files from [How to write to a text file](./how-to-write-to-a-text-file.md), replace the argument to `ReadAllText` and `ReadAllLines` with the appropriate path and file name on your computer.</span></span>
  
## <a name="robust-programming"></a><span data-ttu-id="22e2b-112">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="22e2b-112">Robust Programming</span></span>  

 <span data-ttu-id="22e2b-113">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="22e2b-113">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="22e2b-114">Файл не существует или не существует в указанном месте.</span><span class="sxs-lookup"><span data-stu-id="22e2b-114">The file doesn't exist or doesn't exist at the specified location.</span></span> <span data-ttu-id="22e2b-115">Проверьте правильность написания имени файла и путь к нему.</span><span class="sxs-lookup"><span data-stu-id="22e2b-115">Check the path and the spelling of the file name.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="22e2b-116">Безопасность .NET</span><span class="sxs-lookup"><span data-stu-id="22e2b-116">.NET Security</span></span>  

 <span data-ttu-id="22e2b-117">Не следует полагаться на имя файла, чтобы определить содержимое файла.</span><span class="sxs-lookup"><span data-stu-id="22e2b-117">Do not rely on the name of a file to determine the contents of the file.</span></span> <span data-ttu-id="22e2b-118">Например, файл `myFile.cs` может вовсе не быть исходным файлом C#.</span><span class="sxs-lookup"><span data-stu-id="22e2b-118">For example, the file `myFile.cs` might not be a C# source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22e2b-119">См. также</span><span class="sxs-lookup"><span data-stu-id="22e2b-119">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="22e2b-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="22e2b-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="22e2b-121">Файловая система и реестр (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="22e2b-121">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
