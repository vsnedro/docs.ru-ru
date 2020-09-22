---
title: Лямбда-выражения недопустимы в первом выражении оператора Select Case
ms.date: 07/20/2015
f1_keywords:
- bc36635
- vbc36635
helpviewer_keywords:
- BC36635
ms.assetid: 74609979-9c03-4864-bbce-f588aa2e0917
ms.openlocfilehash: 9f200ea44e7505c407c7df56e596435024394875
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873869"
---
# <a name="lambda-expressions-are-not-valid-in-the-first-expression-of-a-select-case-statement"></a><span data-ttu-id="6cecf-102">Лямбда-выражения недопустимы в первом выражении оператора Select Case</span><span class="sxs-lookup"><span data-stu-id="6cecf-102">Lambda expressions are not valid in the first expression of a 'Select Case' statement</span></span>

<span data-ttu-id="6cecf-103">Нельзя использовать лямбда-выражение для тестового выражения в `Select Case` инструкции.</span><span class="sxs-lookup"><span data-stu-id="6cecf-103">You cannot use a lambda expression for the test expression in a `Select Case` statement.</span></span> <span data-ttu-id="6cecf-104">Определения лямбда-выражений возвращают функции, а тестовое выражение `Select Case` инструкции должно иметь простейший тип данных.</span><span class="sxs-lookup"><span data-stu-id="6cecf-104">Lambda expression definitions return functions, and the test expression of a `Select Case` statement must be an elementary data type.</span></span>  
  
 <span data-ttu-id="6cecf-105">Следующий код вызывает эту ошибку:</span><span class="sxs-lookup"><span data-stu-id="6cecf-105">The following code causes this error:</span></span>  
  
```vb  
' Select Case (Function(arg) arg Is Nothing)  
    ' List of the cases.  
' End Select  
```  
  
 <span data-ttu-id="6cecf-106">**Идентификатор ошибки:** BC36635</span><span class="sxs-lookup"><span data-stu-id="6cecf-106">**Error ID:** BC36635</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6cecf-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="6cecf-107">To correct this error</span></span>  
  
- <span data-ttu-id="6cecf-108">Проверьте свой код, чтобы определить, подойдет ли вам другая условная конструкция, например оператор `If...Then...Else` .</span><span class="sxs-lookup"><span data-stu-id="6cecf-108">Examine your code to determine whether a different conditional construction, such as an `If...Then...Else` statement, would work for you.</span></span>  
  
- <span data-ttu-id="6cecf-109">Возможно, вы предполагали вызвать функцию, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="6cecf-109">You may have intended to call the function, as shown in the following code:</span></span>  
  
```vb  
Dim num? As Integer  
Select Case ((Function(arg? As Integer) arg Is Nothing)(num))  
    ' List of the cases  
End Select  
```  
  
## <a name="see-also"></a><span data-ttu-id="6cecf-110">См. также</span><span class="sxs-lookup"><span data-stu-id="6cecf-110">See also</span></span>

- [<span data-ttu-id="6cecf-111">Лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="6cecf-111">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="6cecf-112">Оператор If…Then…Else</span><span class="sxs-lookup"><span data-stu-id="6cecf-112">If...Then...Else Statement</span></span>](../statements/if-then-else-statement.md)
- [<span data-ttu-id="6cecf-113">Оператор Select…Case</span><span class="sxs-lookup"><span data-stu-id="6cecf-113">Select...Case Statement</span></span>](../statements/select-case-statement.md)
