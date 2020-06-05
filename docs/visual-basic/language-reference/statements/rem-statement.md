---
title: Оператор REM
ms.date: 07/20/2015
f1_keywords:
- vb.'
- vb.Rem
- Rem
- "'"
helpviewer_keywords:
- REM statement [Visual Basic]
- comments, Visual Basic code
- code comments, Visual Basic
- Visual Basic code, comments
- "' comment marker character [Visual Basic]"
ms.assetid: 34126d7f-e0f9-476d-91e6-b31b398615dc
ms.openlocfilehash: 68c898145bd8845c657b6ebb8776a3a9027c359c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404269"
---
# <a name="rem-statement-visual-basic"></a><span data-ttu-id="80145-102">Оператор REM (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="80145-102">REM Statement (Visual Basic)</span></span>
<span data-ttu-id="80145-103">Используется для включения пояснительных примечаний в исходный код программы.</span><span class="sxs-lookup"><span data-stu-id="80145-103">Used to include explanatory remarks in the source code of a program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80145-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="80145-104">Syntax</span></span>  
  
```vb  
REM comment  
' comment  
```  
  
## <a name="parts"></a><span data-ttu-id="80145-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="80145-105">Parts</span></span>  
 `comment`  
 <span data-ttu-id="80145-106">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="80145-106">Optional.</span></span> <span data-ttu-id="80145-107">Текст любого комментария, который требуется включить.</span><span class="sxs-lookup"><span data-stu-id="80145-107">The text of any comment you want to include.</span></span> <span data-ttu-id="80145-108">Между `REM` ключевым словом и должен быть пробел `comment` .</span><span class="sxs-lookup"><span data-stu-id="80145-108">A space is required between the `REM` keyword and `comment`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80145-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="80145-109">Remarks</span></span>  
 <span data-ttu-id="80145-110">Оператор можно разместить `REM` только в строке или вставить в строку, следующую за другой инструкцией.</span><span class="sxs-lookup"><span data-stu-id="80145-110">You can put a `REM` statement alone on a line, or you can put it on a line following another statement.</span></span> <span data-ttu-id="80145-111">`REM`Оператор должен быть последним оператором в строке.</span><span class="sxs-lookup"><span data-stu-id="80145-111">The `REM` statement must be the last statement on the line.</span></span> <span data-ttu-id="80145-112">Если он соответствует другому оператору, он `REM` должен быть отделен от этого оператора пробелом.</span><span class="sxs-lookup"><span data-stu-id="80145-112">If it follows another statement, the `REM` must be separated from that statement by a space.</span></span>  
  
 <span data-ttu-id="80145-113">Можно использовать одиночную кавычку ( `'` ) вместо `REM` .</span><span class="sxs-lookup"><span data-stu-id="80145-113">You can use a single quotation mark (`'`) instead of `REM`.</span></span> <span data-ttu-id="80145-114">Это верно, если ваш комментарий следует другому оператору в той же строке или расподержаться только в строке.</span><span class="sxs-lookup"><span data-stu-id="80145-114">This is true whether your comment follows another statement on the same line or sits alone on a line.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="80145-115">Нельзя продолжить выполнение `REM` инструкции с помощью последовательности продолжения строки ( `_` ).</span><span class="sxs-lookup"><span data-stu-id="80145-115">You cannot continue a `REM` statement by using a line-continuation sequence (`_`).</span></span> <span data-ttu-id="80145-116">После начала комментария компилятор не проверяет символы на предмет особого значения.</span><span class="sxs-lookup"><span data-stu-id="80145-116">Once a comment begins, the compiler does not examine the characters for special meaning.</span></span> <span data-ttu-id="80145-117">Для многострочного комментария используйте другую `REM` инструкцию или символ комментария ( `'` ) в каждой строке.</span><span class="sxs-lookup"><span data-stu-id="80145-117">For a multiple-line comment, use another `REM` statement or a comment symbol (`'`) on each line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80145-118">Пример</span><span class="sxs-lookup"><span data-stu-id="80145-118">Example</span></span>  
 <span data-ttu-id="80145-119">В следующем примере показана `REM` инструкция, которая используется для включения пояснительных примечаний в программу.</span><span class="sxs-lookup"><span data-stu-id="80145-119">The following example illustrates the `REM` statement, which is used to include explanatory remarks in a program.</span></span> <span data-ttu-id="80145-120">Он также показывает альтернативу использованию символа одинарной кавычки ( `'` ) вместо `REM` .</span><span class="sxs-lookup"><span data-stu-id="80145-120">It also shows the alternative of using the single quotation-mark character (`'`) instead of `REM`.</span></span>  
  
 [!code-vb[VbVbalrStatements#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="80145-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="80145-121">See also</span></span>

- [<span data-ttu-id="80145-122">Комментарии в коде</span><span class="sxs-lookup"><span data-stu-id="80145-122">Comments in Code</span></span>](../../programming-guide/program-structure/comments-in-code.md)
- [<span data-ttu-id="80145-123">Практическое руководство. Разбиение и объединение инструкций в коде</span><span class="sxs-lookup"><span data-stu-id="80145-123">How to: Break and Combine Statements in Code</span></span>](../../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
