---
title: Оператор is
ms.date: 07/20/2015
f1_keywords:
- vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
ms.openlocfilehash: 1c2d87ef0a8202332c87af552f488d652c400213
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812267"
---
# <a name="is-operator-visual-basic"></a><span data-ttu-id="edd32-102">Оператор is (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="edd32-102">Is operator (Visual Basic)</span></span>

<span data-ttu-id="edd32-103">Сравнивает две переменные ссылки на объект.</span><span class="sxs-lookup"><span data-stu-id="edd32-103">Compares two object reference variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="edd32-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="edd32-104">Syntax</span></span>

```vb
result = object1 Is object2
```

## <a name="parts"></a><span data-ttu-id="edd32-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="edd32-105">Parts</span></span>

 `result`  
 <span data-ttu-id="edd32-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="edd32-106">Required.</span></span> <span data-ttu-id="edd32-107">Любое `Boolean` значение.</span><span class="sxs-lookup"><span data-stu-id="edd32-107">Any `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="edd32-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="edd32-108">Required.</span></span> <span data-ttu-id="edd32-109">Любое `Object` имя.</span><span class="sxs-lookup"><span data-stu-id="edd32-109">Any `Object` name.</span></span>  
  
 `object2`  
 <span data-ttu-id="edd32-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="edd32-110">Required.</span></span> <span data-ttu-id="edd32-111">Любое `Object` имя.</span><span class="sxs-lookup"><span data-stu-id="edd32-111">Any `Object` name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="edd32-112">Комментарии</span><span class="sxs-lookup"><span data-stu-id="edd32-112">Remarks</span></span>

<span data-ttu-id="edd32-113">`Is`Оператор определяет, ссылаются ли две объектные ссылки на один и тот же объект.</span><span class="sxs-lookup"><span data-stu-id="edd32-113">The `Is` operator determines if two object references refer to the same object.</span></span> <span data-ttu-id="edd32-114">Однако сравнение значений не выполняется.</span><span class="sxs-lookup"><span data-stu-id="edd32-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="edd32-115">Если `object1` и `object2` оба ссылаются на один и тот же экземпляр объекта, `result` имеет значение `True` ; Если нет, `result` то имеет значение `False` .</span><span class="sxs-lookup"><span data-stu-id="edd32-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `True`; if they do not, `result` is `False`.</span></span>

> [!NOTE]
> <span data-ttu-id="edd32-116">`Is`Ключевое слово также используется в [SELECT... Case, инструкция](../statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="edd32-116">The `Is` keyword is also used in the [Select...Case Statement](../statements/select-case-statement.md).</span></span>
  
## <a name="example"></a><span data-ttu-id="edd32-117">Пример</span><span class="sxs-lookup"><span data-stu-id="edd32-117">Example</span></span>

<span data-ttu-id="edd32-118">В следующем примере оператор используется `Is` для сравнения пар ссылок на объекты.</span><span class="sxs-lookup"><span data-stu-id="edd32-118">The following example uses the `Is` operator to compare pairs of object references.</span></span> <span data-ttu-id="edd32-119">Результаты присваиваются `Boolean` значению, представляющему идентичность двух объектов.</span><span class="sxs-lookup"><span data-stu-id="edd32-119">The results are assigned to a `Boolean` value representing whether the two objects are identical.</span></span>

[!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]

<span data-ttu-id="edd32-120">Как показано в предыдущем примере, оператор можно использовать `Is` для тестирования объектов с ранней и поздней привязкой.</span><span class="sxs-lookup"><span data-stu-id="edd32-120">As the preceding example demonstrates, you can use the `Is` operator to test both early bound and late bound objects.</span></span>

## <a name="use-typeof-operator-with-is-operator"></a><span data-ttu-id="edd32-121">Использование оператора TypeOf с оператором is</span><span class="sxs-lookup"><span data-stu-id="edd32-121">Use TypeOf operator with Is operator</span></span>

<span data-ttu-id="edd32-122">`Is` Оператор также можно использовать с `TypeOf` ключевым словом для создания `TypeOf` выражения... `Is` , которое проверяет, совместима ли объектная переменная с типом данных.</span><span class="sxs-lookup"><span data-stu-id="edd32-122">`Is` operator can also be used with the `TypeOf` keyword to make a `TypeOf`...`Is` expression, which tests whether an object variable is compatible with a data type.</span></span> <span data-ttu-id="edd32-123">Пример:</span><span class="sxs-lookup"><span data-stu-id="edd32-123">For example:</span></span>

```vb
If TypeOf sender Is Button Then
```

## <a name="see-also"></a><span data-ttu-id="edd32-124">См. также</span><span class="sxs-lookup"><span data-stu-id="edd32-124">See also</span></span>

- [<span data-ttu-id="edd32-125">TypeOf, оператор</span><span class="sxs-lookup"><span data-stu-id="edd32-125">TypeOf Operator</span></span>](typeof-operator.md)
- [<span data-ttu-id="edd32-126">Оператор IsNot</span><span class="sxs-lookup"><span data-stu-id="edd32-126">IsNot Operator</span></span>](isnot-operator.md)
- [<span data-ttu-id="edd32-127">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="edd32-127">Comparison Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="edd32-128">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="edd32-128">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="edd32-129">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="edd32-129">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="edd32-130">Операторы и выражения</span><span class="sxs-lookup"><span data-stu-id="edd32-130">Operators and Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/index.md)
