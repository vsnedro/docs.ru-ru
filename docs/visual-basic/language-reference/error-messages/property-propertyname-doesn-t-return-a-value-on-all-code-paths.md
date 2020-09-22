---
title: Свойство ''<propertyname>'' возвращает значение не для всех ветвей кода
ms.date: 07/20/2015
f1_keywords:
- bc42107
- vbc42107
helpviewer_keywords:
- BC42107
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
ms.openlocfilehash: 6a80a8275a7b9c5e3cbfa410ee219e0d16ce5918
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870954"
---
# <a name="property-propertyname-doesnt-return-a-value-on-all-code-paths"></a><span data-ttu-id="8dd71-102">Свойство ''\<propertyname>'' возвращает значение не для всех ветвей кода</span><span class="sxs-lookup"><span data-stu-id="8dd71-102">Property '\<propertyname>' doesn't return a value on all code paths</span></span>

<span data-ttu-id="8dd71-103">Свойство " \<propertyname> " не возвращает значение для всех ветвей кода.</span><span class="sxs-lookup"><span data-stu-id="8dd71-103">Property '\<propertyname>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="8dd71-104">Во время выполнения может возникнуть исключение, связанное с пустой ссылкой, когда используется результат.</span><span class="sxs-lookup"><span data-stu-id="8dd71-104">A null reference exception could occur at run time when the result is used.</span></span>  
  
 <span data-ttu-id="8dd71-105">Процедура свойства `Get` имеет по крайней мере один возможный путь в коде, который не возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="8dd71-105">A property `Get` procedure has at least one possible path through its code that does not return a value.</span></span>  
  
 <span data-ttu-id="8dd71-106">Получить значение из процедуры свойства можно `Get` одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="8dd71-106">You can return a value from a property `Get` procedure in any of the following ways:</span></span>  
  
- <span data-ttu-id="8dd71-107">Присвойте значение имени свойства, а затем выполните `Exit Property` инструкцию.</span><span class="sxs-lookup"><span data-stu-id="8dd71-107">Assign the value to the property name and then perform an `Exit Property` statement.</span></span>  
  
- <span data-ttu-id="8dd71-108">Присвойте значение имени свойства, а затем выполните `End Get` инструкцию.</span><span class="sxs-lookup"><span data-stu-id="8dd71-108">Assign the value to the property name and then perform the `End Get` statement.</span></span>  
  
- <span data-ttu-id="8dd71-109">Включите значение в [оператор return](../statements/return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8dd71-109">Include the value in a [Return Statement](../statements/return-statement.md).</span></span>  
  
 <span data-ttu-id="8dd71-110">Если элемент управления передается в `Exit Property` или `End Get` и вы не присвоили какое бы то ни было значение имени свойства, `Get` процедура возвращает значение по умолчанию для типа данных свойства.</span><span class="sxs-lookup"><span data-stu-id="8dd71-110">If control passes to `Exit Property` or `End Get` and you have not assigned any value to the property name, the `Get` procedure returns the default value of the property's data type.</span></span> <span data-ttu-id="8dd71-111">Дополнительные сведения см. в разделе «поведение» в [операторе Function](../statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8dd71-111">For more information, see "Behavior" in [Function Statement](../statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="8dd71-112">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="8dd71-112">By default, this message is a warning.</span></span> <span data-ttu-id="8dd71-113">Дополнительные сведения о скрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="8dd71-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="8dd71-114">**Идентификатор ошибки:** BC42107</span><span class="sxs-lookup"><span data-stu-id="8dd71-114">**Error ID:** BC42107</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8dd71-115">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="8dd71-115">To correct this error</span></span>  
  
- <span data-ttu-id="8dd71-116">Проверьте логику потока управления и убедитесь, что значение присваивается перед каждой инструкцией, которая вызывает возврат.</span><span class="sxs-lookup"><span data-stu-id="8dd71-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>  
  
     <span data-ttu-id="8dd71-117">Проще гарантировать, что каждый возврат из процедуры возвращает значение, если всегда используется `Return` оператор.</span><span class="sxs-lookup"><span data-stu-id="8dd71-117">It is easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="8dd71-118">В этом случае последняя инструкция `End Get` должна быть `Return` оператором.</span><span class="sxs-lookup"><span data-stu-id="8dd71-118">If you do this, the last statement before `End Get` should be a `Return` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dd71-119">См. также</span><span class="sxs-lookup"><span data-stu-id="8dd71-119">See also</span></span>

- [<span data-ttu-id="8dd71-120">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="8dd71-120">Property Procedures</span></span>](../../programming-guide/language-features/procedures/property-procedures.md)
- [<span data-ttu-id="8dd71-121">Property Statement</span><span class="sxs-lookup"><span data-stu-id="8dd71-121">Property Statement</span></span>](../statements/property-statement.md)
- [<span data-ttu-id="8dd71-122">Оператор Get</span><span class="sxs-lookup"><span data-stu-id="8dd71-122">Get Statement</span></span>](../statements/get-statement.md)
