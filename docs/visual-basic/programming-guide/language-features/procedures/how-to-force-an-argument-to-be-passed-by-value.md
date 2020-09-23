---
title: Практическое руководство. Принудительная передача аргумента по значению
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures [Visual Basic], calling
- arguments [Visual Basic], in parentheses
- procedure arguments [Visual Basic], in parentheses
- arguments [Visual Basic], changing value
ms.assetid: 77b4f2d2-1055-4c2f-a521-874d1db86946
ms.openlocfilehash: 0be49e7d4aacbb30956bda7f6ee8494a7ded8b78
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071629"
---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a><span data-ttu-id="51af4-102">Практическое руководство. Принудительная передача аргумента по значению (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="51af4-102">How to: Force an Argument to Be Passed by Value (Visual Basic)</span></span>

<span data-ttu-id="51af4-103">Объявление процедуры определяет механизм передачи.</span><span class="sxs-lookup"><span data-stu-id="51af4-103">The procedure declaration determines the passing mechanism.</span></span> <span data-ttu-id="51af4-104">Если параметр объявлен как [ByRef](../../../language-reference/modifiers/byref.md), Visual Basic предполагался передать соответствующий аргумент по ссылке.</span><span class="sxs-lookup"><span data-stu-id="51af4-104">If a parameter is declared [ByRef](../../../language-reference/modifiers/byref.md), Visual Basic expects to pass the corresponding argument by reference.</span></span> <span data-ttu-id="51af4-105">Это позволяет процедуре изменять значение программного элемента, лежащего в основе аргумента в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="51af4-105">This allows the procedure to change the value of the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="51af4-106">Если вы хотите защитить базовый элемент от таких изменений, можно переопределить `ByRef` механизм передачи в вызове процедуры, заключив имя аргумента в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="51af4-106">If you wish to protect the underlying element against such change, you can override the `ByRef` passing mechanism in the procedure call by enclosing the argument name in parentheses.</span></span> <span data-ttu-id="51af4-107">Эти скобки являются дополнением к круглым скобкам, включающим список аргументов в вызове.</span><span class="sxs-lookup"><span data-stu-id="51af4-107">These parentheses are in addition to the parentheses enclosing the argument list in the call.</span></span>  
  
 <span data-ttu-id="51af4-108">Вызывающий код не может переопределить механизм [ByVal](../../../language-reference/modifiers/byval.md) .</span><span class="sxs-lookup"><span data-stu-id="51af4-108">The calling code cannot override a [ByVal](../../../language-reference/modifiers/byval.md) mechanism.</span></span>  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a><span data-ttu-id="51af4-109">Принудительная передача аргумента по значению</span><span class="sxs-lookup"><span data-stu-id="51af4-109">To force an argument to be passed by value</span></span>  
  
- <span data-ttu-id="51af4-110">Если соответствующий параметр объявлен `ByVal` в процедуре, вам не нужно предпринимать никаких дополнительных действий.</span><span class="sxs-lookup"><span data-stu-id="51af4-110">If the corresponding parameter is declared `ByVal` in the procedure, you do not need to take any additional steps.</span></span> <span data-ttu-id="51af4-111">Visual Basic уже ждет передачи аргумента по значению.</span><span class="sxs-lookup"><span data-stu-id="51af4-111">Visual Basic already expects to pass the argument by value.</span></span>  
  
- <span data-ttu-id="51af4-112">Если соответствующий параметр объявлен `ByRef` в процедуре, заключите аргумент в круглые скобки в вызове процедуры.</span><span class="sxs-lookup"><span data-stu-id="51af4-112">If the corresponding parameter is declared `ByRef` in the procedure, enclose the argument in parentheses in the procedure call.</span></span>  
  
## <a name="example"></a><span data-ttu-id="51af4-113">Пример</span><span class="sxs-lookup"><span data-stu-id="51af4-113">Example</span></span>  

 <span data-ttu-id="51af4-114">В следующем примере переопределяется `ByRef` объявление параметра.</span><span class="sxs-lookup"><span data-stu-id="51af4-114">The following example overrides a `ByRef` parameter declaration.</span></span> <span data-ttu-id="51af4-115">В вызове, который вызывает принудительное выполнение `ByVal` , обратите внимание на два уровня круглых скобок.</span><span class="sxs-lookup"><span data-stu-id="51af4-115">In the call that forces `ByVal`, note the two levels of parentheses.</span></span>  
  
 [!code-vb[VbVbcnProcedures#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#39)]  
  
 [!code-vb[VbVbcnProcedures#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#40)]  
  
 <span data-ttu-id="51af4-116">Если `str` аргумент заключен в круглые скобки в списке аргументов, `setNewString` процедура не может изменить ее значение в вызывающем коде и `MsgBox` выводит "не может быть заменен, если передано ByVal".</span><span class="sxs-lookup"><span data-stu-id="51af4-116">When `str` is enclosed in extra parentheses within the argument list, the `setNewString` procedure cannot change its value in the calling code, and `MsgBox` displays "Cannot be replaced if passed ByVal".</span></span> <span data-ttu-id="51af4-117">Если `str` не заключен в круглые скобки, процедура может изменить ее и `MsgBox` выводит "это новое значение для аргумента строки".</span><span class="sxs-lookup"><span data-stu-id="51af4-117">When `str` is not enclosed in extra parentheses, the procedure can change it, and `MsgBox` displays "This is a new value for the inString argument."</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="51af4-118">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="51af4-118">Compile the code</span></span>  

 <span data-ttu-id="51af4-119">При передаче переменной по ссылке необходимо использовать `ByRef` ключевое слово, чтобы указать этот механизм.</span><span class="sxs-lookup"><span data-stu-id="51af4-119">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="51af4-120">По умолчанию в Visual Basic передаются аргументы по значению.</span><span class="sxs-lookup"><span data-stu-id="51af4-120">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="51af4-121">Однако рекомендуется включать ключевое слово [ByVal](../../../language-reference/modifiers/byval.md) или [ByRef](../../../language-reference/modifiers/byref.md) с каждым объявленным параметром.</span><span class="sxs-lookup"><span data-stu-id="51af4-121">However, it is good programming practice to include either the [ByVal](../../../language-reference/modifiers/byval.md) or [ByRef](../../../language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="51af4-122">Это упрощает чтение кода.</span><span class="sxs-lookup"><span data-stu-id="51af4-122">This makes your code easier to read.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="51af4-123">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="51af4-123">Robust Programming</span></span>  

 <span data-ttu-id="51af4-124">Если процедура объявляет параметр [ByRef](../../../language-reference/modifiers/byref.md), правильное выполнение кода может зависеть от возможности изменения базового элемента в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="51af4-124">If a procedure declares a parameter [ByRef](../../../language-reference/modifiers/byref.md), the correct execution of the code might depend on being able to change the underlying element in the calling code.</span></span> <span data-ttu-id="51af4-125">Если вызывающий код переопределяет этот механизм вызова, заключив аргумент в круглые скобки или передавая неизменяемый аргумент, процедура не может изменить базовый элемент.</span><span class="sxs-lookup"><span data-stu-id="51af4-125">If the calling code overrides this calling mechanism by enclosing the argument in parentheses, or if it passes a nonmodifiable argument, the procedure cannot change the underlying element.</span></span> <span data-ttu-id="51af4-126">Это может привести к непредвиденным результатам в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="51af4-126">This might produce unexpected results in the calling code.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="51af4-127">Безопасность .NET Framework</span><span class="sxs-lookup"><span data-stu-id="51af4-127">.NET Framework Security</span></span>  

 <span data-ttu-id="51af4-128">Всегда существует потенциальный риск, позволяющий процедуре изменять значение, которое является базовым для аргумента в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="51af4-128">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="51af4-129">Убедитесь, что это значение было изменено, и будьте готовы проверить его на допустимость перед его использованием.</span><span class="sxs-lookup"><span data-stu-id="51af4-129">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51af4-130">См. также</span><span class="sxs-lookup"><span data-stu-id="51af4-130">See also</span></span>

- [<span data-ttu-id="51af4-131">Процедуры</span><span class="sxs-lookup"><span data-stu-id="51af4-131">Procedures</span></span>](./index.md)
- [<span data-ttu-id="51af4-132">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="51af4-132">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="51af4-133">Практическое руководство. Передача аргументов в процедуру</span><span class="sxs-lookup"><span data-stu-id="51af4-133">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="51af4-134">Передача аргументов по значению и по ссылке</span><span class="sxs-lookup"><span data-stu-id="51af4-134">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="51af4-135">Различия между изменяемыми и неизменяемыми аргументами</span><span class="sxs-lookup"><span data-stu-id="51af4-135">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [<span data-ttu-id="51af4-136">Различия между передачей аргумента по значению и по ссылке</span><span class="sxs-lookup"><span data-stu-id="51af4-136">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="51af4-137">Практическое руководство. Изменение значения аргумента процедуры</span><span class="sxs-lookup"><span data-stu-id="51af4-137">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="51af4-138">Практическое руководство. Защита аргумента процедуры от изменений значения</span><span class="sxs-lookup"><span data-stu-id="51af4-138">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="51af4-139">Передача аргументов по позиции и по имени</span><span class="sxs-lookup"><span data-stu-id="51af4-139">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="51af4-140">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="51af4-140">Value Types and Reference Types</span></span>](../data-types/value-types-and-reference-types.md)
