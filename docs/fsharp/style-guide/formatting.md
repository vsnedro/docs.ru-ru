---
title: Рекомендации по форматированию кода F#
description: Изучите рекомендации по форматированию кода F.
ms.date: 11/04/2019
ms.openlocfilehash: 2086b515b8ec9b69a44e2e65ca06fb320670dff2
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81278942"
---
# <a name="f-code-formatting-guidelines"></a><span data-ttu-id="cb045-103">Рекомендации по форматированию кода F#</span><span class="sxs-lookup"><span data-stu-id="cb045-103">F# code formatting guidelines</span></span>

<span data-ttu-id="cb045-104">В этой статье предлагаются рекомендации по форматированию кода таким образом, чтобы ваш код F-кода был:</span><span class="sxs-lookup"><span data-stu-id="cb045-104">This article offers guidelines for how to format your code so that your F# code is:</span></span>

* <span data-ttu-id="cb045-105">Как правило, рассматривается как более разборчивый</span><span class="sxs-lookup"><span data-stu-id="cb045-105">Generally viewed as more legible</span></span>
* <span data-ttu-id="cb045-106">Соответствует конвенциям, применяемым путем форматирования инструментов в Visual Studio и других редакторах</span><span class="sxs-lookup"><span data-stu-id="cb045-106">Is in accordance with conventions applied by formatting tools in Visual Studio and other editors</span></span>
* <span data-ttu-id="cb045-107">Похож на другой код онлайн</span><span class="sxs-lookup"><span data-stu-id="cb045-107">Similar to other code online</span></span>

