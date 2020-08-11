---
title: Логические операторы. Справочник по C#
description: Узнайте об операторах C#, которые выполняют такие логические операции, как отрицание, конъюнкция (И), а также инклюзивная и эксклюзивная дизъюнкция (ИЛИ), с использованием соответствующих операндов.
ms.date: 06/29/2020
author: pkulikov
f1_keywords:
- '!_CSharpKeyword'
- '&_CSharpKeyword'
- ^_CSharpKeyword
- '|_CSharpKeyword'
- '&&_CSharpKeyword'
- '||_CSharpKeyword'
- '|=_CSharpKeyword'
- ^=_CSharpKeyword
- '&=_CSharpKeyword'
helpviewer_keywords:
- logical operators [C#]
- short-circuiting operators [C#]
- logical negation operator [C#]
- NOT operator [C#]
- '! operator [C#]'
- AND operator [C#]
- ampersand operator [C#]
- conjunction operator [C#]
- '& operator [C#]'
- exclusive OR operator [C#]
- XOR operator [C#]
- ^ operator [C#]
- OR operator [C#]
- disjunction operator [C#]
- '| operator [C#]'
- conditional AND operator [C#]
- short-circuiting AND operator [C#]
- '&& operator [C#]'
- conditional OR operator [C#]
- short-circuiting OR operator [C#]
- '|| operator [C#]'
ms.openlocfilehash: 00b1523029ed6562fda6947415029cd3b7a9b405
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916892"
---
# <a name="boolean-logical-operators-c-reference"></a><span data-ttu-id="59875-103">Логические операторы (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="59875-103">Boolean logical operators (C# reference)</span></span>

<span data-ttu-id="59875-104">Следующие операторы выполняют логические операции с использованием [логических](../builtin-types/bool.md) операндов:</span><span class="sxs-lookup"><span data-stu-id="59875-104">The following operators perform logical operations with [bool](../builtin-types/bool.md) operands:</span></span>

- <span data-ttu-id="59875-105">Унарный [`!` (логическое отрицание)](#logical-negation-operator-) оператор.</span><span class="sxs-lookup"><span data-stu-id="59875-105">Unary [`!` (logical negation)](#logical-negation-operator-) operator.</span></span>
- <span data-ttu-id="59875-106">Бинарные [`&` (логическое И)](#logical-and-operator-), [`|` (логическое ИЛИ)](#logical-or-operator-), а также [`^` (логическое исключающее ИЛИ)](#logical-exclusive-or-operator-) операторы.</span><span class="sxs-lookup"><span data-stu-id="59875-106">Binary [`&` (logical AND)](#logical-and-operator-), [`|` (logical OR)](#logical-or-operator-), and [`^` (logical exclusive OR)](#logical-exclusive-or-operator-) operators.</span></span> <span data-ttu-id="59875-107">Эти операторы всегда обрабатывают оба операнда.</span><span class="sxs-lookup"><span data-stu-id="59875-107">Those operators always evaluate both operands.</span></span>
- <span data-ttu-id="59875-108">Бинарные [`&&` (условное логическое И)](#conditional-logical-and-operator-) и [`||` (условное логическое ИЛИ)](#conditional-logical-or-operator-) операторы.</span><span class="sxs-lookup"><span data-stu-id="59875-108">Binary [`&&` (conditional logical AND)](#conditional-logical-and-operator-) and [`||` (conditional logical OR)](#conditional-logical-or-operator-) operators.</span></span> <span data-ttu-id="59875-109">Эти операторы вычисляют правый операнд, только если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="59875-109">Those operators evaluate the right-hand operand only if it's necessary.</span></span>

<span data-ttu-id="59875-110">Для операндов [целочисленных](../builtin-types/integral-numeric-types.md) типов операторы `&`, `|` и `^` выполняют побитовые логические операции.</span><span class="sxs-lookup"><span data-stu-id="59875-110">For operands of the [integral numeric types](../builtin-types/integral-numeric-types.md), the `&`, `|`, and `^` operators perform bitwise logical operations.</span></span> <span data-ttu-id="59875-111">Дополнительные сведения см. в разделе [Побитовые операторы и операторы сдвига](bitwise-and-shift-operators.md).</span><span class="sxs-lookup"><span data-stu-id="59875-111">For more information, see [Bitwise and shift operators](bitwise-and-shift-operators.md).</span></span>

## <a name="logical-negation-operator-"></a><span data-ttu-id="59875-112">Оператор логического отрицания !</span><span class="sxs-lookup"><span data-stu-id="59875-112">Logical negation operator !</span></span>

<span data-ttu-id="59875-113">Унарный префиксный оператор `!` выполняет логическое отрицание операнда,</span><span class="sxs-lookup"><span data-stu-id="59875-113">The unary prefix `!` operator computes logical negation of its operand.</span></span> <span data-ttu-id="59875-114">возвращая `true`, если операнд имеет значение `false`, и `false`, если операнд имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="59875-114">That is, it produces `true`, if the operand evaluates to `false`, and `false`, if the operand evaluates to `true`:</span></span>

[!code-csharp-interactive[logical negation](snippets/shared/BooleanLogicalOperators.cs#Negation)]

<span data-ttu-id="59875-115">Начиная с версии C# 8.0, унарный постфиксный оператор `!`[допускает значение NULL](null-forgiving.md).</span><span class="sxs-lookup"><span data-stu-id="59875-115">Beginning with C# 8.0, the unary postfix `!` operator is the [null-forgiving operator](null-forgiving.md).</span></span>

## <a name="logical-and-operator-amp"></a><a name="logical-and-operator-"></a> <span data-ttu-id="59875-116">Оператор логического И &amp;</span><span class="sxs-lookup"><span data-stu-id="59875-116">Logical AND operator &amp;</span></span>

<span data-ttu-id="59875-117">Оператор `&` вычисляет логическое И для всех своих операндов.</span><span class="sxs-lookup"><span data-stu-id="59875-117">The `&` operator computes the logical AND of its operands.</span></span> <span data-ttu-id="59875-118">Результат операции `x & y` принимает значение `true`, если оба оператора `x` и `y` имеют значение `true`.</span><span class="sxs-lookup"><span data-stu-id="59875-118">The result of `x & y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="59875-119">В противном случае результат будет `false`.</span><span class="sxs-lookup"><span data-stu-id="59875-119">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="59875-120">Оператор `&` вычисляет оба операнда, даже если левый операнд имеет значение `false`. При этом операция должна вернуть значение `false`, независимо от значения правого операнда.</span><span class="sxs-lookup"><span data-stu-id="59875-120">The `&` operator evaluates both operands even if the left-hand operand evaluates to `false`, so that the operation result is `false` regardless of the value of the right-hand operand.</span></span>

<span data-ttu-id="59875-121">В следующем примере правый операнд оператора `&` является вызовом метода, который выполняется независимо от значения левого операнда:</span><span class="sxs-lookup"><span data-stu-id="59875-121">In the following example, the right-hand operand of the `&` operator is a method call, which is performed regardless of the value of the left-hand operand:</span></span>

[!code-csharp-interactive[logical AND](snippets/shared/BooleanLogicalOperators.cs#And)]

<span data-ttu-id="59875-122">[Условный оператор логического И](#conditional-logical-and-operator-) `&&` также вычисляет логическое И для своих операндов, но не вычисляет правый операнд, если левый операнд имеет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="59875-122">The [conditional logical AND operator](#conditional-logical-and-operator-) `&&` also computes the logical AND of its operands, but doesn't evaluate the right-hand operand if the left-hand operand evaluates to `false`.</span></span>

<span data-ttu-id="59875-123">Для операндов [целочисленных типов](../builtin-types/integral-numeric-types.md) оператор `&` вычисляет [побитовое логическое И](bitwise-and-shift-operators.md#logical-and-operator-) своих операндов.</span><span class="sxs-lookup"><span data-stu-id="59875-123">For operands of the [integral numeric types](../builtin-types/integral-numeric-types.md), the `&` operator computes the [bitwise logical AND](bitwise-and-shift-operators.md#logical-and-operator-) of its operands.</span></span> <span data-ttu-id="59875-124">Унарный оператор `&` является оператором [AddressOf](pointer-related-operators.md#address-of-operator-).</span><span class="sxs-lookup"><span data-stu-id="59875-124">The unary `&` operator is the [address-of operator](pointer-related-operators.md#address-of-operator-).</span></span>

## <a name="logical-exclusive-or-operator-"></a><span data-ttu-id="59875-125">Оператор логического исключения ИЛИ ^</span><span class="sxs-lookup"><span data-stu-id="59875-125">Logical exclusive OR operator ^</span></span>

<span data-ttu-id="59875-126">Оператор `^` вычисляет логическое исключение ИЛИ для всех своих операндов,</span><span class="sxs-lookup"><span data-stu-id="59875-126">The `^` operator computes the logical exclusive OR, also known as the logical XOR, of its operands.</span></span> <span data-ttu-id="59875-127">возвращая `true` для `x ^ y`, если `x` имеет значение `true` и `y` имеет значение `false` или `x` имеет значение `false` и `y` имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="59875-127">The result of `x ^ y` is `true` if `x` evaluates to `true` and `y` evaluates to `false`, or `x` evaluates to `false` and `y` evaluates to `true`.</span></span> <span data-ttu-id="59875-128">В противном случае результат будет `false`.</span><span class="sxs-lookup"><span data-stu-id="59875-128">Otherwise, the result is `false`.</span></span> <span data-ttu-id="59875-129">То есть для операндов `bool` оператор `^` возвращает тот же результат, что и [оператор неравенства](equality-operators.md#inequality-operator-) `!=`.</span><span class="sxs-lookup"><span data-stu-id="59875-129">That is, for the `bool` operands, the `^` operator computes the same result as the [inequality operator](equality-operators.md#inequality-operator-) `!=`.</span></span>

[!code-csharp-interactive[logical exclusive OR](snippets/shared/BooleanLogicalOperators.cs#Xor)]

<span data-ttu-id="59875-130">Для операндов [целочисленных типов](../builtin-types/integral-numeric-types.md) оператор `^` вычисляет [побитовое исключающее ИЛИ](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) своих операндов.</span><span class="sxs-lookup"><span data-stu-id="59875-130">For operands of the [integral numeric types](../builtin-types/integral-numeric-types.md), the `^` operator computes the [bitwise logical exclusive OR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) of its operands.</span></span>

## <a name="logical-or-operator-"></a><span data-ttu-id="59875-131">Оператор логического ИЛИ |</span><span class="sxs-lookup"><span data-stu-id="59875-131">Logical OR operator |</span></span>

<span data-ttu-id="59875-132">Оператор `|` вычисляет логическое ИЛИ для всех своих операндов.</span><span class="sxs-lookup"><span data-stu-id="59875-132">The `|` operator computes the logical OR of its operands.</span></span> <span data-ttu-id="59875-133">Результат операции `x | y` принимает значение `true`, если хотя бы один из операторов `x` или `y` имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="59875-133">The result of `x | y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="59875-134">В противном случае результат будет `false`.</span><span class="sxs-lookup"><span data-stu-id="59875-134">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="59875-135">Оператор `|` вычисляет оба операнда, даже если левый операнд имеет значение `true`. При этом операция должна вернуть значение `true`, независимо от значения правого операнда.</span><span class="sxs-lookup"><span data-stu-id="59875-135">The `|` operator evaluates both operands even if the left-hand operand evaluates to `true`, so that the operation result is `true` regardless of the value of the right-hand operand.</span></span>

<span data-ttu-id="59875-136">В следующем примере правый операнд оператора `|` является вызовом метода, который выполняется независимо от значения левого операнда:</span><span class="sxs-lookup"><span data-stu-id="59875-136">In the following example, the right-hand operand of the `|` operator is a method call, which is performed regardless of the value of the left-hand operand:</span></span>

[!code-csharp-interactive[logical OR](snippets/shared/BooleanLogicalOperators.cs#Or)]

<span data-ttu-id="59875-137">[Условный оператор логического ИЛИ](#conditional-logical-or-operator-) `||` также вычисляет логическое ИЛИ для своих операндов, но не вычисляет правый операнд, если левый операнд имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="59875-137">The [conditional logical OR operator](#conditional-logical-or-operator-) `||` also computes the logical OR of its operands, but doesn't evaluate the right-hand operand if the left-hand operand evaluates to `true`.</span></span>

<span data-ttu-id="59875-138">Для операндов [целочисленных типов](../builtin-types/integral-numeric-types.md) оператор `|` вычисляет [побитовое логическое ИЛИ](bitwise-and-shift-operators.md#logical-or-operator-) своих операндов.</span><span class="sxs-lookup"><span data-stu-id="59875-138">For operands of the [integral numeric types](../builtin-types/integral-numeric-types.md), the `|` operator computes the [bitwise logical OR](bitwise-and-shift-operators.md#logical-or-operator-) of its operands.</span></span>

## <a name="conditional-logical-and-operator-ampamp"></a><a name="conditional-logical-and-operator-"></a> <span data-ttu-id="59875-139">Условный оператор логического И &amp;&amp;</span><span class="sxs-lookup"><span data-stu-id="59875-139">Conditional logical AND operator &amp;&amp;</span></span>

<span data-ttu-id="59875-140">Условный оператор логического И `&&` (оператор короткого замыкания) вычисляет логическое И для своих операндов.</span><span class="sxs-lookup"><span data-stu-id="59875-140">The conditional logical AND operator `&&`, also known as the "short-circuiting" logical AND operator, computes the logical AND of its operands.</span></span> <span data-ttu-id="59875-141">Результат операции `x && y` принимает значение `true`, если оба оператора `x` и `y` имеют значение `true`.</span><span class="sxs-lookup"><span data-stu-id="59875-141">The result of `x && y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="59875-142">В противном случае результат будет `false`.</span><span class="sxs-lookup"><span data-stu-id="59875-142">Otherwise, the result is `false`.</span></span> <span data-ttu-id="59875-143">Если `x` имеет значение `false`, `y` не вычисляется.</span><span class="sxs-lookup"><span data-stu-id="59875-143">If `x` evaluates to `false`, `y` is not evaluated.</span></span>

<span data-ttu-id="59875-144">В следующем примере правый операнд оператора `&&` является вызовом метода, который не выполняется, если левый операнд имеет значение `false`:</span><span class="sxs-lookup"><span data-stu-id="59875-144">In the following example, the right-hand operand of the `&&` operator is a method call, which isn't performed if the left-hand operand evaluates to `false`:</span></span>

[!code-csharp-interactive[conditional logical AND](snippets/shared/BooleanLogicalOperators.cs#ConditionalAnd)]

<span data-ttu-id="59875-145">[Оператор логического И](#logical-and-operator-) `&` также вычисляет логическое И для своих операндов, но он всегда вычисляет оба операнда.</span><span class="sxs-lookup"><span data-stu-id="59875-145">The [logical AND operator](#logical-and-operator-) `&` also computes the logical AND of its operands, but always evaluates both operands.</span></span>

## <a name="conditional-logical-or-operator-"></a><span data-ttu-id="59875-146">Условный оператор логического ИЛИ ||</span><span class="sxs-lookup"><span data-stu-id="59875-146">Conditional logical OR operator ||</span></span>

<span data-ttu-id="59875-147">Условный оператор логического ИЛИ `||` (оператор короткого замыкания) вычисляет логическое ИЛИ для своих операндов.</span><span class="sxs-lookup"><span data-stu-id="59875-147">The conditional logical OR operator `||`, also known as the "short-circuiting" logical OR operator, computes the logical OR of its operands.</span></span> <span data-ttu-id="59875-148">Результат операции `x || y` принимает значение `true`, если хотя бы один из операторов `x` или `y` имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="59875-148">The result of `x || y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="59875-149">В противном случае результат будет `false`.</span><span class="sxs-lookup"><span data-stu-id="59875-149">Otherwise, the result is `false`.</span></span> <span data-ttu-id="59875-150">Если `x` имеет значение `true`, `y` не вычисляется.</span><span class="sxs-lookup"><span data-stu-id="59875-150">If `x` evaluates to `true`, `y` is not evaluated.</span></span>

<span data-ttu-id="59875-151">В следующем примере правый операнд оператора `||` является вызовом метода, который не выполняется, если левый операнд имеет значение `true`:</span><span class="sxs-lookup"><span data-stu-id="59875-151">In the following example, the right-hand operand of the `||` operator is a method call, which isn't performed if the left-hand operand evaluates to `true`:</span></span>

[!code-csharp-interactive[conditional logical OR](snippets/shared/BooleanLogicalOperators.cs#ConditionalOr)]

<span data-ttu-id="59875-152">[Оператор логического ИЛИ](#logical-or-operator-) `|` также вычисляет логическое ИЛИ для своих операндов, но всегда вычисляет оба операнда.</span><span class="sxs-lookup"><span data-stu-id="59875-152">The [logical OR operator](#logical-or-operator-) `|` also computes the logical OR of its operands, but always evaluates both operands.</span></span>

## <a name="nullable-boolean-logical-operators"></a><span data-ttu-id="59875-153">Операторы, допускающие логическое значение NULL</span><span class="sxs-lookup"><span data-stu-id="59875-153">Nullable Boolean logical operators</span></span>

<span data-ttu-id="59875-154">Для операндов `bool?` операторы [`&` (логическое И)](#logical-and-operator-) и [`|` (логическое ИЛИ)](#logical-or-operator-) поддерживают следующую логику с тремя значениями:</span><span class="sxs-lookup"><span data-stu-id="59875-154">For `bool?` operands, the [`&` (logical AND)](#logical-and-operator-) and [`|` (logical OR)](#logical-or-operator-) operators support the three-valued logic as follows:</span></span>

- <span data-ttu-id="59875-155">Оператор `&` возвращает `true` только в том случае, если оба операнда имеют значение `true`.</span><span class="sxs-lookup"><span data-stu-id="59875-155">The `&` operator produces `true` only if both its operands evaluate to `true`.</span></span> <span data-ttu-id="59875-156">Если `x` или `y` имеет значение `false`, оператор `x & y` возвращает `false` (даже если другой операнд имеет значение `null`).</span><span class="sxs-lookup"><span data-stu-id="59875-156">If either `x` or `y` evaluates to `false`, `x & y` produces `false` (even if another operand evaluates to `null`).</span></span> <span data-ttu-id="59875-157">В противном случае выражение `x & y` будет иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="59875-157">Otherwise, the result of `x & y` is `null`.</span></span>

- <span data-ttu-id="59875-158">Оператор `|` возвращает `false` только в том случае, если оба операнда имеют значение `false`.</span><span class="sxs-lookup"><span data-stu-id="59875-158">The `|` operator produces `false` only if both its operands evaluate to `false`.</span></span> <span data-ttu-id="59875-159">Если `x` или `y` имеет значение `true`, оператор `x | y` возвращает `true` (даже если другой операнд имеет значение `null`).</span><span class="sxs-lookup"><span data-stu-id="59875-159">If either `x` or `y` evaluates to `true`, `x | y` produces `true` (even if another operand evaluates to `null`).</span></span> <span data-ttu-id="59875-160">В противном случае выражение `x | y` будет иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="59875-160">Otherwise, the result of `x | y` is `null`.</span></span>

<span data-ttu-id="59875-161">Эта семантика описывается в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="59875-161">The following table presents that semantics:</span></span>

|<span data-ttu-id="59875-162">x</span><span class="sxs-lookup"><span data-stu-id="59875-162">x</span></span>|<span data-ttu-id="59875-163">y</span><span class="sxs-lookup"><span data-stu-id="59875-163">y</span></span>|<span data-ttu-id="59875-164">x&y</span><span class="sxs-lookup"><span data-stu-id="59875-164">x&y</span></span>|<span data-ttu-id="59875-165">x&#124;y</span><span class="sxs-lookup"><span data-stu-id="59875-165">x&#124;y</span></span>|  
|----|----|----|----|  
|<span data-ttu-id="59875-166">true</span><span class="sxs-lookup"><span data-stu-id="59875-166">true</span></span>|<span data-ttu-id="59875-167">true</span><span class="sxs-lookup"><span data-stu-id="59875-167">true</span></span>|<span data-ttu-id="59875-168">true</span><span class="sxs-lookup"><span data-stu-id="59875-168">true</span></span>|<span data-ttu-id="59875-169">true</span><span class="sxs-lookup"><span data-stu-id="59875-169">true</span></span>|  
|<span data-ttu-id="59875-170">true</span><span class="sxs-lookup"><span data-stu-id="59875-170">true</span></span>|<span data-ttu-id="59875-171">false</span><span class="sxs-lookup"><span data-stu-id="59875-171">false</span></span>|<span data-ttu-id="59875-172">false</span><span class="sxs-lookup"><span data-stu-id="59875-172">false</span></span>|<span data-ttu-id="59875-173">true</span><span class="sxs-lookup"><span data-stu-id="59875-173">true</span></span>|  
|<span data-ttu-id="59875-174">true</span><span class="sxs-lookup"><span data-stu-id="59875-174">true</span></span>|<span data-ttu-id="59875-175">null</span><span class="sxs-lookup"><span data-stu-id="59875-175">null</span></span>|<span data-ttu-id="59875-176">null</span><span class="sxs-lookup"><span data-stu-id="59875-176">null</span></span>|<span data-ttu-id="59875-177">true</span><span class="sxs-lookup"><span data-stu-id="59875-177">true</span></span>|  
|<span data-ttu-id="59875-178">false</span><span class="sxs-lookup"><span data-stu-id="59875-178">false</span></span>|<span data-ttu-id="59875-179">true</span><span class="sxs-lookup"><span data-stu-id="59875-179">true</span></span>|<span data-ttu-id="59875-180">false</span><span class="sxs-lookup"><span data-stu-id="59875-180">false</span></span>|<span data-ttu-id="59875-181">true</span><span class="sxs-lookup"><span data-stu-id="59875-181">true</span></span>|  
|<span data-ttu-id="59875-182">false</span><span class="sxs-lookup"><span data-stu-id="59875-182">false</span></span>|<span data-ttu-id="59875-183">false</span><span class="sxs-lookup"><span data-stu-id="59875-183">false</span></span>|<span data-ttu-id="59875-184">false</span><span class="sxs-lookup"><span data-stu-id="59875-184">false</span></span>|<span data-ttu-id="59875-185">false</span><span class="sxs-lookup"><span data-stu-id="59875-185">false</span></span>|  
|<span data-ttu-id="59875-186">false</span><span class="sxs-lookup"><span data-stu-id="59875-186">false</span></span>|<span data-ttu-id="59875-187">null</span><span class="sxs-lookup"><span data-stu-id="59875-187">null</span></span>|<span data-ttu-id="59875-188">false</span><span class="sxs-lookup"><span data-stu-id="59875-188">false</span></span>|<span data-ttu-id="59875-189">null</span><span class="sxs-lookup"><span data-stu-id="59875-189">null</span></span>|  
|<span data-ttu-id="59875-190">null</span><span class="sxs-lookup"><span data-stu-id="59875-190">null</span></span>|<span data-ttu-id="59875-191">true</span><span class="sxs-lookup"><span data-stu-id="59875-191">true</span></span>|<span data-ttu-id="59875-192">null</span><span class="sxs-lookup"><span data-stu-id="59875-192">null</span></span>|<span data-ttu-id="59875-193">true</span><span class="sxs-lookup"><span data-stu-id="59875-193">true</span></span>|  
|<span data-ttu-id="59875-194">null</span><span class="sxs-lookup"><span data-stu-id="59875-194">null</span></span>|<span data-ttu-id="59875-195">false</span><span class="sxs-lookup"><span data-stu-id="59875-195">false</span></span>|<span data-ttu-id="59875-196">false</span><span class="sxs-lookup"><span data-stu-id="59875-196">false</span></span>|<span data-ttu-id="59875-197">null</span><span class="sxs-lookup"><span data-stu-id="59875-197">null</span></span>|  
|<span data-ttu-id="59875-198">null</span><span class="sxs-lookup"><span data-stu-id="59875-198">null</span></span>|<span data-ttu-id="59875-199">null</span><span class="sxs-lookup"><span data-stu-id="59875-199">null</span></span>|<span data-ttu-id="59875-200">null</span><span class="sxs-lookup"><span data-stu-id="59875-200">null</span></span>|<span data-ttu-id="59875-201">null</span><span class="sxs-lookup"><span data-stu-id="59875-201">null</span></span>|  

<span data-ttu-id="59875-202">Поведение этих операторов отличается от типичного поведения операторов, допускающих значение NULL.</span><span class="sxs-lookup"><span data-stu-id="59875-202">The behavior of those operators differs from the typical operator behavior with nullable value types.</span></span> <span data-ttu-id="59875-203">Как правило, оператор, который определяется для операндов типа значения, можно также использовать с соответствующими операндами типа, допускающего значение NULL.</span><span class="sxs-lookup"><span data-stu-id="59875-203">Typically, an operator which is defined for operands of a value type can be also used with operands of the corresponding nullable value type.</span></span> <span data-ttu-id="59875-204">Такой оператор возвращает `null`, если какой-либо из операндов имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="59875-204">Such an operator produces `null` if any of its operands evaluates to `null`.</span></span> <span data-ttu-id="59875-205">При этом операторы `&` и `|` могут возвращать отличное от NULL значение, даже если один из операндов имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="59875-205">However, the `&` and `|` operators can produce non-null even if one of the operands evaluates to `null`.</span></span> <span data-ttu-id="59875-206">См. подробнее о поведении операторов, допускающих значение NULL, в разделе [Операторы с нулификацией](../builtin-types/nullable-value-types.md#lifted-operators) в статье [Типы, допускающие значение NULL](../builtin-types/nullable-value-types.md).</span><span class="sxs-lookup"><span data-stu-id="59875-206">For more information about the operator behavior with nullable value types, see the [Lifted operators](../builtin-types/nullable-value-types.md#lifted-operators) section of the [Nullable value types](../builtin-types/nullable-value-types.md) article.</span></span>

<span data-ttu-id="59875-207">Вы также можете также использовать операторы `!` и `^` с операндами `bool?`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="59875-207">You can also use the `!` and `^` operators with `bool?` operands, as the following example shows:</span></span>

[!code-csharp-interactive[lifted negation and xor](snippets/shared/BooleanLogicalOperators.cs#WithNullableBoolean)]

<span data-ttu-id="59875-208">Условные логические операторы `&&` и `||` не поддерживают операнды типа `bool?`.</span><span class="sxs-lookup"><span data-stu-id="59875-208">The conditional logical operators `&&` and `||` don't support `bool?` operands.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="59875-209">Составное присваивание</span><span class="sxs-lookup"><span data-stu-id="59875-209">Compound assignment</span></span>

<span data-ttu-id="59875-210">Для бинарного оператора `op` выражение составного присваивания в форме</span><span class="sxs-lookup"><span data-stu-id="59875-210">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="59875-211">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="59875-211">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="59875-212">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="59875-212">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="59875-213">Операторы `&`, `|` и `^` поддерживают составное присваивание, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="59875-213">The `&`, `|`, and `^` operators support compound assignment, as the following example shows:</span></span>

[!code-csharp-interactive[compound assignment](snippets/shared/BooleanLogicalOperators.cs#CompoundAssignment)]

> [!NOTE]
> <span data-ttu-id="59875-214">Условные логические операторы `&&` и `||` не поддерживают составное присваивание.</span><span class="sxs-lookup"><span data-stu-id="59875-214">The conditional logical operators `&&` and `||` don't support compound assignment.</span></span>

## <a name="operator-precedence"></a><span data-ttu-id="59875-215">Приоритет операторов</span><span class="sxs-lookup"><span data-stu-id="59875-215">Operator precedence</span></span>

<span data-ttu-id="59875-216">В следующем списке перечислены логические операторы в порядке убывания приоритета:</span><span class="sxs-lookup"><span data-stu-id="59875-216">The following list orders logical operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="59875-217">Оператор логического отрицания `!`</span><span class="sxs-lookup"><span data-stu-id="59875-217">Logical negation operator `!`</span></span>
- <span data-ttu-id="59875-218">Оператор логического И `&`</span><span class="sxs-lookup"><span data-stu-id="59875-218">Logical AND operator `&`</span></span>
- <span data-ttu-id="59875-219">Оператор логического исключающего ИЛИ `^`</span><span class="sxs-lookup"><span data-stu-id="59875-219">Logical exclusive OR operator `^`</span></span>
- <span data-ttu-id="59875-220">Оператор логического ИЛИ `|`</span><span class="sxs-lookup"><span data-stu-id="59875-220">Logical OR operator `|`</span></span>
- <span data-ttu-id="59875-221">Условный оператор логического И `&&`</span><span class="sxs-lookup"><span data-stu-id="59875-221">Conditional logical AND operator `&&`</span></span>
- <span data-ttu-id="59875-222">Условный оператор логического ИЛИ `||`</span><span class="sxs-lookup"><span data-stu-id="59875-222">Conditional logical OR operator `||`</span></span>

<span data-ttu-id="59875-223">Порядок вычисления, определяемый приоритетом операторов, можно изменить с помощью скобок (`()`).</span><span class="sxs-lookup"><span data-stu-id="59875-223">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence:</span></span>

[!code-csharp-interactive[operator precedence](snippets/shared/BooleanLogicalOperators.cs#Precedence)]

<span data-ttu-id="59875-224">Полный список операторов C#, упорядоченный по уровню приоритета, можно найти в разделе [Приоритет операторов](index.md#operator-precedence) статьи [Операторы C#](index.md).</span><span class="sxs-lookup"><span data-stu-id="59875-224">For the complete list of C# operators ordered by precedence level, see the [Operator precedence](index.md#operator-precedence) section of the [C# operators](index.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="59875-225">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="59875-225">Operator overloadability</span></span>

<span data-ttu-id="59875-226">Определяемый пользователем тип может [перегружать](operator-overloading.md) операторы `!`, `&`, `|` и `^`.</span><span class="sxs-lookup"><span data-stu-id="59875-226">A user-defined type can [overload](operator-overloading.md) the `!`, `&`, `|`, and `^` operators.</span></span> <span data-ttu-id="59875-227">При перегрузке бинарного оператора соответствующий оператор составного присваивания также неявно перегружается.</span><span class="sxs-lookup"><span data-stu-id="59875-227">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="59875-228">Определяемый пользователем тип не может перегружать оператор составного присваивания явным образом.</span><span class="sxs-lookup"><span data-stu-id="59875-228">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

<span data-ttu-id="59875-229">Определяемый пользователем тип не может перегружать условные логические операторы `&&` и `||`.</span><span class="sxs-lookup"><span data-stu-id="59875-229">A user-defined type cannot overload the conditional logical operators `&&` and `||`.</span></span> <span data-ttu-id="59875-230">При этом, если определяемый пользователем тип каким-либо образом перегружает операторы [true и false](true-false-operators.md) и операторы `&` и `|`, операция `&&` или `||` может быть применена для операндов этого типа.</span><span class="sxs-lookup"><span data-stu-id="59875-230">However, if a user-defined type overloads the [true and false operators](true-false-operators.md) and the `&` or `|` operator in a certain way, the `&&` or `||` operation, respectively, can be evaluated for the operands of that type.</span></span> <span data-ttu-id="59875-231">Дополнительные сведения см. в разделе [Пользовательские условные логические операторы](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) в [Спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="59875-231">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="59875-232">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="59875-232">C# language specification</span></span>

<span data-ttu-id="59875-233">Дополнительные сведения см. в следующих разделах статьи [Спецификация языка C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="59875-233">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="59875-234">Оператор логического отрицания</span><span class="sxs-lookup"><span data-stu-id="59875-234">Logical negation operator</span></span>](~/_csharplang/spec/expressions.md#logical-negation-operator)
- [<span data-ttu-id="59875-235">Логические операторы</span><span class="sxs-lookup"><span data-stu-id="59875-235">Logical operators</span></span>](~/_csharplang/spec/expressions.md#logical-operators)
- [<span data-ttu-id="59875-236">Условные логические операторы</span><span class="sxs-lookup"><span data-stu-id="59875-236">Conditional logical operators</span></span>](~/_csharplang/spec/expressions.md#conditional-logical-operators)
- [<span data-ttu-id="59875-237">Составное присваивание</span><span class="sxs-lookup"><span data-stu-id="59875-237">Compound assignment</span></span>](~/_csharplang/spec/expressions.md#compound-assignment)

## <a name="see-also"></a><span data-ttu-id="59875-238">См. также</span><span class="sxs-lookup"><span data-stu-id="59875-238">See also</span></span>

- [<span data-ttu-id="59875-239">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="59875-239">C# reference</span></span>](../index.md)
- [<span data-ttu-id="59875-240">Операторы и выражения C#</span><span class="sxs-lookup"><span data-stu-id="59875-240">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="59875-241">Побитовые операторы и операторы сдвига</span><span class="sxs-lookup"><span data-stu-id="59875-241">Bitwise and shift operators</span></span>](bitwise-and-shift-operators.md)
