---
title: Оператор Enum
ms.date: 07/20/2015
f1_keywords:
- vb.Enum
helpviewer_keywords:
- enumerated constants [Visual Basic]
- Enum statement [Visual Basic]
- Private keyword [Visual Basic], Enum statements
- Public keyword [Visual Basic], in Enum statement
- variables [Visual Basic], enumeration
- constants [Visual Basic], enumerated
ms.assetid: a45e51f1-65ff-48e1-bf32-79130f137377
ms.openlocfilehash: 976cc68d67c69ec86918962ab2dd3406d15aed9a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404736"
---
# <a name="enum-statement-visual-basic"></a><span data-ttu-id="aeb6c-102">Оператор Enum (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aeb6c-102">Enum Statement (Visual Basic)</span></span>

<span data-ttu-id="aeb6c-103">Объявляет перечисление и определяет значения его элементов.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-103">Declares an enumeration and defines the values of its members.</span></span>

## <a name="syntax"></a><span data-ttu-id="aeb6c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aeb6c-104">Syntax</span></span>

```vb
[ <attributelist> ] [ accessmodifier ]  [ Shadows ]
Enum enumerationname [ As datatype ]
   memberlist
End Enum
```

## <a name="parts"></a><span data-ttu-id="aeb6c-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="aeb6c-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="aeb6c-106">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-106">Optional.</span></span> <span data-ttu-id="aeb6c-107">Список атрибутов, которые применяются к этому перечислению.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-107">List of attributes that apply to this enumeration.</span></span> <span data-ttu-id="aeb6c-108">[Список атрибутов](attribute-list.md) необходимо заключить в угловые скобки (" `<` " и " `>` ").</span><span class="sxs-lookup"><span data-stu-id="aeb6c-108">You must enclose the [attribute list](attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>

  <span data-ttu-id="aeb6c-109"><xref:System.FlagsAttribute>Атрибут указывает, что значение экземпляра перечисления может включать несколько членов перечисления и что каждый элемент представляет битовое поле в значении перечисления.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-109">The <xref:System.FlagsAttribute> attribute indicates that the value of an instance of the enumeration can include multiple enumeration members, and that each member represents a bit field in the enumeration value.</span></span>

- `accessmodifier`

  <span data-ttu-id="aeb6c-110">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-110">Optional.</span></span> <span data-ttu-id="aeb6c-111">Указывает, какой код может получить доступ к этому перечислению.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-111">Specifies what code can access this enumeration.</span></span> <span data-ttu-id="aeb6c-112">Может принимать следующие значения:</span><span class="sxs-lookup"><span data-stu-id="aeb6c-112">Can be one of the following:</span></span>

  - [<span data-ttu-id="aeb6c-113">Открытый</span><span class="sxs-lookup"><span data-stu-id="aeb6c-113">Public</span></span>](../modifiers/public.md)

  - [<span data-ttu-id="aeb6c-114">От</span><span class="sxs-lookup"><span data-stu-id="aeb6c-114">Protected</span></span>](../modifiers/protected.md)

  - [<span data-ttu-id="aeb6c-115">Объявление</span><span class="sxs-lookup"><span data-stu-id="aeb6c-115">Friend</span></span>](../modifiers/friend.md)

  - [<span data-ttu-id="aeb6c-116">Частное</span><span class="sxs-lookup"><span data-stu-id="aeb6c-116">Private</span></span>](../modifiers/private.md)

  - [<span data-ttu-id="aeb6c-117">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="aeb6c-117">Protected Friend</span></span>](../modifiers/protected-friend.md)

  - [<span data-ttu-id="aeb6c-118">Частный защищенный</span><span class="sxs-lookup"><span data-stu-id="aeb6c-118">Private Protected</span></span>](../modifiers/private-protected.md)

- `Shadows`

  <span data-ttu-id="aeb6c-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-119">Optional.</span></span> <span data-ttu-id="aeb6c-120">Указывает, что это перечисление повторно объявляет и скрывает идентично именованный элемент программирования или набор перегруженных элементов в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-120">Specifies that this enumeration redeclares and hides an identically named programming element, or set of overloaded elements, in a base class.</span></span> <span data-ttu-id="aeb6c-121">[Тени](../modifiers/shadows.md) можно указывать только в самом перечислении, а не на любом из его членов.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-121">You can specify [Shadows](../modifiers/shadows.md) only on the enumeration itself, not on any of its members.</span></span>

