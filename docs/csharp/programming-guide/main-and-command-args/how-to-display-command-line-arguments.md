---
title: Руководство по программированию на C#. Отображение аргументов командной строки
description: Узнайте, как отобразить аргументы командной строки. Изучите пример кода и ознакомьтесь с дополнительными ресурсами.
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
ms.openlocfilehash: 717e27c23724e63c03a38b028ef99dc6530b4745
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195484"
---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a><span data-ttu-id="2a2bb-104">Руководство по программированию на C#. Отображение аргументов командной строки</span><span class="sxs-lookup"><span data-stu-id="2a2bb-104">How to display command-line arguments (C# Programming Guide)</span></span>

<span data-ttu-id="2a2bb-105">Аргументы, предоставляемые исполняемому файлу в командной строке, доступны через необязательный параметр для `Main`.</span><span class="sxs-lookup"><span data-stu-id="2a2bb-105">Arguments provided to an executable on the command line are accessible through an optional parameter to `Main`.</span></span> <span data-ttu-id="2a2bb-106">Аргументы предоставляются в форме массива строк.</span><span class="sxs-lookup"><span data-stu-id="2a2bb-106">The arguments are provided in the form of an array of strings.</span></span> <span data-ttu-id="2a2bb-107">Каждый элемент массива содержит один аргумент.</span><span class="sxs-lookup"><span data-stu-id="2a2bb-107">Each element of the array contains one argument.</span></span> <span data-ttu-id="2a2bb-108">Пробелы между аргументами удаляются.</span><span class="sxs-lookup"><span data-stu-id="2a2bb-108">White-space between arguments is removed.</span></span> <span data-ttu-id="2a2bb-109">Например, рассмотрим следующие вызовы из командной строки вымышленного исполняемого файла:</span><span class="sxs-lookup"><span data-stu-id="2a2bb-109">For example, consider these command-line invocations of a fictitious executable:</span></span>  
  
|<span data-ttu-id="2a2bb-110">Входные данные в командной строке</span><span class="sxs-lookup"><span data-stu-id="2a2bb-110">Input on command line</span></span>|<span data-ttu-id="2a2bb-111">Массив строк, передаваемых в метод Main</span><span class="sxs-lookup"><span data-stu-id="2a2bb-111">Array of strings passed to Main</span></span>|  
|----------------------------|-------------------------------------|  
|<span data-ttu-id="2a2bb-112">**executable.exe a b c**</span><span class="sxs-lookup"><span data-stu-id="2a2bb-112">**executable.exe a b c**</span></span>|<span data-ttu-id="2a2bb-113">"a"</span><span class="sxs-lookup"><span data-stu-id="2a2bb-113">"a"</span></span><br /><br /> <span data-ttu-id="2a2bb-114">"b"</span><span class="sxs-lookup"><span data-stu-id="2a2bb-114">"b"</span></span><br /><br /> <span data-ttu-id="2a2bb-115">"c"</span><span class="sxs-lookup"><span data-stu-id="2a2bb-115">"c"</span></span>|  
|<span data-ttu-id="2a2bb-116">**executable.exe one two**</span><span class="sxs-lookup"><span data-stu-id="2a2bb-116">**executable.exe one two**</span></span>|<span data-ttu-id="2a2bb-117">"one"</span><span class="sxs-lookup"><span data-stu-id="2a2bb-117">"one"</span></span><br /><br /> <span data-ttu-id="2a2bb-118">"two"</span><span class="sxs-lookup"><span data-stu-id="2a2bb-118">"two"</span></span>|  
|<span data-ttu-id="2a2bb-119">**executable.exe "one two" three**</span><span class="sxs-lookup"><span data-stu-id="2a2bb-119">**executable.exe "one two" three**</span></span>|<span data-ttu-id="2a2bb-120">"один два"</span><span class="sxs-lookup"><span data-stu-id="2a2bb-120">"one two"</span></span><br /><br /> <span data-ttu-id="2a2bb-121">"три"</span><span class="sxs-lookup"><span data-stu-id="2a2bb-121">"three"</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="2a2bb-122">При выполнении приложения в Visual Studio аргументы командной строки можно указать на [странице "Отладка" в конструкторе проектов](/visualstudio/ide/reference/debug-page-project-designer).</span><span class="sxs-lookup"><span data-stu-id="2a2bb-122">When you are running an application in Visual Studio, you can specify command-line arguments in the [Debug Page, Project Designer](/visualstudio/ide/reference/debug-page-project-designer).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a2bb-123">Пример</span><span class="sxs-lookup"><span data-stu-id="2a2bb-123">Example</span></span>  

 <span data-ttu-id="2a2bb-124">Этот пример отображает аргументы командной строки, передаваемые в приложение командной строки.</span><span class="sxs-lookup"><span data-stu-id="2a2bb-124">This example displays the command-line arguments passed to a command-line application.</span></span> <span data-ttu-id="2a2bb-125">Показанные выходные данные — первая запись в таблице выше.</span><span class="sxs-lookup"><span data-stu-id="2a2bb-125">The output shown is for the first entry in the table above.</span></span>  
  
 [!code-csharp[csProgGuideMain#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="2a2bb-126">См. также</span><span class="sxs-lookup"><span data-stu-id="2a2bb-126">See also</span></span>

- [<span data-ttu-id="2a2bb-127">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="2a2bb-127">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="2a2bb-128">Сборка из командной строки с помощью csc.exe</span><span class="sxs-lookup"><span data-stu-id="2a2bb-128">Command-line Building With csc.exe</span></span>](../../language-reference/compiler-options/command-line-building-with-csc-exe.md)
- [<span data-ttu-id="2a2bb-129">Main() и аргументы командной строки</span><span class="sxs-lookup"><span data-stu-id="2a2bb-129">Main() and Command-Line Arguments</span></span>](./index.md)
- [<span data-ttu-id="2a2bb-130">Значения, возвращаемые методом main()</span><span class="sxs-lookup"><span data-stu-id="2a2bb-130">Main() Return Values</span></span>](./main-return-values.md)
