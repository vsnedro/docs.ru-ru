---
description: ?? и ??= — справочник по C#
title: ?? и ??= — справочник по C#
ms.date: 09/10/2019
f1_keywords:
- ??_CSharpKeyword
- ??=_CSharpKeyword
helpviewer_keywords:
- null-coalescing operator [C#]
- ?? operator [C#]
- null-coalescing assignment [C#]
- ??= operator [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
ms.openlocfilehash: 273bc6d3a4c65c09dc600621b435bf0d1baea9e4
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89118290"
---
# <a name="-and--operators-c-reference"></a><span data-ttu-id="df3b8-105">??</span><span class="sxs-lookup"><span data-stu-id="df3b8-105">??</span></span> <span data-ttu-id="df3b8-106">и ??= (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="df3b8-106">and ??= operators (C# reference)</span></span>

<span data-ttu-id="df3b8-107">Оператор объединения с NULL `??` возвращает значение своего операнда слева, если его значение не равно `null`. В противном случае он вычисляет операнд справа и возвращает его результат.</span><span class="sxs-lookup"><span data-stu-id="df3b8-107">The null-coalescing operator `??` returns the value of its left-hand operand if it isn't `null`; otherwise, it evaluates the right-hand operand and returns its result.</span></span> <span data-ttu-id="df3b8-108">Оператор `??` не выполняет оценку своего операнда справа, если его операнд слева имеет значение, отличное от NULL.</span><span class="sxs-lookup"><span data-stu-id="df3b8-108">The `??` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

<span data-ttu-id="df3b8-109">Начиная с C# 8.0 можно использовать оператор присваивания объединения со значением NULL `??=` для присваивания значения правого операнда левому операнду только в том случае, если левый операнд принимает значение `null`.</span><span class="sxs-lookup"><span data-stu-id="df3b8-109">Available in C# 8.0 and later, the null-coalescing assignment operator `??=` assigns the value of its right-hand operand to its left-hand operand only if the left-hand operand evaluates to `null`.</span></span> <span data-ttu-id="df3b8-110">Оператор `??=` не выполняет оценку своего операнда справа, если его операнд слева имеет значение, отличное от NULL.</span><span class="sxs-lookup"><span data-stu-id="df3b8-110">The `??=` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

[!code-csharp[null-coalescing assignment](snippets/shared/NullCoalescingOperator.cs#Assignment)]

<span data-ttu-id="df3b8-111">Левый операнд оператора `??=` должен быть переменной, [свойством](../../programming-guide/classes-and-structs/properties.md) или элементом [индексатора](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="df3b8-111">The left-hand operand of the `??=` operator must be a variable, a [property](../../programming-guide/classes-and-structs/properties.md), or an [indexer](../../programming-guide/indexers/index.md) element.</span></span>

<span data-ttu-id="df3b8-112">В C# 7.3 и более ранних версий левый операнд оператора `??` должен иметь либо [ссылочный тип](../keywords/reference-types.md), либо [тип значения, допускающий значение NULL](../builtin-types/nullable-value-types.md).</span><span class="sxs-lookup"><span data-stu-id="df3b8-112">In C# 7.3 and earlier, the type of the left-hand operand of the `??` operator must be either a [reference type](../keywords/reference-types.md) or a [nullable value type](../builtin-types/nullable-value-types.md).</span></span> <span data-ttu-id="df3b8-113">Начиная с C# 8.0 это требование заменяется следующим: тип левого операнда операторов `??` и `??=` не может быть типом значения, не допускающим значение NULL.</span><span class="sxs-lookup"><span data-stu-id="df3b8-113">Beginning with C# 8.0, that requirement is replaced with the following: the type of the left-hand operand of the `??` and `??=` operators cannot be a non-nullable value type.</span></span> <span data-ttu-id="df3b8-114">В частности, начиная с версии C# 8.0, можно использовать операторы объединения со значением NULL с неограниченными параметрами типа:</span><span class="sxs-lookup"><span data-stu-id="df3b8-114">In particular, beginning with C# 8.0, you can use the null-coalescing operators with unconstrained type parameters:</span></span>

[!code-csharp[unconstrained type parameter](snippets/shared/NullCoalescingOperator.cs#UnconstrainedType)]

<span data-ttu-id="df3b8-115">Операторы объединения со значением NULL являются правоассоциативными.</span><span class="sxs-lookup"><span data-stu-id="df3b8-115">The null-coalescing operators are right-associative.</span></span> <span data-ttu-id="df3b8-116">То есть выражения в форме</span><span class="sxs-lookup"><span data-stu-id="df3b8-116">That is, expressions of the form</span></span>

```csharp
a ?? b ?? c
d ??= e ??= f
```

<span data-ttu-id="df3b8-117">вычисляются как</span><span class="sxs-lookup"><span data-stu-id="df3b8-117">are evaluated as</span></span>

```csharp
a ?? (b ?? c)
d ??= (e ??= f)
```

## <a name="examples"></a><span data-ttu-id="df3b8-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="df3b8-118">Examples</span></span>

<span data-ttu-id="df3b8-119">Операторы `??` и `??=` могут быть полезны в таких случаях:</span><span class="sxs-lookup"><span data-stu-id="df3b8-119">The `??` and `??=` operators can be useful in the following scenarios:</span></span>

- <span data-ttu-id="df3b8-120">В выражениях с [NULL-условными операторами ?. и ?[]](member-access-operators.md#null-conditional-operators--and-) можно использовать оператор `null`, чтобы задать альтернативное выражение для оценки на случай, если результат выражения с NULL-условной операцией будет равен `??`.</span><span class="sxs-lookup"><span data-stu-id="df3b8-120">In expressions with the [null-conditional operators ?. and ?[]](member-access-operators.md#null-conditional-operators--and-), you can use the `??` operator to provide an alternative expression to evaluate in case the result of the expression with null-conditional operations is `null`:</span></span>

  [!code-csharp-interactive[with null-conditional](snippets/shared/NullCoalescingOperator.cs#WithNullConditional)]

- <span data-ttu-id="df3b8-121">Когда вы работаете с [типами, допускающими значение NULL](../builtin-types/nullable-value-types.md), и вам нужно указать значение базового типа значения, используйте оператор `??` для указания значения, возвращаемого в том случае, если значение типа, допускающего значение NULL, равно `null`.</span><span class="sxs-lookup"><span data-stu-id="df3b8-121">When you work with [nullable value types](../builtin-types/nullable-value-types.md) and need to provide a value of an underlying value type, use the `??` operator to specify the value to provide in case a nullable type value is `null`:</span></span>

  [!code-csharp-interactive[with nullable types](snippets/shared/NullCoalescingOperator.cs#WithNullableTypes)]

  <span data-ttu-id="df3b8-122">Используйте метод <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType>, если значение, которое будет использоваться, когда значение типа, допускающего значение NULL, равно `null`, должно быть значением по умолчанию базового типа.</span><span class="sxs-lookup"><span data-stu-id="df3b8-122">Use the <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> method if the value to be used when a nullable type value is `null` should be the default value of the underlying value type.</span></span>

- <span data-ttu-id="df3b8-123">Начиная с версии C# 7.0, можно сократить код проверки аргументов, используя [выражение `throw`](../keywords/throw.md#the-throw-expression) в качестве правого операнда оператора `??`:</span><span class="sxs-lookup"><span data-stu-id="df3b8-123">Beginning with C# 7.0, you can use a [`throw` expression](../keywords/throw.md#the-throw-expression) as the right-hand operand of the `??` operator to make the argument-checking code more concise:</span></span>

  [!code-csharp[with throw expression](snippets/shared/NullCoalescingOperator.cs#WithThrowExpression)]

  <span data-ttu-id="df3b8-124">В предыдущем примере также демонстрируются способы определения свойства с помощью [членов, заданных выражениями](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="df3b8-124">The preceding example also demonstrates how to use [expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) to define a property.</span></span>

- <span data-ttu-id="df3b8-125">Начиная с версии C# 8.0, можно использовать оператор `??=` для замены кода формы</span><span class="sxs-lookup"><span data-stu-id="df3b8-125">Beginning with C# 8.0, you can use the `??=` operator to replace the code of the form</span></span>

  ```csharp
  if (variable is null)
  {
      variable = expression;
  }
  ```

  <span data-ttu-id="df3b8-126">на новый код:</span><span class="sxs-lookup"><span data-stu-id="df3b8-126">with the following code:</span></span>

  ```csharp
  variable ??= expression;
  ```

## <a name="operator-overloadability"></a><span data-ttu-id="df3b8-127">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="df3b8-127">Operator overloadability</span></span>

<span data-ttu-id="df3b8-128">Операторы `??` и `??=` не могут быть перегружены.</span><span class="sxs-lookup"><span data-stu-id="df3b8-128">The operators `??` and `??=` cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="df3b8-129">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="df3b8-129">C# language specification</span></span>

<span data-ttu-id="df3b8-130">Дополнительные сведения об операторе `??` см. в разделе об [операторе объединения со значением NULL](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) в [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="df3b8-130">For more information about the `??` operator, see [The null coalescing operator](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="df3b8-131">См. сведения об операторе `??=` в [примечании к предлагаемой функции](~/_csharplang/proposals/csharp-8.0/null-coalescing-assignment.md).</span><span class="sxs-lookup"><span data-stu-id="df3b8-131">For more information about the `??=` operator, see the [feature proposal note](~/_csharplang/proposals/csharp-8.0/null-coalescing-assignment.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="df3b8-132">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="df3b8-132">See also</span></span>

- [<span data-ttu-id="df3b8-133">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="df3b8-133">C# reference</span></span>](../index.md)
- [<span data-ttu-id="df3b8-134">Операторы и выражения C#</span><span class="sxs-lookup"><span data-stu-id="df3b8-134">C# operators and expressions</span></span>](index.md)
- <span data-ttu-id="df3b8-135">[Операторы ?. и ?[]](member-access-operators.md#null-conditional-operators--and-)</span><span class="sxs-lookup"><span data-stu-id="df3b8-135">[?. and ?[] operators](member-access-operators.md#null-conditional-operators--and-)</span></span>
- [<span data-ttu-id="df3b8-136">Оператор ?</span><span class="sxs-lookup"><span data-stu-id="df3b8-136">?: operator</span></span>](conditional-operator.md)
