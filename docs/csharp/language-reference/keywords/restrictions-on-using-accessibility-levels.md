---
description: Справочник по C#. Ограничения на использование уровней доступности
title: Справочник по C#. Ограничения на использование уровней доступности
ms.date: 07/20/2015
helpviewer_keywords:
- access modifiers [C#], accessibility level restrictions
ms.assetid: 987e2f22-46bf-4fea-80ee-270b9cd01045
ms.openlocfilehash: 542e463e41c70f2e8aed5c20dc1294e296a88518
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137006"
---
# <a name="restrictions-on-using-accessibility-levels-c-reference"></a><span data-ttu-id="de2b0-103">Ограничения на использование уровней доступности (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="de2b0-103">Restrictions on using accessibility levels (C# Reference)</span></span>

<span data-ttu-id="de2b0-104">При задании типа в объявлении необходимо проверить, зависит ли уровень доступности типа от уровня доступности члена или другого типа.</span><span class="sxs-lookup"><span data-stu-id="de2b0-104">When you specify a type in a declaration, check whether the accessibility level of the type is dependent on the accessibility level of a member or of another type.</span></span> <span data-ttu-id="de2b0-105">Например, прямой базовый класс должен иметь по крайней мере такой же уровень доступности, как и производный класс.</span><span class="sxs-lookup"><span data-stu-id="de2b0-105">For example, the direct base class must be at least as accessible as the derived class.</span></span> <span data-ttu-id="de2b0-106">Следующие объявления вызывают ошибку компиляции, так как базовый класс `BaseClass` менее доступен, чем `MyClass`:</span><span class="sxs-lookup"><span data-stu-id="de2b0-106">The following declarations cause a compiler error because the base class `BaseClass` is less accessible than `MyClass`:</span></span>

```csharp
class BaseClass {...}
public class MyClass: BaseClass {...} // Error
```

<span data-ttu-id="de2b0-107">В таблице ниже приведены все ограничения на объявленные уровни доступности.</span><span class="sxs-lookup"><span data-stu-id="de2b0-107">The following table summarizes the restrictions on declared accessibility levels.</span></span>

|<span data-ttu-id="de2b0-108">Контекст</span><span class="sxs-lookup"><span data-stu-id="de2b0-108">Context</span></span>|<span data-ttu-id="de2b0-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="de2b0-109">Remarks</span></span>|
|-------------|-------------|
|[<span data-ttu-id="de2b0-110">Классы</span><span class="sxs-lookup"><span data-stu-id="de2b0-110">Classes</span></span>](../../programming-guide/classes-and-structs/classes.md)|<span data-ttu-id="de2b0-111">Прямой базовый класс для типа класса должен иметь по крайней мере такой же уровень доступности, как и сам тип класса.</span><span class="sxs-lookup"><span data-stu-id="de2b0-111">The direct base class of a class type must be at least as accessible as the class type itself.</span></span>|
|[<span data-ttu-id="de2b0-112">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="de2b0-112">Interfaces</span></span>](../../programming-guide/interfaces/index.md)|<span data-ttu-id="de2b0-113">Явные базовые интерфейсы для типа интерфейса должны иметь по крайней мере такой же уровень доступности, как и сам тип интерфейса.</span><span class="sxs-lookup"><span data-stu-id="de2b0-113">The explicit base interfaces of an interface type must be at least as accessible as the interface type itself.</span></span>|
|[<span data-ttu-id="de2b0-114">Делегаты</span><span class="sxs-lookup"><span data-stu-id="de2b0-114">Delegates</span></span>](../../programming-guide/delegates/index.md)|<span data-ttu-id="de2b0-115">Тип возвращаемого значения и типы параметров для типа делегата должны иметь по крайней мере такой же уровень доступности, как и сам тип делегата.</span><span class="sxs-lookup"><span data-stu-id="de2b0-115">The return type and parameter types of a delegate type must be at least as accessible as the delegate type itself.</span></span>|
|[<span data-ttu-id="de2b0-116">Константы</span><span class="sxs-lookup"><span data-stu-id="de2b0-116">Constants</span></span>](../../programming-guide/classes-and-structs/constants.md)|<span data-ttu-id="de2b0-117">Тип константы должен иметь по крайней мере такой же уровень доступности, как и сама константа.</span><span class="sxs-lookup"><span data-stu-id="de2b0-117">The type of a constant must be at least as accessible as the constant itself.</span></span>|
|[<span data-ttu-id="de2b0-118">Поля</span><span class="sxs-lookup"><span data-stu-id="de2b0-118">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)|<span data-ttu-id="de2b0-119">Тип поля должен иметь по крайней мере такой же уровень доступности, как и само поле.</span><span class="sxs-lookup"><span data-stu-id="de2b0-119">The type of a field must be at least as accessible as the field itself.</span></span>|
|[<span data-ttu-id="de2b0-120">Методы</span><span class="sxs-lookup"><span data-stu-id="de2b0-120">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)|<span data-ttu-id="de2b0-121">Тип возвращаемого значения и типы параметров для метода должны иметь по крайней мере такой же уровень доступности, как и сам метод.</span><span class="sxs-lookup"><span data-stu-id="de2b0-121">The return type and parameter types of a method must be at least as accessible as the method itself.</span></span>|
|[<span data-ttu-id="de2b0-122">Свойства</span><span class="sxs-lookup"><span data-stu-id="de2b0-122">Properties</span></span>](../../programming-guide/classes-and-structs/properties.md)|<span data-ttu-id="de2b0-123">Тип свойства должен иметь по крайней мере такой же уровень доступности, как и само свойство.</span><span class="sxs-lookup"><span data-stu-id="de2b0-123">The type of a property must be at least as accessible as the property itself.</span></span>|
|[<span data-ttu-id="de2b0-124">События</span><span class="sxs-lookup"><span data-stu-id="de2b0-124">Events</span></span>](../../programming-guide/events/index.md)|<span data-ttu-id="de2b0-125">Тип события должен иметь по крайней мере такой же уровень доступности, как и само событие.</span><span class="sxs-lookup"><span data-stu-id="de2b0-125">The type of an event must be at least as accessible as the event itself.</span></span>|
|[<span data-ttu-id="de2b0-126">Индексаторы</span><span class="sxs-lookup"><span data-stu-id="de2b0-126">Indexers</span></span>](../../programming-guide/indexers/index.md)|<span data-ttu-id="de2b0-127">Тип и типы параметров для индексатора должны иметь по крайней мере такой же уровень доступности, как и сам индексатор.</span><span class="sxs-lookup"><span data-stu-id="de2b0-127">The type and parameter types of an indexer must be at least as accessible as the indexer itself.</span></span>|
|[<span data-ttu-id="de2b0-128">Операторы</span><span class="sxs-lookup"><span data-stu-id="de2b0-128">Operators</span></span>](../operators/index.md)|<span data-ttu-id="de2b0-129">Тип возвращаемого значения и типы параметров для оператора должны иметь по крайней мере такой же уровень доступности, как и сам оператор.</span><span class="sxs-lookup"><span data-stu-id="de2b0-129">The return type and parameter types of an operator must be at least as accessible as the operator itself.</span></span>|
|[<span data-ttu-id="de2b0-130">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="de2b0-130">Constructors</span></span>](../../programming-guide/classes-and-structs/constructors.md)|<span data-ttu-id="de2b0-131">Типы параметров для конструктора должны иметь по крайней мере такой же уровень доступности, как и сам конструктор.</span><span class="sxs-lookup"><span data-stu-id="de2b0-131">The parameter types of a constructor must be at least as accessible as the constructor itself.</span></span>|

## <a name="example"></a><span data-ttu-id="de2b0-132">Пример</span><span class="sxs-lookup"><span data-stu-id="de2b0-132">Example</span></span>

<span data-ttu-id="de2b0-133">В приведенном ниже примере содержатся ошибочные объявления различных типов.</span><span class="sxs-lookup"><span data-stu-id="de2b0-133">The following example contains erroneous declarations of different types.</span></span> <span data-ttu-id="de2b0-134">В комментарии после каждого объявления указывается предполагаемая ошибка компиляции.</span><span class="sxs-lookup"><span data-stu-id="de2b0-134">The comment following each declaration indicates the expected compiler error.</span></span>

```csharp
// Restrictions on Using Accessibility Levels
// CS0052 expected as well as CS0053, CS0056, and CS0057
// To make the program work, change access level of both class B
// and MyPrivateMethod() to public.

using System;

// A delegate:
delegate int MyDelegate();

class B
{
    // A private method:
    static int MyPrivateMethod()
    {
        return 0;
    }
}

public class A
{
    // Error: The type B is less accessible than the field A.myField.
    public B myField = new B();

    // Error: The type B is less accessible
    // than the constant A.myConst.
    public readonly B myConst = new B();

    public B MyMethod()
    {
        // Error: The type B is less accessible
        // than the method A.MyMethod.
        return new B();
    }

    // Error: The type B is less accessible than the property A.MyProp
    public B MyProp
    {
        set
        {
        }
    }

    MyDelegate d = new MyDelegate(B.MyPrivateMethod);
    // Even when B is declared public, you still get the error:
    // "The parameter B.MyPrivateMethod is not accessible due to
    // protection level."

    public static B operator +(A m1, B m2)
    {
        // Error: The type B is less accessible
        // than the operator A.operator +(A,B)
        return new B();
    }

    static void Main()
    {
        Console.Write("Compiled successfully");
    }
}
```

## <a name="c-language-specification"></a><span data-ttu-id="de2b0-135">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="de2b0-135">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="de2b0-136">См. также</span><span class="sxs-lookup"><span data-stu-id="de2b0-136">See also</span></span>

- [<span data-ttu-id="de2b0-137">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="de2b0-137">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="de2b0-138">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="de2b0-138">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="de2b0-139">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="de2b0-139">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="de2b0-140">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="de2b0-140">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="de2b0-141">Домен доступности</span><span class="sxs-lookup"><span data-stu-id="de2b0-141">Accessibility Domain</span></span>](accessibility-domain.md)
- [<span data-ttu-id="de2b0-142">Уровни доступности</span><span class="sxs-lookup"><span data-stu-id="de2b0-142">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="de2b0-143">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="de2b0-143">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="de2b0-144">public</span><span class="sxs-lookup"><span data-stu-id="de2b0-144">public</span></span>](public.md)
- [<span data-ttu-id="de2b0-145">private</span><span class="sxs-lookup"><span data-stu-id="de2b0-145">private</span></span>](private.md)
- [<span data-ttu-id="de2b0-146">protected</span><span class="sxs-lookup"><span data-stu-id="de2b0-146">protected</span></span>](protected.md)
- [<span data-ttu-id="de2b0-147">internal</span><span class="sxs-lookup"><span data-stu-id="de2b0-147">internal</span></span>](internal.md)