<span data-ttu-id="cb045-108">Эти руководящие принципы основаны на [всеобъемлющем руководстве по Конвенциям о формировании F'](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) [Anh-Dung Phan](https://github.com/dungpa).</span><span class="sxs-lookup"><span data-stu-id="cb045-108">These guidelines are based on [A comprehensive guide to F# Formatting Conventions](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) by [Anh-Dung Phan](https://github.com/dungpa).</span></span>

## <a name="general-rules-for-indentation"></a><span data-ttu-id="cb045-109">Общие правила для отступов</span><span class="sxs-lookup"><span data-stu-id="cb045-109">General rules for indentation</span></span>

<span data-ttu-id="cb045-110">По умолчанию используется значительное белое пространство.</span><span class="sxs-lookup"><span data-stu-id="cb045-110">F# uses significant white space by default.</span></span> <span data-ttu-id="cb045-111">Следующие руководящие принципы призваны дать рекомендации относительно того, как жонглировать некоторыми проблемами, которые это может навязать.</span><span class="sxs-lookup"><span data-stu-id="cb045-111">The following guidelines are intended to provide guidance as to how to juggle some challenges this can impose.</span></span>

### <a name="using-spaces"></a><span data-ttu-id="cb045-112">Использование пробелов</span><span class="sxs-lookup"><span data-stu-id="cb045-112">Using spaces</span></span>

<span data-ttu-id="cb045-113">При необходимости отступа необходимо использовать пробелы, а не вкладки.</span><span class="sxs-lookup"><span data-stu-id="cb045-113">When indentation is required, you must use spaces, not tabs.</span></span> <span data-ttu-id="cb045-114">Требуется по крайней мере одно пространство.</span><span class="sxs-lookup"><span data-stu-id="cb045-114">At least one space is required.</span></span> <span data-ttu-id="cb045-115">Организация может создавать стандарты кодирования для указания количества пробелов, которые можно использовать для отступов; два, три или четыре пробела отступов на каждом уровне, где происходит отступ, является типичным.</span><span class="sxs-lookup"><span data-stu-id="cb045-115">Your organization can create coding standards to specify the number of spaces to use for indentation; two, three or four spaces of indentation at each level where indentation occurs is typical.</span></span>

<span data-ttu-id="cb045-116">**Мы рекомендуем 4 места на отступ.**</span><span class="sxs-lookup"><span data-stu-id="cb045-116">**We recommend 4 spaces per indentation.**</span></span>

<span data-ttu-id="cb045-117">Тем не менее, отступы программ является субъективным вопросом.</span><span class="sxs-lookup"><span data-stu-id="cb045-117">That said, indentation of programs is a subjective matter.</span></span> <span data-ttu-id="cb045-118">Вариации в порядке, но первое правило, вы должны следовать это *последовательность отступов.*</span><span class="sxs-lookup"><span data-stu-id="cb045-118">Variations are OK, but the first rule you should follow is *consistency of indentation*.</span></span> <span data-ttu-id="cb045-119">Выберите общепринятый стиль отступов и систематически используйте его по всей кодовой базе.</span><span class="sxs-lookup"><span data-stu-id="cb045-119">Choose a generally accepted style of indentation and use it systematically throughout your codebase.</span></span>

## <a name="formatting-white-space"></a><span data-ttu-id="cb045-120">Форматирование белого пространства</span><span class="sxs-lookup"><span data-stu-id="cb045-120">Formatting white space</span></span>

<span data-ttu-id="cb045-121">ФЗ является белым пространством чувствительны.</span><span class="sxs-lookup"><span data-stu-id="cb045-121">F# is white space sensitive.</span></span> <span data-ttu-id="cb045-122">Хотя большинство семантики из белого пространства покрыты надлежащей отступы, Есть некоторые другие вещи, чтобы рассмотреть.</span><span class="sxs-lookup"><span data-stu-id="cb045-122">Although most semantics from white space are covered by proper indentation, there are some other things to consider.</span></span>

### <a name="formatting-operators-in-arithmetic-expressions"></a><span data-ttu-id="cb045-123">Форматирование операторов в арифметических выражениях</span><span class="sxs-lookup"><span data-stu-id="cb045-123">Formatting operators in arithmetic expressions</span></span>

<span data-ttu-id="cb045-124">Всегда используйте белое пространство вокруг бинарных арифметических выражений:</span><span class="sxs-lookup"><span data-stu-id="cb045-124">Always use white space around binary arithmetic expressions:</span></span>

```fsharp
let subtractThenAdd x = x - 1 + 3
```

<span data-ttu-id="cb045-125">Неунарные `-` операторы должны всегда иметь значение, они отрицают сразу же следовать:</span><span class="sxs-lookup"><span data-stu-id="cb045-125">Unary `-` operators should always have the value they are negating immediately follow:</span></span>

```fsharp
// OK
let negate x = -x

// Bad
let negateBad x = - x
```

<span data-ttu-id="cb045-126">Добавление белого пространства символ `-` после оператора может привести к путанице для других.</span><span class="sxs-lookup"><span data-stu-id="cb045-126">Adding a white-space character after the `-` operator can lead to confusion for others.</span></span>

<span data-ttu-id="cb045-127">Таким образом, важно всегда:</span><span class="sxs-lookup"><span data-stu-id="cb045-127">In summary, it's important to always:</span></span>

* <span data-ttu-id="cb045-128">Окружать бинарные операторы с белым пространством</span><span class="sxs-lookup"><span data-stu-id="cb045-128">Surround binary operators with white space</span></span>
* <span data-ttu-id="cb045-129">Никогда не имеют задней белое пространство после необезвиднятого оператора</span><span class="sxs-lookup"><span data-stu-id="cb045-129">Never have trailing white space after a unary operator</span></span>

<span data-ttu-id="cb045-130">Особенно важно ерелита бинарного оператора арифметики.</span><span class="sxs-lookup"><span data-stu-id="cb045-130">The binary arithmetic operator guideline is especially important.</span></span> <span data-ttu-id="cb045-131">Неспособность окружить `-` двоичного оператора, в сочетании с определенными вариантами `-`форматирования, может привести к интерпретации его как unary .</span><span class="sxs-lookup"><span data-stu-id="cb045-131">Failing to surround a binary `-` operator, when combined with certain formatting choices, could lead to interpreting it as a unary `-`.</span></span>

### <a name="surround-a-custom-operator-definition-with-white-space"></a><span data-ttu-id="cb045-132">Окружите пользовательское определение оператора белым пространством</span><span class="sxs-lookup"><span data-stu-id="cb045-132">Surround a custom operator definition with white space</span></span>

<span data-ttu-id="cb045-133">Всегда используйте белое пространство, чтобы окружить определение оператора:</span><span class="sxs-lookup"><span data-stu-id="cb045-133">Always use white space to surround an operator definition:</span></span>

```fsharp
// OK
let ( !> ) x f = f x

// Bad
let (!>) x f = f x
```

<span data-ttu-id="cb045-134">Для любого пользовательского `*` оператора, который начинается с и который имеет более одного символа, необходимо добавить белое пространство в начале определения, чтобы избежать двусмысленности компилятора.</span><span class="sxs-lookup"><span data-stu-id="cb045-134">For any custom operator that starts with `*` and that has more than one character, you need to add a white space to the beginning of the definition to avoid a compiler ambiguity.</span></span> <span data-ttu-id="cb045-135">Поэтому мы рекомендуем просто окружить определения всех операторов одним бело-космическим символом.</span><span class="sxs-lookup"><span data-stu-id="cb045-135">Because of this, we recommend that you simply surround the definitions of all operators with a single white-space character.</span></span>

### <a name="surround-function-parameter-arrows-with-white-space"></a><span data-ttu-id="cb045-136">Сострелка параметра объемной функции с белым пространством</span><span class="sxs-lookup"><span data-stu-id="cb045-136">Surround function parameter arrows with white space</span></span>

<span data-ttu-id="cb045-137">При определении подписи функции используйте `->` белое пространство вокруг символа:</span><span class="sxs-lookup"><span data-stu-id="cb045-137">When defining the signature of a function, use white space around the `->` symbol:</span></span>

```fsharp
// OK
type MyFun = int -> int -> string

// Bad
type MyFunBad = int->int->string
```

### <a name="surround-function-arguments-with-white-space"></a><span data-ttu-id="cb045-138">Аргументы функции окружения с белым пространством</span><span class="sxs-lookup"><span data-stu-id="cb045-138">Surround function arguments with white space</span></span>

<span data-ttu-id="cb045-139">При определении функции используйте белое пространство вокруг каждого аргумента.</span><span class="sxs-lookup"><span data-stu-id="cb045-139">When defining a function, use white space around each argument.</span></span>

```fsharp
// OK
let myFun (a: decimal) b c = a + b + c

// Bad
let myFunBad (a:decimal)(b)c = a + b + c
```

### <a name="place-parameters-on-a-new-line-for-very-long-member-definitions"></a><span data-ttu-id="cb045-140">Место параметров на новой строке для очень длинных определений членов</span><span class="sxs-lookup"><span data-stu-id="cb045-140">Place parameters on a new line for very long member definitions</span></span>

<span data-ttu-id="cb045-141">Если у вас очень длинное определение участника, поместите параметры на новые строки и отодвините их в одну область.</span><span class="sxs-lookup"><span data-stu-id="cb045-141">If you have a very long member definition, place the parameters on new lines and indent them one scope.</span></span>

```fsharp
type C() =
    member _.LongMethodWithLotsOfParameters(
        aVeryLongType: AVeryLongTypeThatYouNeedToUse
        aSecondVeryLongType: AVeryLongTypeThatYouNeedToUse
        aThirdVeryLongType: AVeryLongTypeThatYouNeedToUse) =
        // ... the body of the method follows
```

<span data-ttu-id="cb045-142">Это также относится к конструкторам:</span><span class="sxs-lookup"><span data-stu-id="cb045-142">This also applies to constructors:</span></span>

```fsharp
type C(
    aVeryLongType: AVeryLongTypeThatYouNeedToUse
    aSecondVeryLongType: AVeryLongTypeThatYouNeedToUse
    aThirdVeryLongType: AVeryLongTypeThatYouNeedToUse) =
    // ... the body of the class follows
```

### <a name="type-annotations"></a><span data-ttu-id="cb045-143">Введите аннотации</span><span class="sxs-lookup"><span data-stu-id="cb045-143">Type annotations</span></span>

#### <a name="right-pad-function-argument-type-annotations"></a><span data-ttu-id="cb045-144">Аннотации типа типа типа функции правой панели</span><span class="sxs-lookup"><span data-stu-id="cb045-144">Right-pad function argument type annotations</span></span>

<span data-ttu-id="cb045-145">При определении аргументов с аннотациями типа `:` используйте белое пространство после символа:</span><span class="sxs-lookup"><span data-stu-id="cb045-145">When defining arguments with type annotations, use white space after the `:` symbol:</span></span>

```fsharp
// OK
let complexFunction (a: int) (b: int) c = a + b + c

// Bad
let complexFunctionBad (a :int) (b :int) (c:int) = a + b + c
```

#### <a name="surround-return-type-annotations-with-white-space"></a><span data-ttu-id="cb045-146">Аннотации типа surround возврата с белым пространством</span><span class="sxs-lookup"><span data-stu-id="cb045-146">Surround return type annotations with white space</span></span>

<span data-ttu-id="cb045-147">В аннотации типа let-bound или типе значения (тип возврата в случае функции) используйте белое пространство до и после символа: `:`</span><span class="sxs-lookup"><span data-stu-id="cb045-147">In a let-bound function or value type annotation (return type in the case of a function), use white space before and after the `:` symbol:</span></span>

```fsharp
// OK
let expensiveToCompute : int = 0 // Type annotation for let-bound value
let myFun (a: decimal) b c : decimal = a + b + c // Type annotation for the return type of a function
// Bad
let expensiveToComputeBad1:int = 1
let expensiveToComputeBad2 :int = 2
let myFunBad (a: decimal) b c:decimal = a + b + c
```

## <a name="formatting-blank-lines"></a><span data-ttu-id="cb045-148">Форматирование пустых линий</span><span class="sxs-lookup"><span data-stu-id="cb045-148">Formatting blank lines</span></span>

* <span data-ttu-id="cb045-149">Отдельные определения функции верхнего уровня и класса с двумя пустыми строками.</span><span class="sxs-lookup"><span data-stu-id="cb045-149">Separate top-level function and class definitions with two blank lines.</span></span>
* <span data-ttu-id="cb045-150">Определения метода внутри класса разделены одной пустой строкой.</span><span class="sxs-lookup"><span data-stu-id="cb045-150">Method definitions inside a class are separated by a single blank line.</span></span>
* <span data-ttu-id="cb045-151">Дополнительные пустые строки могут быть использованы (экономно) для разделения групп связанных функций.</span><span class="sxs-lookup"><span data-stu-id="cb045-151">Extra blank lines may be used (sparingly) to separate groups of related functions.</span></span> <span data-ttu-id="cb045-152">Пустые линии могут быть опущены между кучей связанных однострочников (например, набор фиктивных реализаций).</span><span class="sxs-lookup"><span data-stu-id="cb045-152">Blank lines may be omitted between a bunch of related one-liners (for example, a set of dummy implementations).</span></span>
* <span data-ttu-id="cb045-153">Используйте пустые строки в функциях, экономно, чтобы указать логические разделы.</span><span class="sxs-lookup"><span data-stu-id="cb045-153">Use blank lines in functions, sparingly, to indicate logical sections.</span></span>

## <a name="formatting-comments"></a><span data-ttu-id="cb045-154">Форматирование комментариев</span><span class="sxs-lookup"><span data-stu-id="cb045-154">Formatting comments</span></span>

<span data-ttu-id="cb045-155">Как правило, предпочитают несколько двойных слэш комментарии по ML-стиль блок-комментариев.</span><span class="sxs-lookup"><span data-stu-id="cb045-155">Generally prefer multiple double-slash comments over ML-style block comments.</span></span>

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

<span data-ttu-id="cb045-156">В строке комментарии должны капитализировать первое письмо.</span><span class="sxs-lookup"><span data-stu-id="cb045-156">Inline comments should capitalize the first letter.</span></span>

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a><span data-ttu-id="cb045-157">Соглашения об именах</span><span class="sxs-lookup"><span data-stu-id="cb045-157">Naming conventions</span></span>

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a><span data-ttu-id="cb045-158">Используйте верблюжьики для значений и функций, связанных с классом, связанных с ими и шаблонных</span><span class="sxs-lookup"><span data-stu-id="cb045-158">Use camelCase for class-bound, expression-bound and pattern-bound values and functions</span></span>

<span data-ttu-id="cb045-159">Это является общим и принятым стилем F' для использования camelCase для всех имен, связанных как локальные переменные или в шаблонных совпадений и определениях функций.</span><span class="sxs-lookup"><span data-stu-id="cb045-159">It is common and accepted F# style to use camelCase for all names bound as local variables or in pattern matches and function definitions.</span></span>

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

<span data-ttu-id="cb045-160">Функции локального связанного в классах должны также использовать camelCase.</span><span class="sxs-lookup"><span data-stu-id="cb045-160">Locally-bound functions in classes should also use camelCase.</span></span>

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a><span data-ttu-id="cb045-161">Используйте верблюжьики для общественных функций, привязанных к модулю</span><span class="sxs-lookup"><span data-stu-id="cb045-161">Use camelCase for module-bound public functions</span></span>

<span data-ttu-id="cb045-162">Когда функция, связанная с модулем, является частью общедоступного API, она должна использовать camelCase:</span><span class="sxs-lookup"><span data-stu-id="cb045-162">When a module-bound function is part of a public API, it should use camelCase:</span></span>

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a><span data-ttu-id="cb045-163">Используйте camelCase для внутренних и частных значений и функций, связанных с модулем</span><span class="sxs-lookup"><span data-stu-id="cb045-163">Use camelCase for internal and private module-bound values and functions</span></span>

<span data-ttu-id="cb045-164">Используйте camelCase для значений, связанных с частными модулем, включая следующие:</span><span class="sxs-lookup"><span data-stu-id="cb045-164">Use camelCase for private module-bound values, including the following:</span></span>

* <span data-ttu-id="cb045-165">Специальные функции в сценариях</span><span class="sxs-lookup"><span data-stu-id="cb045-165">Ad hoc functions in scripts</span></span>

* <span data-ttu-id="cb045-166">Значения, составляющие внутреннюю реализацию модуля или типа</span><span class="sxs-lookup"><span data-stu-id="cb045-166">Values making up the internal implementation of a module or type</span></span>

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a><span data-ttu-id="cb045-167">Используйте верблюжьики для параметров</span><span class="sxs-lookup"><span data-stu-id="cb045-167">Use camelCase for parameters</span></span>

<span data-ttu-id="cb045-168">Все параметры должны использовать camelCase в соответствии с конвенциями именования .NET.</span><span class="sxs-lookup"><span data-stu-id="cb045-168">All parameters should use camelCase in accordance with .NET naming conventions.</span></span>

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a><span data-ttu-id="cb045-169">Используйте PascalCase для модулей</span><span class="sxs-lookup"><span data-stu-id="cb045-169">Use PascalCase for modules</span></span>

<span data-ttu-id="cb045-170">Все модули (верхний уровень, внутренний, частный, вложенный) должны использовать PascalCase.</span><span class="sxs-lookup"><span data-stu-id="cb045-170">All modules (top-level, internal, private, nested) should use PascalCase.</span></span>

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a><span data-ttu-id="cb045-171">Используйте PascalCase для типовых деклараций, участников и меток</span><span class="sxs-lookup"><span data-stu-id="cb045-171">Use PascalCase for type declarations, members, and labels</span></span>

<span data-ttu-id="cb045-172">Классы, интерфейсы, структуры, перечисления, делегаты, записи и дискриминируемые союзы должны быть названы паскалькейсом.</span><span class="sxs-lookup"><span data-stu-id="cb045-172">Classes, interfaces, structs, enumerations, delegates, records, and discriminated unions should all be named with PascalCase.</span></span> <span data-ttu-id="cb045-173">Члены типов и меток для записей и дискриминируемых союзов должны также использовать PascalCase.</span><span class="sxs-lookup"><span data-stu-id="cb045-173">Members within types and labels for records and discriminated unions should also use PascalCase.</span></span>

```fsharp
type IMyInterface =
    abstract Something: int

type MyClass() =
    member this.MyMethod(x, y) = x + y

type MyRecord = { IntVal: int; StringVal: string }

type SchoolPerson =
    | Professor
    | Student
    | Advisor
    | Administrator
```

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a><span data-ttu-id="cb045-174">Используйте PascalCase для конструкций, присущих .NET</span><span class="sxs-lookup"><span data-stu-id="cb045-174">Use PascalCase for constructs intrinsic to .NET</span></span>

<span data-ttu-id="cb045-175">Пространства имен, исключения, события и`.dll` названия/имена также должны использовать PascalCase.</span><span class="sxs-lookup"><span data-stu-id="cb045-175">Namespaces, exceptions, events, and project/`.dll` names should also use PascalCase.</span></span> <span data-ttu-id="cb045-176">Это не только делает потребление из других языков .NET более естественным для потребителей, но и согласуется с соглашениями о наименовании .NET, с которыми вы, вероятно, столкнетесь.</span><span class="sxs-lookup"><span data-stu-id="cb045-176">Not only does this make consumption from other .NET languages feel more natural to consumers, it's also consistent with .NET naming conventions that you are likely to encounter.</span></span>

### <a name="avoid-underscores-in-names"></a><span data-ttu-id="cb045-177">Избегайте подчеркнутов в именах</span><span class="sxs-lookup"><span data-stu-id="cb045-177">Avoid underscores in names</span></span>

<span data-ttu-id="cb045-178">Исторически сложилось так, что некоторые библиотеки F'а использовали подчеркивание в именах.</span><span class="sxs-lookup"><span data-stu-id="cb045-178">Historically, some F# libraries have used underscores in names.</span></span> <span data-ttu-id="cb045-179">Однако это уже не является широко признанным, отчасти потому, что это противоречит конвенциям именования .NET.</span><span class="sxs-lookup"><span data-stu-id="cb045-179">However, this is no longer widely accepted, partly because it clashes with .NET naming conventions.</span></span> <span data-ttu-id="cb045-180">Тем не менее, некоторые программисты F's используют в значительной степени, отчасти по историческим причинам, и терпимость и уважение имеет важное значение.</span><span class="sxs-lookup"><span data-stu-id="cb045-180">That said, some F# programmers use underscores heavily, partly for historical reasons, and tolerance and respect is important.</span></span> <span data-ttu-id="cb045-181">Однако, имейте в виду, что стиль часто не любят другие, которые имеют выбор о том, чтобы использовать его.</span><span class="sxs-lookup"><span data-stu-id="cb045-181">However, be aware that the style is often disliked by others who have a choice about whether to use it.</span></span>

<span data-ttu-id="cb045-182">Некоторые исключения включают взаимодействие с родными компонентами, где подчеркивание очень распространено.</span><span class="sxs-lookup"><span data-stu-id="cb045-182">Some exceptions includes interoperating with native components, where underscores are very common.</span></span>

### <a name="use-standard-f-operators"></a><span data-ttu-id="cb045-183">Используйте стандартные операторы ФЗ</span><span class="sxs-lookup"><span data-stu-id="cb045-183">Use standard F# operators</span></span>

<span data-ttu-id="cb045-184">Следующие операторы определяются в стандартной библиотеке F и должны использоваться вместо определения эквивалентов.</span><span class="sxs-lookup"><span data-stu-id="cb045-184">The following operators are defined in the F# standard library and should be used instead of defining equivalents.</span></span> <span data-ttu-id="cb045-185">Использование этих операторов рекомендуется, поскольку он стремится сделать код более читаемым и идиоматичным.</span><span class="sxs-lookup"><span data-stu-id="cb045-185">Using these operators is recommended as it tends to make code more readable and idiomatic.</span></span> <span data-ttu-id="cb045-186">Разработчики с опытом работы на OCaml или на другом языке функционального программирования могут привыкнуть к различным идиомам.</span><span class="sxs-lookup"><span data-stu-id="cb045-186">Developers with a background in OCaml or other functional programming language may be accustomed to different idioms.</span></span> <span data-ttu-id="cb045-187">В следующем списке кратко излагаются рекомендуемые операторы F-е.</span><span class="sxs-lookup"><span data-stu-id="cb045-187">The following list summarizes the recommended F# operators.</span></span>

```fsharp
x |> f // Forward pipeline
f >> g // Forward composition
x |> ignore // Discard away a value
x + y // Overloaded addition (including string concatenation)
x - y // Overloaded subtraction
x * y // Overloaded multiplication
x / y // Overloaded division
x % y // Overloaded modulus
x && y // Lazy/short-cut "and"
x || y // Lazy/short-cut "or"
x <<< y // Bitwise left shift
x >>> y // Bitwise right shift
x ||| y // Bitwise or, also for working with “flags” enumeration
x &&& y // Bitwise and, also for working with “flags” enumeration
x ^^^ y // Bitwise xor, also for working with “flags” enumeration
```

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a><span data-ttu-id="cb045-188">Используйте приставку синтаксис`Foo<T>`для генериков ()`T Foo`в предпочтении к postfix синтаксис ()</span><span class="sxs-lookup"><span data-stu-id="cb045-188">Use prefix syntax for generics (`Foo<T>`) in preference to postfix syntax (`T Foo`)</span></span>

<span data-ttu-id="cb045-189">ФЗ наследует как постфикс ML стиль именования `int list`генерических типов (например, ), а `list<int>`также приставку .NET стиль (например, ).</span><span class="sxs-lookup"><span data-stu-id="cb045-189">F# inherits both the postfix ML style of naming generic types (for example, `int list`) as well as the prefix .NET style (for example, `list<int>`).</span></span> <span data-ttu-id="cb045-190">Предпочитаю стиль .NET, за исключением пяти конкретных типов:</span><span class="sxs-lookup"><span data-stu-id="cb045-190">Prefer the .NET style, except for five specific types:</span></span>

1. <span data-ttu-id="cb045-191">Для списков F, используйте `int list` форму `list<int>`postfix: вместо .</span><span class="sxs-lookup"><span data-stu-id="cb045-191">For F# Lists, use the postfix form: `int list` rather than `list<int>`.</span></span>
2. <span data-ttu-id="cb045-192">Для опций F', используйте `int option` форму `option<int>`postfix: вместо .</span><span class="sxs-lookup"><span data-stu-id="cb045-192">For F# Options, use the postfix form: `int option` rather than `option<int>`.</span></span>
3. <span data-ttu-id="cb045-193">Для опций значения F', используйте форму postfix: `int voption` вместо `voption<int>`.</span><span class="sxs-lookup"><span data-stu-id="cb045-193">For F# Value Options, use the postfix form: `int voption` rather than `voption<int>`.</span></span>
4. <span data-ttu-id="cb045-194">Для массивов F-х используйте `int[]` синтаксиче, а `int array` не `array<int>`.</span><span class="sxs-lookup"><span data-stu-id="cb045-194">For F# arrays, use the syntactic name `int[]` rather than `int array` or `array<int>`.</span></span>
5. <span data-ttu-id="cb045-195">Для справочных `int ref` ячеек, использовать, а `ref<int>` не `Ref<int>`.</span><span class="sxs-lookup"><span data-stu-id="cb045-195">For Reference Cells, use `int ref` rather than `ref<int>` or `Ref<int>`.</span></span>

<span data-ttu-id="cb045-196">Для всех остальных типов используйте форму префикса.</span><span class="sxs-lookup"><span data-stu-id="cb045-196">For all other types, use the prefix form.</span></span>

## <a name="formatting-tuples"></a><span data-ttu-id="cb045-197">Форматирование подобие</span><span class="sxs-lookup"><span data-stu-id="cb045-197">Formatting tuples</span></span>

<span data-ttu-id="cb045-198">Мгновенное мгновение туловища должно быть скобками, а за разграничением запятых внутри должно последовать одно пространство, например: `(1, 2)`. `(x, y, z)`</span><span class="sxs-lookup"><span data-stu-id="cb045-198">A tuple instantiation should be parenthesized, and the delimiting commas within should be followed by a single space, for example: `(1, 2)`, `(x, y, z)`.</span></span>

<span data-ttu-id="cb045-199">Принято опускать скобки в сопоставлении шаблонов:</span><span class="sxs-lookup"><span data-stu-id="cb045-199">It is commonly accepted to omit parentheses in pattern matching of tuples:</span></span>

```fsharp
let (x, y) = z // Destructuring
let x, y = z // OK

// OK
match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

<span data-ttu-id="cb045-200">Также принято опускать скобки, если туляк является возвратным значением функции:</span><span class="sxs-lookup"><span data-stu-id="cb045-200">It is also commonly accepted to omit parentheses if the tuple is the return value of a function:</span></span>

```fsharp
// OK
let update model msg =
    match msg with
    | 1 -> model + 1, []
    | _ -> model, [ msg ]
```

<span data-ttu-id="cb045-201">Таким образом, предпочитают скобки tuple мгновенности, но при использовании tuples для сопоставления шаблона или возврата значение, считается прекрасным, чтобы избежать скобки.</span><span class="sxs-lookup"><span data-stu-id="cb045-201">In summary, prefer parenthesized tuple instantiations, but when using tuples for pattern matching or a return value, it is considered fine to avoid parentheses.</span></span>

## <a name="formatting-discriminated-union-declarations"></a><span data-ttu-id="cb045-202">Форматирование дискриминированных профсоюзных деклараций</span><span class="sxs-lookup"><span data-stu-id="cb045-202">Formatting discriminated union declarations</span></span>

<span data-ttu-id="cb045-203">Отступ `|` в определении типа на 4 пространства:</span><span class="sxs-lookup"><span data-stu-id="cb045-203">Indent `|` in type definition by 4 spaces:</span></span>

```fsharp
// OK
type Volume =
    | Liter of float
    | FluidOunce of float
    | ImperialPint of float

// Not OK
type Volume =
| Liter of float
| USPint of float
| ImperialPint of float
```

## <a name="formatting-discriminated-unions"></a><span data-ttu-id="cb045-204">Форматирование дискриминируемых профсоюзов</span><span class="sxs-lookup"><span data-stu-id="cb045-204">Formatting discriminated unions</span></span>

<span data-ttu-id="cb045-205">Мгновенные дискриминированные союзы, разделенные на несколько строк, должны предоставить содержащиеся данные новой области с отступами:</span><span class="sxs-lookup"><span data-stu-id="cb045-205">Instantiated Discriminated Unions that split across multiple lines should give contained data a new scope with indentation:</span></span>

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

<span data-ttu-id="cb045-206">Закрытие скобки также может быть на новой строке:</span><span class="sxs-lookup"><span data-stu-id="cb045-206">The closing parenthesis can also be on a new line:</span></span>

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-record-declarations"></a><span data-ttu-id="cb045-207">Форматирование записи деклараций</span><span class="sxs-lookup"><span data-stu-id="cb045-207">Formatting record declarations</span></span>

<span data-ttu-id="cb045-208">Отступ `{` в определении типа на 4 пространства и начать список полей на той же строке:</span><span class="sxs-lookup"><span data-stu-id="cb045-208">Indent `{` in type definition by 4 spaces and start the field list on the same line:</span></span>

```fsharp
// OK
type PostalAddress =
    { Address: string
      City: string
      Zip: string }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

// Not OK
type PostalAddress =
  { Address: string
    City: string
    Zip: string }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

// Unusual in F#
type PostalAddress =
    {
        Address: string
        City: string
        Zip: string
    }
```

<span data-ttu-id="cb045-209">Размещение токена открытия на новой строке и маркера закрытия на новой строке предпочтительнее, если вы объявляете реализации интерфейса или участников в записи:</span><span class="sxs-lookup"><span data-stu-id="cb045-209">Placing the opening token on a new line and the closing token on a new line is preferable if you are declaring interface implementations or members on the record:</span></span>

```fsharp
// Declaring additional members on PostalAddress
type PostalAddress =
    {
        Address: string
        City: string
        Zip: string
    }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

type MyRecord =
    {
        SomeField: int
    }
    interface IMyInterface
```

## <a name="formatting-records"></a><span data-ttu-id="cb045-210">Форматирование записей</span><span class="sxs-lookup"><span data-stu-id="cb045-210">Formatting records</span></span>

<span data-ttu-id="cb045-211">Короткие записи могут быть написаны в одной строке:</span><span class="sxs-lookup"><span data-stu-id="cb045-211">Short records can be written in one line:</span></span>

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

<span data-ttu-id="cb045-212">Записи, которые больше должны использовать новые линии для меток:</span><span class="sxs-lookup"><span data-stu-id="cb045-212">Records that are longer should use new lines for labels:</span></span>

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

<span data-ttu-id="cb045-213">Размещение токена открытия на новой строке, содержимое вкладки в течение одной области, и закрытие маркера на новой линии предпочтительнее, если вы:</span><span class="sxs-lookup"><span data-stu-id="cb045-213">Placing the opening token on a new line, the contents tabbed over one scope, and the closing token on a new line is preferable if you are:</span></span>

* <span data-ttu-id="cb045-214">Перемещение записей в коде с различными областями отступов</span><span class="sxs-lookup"><span data-stu-id="cb045-214">Moving records around in code with different indentation scopes</span></span>
* <span data-ttu-id="cb045-215">Трубопроводы их в функцию</span><span class="sxs-lookup"><span data-stu-id="cb045-215">Piping them into a function</span></span>

```fsharp
let rainbow =
    {
        Boss1 = "Jeffrey"
        Boss2 = "Jeffrey"
        Boss3 = "Jeffrey"
        Boss4 = "Jeffrey"
        Boss5 = "Jeffrey"
        Boss6 = "Jeffrey"
        Boss7 = "Jeffrey"
        Boss8 = "Jeffrey"
        Lackeys = ["Zippy"; "George"; "Bungle"]
    }

type MyRecord =
    {
        SomeField: int
    }
    interface IMyInterface

let foo a =
    a
    |> Option.map (fun x ->
        {
            MyField = x
        })
```

<span data-ttu-id="cb045-216">Те же правила применяются к элементам списка и массива.</span><span class="sxs-lookup"><span data-stu-id="cb045-216">The same rules apply for list and array elements.</span></span>

## <a name="formatting-copy-and-update-record-expressions"></a><span data-ttu-id="cb045-217">Форматирование выражений записей копий и обновлений</span><span class="sxs-lookup"><span data-stu-id="cb045-217">Formatting copy-and-update record expressions</span></span>

<span data-ttu-id="cb045-218">Выражение записи копирования и обновления по-прежнему является записью, поэтому применяются аналогичные рекомендации.</span><span class="sxs-lookup"><span data-stu-id="cb045-218">A copy-and-update record expression is still a record, so similar guidelines apply.</span></span>

<span data-ttu-id="cb045-219">Короткие выражения могут поместиться на одной строке:</span><span class="sxs-lookup"><span data-stu-id="cb045-219">Short expressions can fit on one line:</span></span>

```fsharp
let point2 = { point with X = 1; Y = 2 }
```

<span data-ttu-id="cb045-220">Более длинные выражения должны использовать новые строки:</span><span class="sxs-lookup"><span data-stu-id="cb045-220">Longer expressions should use new lines:</span></span>

```fsharp
let rainbow2 =
    { rainbow with
        Boss = "Jeffrey"
        Lackeys = ["Zippy"; "George"; "Bungle"] }
```

<span data-ttu-id="cb045-221">И, как и в руководстве записи, вы можете посвятить отдельные строки для скобки и отступ один объем справа с выражением.</span><span class="sxs-lookup"><span data-stu-id="cb045-221">And as with the record guidance, you may want to dedicate separate lines for the braces and indent one scope to the right with the expression.</span></span> <span data-ttu-id="cb045-222">Обратите внимание, что в некоторых особых случаях, таких как упаковка значения с дополнительнымбезными без скобки, возможно, потребуется держать скобки на одной строке:</span><span class="sxs-lookup"><span data-stu-id="cb045-222">Note that in some special cases, such as wrapping a value with an optional without parentheses, you may need to keep a brace on one line:</span></span>

```fsharp
type S = { F1: int; F2: string }
type State = { F:  S option }

let state = { F = Some { F1 = 1; F2 = "Hello" } }
let newState =
    {
        state with
            F = Some {
                    F1 = 0
                    F2 = ""
                }
    }
```

## <a name="formatting-lists-and-arrays"></a><span data-ttu-id="cb045-223">Списки и массивы форматирования</span><span class="sxs-lookup"><span data-stu-id="cb045-223">Formatting lists and arrays</span></span>

<span data-ttu-id="cb045-224">Пишите `x :: l` с пробелами вокруг `::` оператора (является`::` оператором infix, следовательно, окружен пространствами).</span><span class="sxs-lookup"><span data-stu-id="cb045-224">Write `x :: l` with spaces around the `::` operator (`::` is an infix operator, hence surrounded by spaces).</span></span>

<span data-ttu-id="cb045-225">Список и массивы, заявленные на одной строке, должны иметь место после открытия кронштейна и перед закрытием кронштейна:</span><span class="sxs-lookup"><span data-stu-id="cb045-225">List and arrays declared on a single line should have a space after the opening bracket and before the closing bracket:</span></span>

```fsharp
let xs = [ 1; 2; 3 ]
let ys = [| 1; 2; 3; |]
```

<span data-ttu-id="cb045-226">Всегда используйте по крайней мере одно пространство между двумя различными операторами, похожими на скобки.</span><span class="sxs-lookup"><span data-stu-id="cb045-226">Always use at least one space between two distinct brace-like operators.</span></span> <span data-ttu-id="cb045-227">Например, оставьте пространство `[` между `{`a и a .</span><span class="sxs-lookup"><span data-stu-id="cb045-227">For example, leave a space between a `[` and a `{`.</span></span>

```fsharp
// OK
[ { IngredientName = "Green beans"; Quantity = 250 }
  { IngredientName = "Pine nuts"; Quantity = 250 }
  { IngredientName = "Feta cheese"; Quantity = 250 }
  { IngredientName = "Olive oil"; Quantity = 10 }
  { IngredientName = "Lemon"; Quantity = 1 } ]

// Not OK
[{ IngredientName = "Green beans"; Quantity = 250 }
 { IngredientName = "Pine nuts"; Quantity = 250 }
 { IngredientName = "Feta cheese"; Quantity = 250 }
 { IngredientName = "Olive oil"; Quantity = 10 }
 { IngredientName = "Lemon"; Quantity = 1 }]
```

<span data-ttu-id="cb045-228">То же самое правило применяется для списков или массивов зауполей.</span><span class="sxs-lookup"><span data-stu-id="cb045-228">The same guideline applies for lists or arrays of tuples.</span></span>

<span data-ttu-id="cb045-229">Списки и массивы, разделенные на несколько строк, следуют аналогичному правилу, как и записи:</span><span class="sxs-lookup"><span data-stu-id="cb045-229">Lists and arrays that split across multiple lines follow a similar rule as records do:</span></span>

```fsharp
let pascalsTriangle =
    [|
        [| 1 |]
        [| 1; 1 |]
        [| 1; 2; 1 |]
        [| 1; 3; 3; 1 |]
        [| 1; 4; 6; 4; 1 |]
        [| 1; 5; 10; 10; 5; 1 |]
        [| 1; 6; 15; 20; 15; 6; 1 |]
        [| 1; 7; 21; 35; 35; 21; 7; 1 |]
        [| 1; 8; 28; 56; 70; 56; 28; 8; 1 |]
    |]
```

<span data-ttu-id="cb045-230">И как с записями, объявление открытия и закрытия скобки на их собственной линии сделает перемещение кода вокруг и трубопроводов в функции легче.</span><span class="sxs-lookup"><span data-stu-id="cb045-230">And as with records, declaring the opening and closing brackets on their own line will make moving code around and piping into functions easier.</span></span>

<span data-ttu-id="cb045-231">При создании массивов и списков `->` программно, предпочитают, `do ... yield` когда значение всегда генерируется:</span><span class="sxs-lookup"><span data-stu-id="cb045-231">When generating arrays and lists programmatically, prefer `->` over `do ... yield` when a value is always generated:</span></span>

```fsharp
// Preferred
let squares = [ for x in 1..10 -> x*x ]

// Not preferred
let squares' = [ for x in 1..10 do yield x*x ]
```

<span data-ttu-id="cb045-232">Более старые версии языка `yield` F's требовали указания в ситуациях, когда данные могут быть получены условно, или могут быть последовательные выражения для оценки.</span><span class="sxs-lookup"><span data-stu-id="cb045-232">Older versions of the F# language required specifying `yield` in situations where data may be generated conditionally, or there may be consecutive expressions to be evaluated.</span></span> <span data-ttu-id="cb045-233">Предпочитаюнее опускать эти `yield` ключевые слова, если вы не должны компилировать со старой версией языка F':</span><span class="sxs-lookup"><span data-stu-id="cb045-233">Prefer omitting these `yield` keywords unless you must compile with an older F# language version:</span></span>

```fsharp
// Preferred
let daysOfWeek includeWeekend =
    [
        "Monday"
        "Tuesday"
        "Wednesday"
        "Thursday"
        "Friday"
        if includeWeekend then
            "Saturday"
            "Sunday"
    ]

// Not preferred
let daysOfWeek' includeWeekend =
    [
        yield "Monday"
        yield "Tuesday"
        yield "Wednesday"
        yield "Thursday"
        yield "Friday"
        if includeWeekend then
            yield "Saturday"
            yield "Sunday"
    ]
```

<span data-ttu-id="cb045-234">В некоторых `do...yield` случаях, может помочь в читаемости.</span><span class="sxs-lookup"><span data-stu-id="cb045-234">In some cases, `do...yield` may aid in readability.</span></span> <span data-ttu-id="cb045-235">Эти случаи, хотя и субъективные, должны быть приняты во внимание.</span><span class="sxs-lookup"><span data-stu-id="cb045-235">These cases, though subjective, should be taken into consideration.</span></span>

## <a name="formatting-if-expressions"></a><span data-ttu-id="cb045-236">Форматирование, если выражения</span><span class="sxs-lookup"><span data-stu-id="cb045-236">Formatting if expressions</span></span>

<span data-ttu-id="cb045-237">Отступы условных веществ зависят от размеров выражаемых их выражений.</span><span class="sxs-lookup"><span data-stu-id="cb045-237">Indentation of conditionals depends on the sizes of the expressions that make them up.</span></span> <span data-ttu-id="cb045-238">`cond`Если, `e1` `e2` и короткие, просто напишите их на одной строке:</span><span class="sxs-lookup"><span data-stu-id="cb045-238">If `cond`, `e1` and `e2` are short, simply write them on one line:</span></span>

```fsharp
if cond then e1 else e2
```

<span data-ttu-id="cb045-239">Если `cond`либо `e1` `e2` , или больше, но не многолинейный:</span><span class="sxs-lookup"><span data-stu-id="cb045-239">If either `cond`, `e1` or `e2` are longer, but not multi-line:</span></span>

```fsharp
if cond
then e1
else e2
```

<span data-ttu-id="cb045-240">Если какое-либо из выражений является многолинейным:</span><span class="sxs-lookup"><span data-stu-id="cb045-240">If any of the expressions are multi-line:</span></span>

```fsharp
if cond then
    e1
else
    e2
```

<span data-ttu-id="cb045-241">Несколько условных с `elif` и `else` отступом в `if`той же области, как:</span><span class="sxs-lookup"><span data-stu-id="cb045-241">Multiple conditionals with `elif` and `else` are indented at the same scope as the `if`:</span></span>

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a><span data-ttu-id="cb045-242">Конструкции, соответствующие шаблону</span><span class="sxs-lookup"><span data-stu-id="cb045-242">Pattern matching constructs</span></span>

<span data-ttu-id="cb045-243">Используйте `|` для каждого пункта матча без отступов.</span><span class="sxs-lookup"><span data-stu-id="cb045-243">Use a `|` for each clause of a match with no indentation.</span></span> <span data-ttu-id="cb045-244">Если выражение короткое, можно рассмотреть возможность использования одной строки, если каждое подвыражение также просто.</span><span class="sxs-lookup"><span data-stu-id="cb045-244">If the expression is short, you can consider using a single line if each subexpression is also simple.</span></span>

```fsharp
// OK
match l with
| { him = x; her = "Posh" } :: tail -> x
| _ :: tail -> findDavid tail
| [] -> failwith "Couldn't find David"

// Not OK
match l with
    | { him = x; her = "Posh" } :: tail -> x
    | _ :: tail -> findDavid tail
    | [] -> failwith "Couldn't find David"
```

<span data-ttu-id="cb045-245">Если выражение справа от стрелки шаблона слишком велико, переместите ее на `match` / `|`следующую строку, отступив на один шаг от .</span><span class="sxs-lookup"><span data-stu-id="cb045-245">If the expression on the right of the pattern matching arrow is too large, move it to the following line, indented one step from the `match`/`|`.</span></span>

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

<span data-ttu-id="cb045-246">Шаблон сопоставления анонимных функций, начиная `function`с , как правило, не отступ слишком далеко.</span><span class="sxs-lookup"><span data-stu-id="cb045-246">Pattern matching of anonymous functions, starting by `function`, should generally not indent too far.</span></span> <span data-ttu-id="cb045-247">Например, один объем следующим образом:</span><span class="sxs-lookup"><span data-stu-id="cb045-247">For example, indenting one scope as follows is fine:</span></span>

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

<span data-ttu-id="cb045-248">Шаблон, соответствующий `let` функциям, определенным `let rec` или должны быть `let`отступом `function` 4 пространства после начала, даже если ключевое слово используется:</span><span class="sxs-lookup"><span data-stu-id="cb045-248">Pattern matching in functions defined by `let` or `let rec` should be indented 4 spaces after starting of `let`, even if `function` keyword is used:</span></span>

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

<span data-ttu-id="cb045-249">Мы не рекомендуем выравнивать стрелки.</span><span class="sxs-lookup"><span data-stu-id="cb045-249">We do not recommend aligning arrows.</span></span>

## <a name="formatting-trywith-expressions"></a><span data-ttu-id="cb045-250">Попытка форматирования/с выражениями</span><span class="sxs-lookup"><span data-stu-id="cb045-250">Formatting try/with expressions</span></span>

<span data-ttu-id="cb045-251">Шаблон, соответствующий типу исключения, должен быть `with`отступом на том же уровне, что и .</span><span class="sxs-lookup"><span data-stu-id="cb045-251">Pattern matching on the exception type should be indented at the same level as `with`.</span></span>

```fsharp
try
    if System.DateTime.Now.Second % 3 = 0 then
        raise (new System.Exception())
    else
        raise (new System.ApplicationException())
with
| :? System.ApplicationException ->
    printfn "A second that was not a multiple of 3"
| _ ->
    printfn "A second that was a multiple of 3"
```

## <a name="formatting-function-parameter-application"></a><span data-ttu-id="cb045-252">Применение параметра функции форматирования</span><span class="sxs-lookup"><span data-stu-id="cb045-252">Formatting function parameter application</span></span>

<span data-ttu-id="cb045-253">Как правило, большинство приложений параметров функции выполняется на одной линии.</span><span class="sxs-lookup"><span data-stu-id="cb045-253">In general, most function parameter application is done on the same line.</span></span>

<span data-ttu-id="cb045-254">Если вы хотите применить параметры к функции на новой строке, отодвиньте их по одной области.</span><span class="sxs-lookup"><span data-stu-id="cb045-254">If you wish to apply parameters to a function on a new line, indent them by one scope.</span></span>

```fsharp
// OK
sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity

// OK
sprintf
     "\t%s - %i\n\r"
     x.IngredientName x.Quantity

// OK
let printVolumes x =
    printf "Volume in liters = %f, in us pints = %f, in imperial = %f"
        (convertVolumeToLiter x)
        (convertVolumeUSPint x)
        (convertVolumeImperialPint x)
```

<span data-ttu-id="cb045-255">Те же руководящие принципы применяются для выражений лямбды в качестве функциональных аргументов.</span><span class="sxs-lookup"><span data-stu-id="cb045-255">The same guidelines apply for lambda expressions as function arguments.</span></span> <span data-ttu-id="cb045-256">Если тело выражение лямбда, тело может иметь другую линию, отступом на одну область</span><span class="sxs-lookup"><span data-stu-id="cb045-256">If the body of a lambda expression, the body can have another line, indented by one scope</span></span>

```fsharp
let printListWithOffset a list1 =
    List.iter
        (fun elem -> printfn "%d" (a + elem))
        list1

// OK if lambda body is long enough
let printListWithOffset a list1 =
    List.iter
        (fun elem ->
            printfn "%d" (a + elem))
        list1
```

<span data-ttu-id="cb045-257">Однако, если тело выражения лямбды состоит более чем в одной строке, подумайте о том, чтобы учесть его в отдельную функцию, а не иметь многолинейную конструкцию, применяемую в качестве единого аргумента к функции.</span><span class="sxs-lookup"><span data-stu-id="cb045-257">However, if the body of a lambda expression is more than one line, consider factoring it out into a separate function rather than have a multi-line construct applied as a single argument to a function.</span></span>

### <a name="formatting-infix-operators"></a><span data-ttu-id="cb045-258">Форматирование операторов infix</span><span class="sxs-lookup"><span data-stu-id="cb045-258">Formatting infix operators</span></span>

<span data-ttu-id="cb045-259">Отдельные операторы по пространствам.</span><span class="sxs-lookup"><span data-stu-id="cb045-259">Separate operators by spaces.</span></span> <span data-ttu-id="cb045-260">Очевидными исключениями из `!` этого `.` правила являются и операторы.</span><span class="sxs-lookup"><span data-stu-id="cb045-260">Obvious exceptions to this rule are the `!` and `.` operators.</span></span>

<span data-ttu-id="cb045-261">Выражения Infix ок для линейки на той же колонке:</span><span class="sxs-lookup"><span data-stu-id="cb045-261">Infix expressions are OK to lineup on same column:</span></span>

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a><span data-ttu-id="cb045-262">Форматирование операторов трубопроводов</span><span class="sxs-lookup"><span data-stu-id="cb045-262">Formatting pipeline operators</span></span>

<span data-ttu-id="cb045-263">Операторы трубопроводов `|>` должны идти под выражения, на которых они работают.</span><span class="sxs-lookup"><span data-stu-id="cb045-263">Pipeline `|>` operators should go underneath the expressions they operate on.</span></span>

```fsharp
// Preferred approach
let methods2 =
    System.AppDomain.CurrentDomain.GetAssemblies()
    |> List.ofArray
    |> List.map (fun assm -> assm.GetTypes())
    |> Array.concat
    |> List.ofArray
    |> List.map (fun t -> t.GetMethods())
    |> Array.concat

// Not OK
let methods2 = System.AppDomain.CurrentDomain.GetAssemblies()
            |> List.ofArray
            |> List.map (fun assm -> assm.GetTypes())
            |> Array.concat
            |> List.ofArray
            |> List.map (fun t -> t.GetMethods())
            |> Array.concat
```

### <a name="formatting-modules"></a><span data-ttu-id="cb045-264">Модули форматирования</span><span class="sxs-lookup"><span data-stu-id="cb045-264">Formatting modules</span></span>

<span data-ttu-id="cb045-265">Код в локальном модуле должен быть отступом относительно модуля, но код в модуле верхнего уровня не должен быть отступом.</span><span class="sxs-lookup"><span data-stu-id="cb045-265">Code in a local module must be indented relative to the module, but code in a top-level module should not be indented.</span></span> <span data-ttu-id="cb045-266">Элементы пространства имен не должны быть отступом.</span><span class="sxs-lookup"><span data-stu-id="cb045-266">Namespace elements do not have to be indented.</span></span>

```fsharp
// A is a top-level module.
module A

let function1 a b = a - b * b
```

```fsharp
// A1 and A2 are local modules.
module A1 =
    let function1 a b = a*a + b*b

module A2 =
    let function2 a b = a*a - b*b
```

### <a name="formatting-object-expressions-and-interfaces"></a><span data-ttu-id="cb045-267">Форматирование выражений и интерфейсов объектов</span><span class="sxs-lookup"><span data-stu-id="cb045-267">Formatting object expressions and interfaces</span></span>

<span data-ttu-id="cb045-268">Выражения и интерфейсы объектов должны быть выровнены таким же образом, чтобы `member` быть отступом после 4 пробелов.</span><span class="sxs-lookup"><span data-stu-id="cb045-268">Object expressions and interfaces should be aligned in the same way with `member` being indented after 4 spaces.</span></span>

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s: String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-white-space-in-expressions"></a><span data-ttu-id="cb045-269">Форматирование белого пространства в выражениях</span><span class="sxs-lookup"><span data-stu-id="cb045-269">Formatting white space in expressions</span></span>

<span data-ttu-id="cb045-270">Избегайте посторонних белых пространств в выражениях F.'.</span><span class="sxs-lookup"><span data-stu-id="cb045-270">Avoid extraneous white space in F# expressions.</span></span>

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

<span data-ttu-id="cb045-271">Названные аргументы также не `=`должны иметь пространство, окружающее:</span><span class="sxs-lookup"><span data-stu-id="cb045-271">Named arguments should also not have space surrounding the `=`:</span></span>

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```

## <a name="formatting-attributes"></a><span data-ttu-id="cb045-272">Характеристики форматирования</span><span class="sxs-lookup"><span data-stu-id="cb045-272">Formatting attributes</span></span>

<span data-ttu-id="cb045-273">[Атрибуты](../language-reference/attributes.md) размещаются над конструкцией:</span><span class="sxs-lookup"><span data-stu-id="cb045-273">[Attributes](../language-reference/attributes.md) are placed above a construct:</span></span>

```fsharp
[<SomeAttribute>]
type MyClass() = ...

[<RequireQualifiedAccess>]
module M =
    let f x = x

[<Struct>]
type MyRecord =
    { Label1: int
      Label2: string }
```

### <a name="formatting-attributes-on-parameters"></a><span data-ttu-id="cb045-274">Формирование атрибутов по параметрам</span><span class="sxs-lookup"><span data-stu-id="cb045-274">Formatting attributes on parameters</span></span>

<span data-ttu-id="cb045-275">Атрибуты также могут быть местами по параметрам.</span><span class="sxs-lookup"><span data-stu-id="cb045-275">Attributes can also be places on parameters.</span></span> <span data-ttu-id="cb045-276">В этом случае поместите затем на ту же строку, что и параметр, и перед именем:</span><span class="sxs-lookup"><span data-stu-id="cb045-276">In this case, place then on the same line as the parameter and before the name:</span></span>

```fsharp
// Defines a class that takes an optional value as input defaulting to false.
type C() =
    member _.M([<Optional; DefaultParameterValue(false)>] doSomething: bool)
```

### <a name="formatting-multiple-attributes"></a><span data-ttu-id="cb045-277">Формирование нескольких атрибутов</span><span class="sxs-lookup"><span data-stu-id="cb045-277">Formatting multiple attributes</span></span>

<span data-ttu-id="cb045-278">Когда несколько атрибутов применяются к конструкции, которая не является параметром, они должны быть размещены таким образом, что есть один атрибут на строку:</span><span class="sxs-lookup"><span data-stu-id="cb045-278">When multiple attributes are applied to a construct that is not a parameter, they should be placed such that there is one attribute per line:</span></span>

```fsharp
[<Struct>]
[<IsByRefLike>]
type MyRecord =
    { Label1: int
      Label2: string }
```

<span data-ttu-id="cb045-279">При применении к параметру они должны находиться `;` на одной линии и отделяться от сепаратора.</span><span class="sxs-lookup"><span data-stu-id="cb045-279">When applied to a parameter, they must be on the same line and separated by a `;` separator.</span></span>

## <a name="formatting-literals"></a><span data-ttu-id="cb045-280">Форматирование буквальных</span><span class="sxs-lookup"><span data-stu-id="cb045-280">Formatting literals</span></span>

<span data-ttu-id="cb045-281">[Буквальные буквы F',](../language-reference/literals.md) использующие `Literal` атрибут, должны размещать атрибут на своей собственной линии и использовать именования PascalCase:</span><span class="sxs-lookup"><span data-stu-id="cb045-281">[F# literals](../language-reference/literals.md) using the `Literal` attribute should place the attribute on its own line and use PascalCase naming:</span></span>

```fsharp
[<Literal>]
let Path = __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let MyUrl = "www.mywebsitethatiamworkingwith.com"
```

<span data-ttu-id="cb045-282">Избегайте размещения атрибута на той же строке, что и значение.</span><span class="sxs-lookup"><span data-stu-id="cb045-282">Avoid placing the attribute on the same line as the value.</span></span>
