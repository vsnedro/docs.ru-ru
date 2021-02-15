---
description: Дополнительные сведения см. в статье Проверка имен файлов и путей в Visual Basic
title: Практическое руководство. Проверка имен файлов и путей
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], validating
- strings [Visual Basic], validating
- Boolean values [Visual Basic]
- paths [Visual Basic], validating
ms.assetid: f673462d-57b7-4120-b13a-6a7592f7ab2c
ms.openlocfilehash: 02a48ea7cbf3291cb2fe1c64c4e636a273842546
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100429744"
---
# <a name="how-to-validate-file-names-and-paths-in-visual-basic"></a>Практическое руководство. Проверка имен файлов и путей в Visual Basic

В этом примере возвращается `Boolean` значение, указывающее, представляет ли строка имя файла или путь. Проверка проверяет, содержит ли имя символы, недопустимые в файловой системе.  
  
## <a name="example"></a>Пример  

 [!code-vb[VbVbcnRegEx#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#4)]  
  
 В этом примере не проверяется, неправильно ли в имени размещены двоеточия или каталоги без имени, или значение, если длина имени превышает максимальную длину, определенную системой. Он также не проверяет, имеет ли приложение разрешение на доступ к ресурсу файловой системы с указанным именем.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.IO.Path.GetInvalidPathChars%2A>
- [Проверка строк в Visual Basic](validating-strings.md)
