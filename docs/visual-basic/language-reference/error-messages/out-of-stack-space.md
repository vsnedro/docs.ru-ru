---
title: Недостаточно места для стека
ms.date: 07/20/2015
f1_keywords:
- vbrID28
ms.assetid: bfcd792b-ac29-4158-81fc-ea0c13f4ffa2
ms.openlocfilehash: afb6a42372bdbd2e49ac15fbbf2b9e254f8db431
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871311"
---
# <a name="out-of-stack-space-visual-basic"></a><span data-ttu-id="b891d-102">Отсутствует место в стеке (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b891d-102">Out of stack space (Visual Basic)</span></span>

<span data-ttu-id="b891d-103">Стек — это Рабочая область памяти, которая динамически растет и сжимается с учетом требований к выполненной программе.</span><span class="sxs-lookup"><span data-stu-id="b891d-103">The stack is a working area of memory that grows and shrinks dynamically with the demands of your executing program.</span></span> <span data-ttu-id="b891d-104">Превышены его ограничения.</span><span class="sxs-lookup"><span data-stu-id="b891d-104">Its limits have been exceeded.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b891d-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="b891d-105">To correct this error</span></span>  
  
1. <span data-ttu-id="b891d-106">Убедитесь, что процедуры не вложены слишком глубоко.</span><span class="sxs-lookup"><span data-stu-id="b891d-106">Check that procedures are not nested too deeply.</span></span>  
  
2. <span data-ttu-id="b891d-107">Убедитесь, что рекурсивные процедуры завершаются должным образом.</span><span class="sxs-lookup"><span data-stu-id="b891d-107">Make sure recursive procedures terminate properly.</span></span>  
  
3. <span data-ttu-id="b891d-108">Если локальным переменным требуется больше пространства локальных переменных, чем доступно, попробуйте объявить некоторые переменные на уровне модуля.</span><span class="sxs-lookup"><span data-stu-id="b891d-108">If local variables require more local variable space than is available, try declaring some variables at the module level.</span></span> <span data-ttu-id="b891d-109">Кроме того, можно объявить все переменные в процедуре статически, выполнив `Property` `Sub` `Function` ключевое слово, или с помощью `Static` .</span><span class="sxs-lookup"><span data-stu-id="b891d-109">You can also declare all variables in the procedure static by preceding the `Property`, `Sub`, or `Function` keyword with `Static`.</span></span> <span data-ttu-id="b891d-110">Или можно использовать `Static` инструкцию для объявления отдельных статических переменных в процедурах.</span><span class="sxs-lookup"><span data-stu-id="b891d-110">Or you can use the `Static` statement to declare individual static variables within procedures.</span></span>  
  
4. <span data-ttu-id="b891d-111">Переопределите некоторые строки фиксированной длины как строки переменной длины, так как строки фиксированной длины используют больше пространства стека, чем строки переменной длины.</span><span class="sxs-lookup"><span data-stu-id="b891d-111">Redefine some of your fixed-length strings as variable-length strings, as fixed-length strings use more stack space than variable-length strings.</span></span> <span data-ttu-id="b891d-112">Можно также определить строку на уровне модуля, где не требуется пространство стека.</span><span class="sxs-lookup"><span data-stu-id="b891d-112">You can also define the string at module level where it requires no stack space.</span></span>  
  
5. <span data-ttu-id="b891d-113">Проверьте количество вызовов вложенных `DoEvents` функций, используя `Calls` диалоговое окно для просмотра активных процедур в стеке.</span><span class="sxs-lookup"><span data-stu-id="b891d-113">Check the number of nested `DoEvents` function calls, by using the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
6. <span data-ttu-id="b891d-114">Убедитесь, что вы не вызвали "каскадное событие", активируя событие, которое вызывает процедуру события, уже называемую в стеке.</span><span class="sxs-lookup"><span data-stu-id="b891d-114">Make sure you did not cause an "event cascade" by triggering an event that calls an event procedure already on the stack.</span></span> <span data-ttu-id="b891d-115">Каскад событий аналогичен вызову незавершенной рекурсивной процедуры, но он менее очевидн, так как вызов выполняется Visual Basic а не явным вызовом в коде.</span><span class="sxs-lookup"><span data-stu-id="b891d-115">An event cascade is similar to an unterminated recursive procedure call, but it is less obvious, since the call is made by Visual Basic rather than an explicit call in the code.</span></span> <span data-ttu-id="b891d-116">Используйте `Calls` диалоговое окно для просмотра активных процедур в стеке.</span><span class="sxs-lookup"><span data-stu-id="b891d-116">Use the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b891d-117">См. также</span><span class="sxs-lookup"><span data-stu-id="b891d-117">See also</span></span>

- [<span data-ttu-id="b891d-118">Окно памяти</span><span class="sxs-lookup"><span data-stu-id="b891d-118">Memory Windows</span></span>](/visualstudio/debugger/memory-windows)
