---
title: Руководство по программированию на C#. Построчное чтение текстового файла
description: Сведения о построчном чтении текстового файла. Изучите пример кода и ознакомьтесь с дополнительными ресурсами.
ms.date: 07/20/2015
helpviewer_keywords:
- ReadLine method [C#]
- reading text files, line by line
- text files [C#]
ms.assetid: d62e22c5-a13c-48db-af9b-f10c801b0cb1
ms.openlocfilehash: 1e29013b1008e1000c23804dc3056014cc7c104b
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301961"
---
# <a name="how-to-read-a-text-file-one-line-at-a-time-c-programming-guide"></a><span data-ttu-id="723ab-104">Руководство по программированию на C#. Построчное чтение текстового файла</span><span class="sxs-lookup"><span data-stu-id="723ab-104">How to read a text file one line at a time (C# Programming Guide)</span></span>
<span data-ttu-id="723ab-105">В этом примере производится построчное чтение содержимого текстового файла в строку с помощью метода `ReadLine` класса `StreamReader`.</span><span class="sxs-lookup"><span data-stu-id="723ab-105">This example reads the contents of a text file, one line at a time, into a string using the `ReadLine` method of the `StreamReader` class.</span></span> <span data-ttu-id="723ab-106">Каждая строка текста сохраняется в строке `line` и отображается на экране.</span><span class="sxs-lookup"><span data-stu-id="723ab-106">Each text line is stored into the string `line` and displayed on the screen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="723ab-107">Пример</span><span class="sxs-lookup"><span data-stu-id="723ab-107">Example</span></span>  
  
```csharp
int counter = 0;  
string line;  
  
// Read the file and display it line by line.  
System.IO.StreamReader file =
    new System.IO.StreamReader(@"c:\test.txt");  
while((line = file.ReadLine()) != null)  
{  
    System.Console.WriteLine(line);  
    counter++;  
}  
  
file.Close();  
System.Console.WriteLine("There were {0} lines.", counter);  
// Suspend the screen.  
System.Console.ReadLine();  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="723ab-108">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="723ab-108">Compiling the Code</span></span>  
 <span data-ttu-id="723ab-109">Скопируйте код и вставьте его в метод `Main` консольного приложения.</span><span class="sxs-lookup"><span data-stu-id="723ab-109">Copy the code and paste it into the `Main` method of a console application.</span></span>  
  
 <span data-ttu-id="723ab-110">Замените `"c:\test.txt"` фактическим именем файла.</span><span class="sxs-lookup"><span data-stu-id="723ab-110">Replace `"c:\test.txt"` with the actual file name.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="723ab-111">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="723ab-111">Robust Programming</span></span>  
 <span data-ttu-id="723ab-112">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="723ab-112">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="723ab-113">Возможно, файл не существует.</span><span class="sxs-lookup"><span data-stu-id="723ab-113">The file may not exist.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="723ab-114">Безопасность .NET</span><span class="sxs-lookup"><span data-stu-id="723ab-114">.NET Security</span></span>  
 <span data-ttu-id="723ab-115">По имени файла не всегда можно с уверенностью судить о его содержимом.</span><span class="sxs-lookup"><span data-stu-id="723ab-115">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="723ab-116">Например, файл с именем `myFile.cs` может вовсе не быть исходным файлом C#.</span><span class="sxs-lookup"><span data-stu-id="723ab-116">For example, the file `myFile.cs` may not be a C# source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="723ab-117">См. также</span><span class="sxs-lookup"><span data-stu-id="723ab-117">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="723ab-118">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="723ab-118">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="723ab-119">Файловая система и реестр (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="723ab-119">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
