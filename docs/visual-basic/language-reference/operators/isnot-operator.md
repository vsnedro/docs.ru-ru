---
title: IsNot - оператор
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- comparison operators [Visual Basic]
- TypeOf...IsNot expression
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: ea978f8874cee20fb3a005189fd846f7564da777
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811045"
---
# <a name="isnot-operator-visual-basic"></a><span data-ttu-id="5d6d5-102">Оператор IsNot (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d6d5-102">IsNot Operator (Visual Basic)</span></span>

<span data-ttu-id="5d6d5-103">Сравнивает две переменные ссылки на объект.</span><span class="sxs-lookup"><span data-stu-id="5d6d5-103">Compares two object reference variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="5d6d5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5d6d5-104">Syntax</span></span>

```vb
result = object1 IsNot object2
```

## <a name="parts"></a><span data-ttu-id="5d6d5-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="5d6d5-105">Parts</span></span>

- `result`

  <span data-ttu-id="5d6d5-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="5d6d5-106">Required.</span></span> <span data-ttu-id="5d6d5-107">Значение `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="5d6d5-107">A `Boolean` value.</span></span>

- `object1`

  <span data-ttu-id="5d6d5-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="5d6d5-108">Required.</span></span> <span data-ttu-id="5d6d5-109">Любая `Object` переменная или выражение.</span><span class="sxs-lookup"><span data-stu-id="5d6d5-109">Any `Object` variable or expression.</span></span>

- `object2`

  <span data-ttu-id="5d6d5-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="5d6d5-110">Required.</span></span> <span data-ttu-id="5d6d5-111">Любая `Object` переменная или выражение.</span><span class="sxs-lookup"><span data-stu-id="5d6d5-111">Any `Object` variable or expression.</span></span>

## <a name="remarks"></a><span data-ttu-id="5d6d5-112">Комментарии</span><span class="sxs-lookup"><span data-stu-id="5d6d5-112">Remarks</span></span>

<span data-ttu-id="5d6d5-113">`IsNot`Оператор определяет, ссылаются ли две объектные ссылки на разные объекты.</span><span class="sxs-lookup"><span data-stu-id="5d6d5-113">The `IsNot` operator determines if two object references refer to different objects.</span></span> <span data-ttu-id="5d6d5-114">Однако сравнение значений не выполняется.</span><span class="sxs-lookup"><span data-stu-id="5d6d5-114">However, it doesn't perform value comparisons.</span></span> <span data-ttu-id="5d6d5-115">Если `object1` и `object2` оба ссылаются на один и тот же экземпляр объекта, `result` имеет значение `False` ; Если нет, `result` то имеет значение `True` .</span><span class="sxs-lookup"><span data-stu-id="5d6d5-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `False`; if they don't, `result` is `True`.</span></span>

<span data-ttu-id="5d6d5-116">`IsNot` является противоположностью `Is` оператора.</span><span class="sxs-lookup"><span data-stu-id="5d6d5-116">`IsNot` is the opposite of the `Is` operator.</span></span> <span data-ttu-id="5d6d5-117">Преимущество заключается в том `IsNot` , что можно избежать неудобного синтаксиса с `Not` и `Is` , что может быть трудно читать.</span><span class="sxs-lookup"><span data-stu-id="5d6d5-117">The advantage of `IsNot` is that you can avoid awkward syntax with `Not` and `Is`, which can be difficult to read.</span></span>

 <span data-ttu-id="5d6d5-118">Операторы и можно использовать `Is` `IsNot` для тестирования объектов с ранней и поздней привязкой.</span><span class="sxs-lookup"><span data-stu-id="5d6d5-118">You can use the `Is` and `IsNot` operators to test both early-bound and late-bound objects.</span></span>

## <a name="example"></a><span data-ttu-id="5d6d5-119">Пример</span><span class="sxs-lookup"><span data-stu-id="5d6d5-119">Example</span></span>

<span data-ttu-id="5d6d5-120">В следующем примере кода используются `Is` оператор и `IsNot` оператор для выполнения одинакового сравнения.</span><span class="sxs-lookup"><span data-stu-id="5d6d5-120">The following code example uses both the `Is` operator and the `IsNot` operator to accomplish the same comparison.</span></span>

[!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]

## <a name="use-typeof-operator-with-isnot-operator"></a><span data-ttu-id="5d6d5-121">Использование оператора TypeOf с оператором IsNot</span><span class="sxs-lookup"><span data-stu-id="5d6d5-121">Use TypeOf operator with IsNot operator</span></span>

<span data-ttu-id="5d6d5-122">Начиная с Visual Basic 14 можно использовать `TypeOf` оператор с `IsNot` оператором, чтобы проверить, несовместим ли объект с типом *not* данных.</span><span class="sxs-lookup"><span data-stu-id="5d6d5-122">Starting with Visual Basic 14, you can use the `TypeOf` operator with the `IsNot` operator to test whether an object is *not* compatible with a data type.</span></span> <span data-ttu-id="5d6d5-123">Пример:</span><span class="sxs-lookup"><span data-stu-id="5d6d5-123">For example:</span></span>

```vb
If TypeOf sender IsNot Button Then
```

## <a name="see-also"></a><span data-ttu-id="5d6d5-124">См. также</span><span class="sxs-lookup"><span data-stu-id="5d6d5-124">See also</span></span>

- [<span data-ttu-id="5d6d5-125">Оператор is</span><span class="sxs-lookup"><span data-stu-id="5d6d5-125">Is Operator</span></span>](is-operator.md)
- [<span data-ttu-id="5d6d5-126">TypeOf, оператор</span><span class="sxs-lookup"><span data-stu-id="5d6d5-126">TypeOf Operator</span></span>](typeof-operator.md)
- [<span data-ttu-id="5d6d5-127">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5d6d5-127">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="5d6d5-128">Практическое руководство. Проверка совпадения двух объектов</span><span class="sxs-lookup"><span data-stu-id="5d6d5-128">How to: Test Whether Two Objects Are the Same</span></span>](../../programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
