---
title: Размеченные объединения
description: 'Узнайте, как использовать размеченные объединения F #.'
ms.date: 08/15/2020
ms.openlocfilehash: 3f8ac656bd00b1022b2b13ee1be7ca5c98f68db5
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812137"
---
# <a name="discriminated-unions"></a><span data-ttu-id="abcd9-103">Размеченные объединения</span><span class="sxs-lookup"><span data-stu-id="abcd9-103">Discriminated Unions</span></span>

<span data-ttu-id="abcd9-104">Размеченные объединения обеспечивают поддержку значений, которые могут быть одного из нескольких именованных вариантов, возможно, с разными значениями и типами.</span><span class="sxs-lookup"><span data-stu-id="abcd9-104">Discriminated unions provide support for values that can be one of a number of named cases, possibly each with different values and types.</span></span> <span data-ttu-id="abcd9-105">Размеченные объединения полезны для разнородных данных. данные, которые могут иметь особые случаи, включая допустимые и ошибочные варианты; данные, которые могут различаться в типе от одного экземпляра к другому; а также в качестве альтернативы для небольших иерархий объектов.</span><span class="sxs-lookup"><span data-stu-id="abcd9-105">Discriminated unions are useful for heterogeneous data; data that can have special cases, including valid and error cases; data that varies in type from one instance to another; and as an alternative for small object hierarchies.</span></span> <span data-ttu-id="abcd9-106">Кроме того, рекурсивные размеченные объединения используются для представления древовидных структур данных.</span><span class="sxs-lookup"><span data-stu-id="abcd9-106">In addition, recursive discriminated unions are used to represent tree data structures.</span></span>

