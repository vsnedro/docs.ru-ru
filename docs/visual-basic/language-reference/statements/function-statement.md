---
title: Оператор Function
ms.date: 05/12/2018
f1_keywords:
- vb.Function
helpviewer_keywords:
- procedures [Visual Basic], creating
- Function procedures [Visual Basic], Function statement syntax
- functions [Visual Basic], function procedures
- ParamArray keyword [Visual Basic], Function statements
- Private keyword [Visual Basic], Function statements
- declarations [Visual Basic], procedures
- procedures [Visual Basic], declaration
- Public keyword [Visual Basic], in Function statement
- ByVal keyword [Visual Basic], Function statements
- procedures [Visual Basic], recursive
- Implements keyword [Visual Basic], Function statements
- procedures [Visual Basic], returning values
- Exit statement [Visual Basic], in Function procedures
- recursive procedures
- As keyword [Visual Basic], in Function statement
- Optional keyword [Visual Basic], Function statements
- Function statement [Visual Basic]
- Visual Basic code, Function procedures
- procedures [Visual Basic], function
- ByRef keyword [Visual Basic], Function statements
- Friend keyword [Visual Basic], Function statements
- End keyword [Visual Basic], Function statements
- Handles keyword [Visual Basic], Function statements
ms.assetid: a4497077-0f46-4ede-a27f-9e8670df52b9
ms.openlocfilehash: 49cf4fead2c5594b7ac6815f82fea0dc995ea436
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404632"
---
# <a name="function-statement-visual-basic"></a><span data-ttu-id="f8721-102">Оператор Function (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f8721-102">Function Statement (Visual Basic)</span></span>

<span data-ttu-id="f8721-103">Объявляет имя, параметры и код, определяющие `Function` процедуру.</span><span class="sxs-lookup"><span data-stu-id="f8721-103">Declares the name, parameters, and code that define a `Function` procedure.</span></span>

## <a name="syntax"></a><span data-ttu-id="f8721-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f8721-104">Syntax</span></span>

```vb
[ <attributelist> ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async | Iterator ]
Function name [ (Of typeparamlist) ] [ (parameterlist) ] [ As returntype ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Function ]
    [ statements ]
End Function
```

## <a name="parts"></a><span data-ttu-id="f8721-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="f8721-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="f8721-106">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f8721-106">Optional.</span></span> <span data-ttu-id="f8721-107">См. [список атрибутов](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="f8721-107">See [Attribute List](attribute-list.md).</span></span>

