---
title: Type List
ms.date: 07/20/2015
f1_keywords:
- StructureConstraint
- vb.StructureConstraint
- ClassConstraint
- vb.ClassConstraint
helpviewer_keywords:
- class constraint
- constraints, Visual Basic generic types
- generic parameters
- generics [Visual Basic], constraints
- generics [Visual Basic], type list
- structure constraint
- constraints, in type parameters
- generics [Visual Basic], generic types
- parameters [Visual Basic], type
- constraints, Structure keyword
- type parameters [Visual Basic], constraints
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- generics [Visual Basic], type parameters
- type parameters
- constraints, Class keyword
ms.assetid: 56db947a-2ae8-40f2-a70a-960764e9d0db
ms.openlocfilehash: 7e22ad6e32ec13f081391e1d47a80df8b1e65063
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84412992"
---
# <a name="type-list-visual-basic"></a><span data-ttu-id="7f9c0-102">Список типов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7f9c0-102">Type List (Visual Basic)</span></span>

<span data-ttu-id="7f9c0-103">Задает *Параметры типа* для *универсального* программного элемента.</span><span class="sxs-lookup"><span data-stu-id="7f9c0-103">Specifies the *type parameters* for a *generic* programming element.</span></span> <span data-ttu-id="7f9c0-104">Несколько параметров разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="7f9c0-104">Multiple parameters are separated by commas.</span></span> <span data-ttu-id="7f9c0-105">Ниже приведен синтаксис для одного параметра типа.</span><span class="sxs-lookup"><span data-stu-id="7f9c0-105">Following is the syntax for one type parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="7f9c0-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7f9c0-106">Syntax</span></span>

```vb
[genericmodifier] typename [ As constraintlist ]
```

## <a name="parts"></a><span data-ttu-id="7f9c0-107">Компоненты</span><span class="sxs-lookup"><span data-stu-id="7f9c0-107">Parts</span></span>