## <a name="syntax"></a><span data-ttu-id="abcd9-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="abcd9-107">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    | case-identifier1 [of [ fieldname1 : ] type1 [ * [ fieldname2 : ] type2 ...]
    | case-identifier2 [of [fieldname3 : ]type3 [ * [ fieldname4 : ]type4 ...]

    [ member-list ]
```

## <a name="remarks"></a><span data-ttu-id="abcd9-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="abcd9-108">Remarks</span></span>

<span data-ttu-id="abcd9-109">Размеченные объединения похожи на типы объединения на других языках, но существуют различия.</span><span class="sxs-lookup"><span data-stu-id="abcd9-109">Discriminated unions are similar to union types in other languages, but there are differences.</span></span> <span data-ttu-id="abcd9-110">Как и тип объединения в C++ или тип Variant в Visual Basic, данные, хранящиеся в значении, не являются фиксированными; Это может быть один из нескольких различных параметров.</span><span class="sxs-lookup"><span data-stu-id="abcd9-110">As with a union type in C++ or a variant type in Visual Basic, the data stored in the value is not fixed; it can be one of several distinct options.</span></span> <span data-ttu-id="abcd9-111">Однако в отличие от объединений в этих других языках, каждому из возможных параметров присваивается *идентификатор варианта*.</span><span class="sxs-lookup"><span data-stu-id="abcd9-111">Unlike unions in these other languages, however, each of the possible options is given a *case identifier*.</span></span> <span data-ttu-id="abcd9-112">Идентификаторы вариантов — это имена различных возможных типов значений, которые могут быть объектами этого типа. значения являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="abcd9-112">The case identifiers are names for the various possible types of values that objects of this type could be; the values are optional.</span></span> <span data-ttu-id="abcd9-113">Если значения не указаны, регистр эквивалентен регистру перечисления.</span><span class="sxs-lookup"><span data-stu-id="abcd9-113">If values are not present, the case is equivalent to an enumeration case.</span></span> <span data-ttu-id="abcd9-114">При наличии значений каждое значение может быть одним значением указанного типа или кортежем, который объединяет несколько полей одного или разных типов.</span><span class="sxs-lookup"><span data-stu-id="abcd9-114">If values are present, each value can either be a single value of a specified type, or a tuple that aggregates multiple fields of the same or different types.</span></span> <span data-ttu-id="abcd9-115">Можно присвоить имя отдельному полю, но имя является необязательным, даже если другие поля в том же регистре называются.</span><span class="sxs-lookup"><span data-stu-id="abcd9-115">You can give an individual field a name, but the name is optional, even if other fields in the same case are named.</span></span>

<span data-ttu-id="abcd9-116">По умолчанию специальные возможности для размеченных объединений имеют значение `public` .</span><span class="sxs-lookup"><span data-stu-id="abcd9-116">Accessibility for discriminated unions defaults to `public`.</span></span>

<span data-ttu-id="abcd9-117">Например, рассмотрим следующее объявление типа фигуры.</span><span class="sxs-lookup"><span data-stu-id="abcd9-117">For example, consider the following declaration of a Shape type.</span></span>

```fsharp
type Shape =
    | Rectangle of width : float * length : float
    | Circle of radius : float
    | Prism of width : float * float * height : float
```

<span data-ttu-id="abcd9-118">Приведенный выше код объявляет фигуру размеченного объединения, которая может иметь значения любого из трех вариантов: прямоугольника, круга и Prism.</span><span class="sxs-lookup"><span data-stu-id="abcd9-118">The preceding code declares a discriminated union Shape, which can have values of any of three cases: Rectangle, Circle, and Prism.</span></span> <span data-ttu-id="abcd9-119">Каждый вариант имеет другой набор полей.</span><span class="sxs-lookup"><span data-stu-id="abcd9-119">Each case has a different set of fields.</span></span> <span data-ttu-id="abcd9-120">В прямоугольнике есть два именованных поля типа `float` , которые имеют имена Width и length.</span><span class="sxs-lookup"><span data-stu-id="abcd9-120">The Rectangle case has two named fields, both of type `float`, that have the names width and length.</span></span> <span data-ttu-id="abcd9-121">В круглом варианте есть только одно именованное поле, RADIUS.</span><span class="sxs-lookup"><span data-stu-id="abcd9-121">The Circle case has just one named field, radius.</span></span> <span data-ttu-id="abcd9-122">В Prism Case есть три поля, два из которых (ширина и высота) называются полями.</span><span class="sxs-lookup"><span data-stu-id="abcd9-122">The Prism case has three fields, two of which (width and height) are named fields.</span></span> <span data-ttu-id="abcd9-123">Безымянные поля называются анонимными полями.</span><span class="sxs-lookup"><span data-stu-id="abcd9-123">Unnamed fields are referred to as anonymous fields.</span></span>

<span data-ttu-id="abcd9-124">Объекты создаются путем предоставления значений для именованных и анонимных полей в соответствии со следующими примерами.</span><span class="sxs-lookup"><span data-stu-id="abcd9-124">You construct objects by providing values for the named and anonymous fields according to the following examples.</span></span>

```fsharp
let rect = Rectangle(length = 1.3, width = 10.0)
let circ = Circle (1.0)
let prism = Prism(5., 2.0, height = 3.0)
```

<span data-ttu-id="abcd9-125">Этот код показывает, что можно либо использовать именованные поля в инициализации, либо полагаться на порядок полей в объявлении и просто предоставить значения для каждого поля в свою очередь.</span><span class="sxs-lookup"><span data-stu-id="abcd9-125">This code shows that you can either use the named fields in the initialization, or you can rely on the ordering of the fields in the declaration and just provide the values for each field in turn.</span></span> <span data-ttu-id="abcd9-126">При вызове конструктора для `rect` в предыдущем коде используются именованные поля, но при вызове конструктора для `circ` используется упорядочение.</span><span class="sxs-lookup"><span data-stu-id="abcd9-126">The constructor call for `rect` in the previous code uses the named fields, but the constructor call for `circ` uses the ordering.</span></span> <span data-ttu-id="abcd9-127">Можно смешивать упорядоченные поля и именованные поля, как в конструкции `prism` .</span><span class="sxs-lookup"><span data-stu-id="abcd9-127">You can mix the ordered fields and named fields, as in the construction of `prism`.</span></span>

<span data-ttu-id="abcd9-128">`option`Тип является простым размеченное объединением в основной библиотеке F #.</span><span class="sxs-lookup"><span data-stu-id="abcd9-128">The `option` type is a simple discriminated union in the F# core library.</span></span> <span data-ttu-id="abcd9-129">`option`Тип объявляется следующим образом.</span><span class="sxs-lookup"><span data-stu-id="abcd9-129">The `option` type is declared as follows.</span></span>

```fsharp
// The option type is a discriminated union.
type Option<'a> =
    | Some of 'a
    | None
```

<span data-ttu-id="abcd9-130">Предыдущий код указывает, что тип `Option` — это размеченное объединение, которое имеет два варианта: `Some` и `None` .</span><span class="sxs-lookup"><span data-stu-id="abcd9-130">The previous code specifies that the type `Option` is a discriminated union that has two cases, `Some` and `None`.</span></span> <span data-ttu-id="abcd9-131">`Some`Вариант имеет связанное значение, состоящее из одного анонимного поля, тип которого представлен параметром типа `'a` .</span><span class="sxs-lookup"><span data-stu-id="abcd9-131">The `Some` case has an associated value that consists of one anonymous field whose type is represented by the type parameter `'a`.</span></span> <span data-ttu-id="abcd9-132">`None`Регистр не имеет связанного значения.</span><span class="sxs-lookup"><span data-stu-id="abcd9-132">The `None` case has no associated value.</span></span> <span data-ttu-id="abcd9-133">Таким же `option` типом определяется универсальный тип, который либо имеет значение некоторого типа, либо не имеет значения.</span><span class="sxs-lookup"><span data-stu-id="abcd9-133">Thus the `option` type specifies a generic type that either has a value of some type or no value.</span></span> <span data-ttu-id="abcd9-134">Тип `Option` также имеет псевдоним типа "нижний регистр", `option` который чаще всего используется.</span><span class="sxs-lookup"><span data-stu-id="abcd9-134">The type `Option` also has a lowercase type alias, `option`, that is more commonly used.</span></span>

<span data-ttu-id="abcd9-135">Идентификаторы вариантов можно использовать в качестве конструкторов для типа размеченного объединения.</span><span class="sxs-lookup"><span data-stu-id="abcd9-135">The case identifiers can be used as constructors for the discriminated union type.</span></span> <span data-ttu-id="abcd9-136">Например, следующий код используется для создания значений `option` типа.</span><span class="sxs-lookup"><span data-stu-id="abcd9-136">For example, the following code is used to create values of the `option` type.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2001.fs)]

<span data-ttu-id="abcd9-137">Идентификаторы вариантов также используются в выражениях сопоставления шаблонов.</span><span class="sxs-lookup"><span data-stu-id="abcd9-137">The case identifiers are also used in pattern matching expressions.</span></span> <span data-ttu-id="abcd9-138">В выражении сопоставления шаблонов идентификаторы предоставляются для значений, связанных с отдельными вариантами.</span><span class="sxs-lookup"><span data-stu-id="abcd9-138">In a pattern matching expression, identifiers are provided for the values associated with the individual cases.</span></span> <span data-ttu-id="abcd9-139">Например, в следующем коде `x` является идентификатором, заданным значением, связанным с `Some` вариантом `option` типа.</span><span class="sxs-lookup"><span data-stu-id="abcd9-139">For example, in the following code, `x` is the identifier given the value that is associated with the `Some` case of the `option` type.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2002.fs)]

<span data-ttu-id="abcd9-140">В выражениях сопоставления шаблонов можно использовать именованные поля для указания совпадений размеченного объединения.</span><span class="sxs-lookup"><span data-stu-id="abcd9-140">In pattern matching expressions, you can use named fields to specify discriminated union matches.</span></span> <span data-ttu-id="abcd9-141">Для типа фигуры, объявленного ранее, можно использовать именованные поля, как показано в следующем коде, чтобы извлечь значения полей.</span><span class="sxs-lookup"><span data-stu-id="abcd9-141">For the Shape type that was declared previously, you can use the named fields as the following code shows to extract the values of the fields.</span></span>

```fsharp
let getShapeWidth shape =
    match shape with
    | Rectangle(width = w) -> w
    | Circle(radius = r) -> 2. * r
    | Prism(width = w) -> w
```

<span data-ttu-id="abcd9-142">Как правило, идентификаторы вариантов можно использовать без уточнения их именем объединения.</span><span class="sxs-lookup"><span data-stu-id="abcd9-142">Normally, the case identifiers can be used without qualifying them with the name of the union.</span></span> <span data-ttu-id="abcd9-143">Если необходимо, чтобы имя всегда было дополнено именем объединения, можно применить атрибут [рекуирекуалифиедакцесс](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html) к определению типа объединения.</span><span class="sxs-lookup"><span data-stu-id="abcd9-143">If you want the name to always be qualified with the name of the union, you can apply the [RequireQualifiedAccess](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html) attribute to the union type definition.</span></span>

### <a name="unwrapping-discriminated-unions"></a><span data-ttu-id="abcd9-144">Разтекание размеченных объединений</span><span class="sxs-lookup"><span data-stu-id="abcd9-144">Unwrapping Discriminated Unions</span></span>

<span data-ttu-id="abcd9-145">В языке F # размеченные объединения часто используются в моделировании доменов для упаковки одного типа.</span><span class="sxs-lookup"><span data-stu-id="abcd9-145">In F# Discriminated Unions are often used in domain-modeling for wrapping a single type.</span></span> <span data-ttu-id="abcd9-146">Также можно легко извлечь базовое значение с помощью сопоставления шаблонов.</span><span class="sxs-lookup"><span data-stu-id="abcd9-146">It's easy to extract the underlying value via pattern matching as well.</span></span> <span data-ttu-id="abcd9-147">Не нужно использовать выражение соответствия для одного варианта:</span><span class="sxs-lookup"><span data-stu-id="abcd9-147">You don't need to use a match expression for a single case:</span></span>

```fsharp
let ([UnionCaseIdentifier] [values]) = [UnionValue]
```

<span data-ttu-id="abcd9-148">Следующий пример демонстрирует это:</span><span class="sxs-lookup"><span data-stu-id="abcd9-148">The following example demonstrates this:</span></span>

```fsharp
type ShaderProgram = | ShaderProgram of id:int

let someFunctionUsingShaderProgram shaderProgram =
    let (ShaderProgram id) = shaderProgram
    // Use the unwrapped value
    ...
```

<span data-ttu-id="abcd9-149">Сопоставление шаблонов также разрешено непосредственно в параметрах функции, поэтому можно разворачивать один случай:</span><span class="sxs-lookup"><span data-stu-id="abcd9-149">Pattern matching is also allowed directly in function parameters, so you can unwrap a single case there:</span></span>

```fsharp
let someFunctionUsingShaderProgram (ShaderProgram id) =
    // Use the unwrapped value
    ...
```

## <a name="struct-discriminated-unions"></a><span data-ttu-id="abcd9-150">Размеченные объединения структуры</span><span class="sxs-lookup"><span data-stu-id="abcd9-150">Struct Discriminated Unions</span></span>

<span data-ttu-id="abcd9-151">Можно также представить размеченные объединения как структуры.</span><span class="sxs-lookup"><span data-stu-id="abcd9-151">You can also represent Discriminated Unions as structs.</span></span>  <span data-ttu-id="abcd9-152">Это делается с помощью `[<Struct>]` атрибута.</span><span class="sxs-lookup"><span data-stu-id="abcd9-152">This is done with the `[<Struct>]` attribute.</span></span>

```fsharp
[<Struct>]
type SingleCase = Case of string

[<Struct>]
type Multicase =
    | Case1 of Case1 : string
    | Case2 of Case2 : int
    | Case3 of Case3 : double
```

<span data-ttu-id="abcd9-153">Так как это типы значений, а не ссылочные типы, существуют дополнительные рекомендации по сравнению со ссылочными объединениями.</span><span class="sxs-lookup"><span data-stu-id="abcd9-153">Because these are value types and not reference types, there are extra considerations compared with reference discriminated unions:</span></span>

1. <span data-ttu-id="abcd9-154">Они копируются как типы значений и имеют семантику типов значений.</span><span class="sxs-lookup"><span data-stu-id="abcd9-154">They are copied as value types and have value type semantics.</span></span>
2. <span data-ttu-id="abcd9-155">Нельзя использовать определение рекурсивного типа с многовариантным размеченное объединением.</span><span class="sxs-lookup"><span data-stu-id="abcd9-155">You cannot use a recursive type definition with a multicase struct Discriminated Union.</span></span>
3. <span data-ttu-id="abcd9-156">Необходимо указать уникальные имена вариантов для размеченного объединения с многовариантными структурами.</span><span class="sxs-lookup"><span data-stu-id="abcd9-156">You must provide unique case names for a multicase struct Discriminated Union.</span></span>

## <a name="using-discriminated-unions-instead-of-object-hierarchies"></a><span data-ttu-id="abcd9-157">Использование размеченных объединений вместо иерархий объектов</span><span class="sxs-lookup"><span data-stu-id="abcd9-157">Using Discriminated Unions Instead of Object Hierarchies</span></span>

<span data-ttu-id="abcd9-158">Вы часто можете использовать размеченное объединение в качестве более простой альтернативы небольшой иерархии объектов.</span><span class="sxs-lookup"><span data-stu-id="abcd9-158">You can often use a discriminated union as a simpler alternative to a small object hierarchy.</span></span> <span data-ttu-id="abcd9-159">Например, можно использовать следующее размеченное объединение вместо `Shape` базового класса, который имеет производные типы для окружности, квадрата и т. д.</span><span class="sxs-lookup"><span data-stu-id="abcd9-159">For example, the following discriminated union could be used instead of a `Shape` base class that has derived types for circle, square, and so on.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2003.fs)]

<span data-ttu-id="abcd9-160">Вместо виртуального метода для вычисления области или периметра, как при использовании в объектно-ориентированной реализации, можно использовать сопоставление шаблонов для ветвления в соответствующих формулах для вычисления этих количеств.</span><span class="sxs-lookup"><span data-stu-id="abcd9-160">Instead of a virtual method to compute an area or perimeter, as you would use in an object-oriented implementation, you can use pattern matching to branch to appropriate formulas to compute these quantities.</span></span> <span data-ttu-id="abcd9-161">В следующем примере для вычисления области используются различные формулы, в зависимости от фигуры.</span><span class="sxs-lookup"><span data-stu-id="abcd9-161">In the following example, different formulas are used to compute the area, depending on the shape.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2004.fs)]

<span data-ttu-id="abcd9-162">Вывод выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="abcd9-162">The output is as follows:</span></span>

```console
Area of circle that has radius 15.000000: 706.858347
Area of square that has side 10.000000: 100.000000
Area of rectangle that has height 5.000000 and width 10.000000 is 50.000000
```

## <a name="using-discriminated-unions-for-tree-data-structures"></a><span data-ttu-id="abcd9-163">Использование размеченных объединений для структур данных дерева</span><span class="sxs-lookup"><span data-stu-id="abcd9-163">Using Discriminated Unions for Tree Data Structures</span></span>

<span data-ttu-id="abcd9-164">Размеченные объединения могут быть рекурсивными, что означает, что объединение может включаться в тип одного или нескольких вариантов.</span><span class="sxs-lookup"><span data-stu-id="abcd9-164">Discriminated unions can be recursive, meaning that the union itself can be included in the type of one or more cases.</span></span> <span data-ttu-id="abcd9-165">Рекурсивные размеченные объединения можно использовать для создания древовидных структур, которые используются для моделирования выражений в языках программирования.</span><span class="sxs-lookup"><span data-stu-id="abcd9-165">Recursive discriminated unions can be used to create tree structures, which are used to model expressions in programming languages.</span></span> <span data-ttu-id="abcd9-166">В следующем коде рекурсивное размеченное объединение используется для создания структуры данных в двоичном дереве.</span><span class="sxs-lookup"><span data-stu-id="abcd9-166">In the following code, a recursive discriminated union is used to create a binary tree data structure.</span></span> <span data-ttu-id="abcd9-167">Объединение состоит из двух вариантов: `Node` , которые представляют собой узел с целочисленным значением, а также левые и правые поддеревья, и `Tip` , который завершает дерево.</span><span class="sxs-lookup"><span data-stu-id="abcd9-167">The union consists of two cases, `Node`, which is a node with an integer value and left and right subtrees, and `Tip`, which terminates the tree.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2005.fs)]

<span data-ttu-id="abcd9-168">В предыдущем коде `resultSumTree` имеет значение 10.</span><span class="sxs-lookup"><span data-stu-id="abcd9-168">In the previous code, `resultSumTree` has the value 10.</span></span> <span data-ttu-id="abcd9-169">На следующем рисунке показана древовидная структура для `myTree` .</span><span class="sxs-lookup"><span data-stu-id="abcd9-169">The following illustration shows the tree structure for `myTree`.</span></span>

![Схема, показывающая древовидную структуру для Митри.](../media/discriminated-unions/tree-structure-mytree.png)

<span data-ttu-id="abcd9-171">Размеченные объединения хорошо работают, если узлы в дереве являются разнородными.</span><span class="sxs-lookup"><span data-stu-id="abcd9-171">Discriminated unions work well if the nodes in the tree are heterogeneous.</span></span> <span data-ttu-id="abcd9-172">В следующем коде тип `Expression` представляет дерево абстрактного синтаксиса выражения в простом языке программирования, который поддерживает сложение и умножение чисел и переменных.</span><span class="sxs-lookup"><span data-stu-id="abcd9-172">In the following code, the type `Expression` represents the abstract syntax tree of an expression in a simple programming language that supports addition and multiplication of numbers and variables.</span></span> <span data-ttu-id="abcd9-173">Некоторые варианты объединения не являются рекурсивными и представляют либо числа ( `Number` ), либо переменные ( `Variable` ).</span><span class="sxs-lookup"><span data-stu-id="abcd9-173">Some of the union cases are not recursive and represent either numbers (`Number`) or variables (`Variable`).</span></span> <span data-ttu-id="abcd9-174">Другие варианты являются рекурсивными и представляют операции ( `Add` и `Multiply` ), где операнды также являются выражениями.</span><span class="sxs-lookup"><span data-stu-id="abcd9-174">Other cases are recursive, and represent operations (`Add` and `Multiply`), where the operands are also expressions.</span></span> <span data-ttu-id="abcd9-175">`Evaluate`Функция использует выражение match для рекурсивной обработки дерева синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="abcd9-175">The `Evaluate` function uses a match expression to recursively process the syntax tree.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2006.fs)]

<span data-ttu-id="abcd9-176">При выполнении этого кода значение `result` равно 5.</span><span class="sxs-lookup"><span data-stu-id="abcd9-176">When this code is executed, the value of `result` is 5.</span></span>

## <a name="members"></a><span data-ttu-id="abcd9-177">Элементы</span><span class="sxs-lookup"><span data-stu-id="abcd9-177">Members</span></span>

<span data-ttu-id="abcd9-178">Можно определить элементы в размеченных объединениях.</span><span class="sxs-lookup"><span data-stu-id="abcd9-178">It is possible to define members on discriminated unions.</span></span> <span data-ttu-id="abcd9-179">В следующем примере показано, как определить свойство и реализовать интерфейс:</span><span class="sxs-lookup"><span data-stu-id="abcd9-179">The following example shows how to define a property and implement an interface:</span></span>

```fsharp
open System

type IPrintable =
    abstract Print: unit -> unit

type Shape =
    | Circle of float
    | EquilateralTriangle of float
    | Square of float
    | Rectangle of float * float

    member this.Area =
        match this with
        | Circle r -> 2.0 * Math.PI * r
        | EquilateralTriangle s -> s * s * sqrt 3.0 / 4.0
        | Square s -> s * s
        | Rectangle(l, w) -> l * w

    interface IPrintable with
        member this.Print () =
            match this with
            | Circle r -> printfn "Circle with radius %f" r
            | EquilateralTriangle s -> printfn "Equilateral Triangle of side %f" s
            | Square s -> printfn "Square with side %f" s
            | Rectangle(l, w) -> printfn "Rectangle with length %f and width %f" l w
```

## <a name="common-attributes"></a><span data-ttu-id="abcd9-180">Общие атрибуты</span><span class="sxs-lookup"><span data-stu-id="abcd9-180">Common attributes</span></span>

<span data-ttu-id="abcd9-181">В размеченных объединениях обычно встречаются следующие атрибуты:</span><span class="sxs-lookup"><span data-stu-id="abcd9-181">The following attributes are commonly seen in discriminated unions:</span></span>

- `[<RequireQualifiedAccess>]`
- `[<NoEquality>]`
- `[<NoComparison>]`
- `[<Struct>]`

## <a name="see-also"></a><span data-ttu-id="abcd9-182">См. также</span><span class="sxs-lookup"><span data-stu-id="abcd9-182">See also</span></span>

- [<span data-ttu-id="abcd9-183">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="abcd9-183">F# Language Reference</span></span>](index.md)
