---
title: 'Объявление оператора должно быть одним из следующих: +,-, *,-,-, ^, &amp; , Like, mod, and, или, XOR, not,  <<,  >>, =,  <>, <, <=, >, >=, CType, IsTrue, IsFalse'
ms.date: 07/20/2015
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
ms.openlocfilehash: c388b1b0762dd7475ca365a8a62228d0b5d59414
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873611"
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not--"></a><span data-ttu-id="d14fe-102">Объявление оператора должно быть одним из следующих: +,-, \*, \, /, ^, &amp; , Like, mod, and, или, XOR, not, \<\<, >>...</span><span class="sxs-lookup"><span data-stu-id="d14fe-102">Operator declaration must be one of:  +,-,\*,\,/,^, &amp;, Like, Mod, And, Or, Xor, Not, \<\<, >>...</span></span>

<span data-ttu-id="d14fe-103">Можно объявить только оператор, пригодный для перегрузки.</span><span class="sxs-lookup"><span data-stu-id="d14fe-103">You can declare only an operator that is eligible for overloading.</span></span> <span data-ttu-id="d14fe-104">В следующей таблице перечислены операторы, которые можно объявить.</span><span class="sxs-lookup"><span data-stu-id="d14fe-104">The following table lists the operators you can declare.</span></span>  
  
|<span data-ttu-id="d14fe-105">Тип</span><span class="sxs-lookup"><span data-stu-id="d14fe-105">Type</span></span>|<span data-ttu-id="d14fe-106">Операторы</span><span class="sxs-lookup"><span data-stu-id="d14fe-106">Operators</span></span>|  
|----------|---------------|  
|<span data-ttu-id="d14fe-107">Унарный</span><span class="sxs-lookup"><span data-stu-id="d14fe-107">Unary</span></span>|<span data-ttu-id="d14fe-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="d14fe-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|  
|<span data-ttu-id="d14fe-109">Двоичные данные</span><span class="sxs-lookup"><span data-stu-id="d14fe-109">Binary</span></span>|<span data-ttu-id="d14fe-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="d14fe-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|  
|<span data-ttu-id="d14fe-111">Преобразование (унарный)</span><span class="sxs-lookup"><span data-stu-id="d14fe-111">Conversion (unary)</span></span>|`CType`|  
  
 <span data-ttu-id="d14fe-112">Обратите внимание, что `=` оператор в списке binary является оператором сравнения, а не оператором присваивания.</span><span class="sxs-lookup"><span data-stu-id="d14fe-112">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="d14fe-113">**Идентификатор ошибки:** BC33000</span><span class="sxs-lookup"><span data-stu-id="d14fe-113">**Error ID:** BC33000</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d14fe-114">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="d14fe-114">To correct this error</span></span>  
  
1. <span data-ttu-id="d14fe-115">Выберите оператор из набора перегружаемых операторов.</span><span class="sxs-lookup"><span data-stu-id="d14fe-115">Select an operator from the set of overloadable operators.</span></span>  
  
2. <span data-ttu-id="d14fe-116">Если требуется возможность перегрузки оператора, который нельзя перегрузить непосредственно, создайте процедуру `Function` , которая принимает соответствующие параметры и возвращает соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="d14fe-116">If you need the functionality of overloading an operator that you cannot overload directly, create a `Function` procedure that takes the appropriate parameters and returns the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d14fe-117">См. также</span><span class="sxs-lookup"><span data-stu-id="d14fe-117">See also</span></span>

- [<span data-ttu-id="d14fe-118">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="d14fe-118">Operator Statement</span></span>](../statements/operator-statement.md)
- [<span data-ttu-id="d14fe-119">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="d14fe-119">Operator Procedures</span></span>](../../programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="d14fe-120">Практическое руководство. Определение оператора</span><span class="sxs-lookup"><span data-stu-id="d14fe-120">How to: Define an Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="d14fe-121">Практическое руководство. Определение оператора преобразования</span><span class="sxs-lookup"><span data-stu-id="d14fe-121">How to: Define a Conversion Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="d14fe-122">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="d14fe-122">Function Statement</span></span>](../statements/function-statement.md)
