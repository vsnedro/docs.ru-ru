---
title: Функция <procedurename> возвращает значение не для всех путей выполнения
ms.date: 07/20/2015
f1_keywords:
- bc42105
- vbc42105
helpviewer_keywords:
- BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
ms.openlocfilehash: edb2195f4e83c2315aa929936aff8af88ca8556c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84374139"
---
# <a name="function-procedurename-doesnt-return-a-value-on-all-code-paths"></a><span data-ttu-id="b7898-102">Функция \<procedurename> возвращает значение не для всех путей выполнения</span><span class="sxs-lookup"><span data-stu-id="b7898-102">Function '\<procedurename>' doesn't return a value on all code paths</span></span>
<span data-ttu-id="b7898-103">Функция " \<procedurename> " не возвращает значение для всех ветвей кода.</span><span class="sxs-lookup"><span data-stu-id="b7898-103">Function '\<procedurename>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="b7898-104">У вас отсутствует оператор "return"?</span><span class="sxs-lookup"><span data-stu-id="b7898-104">Are you missing a 'Return' statement?</span></span>  
  
 <span data-ttu-id="b7898-105">`Function`Процедура имеет по крайней мере один возможный путь в коде, который не возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="b7898-105">A `Function` procedure has at least one possible path through its code that does not return a value.</span></span>  
  
 <span data-ttu-id="b7898-106">Получить значение из `Function` процедуры можно одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="b7898-106">You can return a value from a `Function` procedure in any of the following ways:</span></span>  
  
- <span data-ttu-id="b7898-107">Включите значение в [оператор return](../statements/return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b7898-107">Include the value in a [Return Statement](../statements/return-statement.md).</span></span>  
  
- <span data-ttu-id="b7898-108">Присвойте значение `Function` имени процедуры, а затем выполните `Exit Function` инструкцию.</span><span class="sxs-lookup"><span data-stu-id="b7898-108">Assign the value to the `Function` procedure name and then perform an `Exit Function` statement.</span></span>  
  
- <span data-ttu-id="b7898-109">Присвойте значение `Function` имени процедуры, а затем выполните `End Function` инструкцию.</span><span class="sxs-lookup"><span data-stu-id="b7898-109">Assign the value to the `Function` procedure name and then perform the `End Function` statement.</span></span>  
  
 <span data-ttu-id="b7898-110">Если элемент управления передается в `Exit Function` или `End Function` и вы не назначили какое бы то ни было значение имени процедуры, процедура возвращает значение по умолчанию для возвращаемого типа данных.</span><span class="sxs-lookup"><span data-stu-id="b7898-110">If control passes to `Exit Function` or `End Function` and you have not assigned any value to the procedure name, the procedure returns the default value of the return data type.</span></span> <span data-ttu-id="b7898-111">Дополнительные сведения см. в разделе «поведение» в [операторе Function](../statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b7898-111">For more information, see "Behavior" in [Function Statement](../statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="b7898-112">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="b7898-112">By default, this message is a warning.</span></span> <span data-ttu-id="b7898-113">Дополнительные сведения о скрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="b7898-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="b7898-114">**Идентификатор ошибки:** BC42105</span><span class="sxs-lookup"><span data-stu-id="b7898-114">**Error ID:** BC42105</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b7898-115">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="b7898-115">To correct this error</span></span>  
  
- <span data-ttu-id="b7898-116">Проверьте логику потока управления и убедитесь, что значение присваивается перед каждой инструкцией, которая вызывает возврат.</span><span class="sxs-lookup"><span data-stu-id="b7898-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>  
  
     <span data-ttu-id="b7898-117">Проще гарантировать, что каждый возврат из процедуры возвращает значение, если всегда используется `Return` оператор.</span><span class="sxs-lookup"><span data-stu-id="b7898-117">It is easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="b7898-118">В этом случае последняя инструкция `End Function` должна быть `Return` оператором.</span><span class="sxs-lookup"><span data-stu-id="b7898-118">If you do this, the last statement before `End Function` should be a `Return` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7898-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b7898-119">See also</span></span>

- [<span data-ttu-id="b7898-120">Процедуры функций</span><span class="sxs-lookup"><span data-stu-id="b7898-120">Function Procedures</span></span>](../../programming-guide/language-features/procedures/function-procedures.md)
- [<span data-ttu-id="b7898-121">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="b7898-121">Function Statement</span></span>](../statements/function-statement.md)
- [<span data-ttu-id="b7898-122">Страница "Компиляция" в конструкторе проектов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b7898-122">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
