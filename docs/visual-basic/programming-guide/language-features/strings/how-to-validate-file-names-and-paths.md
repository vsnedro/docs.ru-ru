---
title: Практическое руководство. Проверка имен файлов и путей
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], validating
- strings [Visual Basic], validating
- Boolean values [Visual Basic]
- paths [Visual Basic], validating
ms.assetid: f673462d-57b7-4120-b13a-6a7592f7ab2c
ms.openlocfilehash: 3b4695dfbcaf05c73bd53af5be7a49d081eb8e47
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410584"
---
# <a name="how-to-validate-file-names-and-paths-in-visual-basic"></a>Практическое руководство. Проверка имен файлов и путей в Visual Basic
В этом примере возвращается `Boolean` значение, указывающее, представляет ли строка имя файла или путь. Проверка проверяет, содержит ли имя символы, недопустимые в файловой системе.  
  
## <a name="example"></a>Пример  
 [!code-vb[VbVbcnRegEx#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#4)]  
  
 В этом примере не проверяется, неправильно ли в имени размещены двоеточия или каталоги без имени, или значение, если длина имени превышает максимальную длину, определенную системой. Он также не проверяет, имеет ли приложение разрешение на доступ к ресурсу файловой системы с указанным именем.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.IO.Path.GetInvalidPathChars%2A>
- [Проверка строк в Visual Basic](validating-strings.md)
