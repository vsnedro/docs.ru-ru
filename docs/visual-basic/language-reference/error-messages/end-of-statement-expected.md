---
title: Ожидается окончание оператора
ms.date: 07/20/2015
f1_keywords:
- bc30205
- vbc30205
helpviewer_keywords:
- BC30205
ms.assetid: 53c7f825-a737-4b76-a1fa-f67745b8bd40
ms.openlocfilehash: 169f01b02df377ba6cc21ffad53c36f5d4537140
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409651"
---
# <a name="end-of-statement-expected"></a><span data-ttu-id="c5e90-102">Ожидается окончание оператора</span><span class="sxs-lookup"><span data-stu-id="c5e90-102">End of statement expected</span></span>
<span data-ttu-id="c5e90-103">Инструкция является синтаксически завершенной, но дополнительный программный элемент следует за элементом, который завершает инструкцию.</span><span class="sxs-lookup"><span data-stu-id="c5e90-103">The statement is syntactically complete, but an additional programming element follows the element that completes the statement.</span></span> <span data-ttu-id="c5e90-104">В конце каждой инструкции требуется признак конца строки.</span><span class="sxs-lookup"><span data-stu-id="c5e90-104">A line terminator is required at the end of every statement.</span></span>
  
 <span data-ttu-id="c5e90-105">Признак конца строки делит символы Visual Basic исходного файла на строки.</span><span class="sxs-lookup"><span data-stu-id="c5e90-105">A line terminator divides the characters of a Visual Basic source file into lines.</span></span> <span data-ttu-id="c5e90-106">Примерами признаков конца строки являются символ возврата каретки в Юникоде (&HD), символ перевода строки в Юникоде (&HA) и символ возврата каретки в Юникоде, за которым следует символ перевода строки в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="c5e90-106">Examples of line terminators are the Unicode carriage return character (&HD), the Unicode linefeed character (&HA), and the Unicode carriage return character followed by the Unicode linefeed character.</span></span> <span data-ttu-id="c5e90-107">Дополнительные сведения о знаках конца строки см. в разделе [Спецификация языка Visual Basic](~/_vblang/spec/lexical-grammar.md#line-terminators).</span><span class="sxs-lookup"><span data-stu-id="c5e90-107">For more information about line terminators, see the [Visual Basic Language Specification](~/_vblang/spec/lexical-grammar.md#line-terminators).</span></span>
  
 <span data-ttu-id="c5e90-108">**Идентификатор ошибки:** BC30205</span><span class="sxs-lookup"><span data-stu-id="c5e90-108">**Error ID:** BC30205</span></span>
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c5e90-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="c5e90-109">To correct this error</span></span>
  
1. <span data-ttu-id="c5e90-110">Убедитесь, что две разные инструкции случайно были помещены в одну и ту же строку.</span><span class="sxs-lookup"><span data-stu-id="c5e90-110">Check to see if two different statements have inadvertently been put on the same line.</span></span>
  
2. <span data-ttu-id="c5e90-111">Вставьте признак конца строки после элемента, который завершает инструкцию.</span><span class="sxs-lookup"><span data-stu-id="c5e90-111">Insert a line terminator after the element that completes the statement.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c5e90-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c5e90-112">See also</span></span>

- [<span data-ttu-id="c5e90-113">Практическое руководство. Разбиение и объединение инструкций в коде</span><span class="sxs-lookup"><span data-stu-id="c5e90-113">How to: Break and Combine Statements in Code</span></span>](../../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
- [<span data-ttu-id="c5e90-114">Операторы</span><span class="sxs-lookup"><span data-stu-id="c5e90-114">Statements</span></span>](../../programming-guide/language-features/statements.md)
