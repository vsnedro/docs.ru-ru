---
title: Оператор Sub
ms.date: 05/12/2018
f1_keywords:
- vb.Sub
helpviewer_keywords:
- Public keyword [Visual Basic], Sub statements
- procedures [Visual Basic], creating
- declaring procedures [Visual Basic], Sub statement
- arguments [Visual Basic], Sub procedures
- As keyword [Visual Basic], Sub statements
- Optional keyword [Visual Basic], Sub statements
- declarations [Visual Basic], procedures
- Sub keyword [Visual Basic]
- Handles keyword [Visual Basic], Sub statements
- Protected Friend keyword [Visual Basic]
- ParamArray keyword [Visual Basic], Sub statements
- Implements keyword [Visual Basic], Sub statements
- Sub statement [Visual Basic]
- subroutines
- ByRef keyword [Visual Basic], Sub statements
- Sub procedures [Visual Basic], Sub statement
- recursive procedures
- Private keyword [Visual Basic], Sub statements
- Friend keyword [Visual Basic], Sub statements
- Exit statement [Visual Basic], Sub statements
- procedures [Visual Basic], Sub
- End keyword [Visual Basic], Sub statements
- ByVal keyword [Visual Basic], Sub statements
- Visual Basic code, Sub procedures
ms.assetid: e347d700-d06c-405b-b302-e9b1edb57dfc
ms.openlocfilehash: e50b79c31c92ac116d6c82bcececba3340894d74
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404178"
---
# <a name="sub-statement-visual-basic"></a><span data-ttu-id="ed7a9-102">Оператор Sub (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed7a9-102">Sub Statement (Visual Basic)</span></span>

<span data-ttu-id="ed7a9-103">Объявляет имя, параметры и код, определяющие `Sub` процедуру.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-103">Declares the name, parameters, and code that define a `Sub` procedure.</span></span>

## <a name="syntax"></a><span data-ttu-id="ed7a9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ed7a9-104">Syntax</span></span>

```vb
[ <attributelist> ] [ Partial ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async ]
Sub name [ (Of typeparamlist) ] [ (parameterlist) ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Sub ]
    [ statements ]
End Sub
```

## <a name="parts"></a><span data-ttu-id="ed7a9-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="ed7a9-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="ed7a9-106">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-106">Optional.</span></span> <span data-ttu-id="ed7a9-107">См. [список атрибутов](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="ed7a9-107">See [Attribute List](attribute-list.md).</span></span>

- `Partial`

  <span data-ttu-id="ed7a9-108">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-108">Optional.</span></span> <span data-ttu-id="ed7a9-109">Указывает определение разделяемого метода.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-109">Indicates definition of a partial method.</span></span> <span data-ttu-id="ed7a9-110">См. раздел [разделяемые методы](../../programming-guide/language-features/procedures/partial-methods.md).</span><span class="sxs-lookup"><span data-stu-id="ed7a9-110">See [Partial Methods](../../programming-guide/language-features/procedures/partial-methods.md).</span></span>

