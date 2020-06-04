---
title: 'Объявление оператора должно быть одним из следующих: +,-, *,-,-, ^, &amp; , Like, mod, and, или, XOR, not,  <<,  >>, =,  <>, <, <=, >, >=, CType, IsTrue, IsFalse'
ms.date: 07/20/2015
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
ms.openlocfilehash: 3fb2cf392611e5ca83818e3bf173513be031085d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409339"
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not--"></a><span data-ttu-id="29a54-102">Объявление оператора должно быть одним из следующих: +,-, \*, \, /, ^, &amp; , Like, mod, and, или, XOR, not, \<\<, >>...</span><span class="sxs-lookup"><span data-stu-id="29a54-102">Operator declaration must be one of:  +,-,\*,\,/,^, &amp;, Like, Mod, And, Or, Xor, Not, \<\<, >>...</span></span>
<span data-ttu-id="29a54-103">Можно объявить только оператор, пригодный для перегрузки.</span><span class="sxs-lookup"><span data-stu-id="29a54-103">You can declare only an operator that is eligible for overloading.</span></span> <span data-ttu-id="29a54-104">В следующей таблице перечислены операторы, которые можно объявить.</span><span class="sxs-lookup"><span data-stu-id="29a54-104">The following table lists the operators you can declare.</span></span>  
  
|<span data-ttu-id="29a54-105">Тип</span><span class="sxs-lookup"><span data-stu-id="29a54-105">Type</span></span>|<span data-ttu-id="29a54-106">Операторы</span><span class="sxs-lookup"><span data-stu-id="29a54-106">Operators</span></span>|  
|----------|---------------|  
|<span data-ttu-id="29a54-107">Унарный</span><span class="sxs-lookup"><span data-stu-id="29a54-107">Unary</span></span>|<span data-ttu-id="29a54-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="29a54-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|  
|<span data-ttu-id="29a54-109">Двоичный</span><span class="sxs-lookup"><span data-stu-id="29a54-109">Binary</span></span>|<span data-ttu-id="29a54-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="29a54-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|  
|<span data-ttu-id="29a54-111">Преобразование (унарный)</span><span class="sxs-lookup"><span data-stu-id="29a54-111">Conversion (unary)</span></span>|`CType`|  
  
 <span data-ttu-id="29a54-112">Обратите внимание, что `=` оператор в списке binary является оператором сравнения, а не оператором присваивания.</span><span class="sxs-lookup"><span data-stu-id="29a54-112">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="29a54-113">**Идентификатор ошибки:** BC33000</span><span class="sxs-lookup"><span data-stu-id="29a54-113">**Error ID:** BC33000</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="29a54-114">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="29a54-114">To correct this error</span></span>  
  
1. <span data-ttu-id="29a54-115">Выберите оператор из набора перегружаемых операторов.</span><span class="sxs-lookup"><span data-stu-id="29a54-115">Select an operator from the set of overloadable operators.</span></span>  
  
2. <span data-ttu-id="29a54-116">Если требуется возможность перегрузки оператора, который нельзя перегрузить непосредственно, создайте процедуру `Function` , которая принимает соответствующие параметры и возвращает соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="29a54-116">If you need the functionality of overloading an operator that you cannot overload directly, create a `Function` procedure that takes the appropriate parameters and returns the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29a54-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="29a54-117">See also</span></span>

- [<span data-ttu-id="29a54-118">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="29a54-118">Operator Statement</span></span>](../statements/operator-statement.md)
- [<span data-ttu-id="29a54-119">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="29a54-119">Operator Procedures</span></span>](../../programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="29a54-120">Практическое руководство. Определение оператора</span><span class="sxs-lookup"><span data-stu-id="29a54-120">How to: Define an Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="29a54-121">Практическое руководство. Определение оператора преобразования</span><span class="sxs-lookup"><span data-stu-id="29a54-121">How to: Define a Conversion Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="29a54-122">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="29a54-122">Function Statement</span></span>](../statements/function-statement.md)
