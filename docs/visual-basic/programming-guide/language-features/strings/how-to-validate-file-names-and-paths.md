---
title: Практическое руководство. Проверка имен файлов и путей
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], validating
- strings [Visual Basic], validating
- Boolean values [Visual Basic]
- paths [Visual Basic], validating
ms.assetid: f673462d-57b7-4120-b13a-6a7592f7ab2c
ms.openlocfilehash: b722222ea8b8088a6b326eef27147c08f8419272
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91072656"
---
# <a name="how-to-validate-file-names-and-paths-in-visual-basic"></a><span data-ttu-id="e1963-102">Практическое руководство. Проверка имен файлов и путей в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e1963-102">How to: Validate File Names and Paths in Visual Basic</span></span>

<span data-ttu-id="e1963-103">В этом примере возвращается `Boolean` значение, указывающее, представляет ли строка имя файла или путь.</span><span class="sxs-lookup"><span data-stu-id="e1963-103">This example returns a `Boolean` value that indicates whether a string represents a file name or path.</span></span> <span data-ttu-id="e1963-104">Проверка проверяет, содержит ли имя символы, недопустимые в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="e1963-104">The validation checks if the name contains characters that are not allowed by the file system.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1963-105">Пример</span><span class="sxs-lookup"><span data-stu-id="e1963-105">Example</span></span>  

 [!code-vb[VbVbcnRegEx#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#4)]  
  
 <span data-ttu-id="e1963-106">В этом примере не проверяется, неправильно ли в имени размещены двоеточия или каталоги без имени, или значение, если длина имени превышает максимальную длину, определенную системой.</span><span class="sxs-lookup"><span data-stu-id="e1963-106">This example does not check if the name has incorrectly placed colons, or directories with no name, or if the length of the name exceeds the system-defined maximum length.</span></span> <span data-ttu-id="e1963-107">Он также не проверяет, имеет ли приложение разрешение на доступ к ресурсу файловой системы с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="e1963-107">It also does not check if the application has permission to access the file-system resource with the specified name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1963-108">См. также</span><span class="sxs-lookup"><span data-stu-id="e1963-108">See also</span></span>

- <xref:System.IO.Path.GetInvalidPathChars%2A>
- [<span data-ttu-id="e1963-109">Проверка строк в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e1963-109">Validating Strings in Visual Basic</span></span>](validating-strings.md)