|<span data-ttu-id="7f9c0-108">Термин</span><span class="sxs-lookup"><span data-stu-id="7f9c0-108">Term</span></span>|<span data-ttu-id="7f9c0-109">Определение</span><span class="sxs-lookup"><span data-stu-id="7f9c0-109">Definition</span></span>|
|---|---|
|`genericmodifier`|<span data-ttu-id="7f9c0-110">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="7f9c0-110">Optional.</span></span> <span data-ttu-id="7f9c0-111">Может использоваться только в универсальных интерфейсах и делегатах.</span><span class="sxs-lookup"><span data-stu-id="7f9c0-111">Can be used only in generic interfaces and delegates.</span></span> <span data-ttu-id="7f9c0-112">Ковариантность типа можно объявить с помощью ключевого слова [out](../modifiers/out-generic-modifier.md) или контравариантного с помощью ключевого слова [in](../modifiers/in-generic-modifier.md) .</span><span class="sxs-lookup"><span data-stu-id="7f9c0-112">You can declare a type covariant by using the [Out](../modifiers/out-generic-modifier.md) keyword or contravariant by using the [In](../modifiers/in-generic-modifier.md) keyword.</span></span> <span data-ttu-id="7f9c0-113">См. раздел [Ковариация и контрвариация](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="7f9c0-113">See [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>|
|`typename`|<span data-ttu-id="7f9c0-114">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="7f9c0-114">Required.</span></span> <span data-ttu-id="7f9c0-115">Имя параметра типа.</span><span class="sxs-lookup"><span data-stu-id="7f9c0-115">Name of the type parameter.</span></span> <span data-ttu-id="7f9c0-116">Это заполнитель, заменяемый определенным типом, предоставленным соответствующим аргументом типа.</span><span class="sxs-lookup"><span data-stu-id="7f9c0-116">This is a placeholder, to be replaced by a defined type supplied by the corresponding type argument.</span></span>|
|`constraintlist`|<span data-ttu-id="7f9c0-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="7f9c0-117">Optional.</span></span> <span data-ttu-id="7f9c0-118">Список требований, ограничивающих тип данных, который может быть представлен для `typename` .</span><span class="sxs-lookup"><span data-stu-id="7f9c0-118">List of requirements that constrain the data type that can be supplied for `typename`.</span></span> <span data-ttu-id="7f9c0-119">При наличии нескольких ограничений заключите их в фигурные скобки ( `{ }` ) и разделите их запятыми.</span><span class="sxs-lookup"><span data-stu-id="7f9c0-119">If you have multiple constraints, enclose them in curly braces (`{ }`) and separate them with commas.</span></span> <span data-ttu-id="7f9c0-120">Список ограничений необходимо ввести с помощью ключевого слова [as](as-clause.md) .</span><span class="sxs-lookup"><span data-stu-id="7f9c0-120">You must introduce the constraint list with the [As](as-clause.md) keyword.</span></span> <span data-ttu-id="7f9c0-121">Используется `As` только один раз в начале списка.</span><span class="sxs-lookup"><span data-stu-id="7f9c0-121">You use `As` only once, at the beginning of the list.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7f9c0-122">Комментарии</span><span class="sxs-lookup"><span data-stu-id="7f9c0-122">Remarks</span></span>

<span data-ttu-id="7f9c0-123">Каждый универсальный программный элемент должен принимать по крайней мере один параметр типа.</span><span class="sxs-lookup"><span data-stu-id="7f9c0-123">Every generic programming element must take at least one type parameter.</span></span> <span data-ttu-id="7f9c0-124">Параметр типа — это заполнитель для определенного типа ( *сконструированного элемента*), который клиентский код указывает при создании экземпляра универсального типа.</span><span class="sxs-lookup"><span data-stu-id="7f9c0-124">A type parameter is a placeholder for a specific type (a *constructed element*) that client code specifies when it creates an instance of the generic type.</span></span> <span data-ttu-id="7f9c0-125">Можно определить универсальный класс, структуру, интерфейс, процедуру или делегат.</span><span class="sxs-lookup"><span data-stu-id="7f9c0-125">You can define a generic class, structure, interface, procedure, or delegate.</span></span>

<span data-ttu-id="7f9c0-126">Дополнительные сведения о том, когда следует определять универсальный тип, см. [в разделе Универсальные типы в Visual Basic](../../programming-guide/language-features/data-types/generic-types.md).</span><span class="sxs-lookup"><span data-stu-id="7f9c0-126">For more information on when to define a generic type, see [Generic Types in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md).</span></span> <span data-ttu-id="7f9c0-127">Дополнительные сведения об именах параметров типов см. в разделе [Имена объявленных элементов](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="7f9c0-127">For more information on type parameter names, see [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

## <a name="rules"></a><span data-ttu-id="7f9c0-128">Правила</span><span class="sxs-lookup"><span data-stu-id="7f9c0-128">Rules</span></span>

- <span data-ttu-id="7f9c0-129">**Скобки.**</span><span class="sxs-lookup"><span data-stu-id="7f9c0-129">**Parentheses.**</span></span> <span data-ttu-id="7f9c0-130">Если вы представите список параметров типа, необходимо заключить его в круглые скобки и ввести в список ключевое слово [of](of-clause.md) .</span><span class="sxs-lookup"><span data-stu-id="7f9c0-130">If you supply a type parameter list, you must enclose it in parentheses, and you must introduce the list with the [Of](of-clause.md) keyword.</span></span> <span data-ttu-id="7f9c0-131">Используется `Of` только один раз в начале списка.</span><span class="sxs-lookup"><span data-stu-id="7f9c0-131">You use `Of` only once, at the beginning of the list.</span></span>

- <span data-ttu-id="7f9c0-132">**Учитывая.**</span><span class="sxs-lookup"><span data-stu-id="7f9c0-132">**Constraints.**</span></span> <span data-ttu-id="7f9c0-133">Список *ограничений* для параметра типа может включать в себя следующие элементы в любом сочетании:</span><span class="sxs-lookup"><span data-stu-id="7f9c0-133">A list of *constraints* on a type parameter can include the following items in any combination:</span></span>

  - <span data-ttu-id="7f9c0-134">Любое количество интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="7f9c0-134">Any number of interfaces.</span></span> <span data-ttu-id="7f9c0-135">Указанный тип должен реализовывать каждый интерфейс в этом списке.</span><span class="sxs-lookup"><span data-stu-id="7f9c0-135">The supplied type must implement every interface in this list.</span></span>

  - <span data-ttu-id="7f9c0-136">Не более одного класса.</span><span class="sxs-lookup"><span data-stu-id="7f9c0-136">At most one class.</span></span> <span data-ttu-id="7f9c0-137">Указанный тип должен наследоваться от этого класса.</span><span class="sxs-lookup"><span data-stu-id="7f9c0-137">The supplied type must inherit from that class.</span></span>

  - <span data-ttu-id="7f9c0-138">Ключевое слово `New`.</span><span class="sxs-lookup"><span data-stu-id="7f9c0-138">The `New` keyword.</span></span> <span data-ttu-id="7f9c0-139">Предоставленный тип должен предоставлять конструктор без параметров, к которому имеет доступ универсальный тип.</span><span class="sxs-lookup"><span data-stu-id="7f9c0-139">The supplied type must expose a parameterless constructor that your generic type can access.</span></span> <span data-ttu-id="7f9c0-140">Это полезно, если параметр типа ограничивается одним или несколькими интерфейсами.</span><span class="sxs-lookup"><span data-stu-id="7f9c0-140">This is useful if you constrain a type parameter by one or more interfaces.</span></span> <span data-ttu-id="7f9c0-141">Тип, реализующий интерфейсы, не обязательно предоставляет конструктор, и в зависимости от уровня доступа конструктора код в универсальном типе может не иметь возможности получить к нему доступ.</span><span class="sxs-lookup"><span data-stu-id="7f9c0-141">A type that implements interfaces does not necessarily expose a constructor, and depending on the access level of a constructor, the code within the generic type might not be able to access it.</span></span>

  - <span data-ttu-id="7f9c0-142">`Class`Ключевое слово или `Structure` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="7f9c0-142">Either the `Class` keyword or the `Structure` keyword.</span></span> <span data-ttu-id="7f9c0-143">`Class`Ключевое слово ограничивает параметр универсального типа, требуя, чтобы любой передаваемый аргумент типа был ссылочным типом, например строкой, массивом или делегатом, или объектом, созданным из класса.</span><span class="sxs-lookup"><span data-stu-id="7f9c0-143">The `Class` keyword constrains a generic type parameter to require that any type argument passed to it be a reference type, for example a string, array, or delegate, or an object created from a class.</span></span> <span data-ttu-id="7f9c0-144">`Structure`Ключевое слово ограничивает параметр универсального типа, требуя, чтобы любой передаваемый аргумент типа был типом значения, например структурой, перечислением или простым типом данных.</span><span class="sxs-lookup"><span data-stu-id="7f9c0-144">The `Structure` keyword constrains a generic type parameter to require that any type argument passed to it be a value type, for example a structure, enumeration, or elementary data type.</span></span> <span data-ttu-id="7f9c0-145">Нельзя включать `Class` и `Structure` в, и в одном и том же `constraintlist` .</span><span class="sxs-lookup"><span data-stu-id="7f9c0-145">You cannot include both `Class` and `Structure` in the same `constraintlist`.</span></span>

  <span data-ttu-id="7f9c0-146">Указанный тип должен отвечать всем требованиям, включенным в `constraintlist` .</span><span class="sxs-lookup"><span data-stu-id="7f9c0-146">The supplied type must satisfy every requirement you include in `constraintlist`.</span></span>

  <span data-ttu-id="7f9c0-147">Ограничения для каждого параметра типа не зависят от ограничений для других параметров типа.</span><span class="sxs-lookup"><span data-stu-id="7f9c0-147">Constraints on each type parameter are independent of constraints on other type parameters.</span></span>

## <a name="behavior"></a><span data-ttu-id="7f9c0-148">Поведение</span><span class="sxs-lookup"><span data-stu-id="7f9c0-148">Behavior</span></span>

- <span data-ttu-id="7f9c0-149">**Подстановка во время компиляции.**</span><span class="sxs-lookup"><span data-stu-id="7f9c0-149">**Compile-Time Substitution.**</span></span> <span data-ttu-id="7f9c0-150">При создании сконструированного типа на основе универсального программного элемента вы предоставляете определенный тип для каждого параметра типа.</span><span class="sxs-lookup"><span data-stu-id="7f9c0-150">When you create a constructed type from a generic programming element, you supply a defined type for each type parameter.</span></span> <span data-ttu-id="7f9c0-151">Компилятор Visual Basic замещает указанный тип для каждого вхождения `typename` в пределах универсального элемента.</span><span class="sxs-lookup"><span data-stu-id="7f9c0-151">The Visual Basic compiler substitutes that supplied type for every occurrence of `typename` within the generic element.</span></span>

- <span data-ttu-id="7f9c0-152">**Отсутствие ограничений.**</span><span class="sxs-lookup"><span data-stu-id="7f9c0-152">**Absence of Constraints.**</span></span> <span data-ttu-id="7f9c0-153">Если не указать какие-либо ограничения на параметр типа, код будет ограничен операциями и элементами, поддерживаемыми [типом данных Object](../data-types/object-data-type.md) для этого параметра типа.</span><span class="sxs-lookup"><span data-stu-id="7f9c0-153">If you do not specify any constraints on a type parameter, your code is limited to the operations and members supported by the [Object Data Type](../data-types/object-data-type.md) for that type parameter.</span></span>

## <a name="example"></a><span data-ttu-id="7f9c0-154">Пример</span><span class="sxs-lookup"><span data-stu-id="7f9c0-154">Example</span></span>

<span data-ttu-id="7f9c0-155">В следующем примере показано определение каркаса универсального класса Dictionary, включая скелет функции для добавления новой записи в словарь.</span><span class="sxs-lookup"><span data-stu-id="7f9c0-155">The following example shows a skeleton definition of a generic dictionary class, including a skeleton function to add a new entry to the dictionary.</span></span>

[!code-vb[VbVbalrStatements#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#3)]

## <a name="example"></a><span data-ttu-id="7f9c0-156">Пример</span><span class="sxs-lookup"><span data-stu-id="7f9c0-156">Example</span></span>

<span data-ttu-id="7f9c0-157">Поскольку `dictionary` является универсальным, код, который использует его, может создавать разнообразные объекты, каждый из которых имеет одинаковые функциональные возможности, но работает с другим типом данных.</span><span class="sxs-lookup"><span data-stu-id="7f9c0-157">Because `dictionary` is generic, the code that uses it can create a variety of objects from it, each having the same functionality but acting on a different data type.</span></span> <span data-ttu-id="7f9c0-158">В следующем примере показана строка кода, создающая `dictionary` объект с `String` записями и `Integer` ключами.</span><span class="sxs-lookup"><span data-stu-id="7f9c0-158">The following example shows a line of code that creates a `dictionary` object with `String` entries and `Integer` keys.</span></span>

[!code-vb[VbVbalrStatements#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#4)]

## <a name="example"></a><span data-ttu-id="7f9c0-159">Пример</span><span class="sxs-lookup"><span data-stu-id="7f9c0-159">Example</span></span>

<span data-ttu-id="7f9c0-160">В следующем примере показано эквивалентное определение скелета, созданное в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="7f9c0-160">The following example shows the equivalent skeleton definition generated by the preceding example.</span></span>

[!code-vb[VbVbalrStatements#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#5)]

## <a name="see-also"></a><span data-ttu-id="7f9c0-161">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7f9c0-161">See also</span></span>

- [<span data-ttu-id="7f9c0-162">Окна</span><span class="sxs-lookup"><span data-stu-id="7f9c0-162">Of</span></span>](of-clause.md)
- [<span data-ttu-id="7f9c0-163">Оператор New</span><span class="sxs-lookup"><span data-stu-id="7f9c0-163">New Operator</span></span>](../operators/new-operator.md)
- [<span data-ttu-id="7f9c0-164">Уровни доступа в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7f9c0-164">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="7f9c0-165">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="7f9c0-165">Object Data Type</span></span>](../data-types/object-data-type.md)
- [<span data-ttu-id="7f9c0-166">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="7f9c0-166">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="7f9c0-167">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="7f9c0-167">Structure Statement</span></span>](structure-statement.md)
- [<span data-ttu-id="7f9c0-168">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="7f9c0-168">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="7f9c0-169">Практическое руководство. Использование универсального класса</span><span class="sxs-lookup"><span data-stu-id="7f9c0-169">How to: Use a Generic Class</span></span>](../../programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="7f9c0-170">Ковариация и контрвариантность</span><span class="sxs-lookup"><span data-stu-id="7f9c0-170">Covariance and Contravariance</span></span>](../../programming-guide/concepts/covariance-contravariance/index.md)
- [<span data-ttu-id="7f9c0-171">В</span><span class="sxs-lookup"><span data-stu-id="7f9c0-171">In</span></span>](../modifiers/in-generic-modifier.md)
- [<span data-ttu-id="7f9c0-172">Заполняет</span><span class="sxs-lookup"><span data-stu-id="7f9c0-172">Out</span></span>](../modifiers/out-generic-modifier.md)
