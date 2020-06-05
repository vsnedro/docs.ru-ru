---
title: Оператор Return
ms.date: 07/20/2015
f1_keywords:
- vb.Return
helpviewer_keywords:
- Return statement [Visual Basic], syntax
- control flow [Visual Basic], returning control to expressions
- Return statement [Visual Basic]
- expressions [Visual Basic], returning control to
ms.assetid: ac86e7f0-5a67-42c3-9834-0e0381efa3ec
ms.openlocfilehash: cdb58e32c30c8e6c1662fb698ac5576c3f71258c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404204"
---
# <a name="return-statement-visual-basic"></a><span data-ttu-id="b196e-102">Оператор Return (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b196e-102">Return Statement (Visual Basic)</span></span>
<span data-ttu-id="b196e-103">Возвращает управление коду, который вызвал `Function` процедуру,, `Sub` `Get` , `Set` или `Operator` .</span><span class="sxs-lookup"><span data-stu-id="b196e-103">Returns control to the code that called a `Function`, `Sub`, `Get`, `Set`, or `Operator` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b196e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b196e-104">Syntax</span></span>  
  
```vb  
Return  
' -or-  
Return expression  
```  
  
## <a name="part"></a><span data-ttu-id="b196e-105">Часть</span><span class="sxs-lookup"><span data-stu-id="b196e-105">Part</span></span>  
 `expression`  
 <span data-ttu-id="b196e-106">Требуется в `Function` процедуре, `Get` или `Operator` .</span><span class="sxs-lookup"><span data-stu-id="b196e-106">Required in a `Function`, `Get`, or `Operator` procedure.</span></span> <span data-ttu-id="b196e-107">Выражение, представляющее значение, возвращаемое вызывающему коду.</span><span class="sxs-lookup"><span data-stu-id="b196e-107">Expression that represents the value to be returned to the calling code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b196e-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="b196e-108">Remarks</span></span>  
 <span data-ttu-id="b196e-109">В `Sub` процедуре или `Set` `Return` инструкция эквивалентна `Exit Sub` `Exit Property` оператору или и `expression` не должна быть указана.</span><span class="sxs-lookup"><span data-stu-id="b196e-109">In a `Sub` or `Set` procedure, the `Return` statement is equivalent to an `Exit Sub` or `Exit Property` statement, and `expression` must not be supplied.</span></span>  
  
 <span data-ttu-id="b196e-110">В `Function` процедуре, `Get` или `Operator` `Return` инструкция должна включать оператор `expression` и `expression` должен иметь тип данных, преобразуемый в возвращаемый тип процедуры.</span><span class="sxs-lookup"><span data-stu-id="b196e-110">In a `Function`, `Get`, or `Operator` procedure, the `Return` statement must include `expression`, and `expression` must evaluate to a data type that is convertible to the return type of the procedure.</span></span> <span data-ttu-id="b196e-111">В `Function` процедуре или `Get` вы также можете назначить выражение имени процедуры, которое будет использоваться в качестве возвращаемого значения, а затем выполнить `Exit Function` `Exit Property` инструкцию или.</span><span class="sxs-lookup"><span data-stu-id="b196e-111">In a `Function` or `Get` procedure, you also have the alternative of assigning an expression to the procedure name to serve as the return value, and then executing an `Exit Function` or `Exit Property` statement.</span></span> <span data-ttu-id="b196e-112">В `Operator` процедуре необходимо использовать `Return expression` .</span><span class="sxs-lookup"><span data-stu-id="b196e-112">In an `Operator` procedure, you must use `Return expression`.</span></span>  
  
 <span data-ttu-id="b196e-113">В одной процедуре можно включить столько инструкций, сколько `Return` необходимо.</span><span class="sxs-lookup"><span data-stu-id="b196e-113">You can include as many `Return` statements as appropriate in the same procedure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b196e-114">Код в `Finally` блоке выполняется после `Return` обнаружения оператора в `Try` `Catch` блоке или, но перед `Return` выполнением этой инструкции.</span><span class="sxs-lookup"><span data-stu-id="b196e-114">The code in a `Finally` block runs after a `Return` statement in a `Try` or `Catch` block is encountered, but before that `Return` statement executes.</span></span> <span data-ttu-id="b196e-115">`Return`Инструкция не может быть включена в `Finally` блок.</span><span class="sxs-lookup"><span data-stu-id="b196e-115">A `Return` statement cannot be included in a `Finally` block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b196e-116">Пример</span><span class="sxs-lookup"><span data-stu-id="b196e-116">Example</span></span>  
 <span data-ttu-id="b196e-117">В следующем примере оператор используется `Return` несколько раз для возврата к вызывающему коду, если процедура не должна предпринимать никаких других действий.</span><span class="sxs-lookup"><span data-stu-id="b196e-117">The following example uses the `Return` statement several times to return to the calling code when the procedure does not have to do anything else.</span></span>  
  
 [!code-vb[VbVbalrStatements#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#53)]  
  
## <a name="see-also"></a><span data-ttu-id="b196e-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b196e-118">See also</span></span>

- [<span data-ttu-id="b196e-119">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="b196e-119">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="b196e-120">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="b196e-120">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="b196e-121">Оператор Get</span><span class="sxs-lookup"><span data-stu-id="b196e-121">Get Statement</span></span>](get-statement.md)
- [<span data-ttu-id="b196e-122">Инструкция SET</span><span class="sxs-lookup"><span data-stu-id="b196e-122">Set Statement</span></span>](set-statement.md)
- [<span data-ttu-id="b196e-123">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="b196e-123">Operator Statement</span></span>](operator-statement.md)
- [<span data-ttu-id="b196e-124">Property Statement</span><span class="sxs-lookup"><span data-stu-id="b196e-124">Property Statement</span></span>](property-statement.md)
- [<span data-ttu-id="b196e-125">Оператор Exit</span><span class="sxs-lookup"><span data-stu-id="b196e-125">Exit Statement</span></span>](exit-statement.md)
- [<span data-ttu-id="b196e-126">Оператор Try…Catch…Finally</span><span class="sxs-lookup"><span data-stu-id="b196e-126">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
