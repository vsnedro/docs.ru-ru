---
title: Практическое руководство. Создание строки из значений массива символьного типа
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: d9ec897467f0caac0afc089a028516c0316a2bda
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410597"
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a><span data-ttu-id="bbbea-102">Практическое руководство. Создание строки из значений массива символьного типа (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bbbea-102">How to: Create a String from An Array of Char Values (Visual Basic)</span></span>
<span data-ttu-id="bbbea-103">В этом примере создается строка «ABCD» из отдельных символов.</span><span class="sxs-lookup"><span data-stu-id="bbbea-103">This example creates the string "abcd" from individual characters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bbbea-104">Пример</span><span class="sxs-lookup"><span data-stu-id="bbbea-104">Example</span></span>  
 [!code-vb[VbVbalrStrings#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#61)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="bbbea-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="bbbea-105">Compile the code</span></span>  
 <span data-ttu-id="bbbea-106">Этот метод не имеет особых требований.</span><span class="sxs-lookup"><span data-stu-id="bbbea-106">This method has no special requirements.</span></span>  
  
 <span data-ttu-id="bbbea-107">Синтаксис `"a"c` , где один `c` символ следует за одиночным знаком в кавычках, используется для создания символьного литерала.</span><span class="sxs-lookup"><span data-stu-id="bbbea-107">The syntax `"a"c`, where a single `c` follows a single character in quotation marks, is used to create a character literal.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="bbbea-108">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="bbbea-108">Robust Programming</span></span>  
 <span data-ttu-id="bbbea-109">Символы NULL (эквивалентны `Chr(0)` ) в строке ведут к непредвиденным результатам при использовании строки.</span><span class="sxs-lookup"><span data-stu-id="bbbea-109">Null characters (equivalent to `Chr(0)`) in the string lead to unexpected results when using the string.</span></span> <span data-ttu-id="bbbea-110">Символ null будет включаться в строку, но символы, следующие за символом NULL, не будут отображаться в некоторых ситуациях.</span><span class="sxs-lookup"><span data-stu-id="bbbea-110">The null character will be included with the string, but characters following the null character will not be displayed in some situations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbbea-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bbbea-111">See also</span></span>

- <xref:System.String>
- [<span data-ttu-id="bbbea-112">Тип данных Char</span><span class="sxs-lookup"><span data-stu-id="bbbea-112">Char Data Type</span></span>](../../../language-reference/data-types/char-data-type.md)
- [<span data-ttu-id="bbbea-113">Типы данных</span><span class="sxs-lookup"><span data-stu-id="bbbea-113">Data Types</span></span>](../data-types/index.md)