- `accessmodifier`

  <span data-ttu-id="f8721-108">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f8721-108">Optional.</span></span> <span data-ttu-id="f8721-109">Может принимать следующие значения:</span><span class="sxs-lookup"><span data-stu-id="f8721-109">Can be one of the following:</span></span>

  - [<span data-ttu-id="f8721-110">Открытый</span><span class="sxs-lookup"><span data-stu-id="f8721-110">Public</span></span>](../modifiers/public.md)

  - [<span data-ttu-id="f8721-111">От</span><span class="sxs-lookup"><span data-stu-id="f8721-111">Protected</span></span>](../modifiers/protected.md)

  - [<span data-ttu-id="f8721-112">Объявление</span><span class="sxs-lookup"><span data-stu-id="f8721-112">Friend</span></span>](../modifiers/friend.md)

  - [<span data-ttu-id="f8721-113">Частное</span><span class="sxs-lookup"><span data-stu-id="f8721-113">Private</span></span>](../modifiers/private.md)

  - [<span data-ttu-id="f8721-114">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="f8721-114">Protected Friend</span></span>](../modifiers/protected-friend.md)

  - [<span data-ttu-id="f8721-115">Частный защищенный</span><span class="sxs-lookup"><span data-stu-id="f8721-115">Private Protected</span></span>](../modifiers/private-protected.md)

  <span data-ttu-id="f8721-116">См. раздел [уровни доступа в Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="f8721-116">See [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `proceduremodifiers`

  <span data-ttu-id="f8721-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f8721-117">Optional.</span></span> <span data-ttu-id="f8721-118">Может принимать следующие значения:</span><span class="sxs-lookup"><span data-stu-id="f8721-118">Can be one of the following:</span></span>

  - [<span data-ttu-id="f8721-119">Перегрузки</span><span class="sxs-lookup"><span data-stu-id="f8721-119">Overloads</span></span>](../modifiers/overloads.md)

  - [<span data-ttu-id="f8721-120">Переопределения</span><span class="sxs-lookup"><span data-stu-id="f8721-120">Overrides</span></span>](../modifiers/overrides.md)

  - [<span data-ttu-id="f8721-121">Overridable</span><span class="sxs-lookup"><span data-stu-id="f8721-121">Overridable</span></span>](../modifiers/overridable.md)

  - [<span data-ttu-id="f8721-122">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="f8721-122">NotOverridable</span></span>](../modifiers/notoverridable.md)

  - [<span data-ttu-id="f8721-123">MustOverride</span><span class="sxs-lookup"><span data-stu-id="f8721-123">MustOverride</span></span>](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  <span data-ttu-id="f8721-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f8721-124">Optional.</span></span> <span data-ttu-id="f8721-125">См. раздел [Shared](../modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="f8721-125">See [Shared](../modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="f8721-126">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f8721-126">Optional.</span></span> <span data-ttu-id="f8721-127">См. раздел [Shadows](../modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="f8721-127">See [Shadows](../modifiers/shadows.md).</span></span>

- `Async`

  <span data-ttu-id="f8721-128">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f8721-128">Optional.</span></span> <span data-ttu-id="f8721-129">См. статью [Async](../modifiers/async.md).</span><span class="sxs-lookup"><span data-stu-id="f8721-129">See [Async](../modifiers/async.md).</span></span>

- `Iterator`

  <span data-ttu-id="f8721-130">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f8721-130">Optional.</span></span> <span data-ttu-id="f8721-131">См. [итератор](../modifiers/iterator.md).</span><span class="sxs-lookup"><span data-stu-id="f8721-131">See [Iterator](../modifiers/iterator.md).</span></span>

- `name`

  <span data-ttu-id="f8721-132">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="f8721-132">Required.</span></span> <span data-ttu-id="f8721-133">Имя процедуры.</span><span class="sxs-lookup"><span data-stu-id="f8721-133">Name of the procedure.</span></span> <span data-ttu-id="f8721-134">См. раздел [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="f8721-134">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

- `typeparamlist`

  <span data-ttu-id="f8721-135">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f8721-135">Optional.</span></span> <span data-ttu-id="f8721-136">Список параметров типа для универсальной процедуры.</span><span class="sxs-lookup"><span data-stu-id="f8721-136">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="f8721-137">См. [список типов](type-list.md).</span><span class="sxs-lookup"><span data-stu-id="f8721-137">See [Type List](type-list.md).</span></span>

- `parameterlist`

  <span data-ttu-id="f8721-138">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f8721-138">Optional.</span></span> <span data-ttu-id="f8721-139">Список имен локальных переменных, представляющих параметры этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="f8721-139">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="f8721-140">См. [список параметров](parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="f8721-140">See [Parameter List](parameter-list.md).</span></span>

- `returntype`

  <span data-ttu-id="f8721-141">Обязательный `Option Strict` , если имеет значение `On` .</span><span class="sxs-lookup"><span data-stu-id="f8721-141">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="f8721-142">Тип данных значения, возвращаемого этой процедурой.</span><span class="sxs-lookup"><span data-stu-id="f8721-142">Data type of the value returned by this procedure.</span></span>

- `Implements`

  <span data-ttu-id="f8721-143">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f8721-143">Optional.</span></span> <span data-ttu-id="f8721-144">Указывает, что эта процедура реализует одну или несколько `Function` процедур, каждая из которых определена в интерфейсе, реализованном классом или структурой этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="f8721-144">Indicates that this procedure implements one or more `Function` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="f8721-145">См. [инструкцию Implements](implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f8721-145">See [Implements Statement](implements-statement.md).</span></span>

- `implementslist`

  <span data-ttu-id="f8721-146">Является обязательным, если предоставлен параметр `Implements`.</span><span class="sxs-lookup"><span data-stu-id="f8721-146">Required if `Implements` is supplied.</span></span> <span data-ttu-id="f8721-147">Список реализуемых процедур `Function`.</span><span class="sxs-lookup"><span data-stu-id="f8721-147">List of `Function` procedures being implemented.</span></span>

  `implementedprocedure [ , implementedprocedure ... ]`

  <span data-ttu-id="f8721-148">Каждый элемент `implementedprocedure` имеет перечисленные ниже синтаксис и компоненты.</span><span class="sxs-lookup"><span data-stu-id="f8721-148">Each `implementedprocedure` has the following syntax and parts:</span></span>

  `interface.definedname`

  |<span data-ttu-id="f8721-149">Часть</span><span class="sxs-lookup"><span data-stu-id="f8721-149">Part</span></span>|<span data-ttu-id="f8721-150">Описание</span><span class="sxs-lookup"><span data-stu-id="f8721-150">Description</span></span>|
  |---|---|
  |`interface`|<span data-ttu-id="f8721-151">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="f8721-151">Required.</span></span> <span data-ttu-id="f8721-152">Имя интерфейса, реализованного классом или структурой, содержащейся в этой процедуре.</span><span class="sxs-lookup"><span data-stu-id="f8721-152">Name of an interface implemented by this procedure's containing class or structure.</span></span>|
  |`definedname`|<span data-ttu-id="f8721-153">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="f8721-153">Required.</span></span> <span data-ttu-id="f8721-154">Имя, под которым процедура определена в `interface`.</span><span class="sxs-lookup"><span data-stu-id="f8721-154">Name by which the procedure is defined in `interface`.</span></span>|

- `Handles`

  <span data-ttu-id="f8721-155">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f8721-155">Optional.</span></span> <span data-ttu-id="f8721-156">Указывает, что эта процедура может управлять одним или несколькими конкретными событиями.</span><span class="sxs-lookup"><span data-stu-id="f8721-156">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="f8721-157">См. раздел [Handles](handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="f8721-157">See [Handles](handles-clause.md).</span></span>

- `eventlist`

  <span data-ttu-id="f8721-158">Является обязательным, если предоставлен параметр `Handles`.</span><span class="sxs-lookup"><span data-stu-id="f8721-158">Required if `Handles` is supplied.</span></span> <span data-ttu-id="f8721-159">Список событий, обрабатываемых этой процедурой.</span><span class="sxs-lookup"><span data-stu-id="f8721-159">List of events this procedure handles.</span></span>

  `eventspecifier [ , eventspecifier ... ]`

  <span data-ttu-id="f8721-160">Каждый элемент `eventspecifier` имеет перечисленные ниже синтаксис и компоненты.</span><span class="sxs-lookup"><span data-stu-id="f8721-160">Each `eventspecifier` has the following syntax and parts:</span></span>

  `eventvariable.event`

  |<span data-ttu-id="f8721-161">Часть</span><span class="sxs-lookup"><span data-stu-id="f8721-161">Part</span></span>|<span data-ttu-id="f8721-162">Описание</span><span class="sxs-lookup"><span data-stu-id="f8721-162">Description</span></span>|
  |---|---|
  |`eventvariable`|<span data-ttu-id="f8721-163">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="f8721-163">Required.</span></span> <span data-ttu-id="f8721-164">Объектная переменная, объявленная с типом данных класса или структуры, которая вызывает событие.</span><span class="sxs-lookup"><span data-stu-id="f8721-164">Object variable declared with the data type of the class or structure that raises the event.</span></span>|
  |`event`|<span data-ttu-id="f8721-165">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="f8721-165">Required.</span></span> <span data-ttu-id="f8721-166">Имя события, обрабатываемого этой процедурой.</span><span class="sxs-lookup"><span data-stu-id="f8721-166">Name of the event this procedure handles.</span></span>|

- `statements`

  <span data-ttu-id="f8721-167">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f8721-167">Optional.</span></span> <span data-ttu-id="f8721-168">Блок инструкций для выполнения в рамках этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="f8721-168">Block of statements to be executed within this procedure.</span></span>

- `End Function`

  <span data-ttu-id="f8721-169">Завершает определение этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="f8721-169">Terminates the definition of this procedure.</span></span>

## <a name="remarks"></a><span data-ttu-id="f8721-170">Комментарии</span><span class="sxs-lookup"><span data-stu-id="f8721-170">Remarks</span></span>

<span data-ttu-id="f8721-171">Весь исполняемый код должен находиться внутри процедуры.</span><span class="sxs-lookup"><span data-stu-id="f8721-171">All executable code must be inside a procedure.</span></span> <span data-ttu-id="f8721-172">Каждая процедура, в свою очередь, объявляется в классе, структуре или модуле, который называется содержащим классом, структурой или модулем.</span><span class="sxs-lookup"><span data-stu-id="f8721-172">Each procedure, in turn, is declared within a class, a structure, or a module that is referred to as the containing class, structure, or module.</span></span>

<span data-ttu-id="f8721-173">Чтобы вернуть значение в вызывающий код, используйте `Function` процедуру; в противном случае используйте `Sub` процедуру.</span><span class="sxs-lookup"><span data-stu-id="f8721-173">To return a value to the calling code, use a `Function` procedure; otherwise, use a `Sub` procedure.</span></span>

## <a name="defining-a-function"></a><span data-ttu-id="f8721-174">Определение функции</span><span class="sxs-lookup"><span data-stu-id="f8721-174">Defining a Function</span></span>

<span data-ttu-id="f8721-175">Процедуру можно определить `Function` только на уровне модуля.</span><span class="sxs-lookup"><span data-stu-id="f8721-175">You can define a `Function` procedure only at the module level.</span></span> <span data-ttu-id="f8721-176">Таким образом, контекст объявления для функции должен быть классом, структурой, модулем или интерфейсом и не может быть исходным файлом, пространством имен, процедурой или блоком.</span><span class="sxs-lookup"><span data-stu-id="f8721-176">Therefore, the declaration context for a function must be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="f8721-177">Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="f8721-177">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="f8721-178">`Function`процедуры по умолчанию имеют открытый доступ.</span><span class="sxs-lookup"><span data-stu-id="f8721-178">`Function` procedures default to public access.</span></span> <span data-ttu-id="f8721-179">Уровни доступа можно изменить с помощью модификаторов доступа.</span><span class="sxs-lookup"><span data-stu-id="f8721-179">You can adjust their access levels with the access modifiers.</span></span>

<span data-ttu-id="f8721-180">`Function`Процедура может объявлять тип данных возвращаемого процедурой значения.</span><span class="sxs-lookup"><span data-stu-id="f8721-180">A `Function` procedure can declare the data type of the value that the procedure returns.</span></span> <span data-ttu-id="f8721-181">Можно указать любой тип данных или имя перечисления, структуру, класс или интерфейс.</span><span class="sxs-lookup"><span data-stu-id="f8721-181">You can specify any data type or the name of an enumeration, a structure, a class, or an interface.</span></span> <span data-ttu-id="f8721-182">Если параметр не указан `returntype` , процедура возвращает `Object` .</span><span class="sxs-lookup"><span data-stu-id="f8721-182">If you don't specify the `returntype` parameter, the procedure returns `Object`.</span></span>

<span data-ttu-id="f8721-183">Если в этой процедуре используется `Implements` ключевое слово, содержащий класс или структуру также должны иметь `Implements` оператор, который сразу следует `Class` за `Structure` оператором или.</span><span class="sxs-lookup"><span data-stu-id="f8721-183">If this procedure uses the `Implements` keyword, the containing class or structure must also have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="f8721-184">`Implements`Инструкция должна включать каждый интерфейс, указанный в `implementslist` .</span><span class="sxs-lookup"><span data-stu-id="f8721-184">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="f8721-185">Однако имя, по которому интерфейс определяет `Function` (в `definedname` ), не обязательно должно совпадать с именем этой процедуры (в `name` ).</span><span class="sxs-lookup"><span data-stu-id="f8721-185">However, the name by which an interface defines the `Function` (in `definedname`) doesn't need to match the name of this procedure (in `name`).</span></span>

> [!NOTE]
> <span data-ttu-id="f8721-186">Лямбда-выражения можно использовать для определения выражений функций встроенным.</span><span class="sxs-lookup"><span data-stu-id="f8721-186">You can use lambda expressions to define function expressions inline.</span></span> <span data-ttu-id="f8721-187">Дополнительные сведения см. в разделе [выражение функции](../operators/function-expression.md) и [лямбда-выражения](../../programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="f8721-187">For more information, see [Function Expression](../operators/function-expression.md) and [Lambda Expressions](../../programming-guide/language-features/procedures/lambda-expressions.md).</span></span>

## <a name="returning-from-a-function"></a><span data-ttu-id="f8721-188">Возврат из функции</span><span class="sxs-lookup"><span data-stu-id="f8721-188">Returning from a Function</span></span>

<span data-ttu-id="f8721-189">Когда `Function` процедура возвращается в вызывающий код, выполнение переходит к инструкции, следующей за инструкцией, вызвавшей процедуру.</span><span class="sxs-lookup"><span data-stu-id="f8721-189">When the `Function` procedure returns to the calling code, execution continues with the statement that follows the statement that called the procedure.</span></span>

<span data-ttu-id="f8721-190">Чтобы вернуть значение из функции, можно либо присвоить значение имени функции, либо включить его в `Return` инструкцию.</span><span class="sxs-lookup"><span data-stu-id="f8721-190">To return a value from a function, you can either assign the value to the function name or include it in a `Return` statement.</span></span>

<span data-ttu-id="f8721-191">`Return`Оператор одновременно назначает возвращаемое значение и завершает функцию, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f8721-191">The `Return` statement simultaneously assigns the return value and exits the function, as the following example shows.</span></span>

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

<span data-ttu-id="f8721-192">В следующем примере возвращаемое значение присваивается имени функции `myFunction` , а затем используется `Exit Function` оператор для возврата.</span><span class="sxs-lookup"><span data-stu-id="f8721-192">The following example assigns the return value to the function name `myFunction` and then uses the `Exit Function` statement to return.</span></span>

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

<span data-ttu-id="f8721-193">`Exit Function`Операторы и `Return` вызывают немедленный выход из `Function` процедуры.</span><span class="sxs-lookup"><span data-stu-id="f8721-193">The `Exit Function` and `Return` statements cause an immediate exit from a `Function` procedure.</span></span> <span data-ttu-id="f8721-194">Любое количество `Exit Function` инструкций и `Return` может использоваться в любом месте процедуры, и можно смешивать `Exit Function` `Return` операторы и.</span><span class="sxs-lookup"><span data-stu-id="f8721-194">Any number of `Exit Function` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Function` and `Return` statements.</span></span>

<span data-ttu-id="f8721-195">Если вы используете `Exit Function` без присвоения значения `name` , процедура возвращает значение по умолчанию для типа данных, указанного в параметре `returntype` .</span><span class="sxs-lookup"><span data-stu-id="f8721-195">If you use `Exit Function` without assigning a value to `name`, the procedure returns the default value for the data type that's specified in `returntype`.</span></span> <span data-ttu-id="f8721-196">Если параметр `returntype` не указан, процедура возвращает `Nothing` значение, которое является значением по умолчанию для `Object` .</span><span class="sxs-lookup"><span data-stu-id="f8721-196">If `returntype` isn't specified, the procedure returns `Nothing`, which is the default value for `Object`.</span></span>

## <a name="calling-a-function"></a><span data-ttu-id="f8721-197">Вызов функции</span><span class="sxs-lookup"><span data-stu-id="f8721-197">Calling a Function</span></span>

<span data-ttu-id="f8721-198">Процедура вызывается с `Function` использованием имени процедуры, за которым следует список аргументов в выражении в круглых скобках.</span><span class="sxs-lookup"><span data-stu-id="f8721-198">You call a `Function` procedure by using the procedure name, followed by the argument list in parentheses, in an expression.</span></span> <span data-ttu-id="f8721-199">Скобки можно опустить, только если вы не предоставляете никаких аргументов.</span><span class="sxs-lookup"><span data-stu-id="f8721-199">You can omit the parentheses only if you aren't supplying any arguments.</span></span> <span data-ttu-id="f8721-200">Однако код является более удобочитаемым, если всегда включать круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="f8721-200">However, your code is more readable if you always include the parentheses.</span></span>

<span data-ttu-id="f8721-201">Процедура вызывается `Function` так же, как и любая библиотечная функция, такая как `Sqrt` , `Cos` или `ChrW` .</span><span class="sxs-lookup"><span data-stu-id="f8721-201">You call a `Function` procedure the same way that you call any library function such as `Sqrt`, `Cos`, or `ChrW`.</span></span>

<span data-ttu-id="f8721-202">Функцию можно также вызвать с помощью `Call` ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="f8721-202">You can also call a function by using the `Call` keyword.</span></span> <span data-ttu-id="f8721-203">В этом случае возвращаемое значение игнорируется.</span><span class="sxs-lookup"><span data-stu-id="f8721-203">In that case, the return value is ignored.</span></span> <span data-ttu-id="f8721-204">`Call`В большинстве случаев использование ключевого слова не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f8721-204">Use of the `Call` keyword isn't recommended in most cases.</span></span> <span data-ttu-id="f8721-205">Дополнительные сведения см. в разделе [оператор Call](call-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f8721-205">For more information, see [Call Statement](call-statement.md).</span></span>

<span data-ttu-id="f8721-206">Visual Basic иногда переупорядочивает арифметические выражения для повышения внутренней эффективности.</span><span class="sxs-lookup"><span data-stu-id="f8721-206">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="f8721-207">По этой причине не следует использовать `Function` процедуру в арифметическом выражении, если функция изменяет значение переменных в том же выражении.</span><span class="sxs-lookup"><span data-stu-id="f8721-207">For that reason, you shouldn't use a `Function` procedure in an arithmetic expression when the function changes the value of variables in the same expression.</span></span>

## <a name="async-functions"></a><span data-ttu-id="f8721-208">Асинхронные функции</span><span class="sxs-lookup"><span data-stu-id="f8721-208">Async Functions</span></span>

<span data-ttu-id="f8721-209">Функция *Async* позволяет вызывать асинхронные функции без использования явных обратных вызовов или вручную разделять код между несколькими функциями или лямбда-выражениями.</span><span class="sxs-lookup"><span data-stu-id="f8721-209">The *Async* feature allows you to invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>

<span data-ttu-id="f8721-210">Если вы помечаете функцию модификатором [Async](../modifiers/async.md) , то можете использовать оператор [await](../operators/await-operator.md) в функции.</span><span class="sxs-lookup"><span data-stu-id="f8721-210">If you mark a function with the [Async](../modifiers/async.md) modifier, you can use the [Await](../operators/await-operator.md) operator in the function.</span></span> <span data-ttu-id="f8721-211">Когда управление достигает `Await` выражения в `Async` функции, управление возвращается вызывающему объекту, и ход выполнения функции приостанавливается до тех пор, пока не завершится ожидаемая задача.</span><span class="sxs-lookup"><span data-stu-id="f8721-211">When control reaches an `Await` expression in the `Async` function, control returns to the caller, and progress in the function is suspended until the awaited task completes.</span></span> <span data-ttu-id="f8721-212">После завершения задачи выполнение может возобновиться в функции.</span><span class="sxs-lookup"><span data-stu-id="f8721-212">When the task is complete, execution can resume in the function.</span></span>

> [!NOTE]
> <span data-ttu-id="f8721-213">`Async`Процедура возвращается к вызывающему объекту, когда он встречает первый ожидающий объект, который еще не завершен, или на конец процедуры, в зависимости от того, что `Async` происходит раньше.</span><span class="sxs-lookup"><span data-stu-id="f8721-213">An `Async` procedure returns to the caller when either it encounters the first awaited object that’s not yet complete, or it gets to the end of the `Async` procedure, whichever occurs first.</span></span>

<span data-ttu-id="f8721-214">`Async`Функция может иметь тип возвращаемого значения <xref:System.Threading.Tasks.Task%601> или <xref:System.Threading.Tasks.Task> .</span><span class="sxs-lookup"><span data-stu-id="f8721-214">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="f8721-215">Ниже приведен пример `Async` функции, имеющей тип возвращаемого значения <xref:System.Threading.Tasks.Task%601> .</span><span class="sxs-lookup"><span data-stu-id="f8721-215">An example of an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601> is provided below.</span></span>

<span data-ttu-id="f8721-216">`Async`Функция не может объявлять никакие параметры [ByRef](../modifiers/byref.md) .</span><span class="sxs-lookup"><span data-stu-id="f8721-216">An `Async` function cannot declare any [ByRef](../modifiers/byref.md) parameters.</span></span>

<span data-ttu-id="f8721-217">[Оператор](sub-statement.md) подвыражения также может быть помечен `Async` модификатором.</span><span class="sxs-lookup"><span data-stu-id="f8721-217">A [Sub Statement](sub-statement.md) can also be marked with the `Async` modifier.</span></span> <span data-ttu-id="f8721-218">Это в основном используется для обработчиков событий, где значение не может быть возвращено.</span><span class="sxs-lookup"><span data-stu-id="f8721-218">This is primarily used for event handlers, where a value cannot be returned.</span></span> <span data-ttu-id="f8721-219">`Async` `Sub` Процедуру нельзя ожидать, и вызывающая `Async` `Sub` процедура не может перехватывать исключения, создаваемые `Sub` процедурой.</span><span class="sxs-lookup"><span data-stu-id="f8721-219">An `Async` `Sub` procedure can't be awaited, and the caller of an `Async` `Sub` procedure can't catch exceptions that are thrown by the `Sub` procedure.</span></span>

<span data-ttu-id="f8721-220">Дополнительные сведения о `Async` функциях см. в разделе [Асинхронное программирование с использованием Async и await](../../programming-guide/concepts/async/index.md), [поток управления в асинхронных программах](../../programming-guide/concepts/async/control-flow-in-async-programs.md)и [асинхронные типы возвращаемых](../../programming-guide/concepts/async/async-return-types.md)данных.</span><span class="sxs-lookup"><span data-stu-id="f8721-220">For more information about `Async` functions, see [Asynchronous Programming with Async and Await](../../programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../programming-guide/concepts/async/async-return-types.md).</span></span>

## <a name="iterator-functions"></a><span data-ttu-id="f8721-221">Функции итератора</span><span class="sxs-lookup"><span data-stu-id="f8721-221">Iterator Functions</span></span>

<span data-ttu-id="f8721-222">Функция *итератора* выполняет настраиваемую итерацию для коллекции, например списка или массива.</span><span class="sxs-lookup"><span data-stu-id="f8721-222">An *iterator* function performs a custom iteration over a collection, such as a list or array.</span></span> <span data-ttu-id="f8721-223">Функция итератора использует оператор [yield](yield-statement.md) для возвращения каждого элемента по одному за раз.</span><span class="sxs-lookup"><span data-stu-id="f8721-223">An iterator function uses the [Yield](yield-statement.md) statement to return each element one at a time.</span></span> <span data-ttu-id="f8721-224">При достижении оператора [yield](yield-statement.md) текущее расположение в коде запоминается.</span><span class="sxs-lookup"><span data-stu-id="f8721-224">When a [Yield](yield-statement.md) statement is reached, the current location in code is remembered.</span></span> <span data-ttu-id="f8721-225">При следующем вызове функции итератора выполнение возобновляется с этого места.</span><span class="sxs-lookup"><span data-stu-id="f8721-225">Execution is restarted from that location the next time the iterator function is called.</span></span>

<span data-ttu-id="f8721-226">Итератор вызывается из клиентского кода с помощью метода [For Each... Следующий](for-each-next-statement.md) оператор.</span><span class="sxs-lookup"><span data-stu-id="f8721-226">You call an iterator from client code by using a [For Each…Next](for-each-next-statement.md) statement.</span></span>

<span data-ttu-id="f8721-227">Тип возвращаемого значения функции итератора может быть <xref:System.Collections.IEnumerable> , <xref:System.Collections.Generic.IEnumerable%601> , <xref:System.Collections.IEnumerator> или <xref:System.Collections.Generic.IEnumerator%601> .</span><span class="sxs-lookup"><span data-stu-id="f8721-227">The return type of an iterator function can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>

<span data-ttu-id="f8721-228">Дополнительные сведения см. в разделе [итераторы](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="f8721-228">For more information, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>

## <a name="example"></a><span data-ttu-id="f8721-229">Пример</span><span class="sxs-lookup"><span data-stu-id="f8721-229">Example</span></span>

<span data-ttu-id="f8721-230">В следующем примере оператор используется `Function` для объявления имени, параметров и кода, образующих тело `Function` процедуры.</span><span class="sxs-lookup"><span data-stu-id="f8721-230">The following example uses the `Function` statement to declare the name, parameters, and code that form the body of a `Function` procedure.</span></span> <span data-ttu-id="f8721-231">`ParamArray`Модификатор позволяет функции принимать переменное число аргументов.</span><span class="sxs-lookup"><span data-stu-id="f8721-231">The `ParamArray` modifier enables the function to accept a variable number of arguments.</span></span>

[!code-vb[VbVbalrStatements#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#25)]

## <a name="example"></a><span data-ttu-id="f8721-232">Пример</span><span class="sxs-lookup"><span data-stu-id="f8721-232">Example</span></span>

<span data-ttu-id="f8721-233">В следующем примере вызывается функция, объявленная в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="f8721-233">The following example invokes the function declared in the preceding example.</span></span>

[!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]

## <a name="example"></a><span data-ttu-id="f8721-234">Пример</span><span class="sxs-lookup"><span data-stu-id="f8721-234">Example</span></span>

<span data-ttu-id="f8721-235">В следующем примере `DelayAsync` — это, `Async` `Function` имеющий тип возвращаемого значения <xref:System.Threading.Tasks.Task%601> .</span><span class="sxs-lookup"><span data-stu-id="f8721-235">In the following example, `DelayAsync` is an `Async` `Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="f8721-236">`DelayAsync` имеет инструкцию `Return` , которая возвращает целое число.</span><span class="sxs-lookup"><span data-stu-id="f8721-236">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="f8721-237">Поэтому объявление функции `DelayAsync` должно иметь тип возвращаемого значения `Task(Of Integer)` .</span><span class="sxs-lookup"><span data-stu-id="f8721-237">Therefore the function declaration of `DelayAsync` needs to have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="f8721-238">Так как тип возвращаемого значения — `Task(Of Integer)` , вычисление `Await` выражения в `DoSomethingAsync` создает целое число.</span><span class="sxs-lookup"><span data-stu-id="f8721-238">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer.</span></span> <span data-ttu-id="f8721-239">Это продемонстрировано в этой инструкции: `Dim result As Integer = Await delayTask` .</span><span class="sxs-lookup"><span data-stu-id="f8721-239">This is demonstrated in this statement: `Dim result As Integer = Await delayTask`.</span></span>

<span data-ttu-id="f8721-240">`startButton_Click`Процедура является примером `Async Sub` процедуры.</span><span class="sxs-lookup"><span data-stu-id="f8721-240">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="f8721-241">Поскольку `DoSomethingAsync` является `Async` функцией, задача для вызова `DoSomethingAsync` должна быть ожидаемой, как показано в следующей инструкции: `Await DoSomethingAsync()` .</span><span class="sxs-lookup"><span data-stu-id="f8721-241">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement demonstrates: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="f8721-242">`startButton_Click` `Sub` Процедура должна быть определена с `Async` модификатором, так как содержит `Await` выражение.</span><span class="sxs-lookup"><span data-stu-id="f8721-242">The `startButton_Click` `Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="f8721-243">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f8721-243">See also</span></span>

- [<span data-ttu-id="f8721-244">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="f8721-244">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="f8721-245">Процедуры функций</span><span class="sxs-lookup"><span data-stu-id="f8721-245">Function Procedures</span></span>](../../programming-guide/language-features/procedures/function-procedures.md)
- [<span data-ttu-id="f8721-246">Список параметров</span><span class="sxs-lookup"><span data-stu-id="f8721-246">Parameter List</span></span>](parameter-list.md)
- [<span data-ttu-id="f8721-247">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="f8721-247">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="f8721-248">Оператор Call</span><span class="sxs-lookup"><span data-stu-id="f8721-248">Call Statement</span></span>](call-statement.md)
- [<span data-ttu-id="f8721-249">Окна</span><span class="sxs-lookup"><span data-stu-id="f8721-249">Of</span></span>](of-clause.md)
- [<span data-ttu-id="f8721-250">Массивы параметров</span><span class="sxs-lookup"><span data-stu-id="f8721-250">Parameter Arrays</span></span>](../../programming-guide/language-features/procedures/parameter-arrays.md)
- [<span data-ttu-id="f8721-251">Практическое руководство. Использование универсального класса</span><span class="sxs-lookup"><span data-stu-id="f8721-251">How to: Use a Generic Class</span></span>](../../programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="f8721-252">Рекомендации по устранению неполадок</span><span class="sxs-lookup"><span data-stu-id="f8721-252">Troubleshooting Procedures</span></span>](../../programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [<span data-ttu-id="f8721-253">Лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="f8721-253">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="f8721-254">Выражение функции</span><span class="sxs-lookup"><span data-stu-id="f8721-254">Function Expression</span></span>](../operators/function-expression.md)