- `accessmodifier`

  <span data-ttu-id="ed7a9-111">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-111">Optional.</span></span> <span data-ttu-id="ed7a9-112">Может принимать следующие значения:</span><span class="sxs-lookup"><span data-stu-id="ed7a9-112">Can be one of the following:</span></span>

  - [<span data-ttu-id="ed7a9-113">Открытый</span><span class="sxs-lookup"><span data-stu-id="ed7a9-113">Public</span></span>](../modifiers/public.md)

  - [<span data-ttu-id="ed7a9-114">От</span><span class="sxs-lookup"><span data-stu-id="ed7a9-114">Protected</span></span>](../modifiers/protected.md)

  - [<span data-ttu-id="ed7a9-115">Объявление</span><span class="sxs-lookup"><span data-stu-id="ed7a9-115">Friend</span></span>](../modifiers/friend.md)

  - [<span data-ttu-id="ed7a9-116">Частное</span><span class="sxs-lookup"><span data-stu-id="ed7a9-116">Private</span></span>](../modifiers/private.md)

  - [<span data-ttu-id="ed7a9-117">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="ed7a9-117">Protected Friend</span></span>](../modifiers/protected-friend.md)

  - [<span data-ttu-id="ed7a9-118">Частный защищенный</span><span class="sxs-lookup"><span data-stu-id="ed7a9-118">Private Protected</span></span>](../modifiers/private-protected.md)

  <span data-ttu-id="ed7a9-119">См. раздел [уровни доступа в Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="ed7a9-119">See [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `proceduremodifiers`

  <span data-ttu-id="ed7a9-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-120">Optional.</span></span> <span data-ttu-id="ed7a9-121">Может принимать следующие значения:</span><span class="sxs-lookup"><span data-stu-id="ed7a9-121">Can be one of the following:</span></span>

  - [<span data-ttu-id="ed7a9-122">Перегрузки</span><span class="sxs-lookup"><span data-stu-id="ed7a9-122">Overloads</span></span>](../modifiers/overloads.md)

  - [<span data-ttu-id="ed7a9-123">Переопределения</span><span class="sxs-lookup"><span data-stu-id="ed7a9-123">Overrides</span></span>](../modifiers/overrides.md)

  - [<span data-ttu-id="ed7a9-124">Overridable</span><span class="sxs-lookup"><span data-stu-id="ed7a9-124">Overridable</span></span>](../modifiers/overridable.md)

  - [<span data-ttu-id="ed7a9-125">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="ed7a9-125">NotOverridable</span></span>](../modifiers/notoverridable.md)

  - [<span data-ttu-id="ed7a9-126">MustOverride</span><span class="sxs-lookup"><span data-stu-id="ed7a9-126">MustOverride</span></span>](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  <span data-ttu-id="ed7a9-127">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-127">Optional.</span></span> <span data-ttu-id="ed7a9-128">См. раздел [Shared](../modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="ed7a9-128">See [Shared](../modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="ed7a9-129">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-129">Optional.</span></span> <span data-ttu-id="ed7a9-130">См. раздел [Shadows](../modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="ed7a9-130">See [Shadows](../modifiers/shadows.md).</span></span>

- `Async`

  <span data-ttu-id="ed7a9-131">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-131">Optional.</span></span> <span data-ttu-id="ed7a9-132">См. статью [Async](../modifiers/async.md).</span><span class="sxs-lookup"><span data-stu-id="ed7a9-132">See [Async](../modifiers/async.md).</span></span>

- `name`

  <span data-ttu-id="ed7a9-133">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-133">Required.</span></span> <span data-ttu-id="ed7a9-134">Имя процедуры.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-134">Name of the procedure.</span></span> <span data-ttu-id="ed7a9-135">См. раздел [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="ed7a9-135">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span> <span data-ttu-id="ed7a9-136">Чтобы создать процедуру конструктора для класса, задайте в качестве имени `Sub` процедуры `New` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-136">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="ed7a9-137">Дополнительные сведения см. в разделе [время существования объекта: как создаются и уничтожаются объекты](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span><span class="sxs-lookup"><span data-stu-id="ed7a9-137">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>

- `typeparamlist`

  <span data-ttu-id="ed7a9-138">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-138">Optional.</span></span> <span data-ttu-id="ed7a9-139">Список параметров типа для универсальной процедуры.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-139">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="ed7a9-140">См. [список типов](type-list.md).</span><span class="sxs-lookup"><span data-stu-id="ed7a9-140">See [Type List](type-list.md).</span></span>

- `parameterlist`

  <span data-ttu-id="ed7a9-141">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-141">Optional.</span></span> <span data-ttu-id="ed7a9-142">Список имен локальных переменных, представляющих параметры этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-142">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="ed7a9-143">См. [список параметров](parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="ed7a9-143">See [Parameter List](parameter-list.md).</span></span>

- `Implements`

  <span data-ttu-id="ed7a9-144">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-144">Optional.</span></span> <span data-ttu-id="ed7a9-145">Указывает, что эта процедура реализует одну или несколько `Sub` процедур, каждая из которых определена в интерфейсе, реализованном классом или структурой этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-145">Indicates that this procedure implements one or more `Sub` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="ed7a9-146">См. [инструкцию Implements](implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ed7a9-146">See [Implements Statement](implements-statement.md).</span></span>

- `implementslist`

  <span data-ttu-id="ed7a9-147">Является обязательным, если предоставлен параметр `Implements`.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-147">Required if `Implements` is supplied.</span></span> <span data-ttu-id="ed7a9-148">Список реализуемых процедур `Sub`.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-148">List of `Sub` procedures being implemented.</span></span>

  `implementedprocedure [ , implementedprocedure ... ]`

  <span data-ttu-id="ed7a9-149">Каждый элемент `implementedprocedure` имеет перечисленные ниже синтаксис и компоненты.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-149">Each `implementedprocedure` has the following syntax and parts:</span></span>

  `interface.definedname`

  |<span data-ttu-id="ed7a9-150">Часть</span><span class="sxs-lookup"><span data-stu-id="ed7a9-150">Part</span></span>|<span data-ttu-id="ed7a9-151">Описание</span><span class="sxs-lookup"><span data-stu-id="ed7a9-151">Description</span></span>|
  |---|---|
  |`interface`|<span data-ttu-id="ed7a9-152">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-152">Required.</span></span> <span data-ttu-id="ed7a9-153">Имя интерфейса, реализованного классом или структурой, содержащейся в этой процедуре.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-153">Name of an interface implemented by this procedure's containing class or structure.</span></span>|
  |`definedname`|<span data-ttu-id="ed7a9-154">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-154">Required.</span></span> <span data-ttu-id="ed7a9-155">Имя, под которым процедура определена в `interface`.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-155">Name by which the procedure is defined in `interface`.</span></span>|

- `Handles`

  <span data-ttu-id="ed7a9-156">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-156">Optional.</span></span> <span data-ttu-id="ed7a9-157">Указывает, что эта процедура может управлять одним или несколькими конкретными событиями.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-157">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="ed7a9-158">См. раздел [Handles](handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="ed7a9-158">See [Handles](handles-clause.md).</span></span>

- `eventlist`

  <span data-ttu-id="ed7a9-159">Является обязательным, если предоставлен параметр `Handles`.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-159">Required if `Handles` is supplied.</span></span> <span data-ttu-id="ed7a9-160">Список событий, обрабатываемых этой процедурой.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-160">List of events this procedure handles.</span></span>

  `eventspecifier [ , eventspecifier ... ]`

  <span data-ttu-id="ed7a9-161">Каждый элемент `eventspecifier` имеет перечисленные ниже синтаксис и компоненты.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-161">Each `eventspecifier` has the following syntax and parts:</span></span>

  `eventvariable.event`

  |<span data-ttu-id="ed7a9-162">Часть</span><span class="sxs-lookup"><span data-stu-id="ed7a9-162">Part</span></span>|<span data-ttu-id="ed7a9-163">Описание</span><span class="sxs-lookup"><span data-stu-id="ed7a9-163">Description</span></span>|
  |---|---|
  |`eventvariable`|<span data-ttu-id="ed7a9-164">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-164">Required.</span></span> <span data-ttu-id="ed7a9-165">Объектная переменная, объявленная с типом данных класса или структуры, которая вызывает событие.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-165">Object variable declared with the data type of the class or structure that raises the event.</span></span>|
  |`event`|<span data-ttu-id="ed7a9-166">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-166">Required.</span></span> <span data-ttu-id="ed7a9-167">Имя события, обрабатываемого этой процедурой.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-167">Name of the event this procedure handles.</span></span>|

- `statements`

  <span data-ttu-id="ed7a9-168">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-168">Optional.</span></span> <span data-ttu-id="ed7a9-169">Блок инструкций для выполнения в рамках этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-169">Block of statements to run within this procedure.</span></span>

- `End Sub`

  <span data-ttu-id="ed7a9-170">Завершает определение этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-170">Terminates the definition of this procedure.</span></span>

## <a name="remarks"></a><span data-ttu-id="ed7a9-171">Комментарии</span><span class="sxs-lookup"><span data-stu-id="ed7a9-171">Remarks</span></span>

<span data-ttu-id="ed7a9-172">Весь исполняемый код должен находиться внутри процедуры.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-172">All executable code must be inside a procedure.</span></span> <span data-ttu-id="ed7a9-173">Используйте `Sub` процедуру, если не нужно возвращать значение в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-173">Use a `Sub` procedure when you don't want to return a value to the calling code.</span></span> <span data-ttu-id="ed7a9-174">Используйте `Function` процедуру, если требуется вернуть значение.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-174">Use a `Function` procedure when you want to return a value.</span></span>

## <a name="defining-a-sub-procedure"></a><span data-ttu-id="ed7a9-175">Определение подпроцедуры</span><span class="sxs-lookup"><span data-stu-id="ed7a9-175">Defining a Sub Procedure</span></span>

<span data-ttu-id="ed7a9-176">Процедуру можно определить `Sub` только на уровне модуля.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-176">You can define a `Sub` procedure only at the module level.</span></span> <span data-ttu-id="ed7a9-177">Контекст объявления для процедуры, следовательно, должен быть классом, структурой, модулем или интерфейсом и не может быть исходным файлом, пространством имен, процедурой или блоком.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-177">The declaration context for a sub procedure must, therefore, be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="ed7a9-178">Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="ed7a9-178">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="ed7a9-179">`Sub`процедуры по умолчанию имеют открытый доступ.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-179">`Sub` procedures default to public access.</span></span> <span data-ttu-id="ed7a9-180">Уровни доступа можно изменить с помощью модификаторов доступа.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-180">You can adjust their access levels by using the access modifiers.</span></span>

<span data-ttu-id="ed7a9-181">Если в процедуре используется `Implements` ключевое слово, содержащий класс или структуру должны иметь `Implements` оператор, который сразу следует за `Class` `Structure` оператором или.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-181">If the procedure uses the `Implements` keyword, the containing class or structure must have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="ed7a9-182">`Implements`Инструкция должна включать каждый интерфейс, указанный в `implementslist` .</span><span class="sxs-lookup"><span data-stu-id="ed7a9-182">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="ed7a9-183">Однако имя, по которому интерфейс определяет `Sub` (в `definedname` ), не обязательно должен совпадать с именем этой процедуры (в `name` ).</span><span class="sxs-lookup"><span data-stu-id="ed7a9-183">However, the name by which an interface defines the `Sub` (in `definedname`) doesn't have to match the name of this procedure (in `name`).</span></span>

## <a name="returning-from-a-sub-procedure"></a><span data-ttu-id="ed7a9-184">Возврат из подпроцедуры</span><span class="sxs-lookup"><span data-stu-id="ed7a9-184">Returning from a Sub Procedure</span></span>

<span data-ttu-id="ed7a9-185">Когда `Sub` процедура возвращается в вызывающий код, выполнение переходит к инструкции после оператора, вызвавшего ее.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-185">When a `Sub` procedure returns to the calling code, execution continues with the statement after the statement that called it.</span></span>

<span data-ttu-id="ed7a9-186">В следующем примере показан возврат из `Sub` процедуры.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-186">The following example shows a return from a `Sub` procedure.</span></span>

```vb
Sub mySub(ByVal q As String)
    Return
End Sub
```

<span data-ttu-id="ed7a9-187">`Exit Sub`Операторы и `Return` вызывают немедленный выход из `Sub` процедуры.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-187">The `Exit Sub` and `Return` statements cause an immediate exit from a `Sub` procedure.</span></span> <span data-ttu-id="ed7a9-188">Любое количество `Exit Sub` инструкций и `Return` может использоваться в любом месте процедуры, и можно смешивать `Exit Sub` `Return` операторы и.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-188">Any number of `Exit Sub` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Sub` and `Return` statements.</span></span>

## <a name="calling-a-sub-procedure"></a><span data-ttu-id="ed7a9-189">Вызов процедуры подпрограммы</span><span class="sxs-lookup"><span data-stu-id="ed7a9-189">Calling a Sub Procedure</span></span>

<span data-ttu-id="ed7a9-190">Процедура вызывается с `Sub` помощью имени процедуры в инструкции и затем после этого имени вместе со списком аргументов в круглых скобках.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-190">You call a `Sub` procedure by using the procedure name in a statement and then following that name with its argument list in parentheses.</span></span> <span data-ttu-id="ed7a9-191">Скобки можно опустить, только если не указаны аргументы.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-191">You can omit the parentheses only if you don't supply any arguments.</span></span> <span data-ttu-id="ed7a9-192">Однако код является более удобочитаемым, если всегда включать круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-192">However, your code is more readable if you always include the parentheses.</span></span>

<span data-ttu-id="ed7a9-193">`Sub`Процедура и `Function` процедура могут иметь параметры и выполнять ряд инструкций.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-193">A `Sub` procedure and a `Function` procedure  can have parameters and perform a series of statements.</span></span> <span data-ttu-id="ed7a9-194">Однако `Function` процедура возвращает значение, а `Sub` процедура — нет.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-194">However, a `Function` procedure returns a value, and a `Sub` procedure doesn't.</span></span> <span data-ttu-id="ed7a9-195">Поэтому нельзя использовать `Sub` процедуру в выражении.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-195">Therefore, you can't use a `Sub` procedure in an expression.</span></span>

<span data-ttu-id="ed7a9-196">`Call`Ключевое слово можно использовать при вызове `Sub` процедуры, но это ключевое слово не рекомендуется для большинства случаев использования.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-196">You can use the `Call` keyword when you call a `Sub` procedure, but that keyword isn't recommended for most uses.</span></span> <span data-ttu-id="ed7a9-197">Дополнительные сведения см. в разделе [оператор Call](call-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ed7a9-197">For more information, see [Call Statement](call-statement.md).</span></span>

<span data-ttu-id="ed7a9-198">Visual Basic иногда переупорядочивает арифметические выражения для повышения внутренней эффективности.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-198">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="ed7a9-199">По этой причине, если список аргументов содержит выражения, вызывающие другие процедуры, не следует рассчитывать на то, что эти выражения будут вызываться в определенном порядке.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-199">For that reason, if your argument list includes expressions that call other procedures, you shouldn't assume that those expressions will be called in a particular order.</span></span>

## <a name="async-sub-procedures"></a><span data-ttu-id="ed7a9-200">Процедуры Async</span><span class="sxs-lookup"><span data-stu-id="ed7a9-200">Async Sub Procedures</span></span>

<span data-ttu-id="ed7a9-201">С помощью функции Async можно вызывать асинхронные функции без использования явных обратных вызовов или вручную разделить код по нескольким функциям или лямбда-выражениям.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-201">By using the Async feature, you can invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>

<span data-ttu-id="ed7a9-202">Если вы пометите процедуру с модификатором [Async](../modifiers/async.md) , то можете использовать оператор [await](../operators/await-operator.md) в процедуре.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-202">If you mark a procedure with the [Async](../modifiers/async.md) modifier, you can use the [Await](../operators/await-operator.md) operator in the procedure.</span></span> <span data-ttu-id="ed7a9-203">Когда управление достигает `Await` выражения в `Async` процедуре, управление возвращается вызывающему объекту, и ход выполнения процедуры приостанавливается до тех пор, пока не завершится ожидаемая задача.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-203">When control reaches an `Await` expression in the `Async` procedure, control returns to the caller, and progress in the procedure is suspended until the awaited task completes.</span></span> <span data-ttu-id="ed7a9-204">После завершения задачи выполнение может быть возобновлено в процедуре.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-204">When the task is complete, execution can resume in the procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="ed7a9-205">`Async`Процедура возвращается к вызывающему объекту, когда происходит либо первый ожидающий объект, который еще не завершен, либо `Async` достигнут конец процедуры, в зависимости от того, что произойдет раньше.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-205">An `Async` procedure returns to the caller when either the first awaited object that’s not yet complete is encountered or the end of the `Async` procedure is reached, whichever occurs first.</span></span>

<span data-ttu-id="ed7a9-206">Можно также пометить [оператор Function](function-statement.md) с помощью `Async` модификатора.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-206">You can also mark a [Function Statement](function-statement.md) with the `Async` modifier.</span></span> <span data-ttu-id="ed7a9-207">`Async`Функция может иметь тип возвращаемого значения <xref:System.Threading.Tasks.Task%601> или <xref:System.Threading.Tasks.Task> .</span><span class="sxs-lookup"><span data-stu-id="ed7a9-207">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="ed7a9-208">В примере далее в этом разделе показана `Async` функция, имеющая тип возвращаемого значения <xref:System.Threading.Tasks.Task%601> .</span><span class="sxs-lookup"><span data-stu-id="ed7a9-208">An example later in this topic shows an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span>

<span data-ttu-id="ed7a9-209">`Async``Sub`процедуры в основном используются для обработчиков событий, где значение не может быть возвращено.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-209">`Async` `Sub` procedures are primarily used for event handlers, where a value can't be returned.</span></span> <span data-ttu-id="ed7a9-210">`Async` `Sub` Процедуру нельзя ожидать, и вызывающая `Async` `Sub` процедура не может перехватывать исключения, которые `Sub` создает процедура.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-210">An `Async` `Sub` procedure can't be awaited, and the caller of an `Async` `Sub` procedure can't catch exceptions that the `Sub` procedure throws.</span></span>

<span data-ttu-id="ed7a9-211">`Async`Процедура не может объявлять параметры [ByRef](../modifiers/byref.md) .</span><span class="sxs-lookup"><span data-stu-id="ed7a9-211">An `Async` procedure can't declare any [ByRef](../modifiers/byref.md) parameters.</span></span>

<span data-ttu-id="ed7a9-212">Дополнительные сведения о `Async` процедурах см. в разделе [Асинхронное программирование с использованием Async и await](../../programming-guide/concepts/async/index.md), [поток управления в асинхронных программах](../../programming-guide/concepts/async/control-flow-in-async-programs.md)и [асинхронные типы возвращаемых](../../programming-guide/concepts/async/async-return-types.md)данных.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-212">For more information about `Async` procedures, see [Asynchronous Programming with Async and Await](../../programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../programming-guide/concepts/async/async-return-types.md).</span></span>

## <a name="example"></a><span data-ttu-id="ed7a9-213">Пример</span><span class="sxs-lookup"><span data-stu-id="ed7a9-213">Example</span></span>

<span data-ttu-id="ed7a9-214">В следующем примере оператор используется `Sub` для определения имени, параметров и кода, образующих тело `Sub` процедуры.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-214">The following example uses the `Sub` statement to define the name, parameters, and code that form the body of a `Sub` procedure.</span></span>

[!code-vb[VbVbalrStatements#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#58)]

## <a name="example"></a><span data-ttu-id="ed7a9-215">Пример</span><span class="sxs-lookup"><span data-stu-id="ed7a9-215">Example</span></span>

<span data-ttu-id="ed7a9-216">В следующем примере `DelayAsync` — это, `Async` `Function` имеющий тип возвращаемого значения <xref:System.Threading.Tasks.Task%601> .</span><span class="sxs-lookup"><span data-stu-id="ed7a9-216">In the following example, `DelayAsync` is an `Async` `Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="ed7a9-217">`DelayAsync` имеет инструкцию `Return` , которая возвращает целое число.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-217">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="ed7a9-218">Поэтому объявление функции `DelayAsync` должно иметь тип возвращаемого значения `Task(Of Integer)` .</span><span class="sxs-lookup"><span data-stu-id="ed7a9-218">Therefore, the function declaration of `DelayAsync` must have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="ed7a9-219">Так как тип возвращаемого значения — `Task(Of Integer)` , вычисление `Await` выражения в `DoSomethingAsync` создает целое число, как показано в следующей инструкции: `Dim result As Integer = Await delayTask` .</span><span class="sxs-lookup"><span data-stu-id="ed7a9-219">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer, as the following statement shows: `Dim result As Integer = Await delayTask`.</span></span>

<span data-ttu-id="ed7a9-220">`startButton_Click`Процедура является примером `Async Sub` процедуры.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-220">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="ed7a9-221">Поскольку `DoSomethingAsync` является `Async` функцией, задача для вызова `DoSomethingAsync` должна быть ожидаемой, как показано в следующей инструкции: `Await DoSomethingAsync()` .</span><span class="sxs-lookup"><span data-stu-id="ed7a9-221">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement shows: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="ed7a9-222">`startButton_Click` `Sub` Процедура должна быть определена с `Async` модификатором, так как содержит `Await` выражение.</span><span class="sxs-lookup"><span data-stu-id="ed7a9-222">The `startButton_Click` `Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="ed7a9-223">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ed7a9-223">See also</span></span>

- [<span data-ttu-id="ed7a9-224">Оператор Implements</span><span class="sxs-lookup"><span data-stu-id="ed7a9-224">Implements Statement</span></span>](implements-statement.md)
- [<span data-ttu-id="ed7a9-225">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="ed7a9-225">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="ed7a9-226">Список параметров</span><span class="sxs-lookup"><span data-stu-id="ed7a9-226">Parameter List</span></span>](parameter-list.md)
- [<span data-ttu-id="ed7a9-227">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="ed7a9-227">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="ed7a9-228">Оператор Call</span><span class="sxs-lookup"><span data-stu-id="ed7a9-228">Call Statement</span></span>](call-statement.md)
- [<span data-ttu-id="ed7a9-229">Окна</span><span class="sxs-lookup"><span data-stu-id="ed7a9-229">Of</span></span>](of-clause.md)
- [<span data-ttu-id="ed7a9-230">Массивы параметров</span><span class="sxs-lookup"><span data-stu-id="ed7a9-230">Parameter Arrays</span></span>](../../programming-guide/language-features/procedures/parameter-arrays.md)
- [<span data-ttu-id="ed7a9-231">Практическое руководство. Использование универсального класса</span><span class="sxs-lookup"><span data-stu-id="ed7a9-231">How to: Use a Generic Class</span></span>](../../programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="ed7a9-232">Рекомендации по устранению неполадок</span><span class="sxs-lookup"><span data-stu-id="ed7a9-232">Troubleshooting Procedures</span></span>](../../programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [<span data-ttu-id="ed7a9-233">Разделяемые методы</span><span class="sxs-lookup"><span data-stu-id="ed7a9-233">Partial Methods</span></span>](../../programming-guide/language-features/procedures/partial-methods.md)
