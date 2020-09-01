---
description: Справочник по C#. Ключевое слово class
title: Справочник по C#. Ключевое слово class
ms.date: 07/18/2017
f1_keywords:
- class_CSharpKeyword
- class
helpviewer_keywords:
- class keyword [C#]
ms.assetid: b95d8815-de18-4c3f-a8cc-a0a53bdf8690
ms.openlocfilehash: 67c9c4be55cce25edf9ecb84b257a8523f193bec
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142119"
---
# <a name="class-c-reference"></a><span data-ttu-id="71a8c-103">класс (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="71a8c-103">class (C# Reference)</span></span>

<span data-ttu-id="71a8c-104">Классы объявляются с помощью ключевого слова `class`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="71a8c-104">Classes are declared using the keyword `class`, as shown in the following example:</span></span>

```csharp
class TestClass
{
    // Methods, properties, fields, events, delegates
    // and nested classes go here.
}
```

## <a name="remarks"></a><span data-ttu-id="71a8c-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="71a8c-105">Remarks</span></span>

<span data-ttu-id="71a8c-106">В C# допускается только одиночное наследование.</span><span class="sxs-lookup"><span data-stu-id="71a8c-106">Only single inheritance is allowed in C#.</span></span> <span data-ttu-id="71a8c-107">Другими словами, класс может наследовать реализацию только от одного базового класса.</span><span class="sxs-lookup"><span data-stu-id="71a8c-107">In other words, a class can inherit implementation from one base class only.</span></span> <span data-ttu-id="71a8c-108">Однако класс может реализовывать несколько интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="71a8c-108">However, a class can implement more than one interface.</span></span> <span data-ttu-id="71a8c-109">В таблице ниже приведены примеры наследования класса и реализации интерфейса.</span><span class="sxs-lookup"><span data-stu-id="71a8c-109">The following table shows examples of class inheritance and interface implementation:</span></span>

|<span data-ttu-id="71a8c-110">Наследование</span><span class="sxs-lookup"><span data-stu-id="71a8c-110">Inheritance</span></span>|<span data-ttu-id="71a8c-111">Пример</span><span class="sxs-lookup"><span data-stu-id="71a8c-111">Example</span></span>|
|-----------------|-------------|
|<span data-ttu-id="71a8c-112">Нет</span><span class="sxs-lookup"><span data-stu-id="71a8c-112">None</span></span>|`class ClassA { }`|
|<span data-ttu-id="71a8c-113">Однонаправленная</span><span class="sxs-lookup"><span data-stu-id="71a8c-113">Single</span></span>|`class DerivedClass : BaseClass { }`|
|<span data-ttu-id="71a8c-114">Отсутствует, реализует два интерфейса</span><span class="sxs-lookup"><span data-stu-id="71a8c-114">None, implements two interfaces</span></span>|`class ImplClass : IFace1, IFace2 { }`|
|<span data-ttu-id="71a8c-115">Одиночное, реализует один интерфейс</span><span class="sxs-lookup"><span data-stu-id="71a8c-115">Single, implements one interface</span></span>|`class ImplDerivedClass : BaseClass, IFace1 { }`|

<span data-ttu-id="71a8c-116">Классы, объявленные непосредственно в пространстве имен и не вложенные в другие классы, могут быть [открытыми](./public.md) или [внутренними](./internal.md).</span><span class="sxs-lookup"><span data-stu-id="71a8c-116">Classes that you declare directly within a namespace, not nested within other classes, can be either [public](./public.md) or [internal](./internal.md).</span></span> <span data-ttu-id="71a8c-117">По умолчанию классы являются `internal`.</span><span class="sxs-lookup"><span data-stu-id="71a8c-117">Classes are `internal` by default.</span></span>

<span data-ttu-id="71a8c-118">Члены класса, включая вложенные классы, могут объявляться с типом доступа [public](public.md), [protected internal](protected-internal.md), [protected](protected.md), [internal](internal.md), [private](private.md) или [private protected](private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="71a8c-118">Class members, including nested classes, can be [public](public.md), [protected internal](protected-internal.md), [protected](protected.md), [internal](internal.md), [private](private.md), or [private protected](private-protected.md).</span></span> <span data-ttu-id="71a8c-119">По умолчанию члены имеют тип доступа `private`.</span><span class="sxs-lookup"><span data-stu-id="71a8c-119">Members are `private` by default.</span></span>

<span data-ttu-id="71a8c-120">Дополнительные сведения см. в статье [Модификаторы доступа](../../programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="71a8c-120">For more information, see [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md).</span></span>

<span data-ttu-id="71a8c-121">Можно объявить универсальные классы, имеющие параметры типа.</span><span class="sxs-lookup"><span data-stu-id="71a8c-121">You can declare generic classes that have type parameters.</span></span> <span data-ttu-id="71a8c-122">Дополнительные сведения см. в разделе [Универсальные классы](../../programming-guide/generics/generic-classes.md).</span><span class="sxs-lookup"><span data-stu-id="71a8c-122">For more information, see [Generic Classes](../../programming-guide/generics/generic-classes.md).</span></span>

<span data-ttu-id="71a8c-123">Класс может содержать объявления следующих членов:</span><span class="sxs-lookup"><span data-stu-id="71a8c-123">A class can contain declarations of the following members:</span></span>

- [<span data-ttu-id="71a8c-124">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="71a8c-124">Constructors</span></span>](../../programming-guide/classes-and-structs/constructors.md)

- [<span data-ttu-id="71a8c-125">Константы</span><span class="sxs-lookup"><span data-stu-id="71a8c-125">Constants</span></span>](../../programming-guide/classes-and-structs/constants.md)

- [<span data-ttu-id="71a8c-126">Поля</span><span class="sxs-lookup"><span data-stu-id="71a8c-126">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)

- [<span data-ttu-id="71a8c-127">Методы завершения</span><span class="sxs-lookup"><span data-stu-id="71a8c-127">Finalizers</span></span>](../../programming-guide/classes-and-structs/destructors.md)

- [<span data-ttu-id="71a8c-128">Методы</span><span class="sxs-lookup"><span data-stu-id="71a8c-128">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)

- [<span data-ttu-id="71a8c-129">Свойства</span><span class="sxs-lookup"><span data-stu-id="71a8c-129">Properties</span></span>](../../programming-guide/classes-and-structs/properties.md)

- [<span data-ttu-id="71a8c-130">Индексаторы</span><span class="sxs-lookup"><span data-stu-id="71a8c-130">Indexers</span></span>](../../programming-guide/indexers/index.md)

- [<span data-ttu-id="71a8c-131">Инструкции</span><span class="sxs-lookup"><span data-stu-id="71a8c-131">Operators</span></span>](../operators/index.md)

- [<span data-ttu-id="71a8c-132">События</span><span class="sxs-lookup"><span data-stu-id="71a8c-132">Events</span></span>](../../programming-guide/events/index.md)

- [<span data-ttu-id="71a8c-133">Делегаты</span><span class="sxs-lookup"><span data-stu-id="71a8c-133">Delegates</span></span>](../../programming-guide/delegates/index.md)

- [<span data-ttu-id="71a8c-134">Классы</span><span class="sxs-lookup"><span data-stu-id="71a8c-134">Classes</span></span>](../../programming-guide/classes-and-structs/classes.md)

- [<span data-ttu-id="71a8c-135">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="71a8c-135">Interfaces</span></span>](../../programming-guide/interfaces/index.md)

- [<span data-ttu-id="71a8c-136">Типы структур</span><span class="sxs-lookup"><span data-stu-id="71a8c-136">Structure types</span></span>](../builtin-types/struct.md)

- [<span data-ttu-id="71a8c-137">Типы перечислений</span><span class="sxs-lookup"><span data-stu-id="71a8c-137">Enumeration types</span></span>](../builtin-types/enum.md)

## <a name="example"></a><span data-ttu-id="71a8c-138">Пример</span><span class="sxs-lookup"><span data-stu-id="71a8c-138">Example</span></span>

<span data-ttu-id="71a8c-139">В приведенном ниже примере показано объявление полей, конструкторов и методов класса.</span><span class="sxs-lookup"><span data-stu-id="71a8c-139">The following example demonstrates declaring class fields, constructors, and methods.</span></span> <span data-ttu-id="71a8c-140">В нем также демонстрируется создание экземпляра объекта и печать данных экземпляра.</span><span class="sxs-lookup"><span data-stu-id="71a8c-140">It also demonstrates object instantiation and printing instance data.</span></span> <span data-ttu-id="71a8c-141">В этом примере объявляются два класса.</span><span class="sxs-lookup"><span data-stu-id="71a8c-141">In this example, two classes are declared.</span></span> <span data-ttu-id="71a8c-142">Первый класс, `Child`, содержит два частных поля (`name` и `age`), два общих конструктора и один общий метод.</span><span class="sxs-lookup"><span data-stu-id="71a8c-142">The first class, `Child`, contains two private fields (`name` and `age`), two public constructors and one public method.</span></span> <span data-ttu-id="71a8c-143">Второй класс, `StringTest`, используется для хранения `Main`.</span><span class="sxs-lookup"><span data-stu-id="71a8c-143">The second class, `StringTest`, is used to contain `Main`.</span></span>

[!code-csharp[csrefKeywordsTypes#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#5)]

## <a name="comments"></a><span data-ttu-id="71a8c-144">Примечания</span><span class="sxs-lookup"><span data-stu-id="71a8c-144">Comments</span></span>

<span data-ttu-id="71a8c-145">Обратите внимание, что в предыдущем примере доступ к частным полям (`name` и `age`) возможен только с помощью общих методов класса `Child`.</span><span class="sxs-lookup"><span data-stu-id="71a8c-145">Notice that in the previous example the private fields (`name` and `age`) can only be accessed through the public method of the `Child` class.</span></span> <span data-ttu-id="71a8c-146">Например, имя ребенка нельзя напечатать из метода `Main` с помощью следующего оператора:</span><span class="sxs-lookup"><span data-stu-id="71a8c-146">For example, you cannot print the child's name, from the `Main` method, using a statement like this:</span></span>

```csharp
Console.Write(child1.name);   // Error
```

<span data-ttu-id="71a8c-147">Получить доступ к закрытым членам класса `Child` из метода `Main` можно было бы лишь в том случае, если бы `Main` был членом класса.</span><span class="sxs-lookup"><span data-stu-id="71a8c-147">Accessing private members of `Child` from `Main` would only be possible if `Main` were a member of the class.</span></span>

<span data-ttu-id="71a8c-148">Типы, объявленные в классе без модификатора доступа, по умолчанию являются `private`, поэтому члены данных в этом примере останутся `private`, если ключевые слова будут удалены.</span><span class="sxs-lookup"><span data-stu-id="71a8c-148">Types declared inside a class without an access modifier default to `private`, so the data members in this example would still be `private` if the keyword were removed.</span></span>

<span data-ttu-id="71a8c-149">Наконец, обратите внимание, что для объекта, созданного с помощью конструктора без параметров (`child3`), поле `age` по умолчанию инициализировано с нулевым значением.</span><span class="sxs-lookup"><span data-stu-id="71a8c-149">Finally, notice that for the object created using the parameterless constructor (`child3`), the `age` field was initialized to zero by default.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="71a8c-150">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="71a8c-150">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="71a8c-151">См. также</span><span class="sxs-lookup"><span data-stu-id="71a8c-151">See also</span></span>

- [<span data-ttu-id="71a8c-152">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="71a8c-152">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="71a8c-153">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="71a8c-153">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="71a8c-154">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="71a8c-154">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="71a8c-155">Ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="71a8c-155">Reference Types</span></span>](./reference-types.md)