- `enumerationname`

  <span data-ttu-id="aeb6c-122">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-122">Required.</span></span> <span data-ttu-id="aeb6c-123">Имя перечисления.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-123">Name of the enumeration.</span></span> <span data-ttu-id="aeb6c-124">Сведения о допустимых именах см. в разделе [Имена объявленных элементов](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="aeb6c-124">For information on valid names, see [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

- `datatype`

  <span data-ttu-id="aeb6c-125">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-125">Optional.</span></span> <span data-ttu-id="aeb6c-126">Тип данных перечисления и всех его элементов.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-126">Data type of the enumeration and all its members.</span></span>

- `memberlist`

  <span data-ttu-id="aeb6c-127">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-127">Required.</span></span> <span data-ttu-id="aeb6c-128">Список констант членов, объявляемых в этой инструкции.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-128">List of member constants being declared in this statement.</span></span> <span data-ttu-id="aeb6c-129">В отдельных строках исходного кода отображаются несколько элементов.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-129">Multiple members appear on individual source code lines.</span></span>

  <span data-ttu-id="aeb6c-130">Каждый `member` из них имеет следующий синтаксис и фрагменты:`[<attribute list>] member name [ = initializer ]`</span><span class="sxs-lookup"><span data-stu-id="aeb6c-130">Each `member` has the following syntax and parts: `[<attribute list>] member name [ = initializer ]`</span></span>

  |<span data-ttu-id="aeb6c-131">Часть</span><span class="sxs-lookup"><span data-stu-id="aeb6c-131">Part</span></span>|<span data-ttu-id="aeb6c-132">Описание</span><span class="sxs-lookup"><span data-stu-id="aeb6c-132">Description</span></span>|
  |---|---|
  |`membername`|<span data-ttu-id="aeb6c-133">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-133">Required.</span></span> <span data-ttu-id="aeb6c-134">Имя этого элемента.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-134">Name of this member.</span></span>|
  |`initializer`|<span data-ttu-id="aeb6c-135">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-135">Optional.</span></span> <span data-ttu-id="aeb6c-136">Выражение, которое вычисляется во время компиляции и присваивается этому элементу.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-136">Expression that is evaluated at compile time and assigned to this member.</span></span>|

- <span data-ttu-id="aeb6c-137">`End` `Enum`</span><span class="sxs-lookup"><span data-stu-id="aeb6c-137">`End` `Enum`</span></span>

  <span data-ttu-id="aeb6c-138">Завершает блок `Enum`.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-138">Terminates the `Enum` block.</span></span>

## <a name="remarks"></a><span data-ttu-id="aeb6c-139">Комментарии</span><span class="sxs-lookup"><span data-stu-id="aeb6c-139">Remarks</span></span>

<span data-ttu-id="aeb6c-140">Если имеется набор неизменяемых значений, логически связанных друг с другом, их можно определить вместе в перечислении.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-140">If you have a set of unchanging values that are logically related to each other, you can define them together in an enumeration.</span></span> <span data-ttu-id="aeb6c-141">Это дает осмысленные имена для перечисления и его членов, которые проще запомнить, чем их значения.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-141">This provides meaningful names for the enumeration and its members, which are easier to remember than their values.</span></span> <span data-ttu-id="aeb6c-142">Затем можно использовать элементы перечисления во многих местах кода.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-142">You can then use the enumeration members in many places in your code.</span></span>

<span data-ttu-id="aeb6c-143">Ниже перечислены преимущества использования перечислений.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-143">The benefits of using enumerations include the following:</span></span>

- <span data-ttu-id="aeb6c-144">Сокращает количество ошибок, вызванных перечислением или неотрицательным вводом чисел.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-144">Reduces errors caused by transposing or mistyping numbers.</span></span>

- <span data-ttu-id="aeb6c-145">Упрощает изменение значений в будущем.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-145">Makes it easy to change values in the future.</span></span>

- <span data-ttu-id="aeb6c-146">Упрощает чтение кода, что означает меньшее количество ошибок, которые могут возникать.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-146">Makes code easier to read, which means it is less likely that errors will be introduced.</span></span>

- <span data-ttu-id="aeb6c-147">Обеспечивает прямую совместимость.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-147">Ensures forward compatibility.</span></span> <span data-ttu-id="aeb6c-148">При использовании перечислений код менее вероятен, если в будущем кто-то изменит значения, соответствующие именам элементов.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-148">If you use enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>

<span data-ttu-id="aeb6c-149">Перечисление имеет имя, базовый тип данных и набор элементов.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-149">An enumeration has a name, an underlying data type, and a set of members.</span></span> <span data-ttu-id="aeb6c-150">Каждый элемент представляет константу.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-150">Each member represents a constant.</span></span>

<span data-ttu-id="aeb6c-151">Перечисление, объявленное на уровне класса, структуры, модуля или интерфейса, за пределами любой процедуры, является *перечислителем элементов*.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-151">An enumeration declared at class, structure, module, or interface level, outside any procedure, is a *member enumeration*.</span></span> <span data-ttu-id="aeb6c-152">Он является членом класса, структуры, модуля или интерфейса, объявляющего его.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-152">It is a member of the class, structure, module, or interface that declares it.</span></span>

<span data-ttu-id="aeb6c-153">К перечислениям членов можно обращаться из любого места в своем классе, структуре, модуле или интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-153">Member enumerations can be accessed from anywhere within their class, structure, module, or interface.</span></span> <span data-ttu-id="aeb6c-154">Код за пределами класса, структуры или модуля должен уточнять имя перечисления членов именем этого класса, структуры или модуля.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-154">Code outside a class, structure, or module must qualify a member enumeration's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="aeb6c-155">Можно избежать необходимости использовать полные имена, добавив оператор [Imports](imports-statement-net-namespace-and-type.md) в исходный файл.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-155">You can avoid the need to use fully qualified names by adding an [Imports](imports-statement-net-namespace-and-type.md) statement to the source file.</span></span>

<span data-ttu-id="aeb6c-156">Перечисление, объявленное на уровне пространства имен вне любого класса, структуры, модуля или интерфейса, является членом пространства имен, в котором оно отображается.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-156">An enumeration declared at namespace level, outside any class, structure, module, or interface, is a member of the namespace in which it appears.</span></span>

<span data-ttu-id="aeb6c-157">*Контекст объявления* для перечисления должен быть исходным файлом, пространством имен, классом, структурой, модулем или интерфейсом и не может быть процедурой.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-157">The *declaration context* for an enumeration must be a source file, namespace, class, structure, module, or interface, and cannot be a procedure.</span></span> <span data-ttu-id="aeb6c-158">Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="aeb6c-158">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="aeb6c-159">К перечислению можно применять атрибуты в целом, но не в отдельные элементы.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-159">You can apply attributes to an enumeration as a whole, but not to its members individually.</span></span> <span data-ttu-id="aeb6c-160">Атрибут вносит сведения в метаданные сборки.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-160">An attribute contributes information to the assembly's metadata.</span></span>

## <a name="data-type"></a><span data-ttu-id="aeb6c-161">Тип данных</span><span class="sxs-lookup"><span data-stu-id="aeb6c-161">Data Type</span></span>

<span data-ttu-id="aeb6c-162">`Enum`Оператор может объявлять тип данных перечисления.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-162">The `Enum` statement can declare the data type of an enumeration.</span></span> <span data-ttu-id="aeb6c-163">Каждый член принимает тип данных перечисления.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-163">Each member takes the enumeration's data type.</span></span> <span data-ttu-id="aeb6c-164">Можно указать `Byte` , `Integer` , `Long` , `SByte` , `Short` , `UInteger` , `ULong` или `UShort` .</span><span class="sxs-lookup"><span data-stu-id="aeb6c-164">You can specify `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort`.</span></span>

<span data-ttu-id="aeb6c-165">Если не указать `datatype` для перечисления, каждый элемент принимает тип данных его `initializer` .</span><span class="sxs-lookup"><span data-stu-id="aeb6c-165">If you do not specify `datatype` for the enumeration, each member takes the data type of its `initializer`.</span></span> <span data-ttu-id="aeb6c-166">Если заданы оба параметра `datatype` и `initializer` , тип данных `initializer` должен быть преобразован в `datatype` .</span><span class="sxs-lookup"><span data-stu-id="aeb6c-166">If you specify both `datatype` and `initializer`, the data type of `initializer` must be convertible to `datatype`.</span></span> <span data-ttu-id="aeb6c-167">Если оба `datatype` `initializer` параметра и не указаны, по умолчанию используется тип данных `Integer` .</span><span class="sxs-lookup"><span data-stu-id="aeb6c-167">If neither `datatype` nor `initializer` is present, the data type defaults to `Integer`.</span></span>

## <a name="initializing-members"></a><span data-ttu-id="aeb6c-168">Инициализация членов</span><span class="sxs-lookup"><span data-stu-id="aeb6c-168">Initializing Members</span></span>

<span data-ttu-id="aeb6c-169">`Enum`Оператор может инициализировать содержимое выбранных элементов в `memberlist` .</span><span class="sxs-lookup"><span data-stu-id="aeb6c-169">The `Enum` statement can initialize the contents of selected members in `memberlist`.</span></span> <span data-ttu-id="aeb6c-170">Используется `initializer` для предоставления выражения, присваиваемого элементу.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-170">You use `initializer` to supply an expression to be assigned to the member.</span></span>

<span data-ttu-id="aeb6c-171">Если вы не укажете `initializer` для члена, Visual Basic инициализирует его как ноль (если он является первым `member` в `memberlist` ) или значение, большее значения, превышающего, чем ранее `member` .</span><span class="sxs-lookup"><span data-stu-id="aeb6c-171">If you do not specify `initializer` for a member, Visual Basic initializes it either to zero (if it is the first `member` in `memberlist`), or to a value greater by one than that of the immediately preceding `member`.</span></span>

<span data-ttu-id="aeb6c-172">Выражение, передаваемое в each, `initializer` может быть любым сочетанием литералов, других уже определенных констант и уже определенных членов перечисления, включая предыдущий элемент этого перечисления.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-172">The expression supplied in each `initializer` can be any combination of literals, other constants that are already defined, and enumeration members that are already defined, including a previous member of this enumeration.</span></span> <span data-ttu-id="aeb6c-173">Для объединения таких элементов можно использовать арифметические и логические операторы.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-173">You can use arithmetic and logical operators to combine such elements.</span></span>

<span data-ttu-id="aeb6c-174">В нельзя использовать переменные или функции `initializer` .</span><span class="sxs-lookup"><span data-stu-id="aeb6c-174">You cannot use variables or functions in `initializer`.</span></span> <span data-ttu-id="aeb6c-175">Однако можно использовать ключевые слова преобразования, такие как `CByte` и `CShort` .</span><span class="sxs-lookup"><span data-stu-id="aeb6c-175">However, you can use conversion keywords such as `CByte` and `CShort`.</span></span> <span data-ttu-id="aeb6c-176">Можно также использовать `AscW` , если вы вызываете его с константой `String` или `Char` аргументом, так как это может быть вычислено во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-176">You can also use `AscW` if you call it with a constant `String` or `Char` argument, since that can be evaluated at compile time.</span></span>

<span data-ttu-id="aeb6c-177">Перечисления не могут иметь значения с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-177">Enumerations cannot have floating-point values.</span></span> <span data-ttu-id="aeb6c-178">Если члену присваивается значение с плавающей запятой и `Option Strict` для него задано состояние ON, возникает ошибка компилятора.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-178">If a member is assigned a floating-point value and `Option Strict` is set to on, a compiler error occurs.</span></span> <span data-ttu-id="aeb6c-179">Если параметр `Option Strict` равен OFF, значение автоматически преобразуется в `Enum` тип.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-179">If `Option Strict` is off, the value is automatically converted to the `Enum` type.</span></span>

<span data-ttu-id="aeb6c-180">Если значение элемента превышает допустимый диапазон для базового типа данных или если любой элемент инициализируется максимальным значением, разрешенным базовым типом данных, то компилятор сообщает об ошибке.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-180">If the value of a member exceeds the allowable range for the underlying data type, or if you initialize any member to the maximum value allowed by the underlying data type, the compiler reports an error.</span></span>

## <a name="modifiers"></a><span data-ttu-id="aeb6c-181">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="aeb6c-181">Modifiers</span></span>

<span data-ttu-id="aeb6c-182">Перечисления членов класса, структуры, модуля и интерфейса по умолчанию имеют открытый доступ.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-182">Class, structure, module, and interface member enumerations default to public access.</span></span> <span data-ttu-id="aeb6c-183">Уровни доступа можно изменить с помощью модификаторов доступа.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-183">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="aeb6c-184">Перечисления членов пространств имен по умолчанию имеют дружественный доступ.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-184">Namespace member enumerations default to friend access.</span></span> <span data-ttu-id="aeb6c-185">Уровни доступа можно изменить на "общий", но не на "частный" или "защищенный".</span><span class="sxs-lookup"><span data-stu-id="aeb6c-185">You can adjust their access levels to public, but not to private or protected.</span></span> <span data-ttu-id="aeb6c-186">Дополнительные сведения см. [в разделе уровни доступа в Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="aeb6c-186">For more information, see [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="aeb6c-187">Все члены перечисления имеют общий доступ, и в них нельзя использовать никакие модификаторы доступа.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-187">All enumeration members have public access, and you cannot use any access modifiers on them.</span></span> <span data-ttu-id="aeb6c-188">Однако если перечисление имеет более ограниченный уровень доступа, приоритет имеет указанный уровень доступа к перечислению.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-188">However, if the enumeration itself has a more restricted access level, the specified enumeration access level takes precedence.</span></span>

<span data-ttu-id="aeb6c-189">По умолчанию все перечисления являются типами, а их поля — константами.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-189">By default, all enumerations are types and their fields are constants.</span></span> <span data-ttu-id="aeb6c-190">Поэтому `Shared` `Static` Ключевые слова, и `ReadOnly` не могут быть использованы при объявлении перечисления или его членов.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-190">Therefore the `Shared`, `Static`, and `ReadOnly` keywords cannot be used when declaring an enumeration or its members.</span></span>

## <a name="assigning-multiple-values"></a><span data-ttu-id="aeb6c-191">Присваивание нескольких значений</span><span class="sxs-lookup"><span data-stu-id="aeb6c-191">Assigning Multiple Values</span></span>

<span data-ttu-id="aeb6c-192">Перечисления обычно представляют взаимоисключающие значения.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-192">Enumerations typically represent mutually exclusive values.</span></span> <span data-ttu-id="aeb6c-193">Включив <xref:System.FlagsAttribute> атрибут в `Enum` объявление, можно присвоить экземпляру перечисления несколько значений.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-193">By including the <xref:System.FlagsAttribute> attribute in the `Enum` declaration, you can instead assign multiple values to an instance of the enumeration.</span></span> <span data-ttu-id="aeb6c-194"><xref:System.FlagsAttribute>Атрибут указывает, что перечисление будет рассматриваться как битовое поле, то есть набор флагов.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-194">The <xref:System.FlagsAttribute> attribute specifies that the enumeration be treated as a bit field, that is, a set of flags.</span></span> <span data-ttu-id="aeb6c-195">Они называются *побитовыми* перечислениями.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-195">These are called *bitwise* enumerations.</span></span>

<span data-ttu-id="aeb6c-196">Если перечисление объявляется с помощью <xref:System.FlagsAttribute> атрибута, для значений рекомендуется использовать степени 2, то есть 1, 2, 4, 8, 16 и т. д.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-196">When you declare an enumeration by using the <xref:System.FlagsAttribute> attribute, we recommend that you use powers of 2, that is, 1, 2, 4, 8, 16, and so on, for the values.</span></span> <span data-ttu-id="aeb6c-197">Также рекомендуется, чтобы "None" было именем члена, значение которого равно 0.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-197">We also recommend that "None" be the name of a member whose value is 0.</span></span> <span data-ttu-id="aeb6c-198">Дополнительные рекомендации см. в статьях <xref:System.FlagsAttribute> и <xref:System.Enum> .</span><span class="sxs-lookup"><span data-stu-id="aeb6c-198">For additional guidelines, see <xref:System.FlagsAttribute> and <xref:System.Enum>.</span></span>

## <a name="example"></a><span data-ttu-id="aeb6c-199">Пример</span><span class="sxs-lookup"><span data-stu-id="aeb6c-199">Example</span></span>

<span data-ttu-id="aeb6c-200">В следующем примере показано использование оператора `Enum`.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-200">The following example shows how to use the `Enum` statement.</span></span> <span data-ttu-id="aeb6c-201">Обратите внимание, что элемент называется `EggSizeEnum.Medium` , а не как `Medium` .</span><span class="sxs-lookup"><span data-stu-id="aeb6c-201">Note that the member is referred to as `EggSizeEnum.Medium`, and not as `Medium`.</span></span>

[!code-vb[VbEnumsTask#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#41)]

## <a name="example"></a><span data-ttu-id="aeb6c-202">Пример</span><span class="sxs-lookup"><span data-stu-id="aeb6c-202">Example</span></span>

<span data-ttu-id="aeb6c-203">Метод в следующем примере находится за пределами `Egg` класса.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-203">The method in the following example is outside the `Egg` class.</span></span> <span data-ttu-id="aeb6c-204">Таким образом, `EggSizeEnum` имеет полное имя `Egg.EggSizeEnum` .</span><span class="sxs-lookup"><span data-stu-id="aeb6c-204">Therefore, `EggSizeEnum` is fully qualified as `Egg.EggSizeEnum`.</span></span>

[!code-vb[VbEnumsTask#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#42)]

## <a name="example"></a><span data-ttu-id="aeb6c-205">Пример</span><span class="sxs-lookup"><span data-stu-id="aeb6c-205">Example</span></span>

<span data-ttu-id="aeb6c-206">В следующем примере оператор используется `Enum` для определения связанного набора именованных постоянных значений.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-206">The following example uses the `Enum` statement to define a related set of named constant values.</span></span> <span data-ttu-id="aeb6c-207">В этом случае значения представляют собой цвета, которые можно выбрать для создания форм ввода данных для базы данных.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-207">In this case, the values are colors you might choose to design data entry forms for a database.</span></span>

[!code-vb[VbEnumsTask#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#30)]

## <a name="example"></a><span data-ttu-id="aeb6c-208">Пример</span><span class="sxs-lookup"><span data-stu-id="aeb6c-208">Example</span></span>

<span data-ttu-id="aeb6c-209">В следующем примере показаны значения, включающие положительные и отрицательные числа.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-209">The following example shows values that include both positive and negative numbers.</span></span>

[!code-vb[VbEnumsTask#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#31)]

## <a name="example"></a><span data-ttu-id="aeb6c-210">Пример</span><span class="sxs-lookup"><span data-stu-id="aeb6c-210">Example</span></span>

<span data-ttu-id="aeb6c-211">В следующем примере `As` используется предложение для указания `datatype` перечисления.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-211">In the following example, an `As` clause is used to specify the `datatype` of an enumeration.</span></span>

[!code-vb[VbEnumsTask#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#6)]

## <a name="example"></a><span data-ttu-id="aeb6c-212">Пример</span><span class="sxs-lookup"><span data-stu-id="aeb6c-212">Example</span></span>

<span data-ttu-id="aeb6c-213">В следующем примере показано, как использовать побитовое перечисление.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-213">The following example shows how to use a bitwise enumeration.</span></span> <span data-ttu-id="aeb6c-214">Экземпляру побитового перечисления можно назначить несколько значений.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-214">Multiple values can be assigned to an instance of a bitwise enumeration.</span></span> <span data-ttu-id="aeb6c-215">`Enum`Объявление включает <xref:System.FlagsAttribute> атрибут, указывающий, что перечисление может рассматриваться как набор флагов.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-215">The `Enum` declaration includes the <xref:System.FlagsAttribute> attribute, which indicates that the enumeration can be treated as a set of flags.</span></span>

[!code-vb[VbEnumsTask#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#61)]

## <a name="example"></a><span data-ttu-id="aeb6c-216">Пример</span><span class="sxs-lookup"><span data-stu-id="aeb6c-216">Example</span></span>

<span data-ttu-id="aeb6c-217">В следующем примере выполняется итерация по перечислению.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-217">The following example iterates through an enumeration.</span></span> <span data-ttu-id="aeb6c-218">Он использует <xref:System.Enum.GetNames%2A> метод для получения массива имен членов из перечисления и <xref:System.Enum.GetValues%2A> для получения массива значений элементов.</span><span class="sxs-lookup"><span data-stu-id="aeb6c-218">It uses the <xref:System.Enum.GetNames%2A> method to retrieve an array of member names from the enumeration, and <xref:System.Enum.GetValues%2A> to retrieve an array of member values.</span></span>

[!code-vb[VbEnumsTask#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#51)]

## <a name="see-also"></a><span data-ttu-id="aeb6c-219">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="aeb6c-219">See also</span></span>

- <xref:System.Enum>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- [<span data-ttu-id="aeb6c-220">Оператор Const</span><span class="sxs-lookup"><span data-stu-id="aeb6c-220">Const Statement</span></span>](const-statement.md)
- [<span data-ttu-id="aeb6c-221">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="aeb6c-221">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="aeb6c-222">Явные и неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="aeb6c-222">Implicit and Explicit Conversions</span></span>](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="aeb6c-223">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="aeb6c-223">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="aeb6c-224">Константы и перечисления</span><span class="sxs-lookup"><span data-stu-id="aeb6c-224">Constants and Enumerations</span></span>](../constants-and-enumerations.md)
