---
title: Оператор Throw
ms.date: 07/20/2015
f1_keywords:
- vb.Throw
helpviewer_keywords:
- structured exception handling, throw statements
- try-catch exception handling, throw statements
- throw statement [Visual Basic], about throw statements
- throwing exceptions, throw statement
- exception handling, throw statement
- On Error statement [Visual Basic], throwing exceptions
- throwing exceptions
- exception handling, unstructured
- throw statement [Visual Basic]
ms.assetid: a6e07406-5c8a-4498-87a2-8339f3651d62
ms.openlocfilehash: 95572b1739490e90f53da6b6ec283bfb532c46d3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404139"
---
# <a name="throw-statement-visual-basic"></a><span data-ttu-id="fa9bc-102">Оператор Throw (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fa9bc-102">Throw Statement (Visual Basic)</span></span>

<span data-ttu-id="fa9bc-103">Создает исключение в процедуре.</span><span class="sxs-lookup"><span data-stu-id="fa9bc-103">Throws an exception within a procedure.</span></span>

## <a name="syntax"></a><span data-ttu-id="fa9bc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fa9bc-104">Syntax</span></span>

```vb
Throw [ expression ]
```

## <a name="part"></a><span data-ttu-id="fa9bc-105">Часть</span><span class="sxs-lookup"><span data-stu-id="fa9bc-105">Part</span></span>

`expression`\
<span data-ttu-id="fa9bc-106">Предоставляет сведения о вызываемом исключении.</span><span class="sxs-lookup"><span data-stu-id="fa9bc-106">Provides information about the exception to be thrown.</span></span> <span data-ttu-id="fa9bc-107">Необязательно, если размещен в `Catch` операторе, в противном случае является обязательным.</span><span class="sxs-lookup"><span data-stu-id="fa9bc-107">Optional when residing in a `Catch` statement, otherwise required.</span></span>

## <a name="remarks"></a><span data-ttu-id="fa9bc-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="fa9bc-108">Remarks</span></span>

<span data-ttu-id="fa9bc-109">`Throw`Оператор создает исключение, которое можно обработать с помощью структурированного кода обработки исключений ( `Try` ... `Catch` ...`Finally`) или неструктурированный код обработки исключений ( `On Error GoTo` ).</span><span class="sxs-lookup"><span data-stu-id="fa9bc-109">The `Throw` statement throws an exception that you can handle with structured exception-handling code (`Try`...`Catch`...`Finally`) or unstructured exception-handling code (`On Error GoTo`).</span></span> <span data-ttu-id="fa9bc-110">Можно использовать `Throw` инструкцию для перехвата ошибок в коде, так как Visual Basic перемещается вверх по стеку вызовов до тех пор, пока не найдет соответствующий код обработки исключений.</span><span class="sxs-lookup"><span data-stu-id="fa9bc-110">You can use the `Throw` statement to trap errors within your code because Visual Basic moves up the call stack until it finds the appropriate exception-handling code.</span></span>

<span data-ttu-id="fa9bc-111">`Throw`Инструкцию без выражения можно использовать только в `Catch` операторе, в этом случае инструкция повторно создает исключение, которое в настоящее время обрабатывается `Catch` инструкцией.</span><span class="sxs-lookup"><span data-stu-id="fa9bc-111">A `Throw` statement with no expression can only be used in a `Catch` statement, in which case the statement rethrows the exception currently being handled by the `Catch` statement.</span></span>

<span data-ttu-id="fa9bc-112">`Throw`Инструкция сбрасывает стек вызовов для `expression` исключения.</span><span class="sxs-lookup"><span data-stu-id="fa9bc-112">The `Throw` statement resets the call stack for the `expression` exception.</span></span> <span data-ttu-id="fa9bc-113">Если `expression` параметр не указан, стек вызовов остается без изменений.</span><span class="sxs-lookup"><span data-stu-id="fa9bc-113">If `expression` is not provided, the call stack is left unchanged.</span></span> <span data-ttu-id="fa9bc-114">Доступ к стеку вызовов для исключения можно получить с помощью <xref:System.Exception.StackTrace%2A> Свойства.</span><span class="sxs-lookup"><span data-stu-id="fa9bc-114">You can access the call stack for the exception through the <xref:System.Exception.StackTrace%2A> property.</span></span>

## <a name="example"></a><span data-ttu-id="fa9bc-115">Пример</span><span class="sxs-lookup"><span data-stu-id="fa9bc-115">Example</span></span>

<span data-ttu-id="fa9bc-116">Следующий код использует `Throw` инструкцию для создания исключения:</span><span class="sxs-lookup"><span data-stu-id="fa9bc-116">The following code uses the `Throw` statement to throw an exception:</span></span>

[!code-vb[VbVbalrStatements#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#84)]

## <a name="see-also"></a><span data-ttu-id="fa9bc-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="fa9bc-117">See also</span></span>

- [<span data-ttu-id="fa9bc-118">Оператор Try…Catch…Finally</span><span class="sxs-lookup"><span data-stu-id="fa9bc-118">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
- [<span data-ttu-id="fa9bc-119">Оператор On Error</span><span class="sxs-lookup"><span data-stu-id="fa9bc-119">On Error Statement</span></span>](on-error-statement.md)
