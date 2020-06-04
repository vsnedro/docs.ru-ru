---
title: Оператор Is
ms.date: 07/20/2015
f1_keywords:
- vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
ms.openlocfilehash: 3cc0ae5f04358fbe6b2aabc50498f39ca7225164
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84370808"
---
# <a name="is-operator-visual-basic"></a><span data-ttu-id="33aaa-102">Оператор Is (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="33aaa-102">Is Operator (Visual Basic)</span></span>
<span data-ttu-id="33aaa-103">Сравнивает две переменные ссылки на объект.</span><span class="sxs-lookup"><span data-stu-id="33aaa-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33aaa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="33aaa-104">Syntax</span></span>  
  
```vb  
result = object1 Is object2  
```  
  
## <a name="parts"></a><span data-ttu-id="33aaa-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="33aaa-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="33aaa-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="33aaa-106">Required.</span></span> <span data-ttu-id="33aaa-107">Любое `Boolean` значение.</span><span class="sxs-lookup"><span data-stu-id="33aaa-107">Any `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="33aaa-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="33aaa-108">Required.</span></span> <span data-ttu-id="33aaa-109">Любое `Object` имя.</span><span class="sxs-lookup"><span data-stu-id="33aaa-109">Any `Object` name.</span></span>  
  
 `object2`  
 <span data-ttu-id="33aaa-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="33aaa-110">Required.</span></span> <span data-ttu-id="33aaa-111">Любое `Object` имя.</span><span class="sxs-lookup"><span data-stu-id="33aaa-111">Any `Object` name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33aaa-112">Комментарии</span><span class="sxs-lookup"><span data-stu-id="33aaa-112">Remarks</span></span>  
 <span data-ttu-id="33aaa-113">`Is`Оператор определяет, ссылаются ли две объектные ссылки на один и тот же объект.</span><span class="sxs-lookup"><span data-stu-id="33aaa-113">The `Is` operator determines if two object references refer to the same object.</span></span> <span data-ttu-id="33aaa-114">Однако сравнение значений не выполняется.</span><span class="sxs-lookup"><span data-stu-id="33aaa-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="33aaa-115">Если `object1` и `object2` оба ссылаются на один и тот же экземпляр объекта, `result` имеет значение `True` ; Если нет, `result` то имеет значение `False` .</span><span class="sxs-lookup"><span data-stu-id="33aaa-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `True`; if they do not, `result` is `False`.</span></span>  
  
 <span data-ttu-id="33aaa-116">`Is`также можно использовать с `TypeOf` ключевым словом для создания `TypeOf` выражения... `Is` , которое проверяет, совместима ли объектная переменная с типом данных.</span><span class="sxs-lookup"><span data-stu-id="33aaa-116">`Is` can also be used with the `TypeOf` keyword to make a `TypeOf`...`Is` expression, which tests whether an object variable is compatible with a data type.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="33aaa-117">`Is`Ключевое слово также используется в [SELECT... Case, инструкция](../statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="33aaa-117">The `Is` keyword is also used in the [Select...Case Statement](../statements/select-case-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="33aaa-118">Пример</span><span class="sxs-lookup"><span data-stu-id="33aaa-118">Example</span></span>  
 <span data-ttu-id="33aaa-119">В следующем примере оператор используется `Is` для сравнения пар ссылок на объекты.</span><span class="sxs-lookup"><span data-stu-id="33aaa-119">The following example uses the `Is` operator to compare pairs of object references.</span></span> <span data-ttu-id="33aaa-120">Результаты присваиваются `Boolean` значению, представляющему идентичность двух объектов.</span><span class="sxs-lookup"><span data-stu-id="33aaa-120">The results are assigned to a `Boolean` value representing whether the two objects are identical.</span></span>  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 <span data-ttu-id="33aaa-121">Как показано в предыдущем примере, оператор можно использовать `Is` для тестирования объектов с ранней и поздней привязкой.</span><span class="sxs-lookup"><span data-stu-id="33aaa-121">As the preceding example demonstrates, you can use the `Is` operator to test both early bound and late bound objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33aaa-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="33aaa-122">See also</span></span>

- [<span data-ttu-id="33aaa-123">TypeOf, оператор</span><span class="sxs-lookup"><span data-stu-id="33aaa-123">TypeOf Operator</span></span>](typeof-operator.md)
- [<span data-ttu-id="33aaa-124">Оператор IsNot</span><span class="sxs-lookup"><span data-stu-id="33aaa-124">IsNot Operator</span></span>](isnot-operator.md)
- [<span data-ttu-id="33aaa-125">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="33aaa-125">Comparison Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="33aaa-126">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="33aaa-126">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="33aaa-127">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="33aaa-127">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="33aaa-128">Операторы и выражения</span><span class="sxs-lookup"><span data-stu-id="33aaa-128">Operators and Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/index.md)
