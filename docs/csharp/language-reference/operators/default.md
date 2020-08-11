---
title: Выражения default value. Справочник по C#
description: Используйте выражения default value, чтобы получить значение по умолчанию для типа.
ms.date: 03/13/2020
f1_keywords:
- default_CSharpKeyword
- default
helpviewer_keywords:
- default keyword [C#]
ms.openlocfilehash: f03971efa87bf03967c79512e44d22134dd80c17
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916865"
---
# <a name="default-value-expressions-c-reference"></a><span data-ttu-id="ebde4-103">Выражения default value (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="ebde4-103">default value expressions (C# reference)</span></span>

<span data-ttu-id="ebde4-104">Выражение default value создает [значение по умолчанию](../builtin-types/default-values.md) для типа.</span><span class="sxs-lookup"><span data-stu-id="ebde4-104">A default value expression produces the [default value](../builtin-types/default-values.md) of a type.</span></span> <span data-ttu-id="ebde4-105">Выражения default value бывают двух видов: вызов [оператора default](#default-operator) и [литерал default](#default-literal).</span><span class="sxs-lookup"><span data-stu-id="ebde4-105">There are two kinds of default value expressions: the [default operator](#default-operator) call and a [default literal](#default-literal).</span></span>

<span data-ttu-id="ebde4-106">Также используется ключевое слово `default` в качестве метки варианта по умолчанию в [инструкции `switch`](../keywords/switch.md).</span><span class="sxs-lookup"><span data-stu-id="ebde4-106">You also use the `default` keyword as the default case label within a [`switch` statement](../keywords/switch.md).</span></span>

## <a name="default-operator"></a><span data-ttu-id="ebde4-107">оператор default</span><span class="sxs-lookup"><span data-stu-id="ebde4-107">default operator</span></span>

<span data-ttu-id="ebde4-108">Оператор `default` принимает в качестве аргумента имя типа или параметр типа, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="ebde4-108">The argument to the `default` operator must be the name of a type or a type parameter, as the following example shows:</span></span>

[!code-csharp-interactive[default of T](snippets/shared/DefaultOperator.cs#WithOperand)]

## <a name="default-literal"></a><span data-ttu-id="ebde4-109">Литерал default</span><span class="sxs-lookup"><span data-stu-id="ebde4-109">default literal</span></span>

<span data-ttu-id="ebde4-110">Начиная с C# 7.1, можно использовать литерал `default` для создания значения по умолчанию для типа, если компилятор может вывести тип выражения.</span><span class="sxs-lookup"><span data-stu-id="ebde4-110">Beginning with C# 7.1, you can use the `default` literal to produce the default value of a type when the compiler can infer the expression type.</span></span> <span data-ttu-id="ebde4-111">Литеральное выражение `default` создает то же значение, что и выражение `default(T)`, где `T` является выведенным типом.</span><span class="sxs-lookup"><span data-stu-id="ebde4-111">The `default` literal expression produces the same value as the `default(T)` expression where `T` is the inferred type.</span></span> <span data-ttu-id="ebde4-112">Литерал `default` можно использовать в любом из следующих случаев:</span><span class="sxs-lookup"><span data-stu-id="ebde4-112">You can use the `default` literal in any of the following cases:</span></span>

- <span data-ttu-id="ebde4-113">при назначении или инициализации переменной;</span><span class="sxs-lookup"><span data-stu-id="ebde4-113">In the assignment or initialization of a variable.</span></span>
- <span data-ttu-id="ebde4-114">в объявлении значения по умолчанию для [необязательного параметра метода](../../methods.md#optional-parameters-and-arguments);</span><span class="sxs-lookup"><span data-stu-id="ebde4-114">In the declaration of the default value for an [optional method parameter](../../methods.md#optional-parameters-and-arguments).</span></span>
- <span data-ttu-id="ebde4-115">в вызове метода для предоставления значения аргумента;</span><span class="sxs-lookup"><span data-stu-id="ebde4-115">In a method call to provide an argument value.</span></span>
- <span data-ttu-id="ebde4-116">в [инструкции `return`](../keywords/return.md) или в качестве выражения в [элементе в тексте выражения](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="ebde4-116">In a [`return` statement](../keywords/return.md) or as an expression in an [expression-bodied member](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

<span data-ttu-id="ebde4-117">Ниже приведен пример применения литерала `default`.</span><span class="sxs-lookup"><span data-stu-id="ebde4-117">The following example shows the usage of the `default` literal:</span></span>

[!code-csharp-interactive[default literal](snippets/shared/DefaultOperator.cs#DefaultLiteral)]

## <a name="c-language-specification"></a><span data-ttu-id="ebde4-118">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="ebde4-118">C# language specification</span></span>

<span data-ttu-id="ebde4-119">Дополнительные сведения см. в разделе о [выражениях значения по умолчанию](~/_csharplang/spec/expressions.md#default-value-expressions) в [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="ebde4-119">For more information, see the [Default value expressions](~/_csharplang/spec/expressions.md#default-value-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="ebde4-120">Дополнительные сведения о литерале `default` см. в [примечании к предлагаемой функции](~/_csharplang/proposals/csharp-7.1/target-typed-default.md).</span><span class="sxs-lookup"><span data-stu-id="ebde4-120">For more information about the `default` literal, see the [feature proposal note](~/_csharplang/proposals/csharp-7.1/target-typed-default.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ebde4-121">См. также</span><span class="sxs-lookup"><span data-stu-id="ebde4-121">See also</span></span>

- [<span data-ttu-id="ebde4-122">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="ebde4-122">C# reference</span></span>](../index.md)
- [<span data-ttu-id="ebde4-123">Операторы и выражения C#</span><span class="sxs-lookup"><span data-stu-id="ebde4-123">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="ebde4-124">Значения по умолчанию типов C#</span><span class="sxs-lookup"><span data-stu-id="ebde4-124">Default values of C# types</span></span>](../builtin-types/default-values.md)
- [<span data-ttu-id="ebde4-125">Универсальные шаблоны в .NET</span><span class="sxs-lookup"><span data-stu-id="ebde4-125">Generics in .NET</span></span>](../../../standard/generics/index.md)
