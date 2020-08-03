---
title: Создание вариантных универсальных интерфейсов (C#)
description: Узнайте, как создать вариативный универсальный интерфейс, который имеет ковариантные или контрвариантные параметры универсального типа.
ms.date: 07/20/2015
ms.assetid: 30330ec4-9df2-4838-a535-6c406d0ed4df
ms.openlocfilehash: 38b32784b681e748cd508c3d431fd4b18ec2c81a
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105724"
---
# <a name="creating-variant-generic-interfaces-c"></a><span data-ttu-id="8f07d-103">Создание вариантных универсальных интерфейсов (C#)</span><span class="sxs-lookup"><span data-stu-id="8f07d-103">Creating Variant Generic Interfaces (C#)</span></span>

<span data-ttu-id="8f07d-104">Параметры универсального типа можно объявить в интерфейсах как ковариантные или контравариантные.</span><span class="sxs-lookup"><span data-stu-id="8f07d-104">You can declare generic type parameters in interfaces as covariant or contravariant.</span></span> <span data-ttu-id="8f07d-105">*Ковариация* позволяет методам интерфейса иметь тип возвращаемого значения, степень наследования которого больше, чем указано в параметрах универсального типа.</span><span class="sxs-lookup"><span data-stu-id="8f07d-105">*Covariance* allows interface methods to have more derived return types than that defined by the generic type parameters.</span></span> <span data-ttu-id="8f07d-106">*Контравариантность* позволяет методам интерфейса иметь типы аргументов, степень наследования которых меньше, чем указано в параметре универсального типа.</span><span class="sxs-lookup"><span data-stu-id="8f07d-106">*Contravariance* allows interface methods to have argument types that are less derived than that specified by the generic parameters.</span></span> <span data-ttu-id="8f07d-107">Универсальный интерфейс, который имеет ковариантные или контравариантные параметры универсального типа, называется *вариантным*.</span><span class="sxs-lookup"><span data-stu-id="8f07d-107">A generic interface that has covariant or contravariant generic type parameters is called *variant*.</span></span>

> [!NOTE]
> <span data-ttu-id="8f07d-108">В платформе .NET Framework 4 появилась поддержка вариативности для нескольких существующих универсальных интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="8f07d-108">.NET Framework 4 introduced variance support for several existing generic interfaces.</span></span> <span data-ttu-id="8f07d-109">Список вариативных интерфейсов в .NET см. в статье [Вариативность в универсальных интерфейсах (C#)](./variance-in-generic-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="8f07d-109">For the list of the variant interfaces in .NET, see [Variance in Generic Interfaces (C#)](./variance-in-generic-interfaces.md).</span></span>

## <a name="declaring-variant-generic-interfaces"></a><span data-ttu-id="8f07d-110">Объявление вариантных универсальных интерфейсов</span><span class="sxs-lookup"><span data-stu-id="8f07d-110">Declaring Variant Generic Interfaces</span></span>

<span data-ttu-id="8f07d-111">Вариантные универсальные интерфейсы можно объявить с помощью ключевых слов `in` и `out` для параметров универсального типа.</span><span class="sxs-lookup"><span data-stu-id="8f07d-111">You can declare variant generic interfaces by using the `in` and `out` keywords for generic type parameters.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8f07d-112">Параметры `ref`, `in` и `out` в C# не могут быть вариантными.</span><span class="sxs-lookup"><span data-stu-id="8f07d-112">`ref`, `in`, and `out` parameters in C# cannot be variant.</span></span> <span data-ttu-id="8f07d-113">Типы значений также не поддерживают вариативность.</span><span class="sxs-lookup"><span data-stu-id="8f07d-113">Value types also do not support variance.</span></span>

<span data-ttu-id="8f07d-114">Для объявления ковариантного параметра универсального типа можно использовать ключевое слово `out`.</span><span class="sxs-lookup"><span data-stu-id="8f07d-114">You can declare a generic type parameter covariant by using the `out` keyword.</span></span> <span data-ttu-id="8f07d-115">Ковариантный тип должен удовлетворять следующим условиям:</span><span class="sxs-lookup"><span data-stu-id="8f07d-115">The covariant type must satisfy the following conditions:</span></span>

- <span data-ttu-id="8f07d-116">Тип используется только в качестве типа значения, возвращаемого методами интерфейса, и не используется в качестве типа аргументов метода.</span><span class="sxs-lookup"><span data-stu-id="8f07d-116">The type is used only as a return type of interface methods and not used as a type of method arguments.</span></span> <span data-ttu-id="8f07d-117">Это показано в следующем примере, в котором тип `R` объявлен ковариантным.</span><span class="sxs-lookup"><span data-stu-id="8f07d-117">This is illustrated in the following example, in which the type `R` is declared covariant.</span></span>

    ```csharp
    interface ICovariant<out R>
    {
        R GetSomething();
        // The following statement generates a compiler error.
        // void SetSomething(R sampleArg);

    }
    ```

    <span data-ttu-id="8f07d-118">Существует одно исключение из данного правила.</span><span class="sxs-lookup"><span data-stu-id="8f07d-118">There is one exception to this rule.</span></span> <span data-ttu-id="8f07d-119">Если в качестве параметра метода используется контравариантный универсальный делегат, этот тип можно использовать в качестве параметра универсального типа для этого делегата.</span><span class="sxs-lookup"><span data-stu-id="8f07d-119">If you have a contravariant generic delegate as a method parameter, you can use the type as a generic type parameter for the delegate.</span></span> <span data-ttu-id="8f07d-120">Это продемонстрировано ниже на примере типа `R`.</span><span class="sxs-lookup"><span data-stu-id="8f07d-120">This is illustrated by the type `R` in the following example.</span></span> <span data-ttu-id="8f07d-121">Дополнительные сведения см. в разделах [Вариативность в делегатах (C#)](./variance-in-delegates.md) и [Использование вариативности в универсальных методах-делегатах Func и Action (C#)](./using-variance-for-func-and-action-generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="8f07d-121">For more information, see [Variance in Delegates (C#)](./variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates (C#)](./using-variance-for-func-and-action-generic-delegates.md).</span></span>

    ```csharp
    interface ICovariant<out R>
    {
        void DoSomething(Action<R> callback);
    }
    ```

- <span data-ttu-id="8f07d-122">Тип не используется в качестве универсального ограничения для методов интерфейса.</span><span class="sxs-lookup"><span data-stu-id="8f07d-122">The type is not used as a generic constraint for the interface methods.</span></span> <span data-ttu-id="8f07d-123">Это демонстрируется в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="8f07d-123">This is illustrated in the following code.</span></span>

    ```csharp
    interface ICovariant<out R>
    {
        // The following statement generates a compiler error
        // because you can use only contravariant or invariant types
        // in generic constraints.
        // void DoSomething<T>() where T : R;
    }
    ```

<span data-ttu-id="8f07d-124">Для объявления контравариантного параметра универсального типа можно использовать ключевое слово `in`.</span><span class="sxs-lookup"><span data-stu-id="8f07d-124">You can declare a generic type parameter contravariant by using the `in` keyword.</span></span> <span data-ttu-id="8f07d-125">Контравариантный тип можно использовать только в качестве типа аргументов метода, но не в качестве типа значения, возвращаемого методами интерфейса.</span><span class="sxs-lookup"><span data-stu-id="8f07d-125">The contravariant type can be used only as a type of method arguments and not as a return type of interface methods.</span></span> <span data-ttu-id="8f07d-126">Контравариантный тип можно также использовать для универсальных ограничений.</span><span class="sxs-lookup"><span data-stu-id="8f07d-126">The contravariant type can also be used for generic constraints.</span></span> <span data-ttu-id="8f07d-127">В следующем примере кода показано объявление контравариантного интерфейса и использование универсального ограничения для одного из его методов.</span><span class="sxs-lookup"><span data-stu-id="8f07d-127">The following code shows how to declare a contravariant interface and use a generic constraint for one of its methods.</span></span>

```csharp
interface IContravariant<in A>
{
    void SetSomething(A sampleArg);
    void DoSomething<T>() where T : A;
    // The following statement generates a compiler error.
    // A GetSomething();
}
```

<span data-ttu-id="8f07d-128">Кроме того, можно реализовать поддержку ковариации и контравариации в одном интерфейсе, но для разных параметров типа, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="8f07d-128">It is also possible to support both covariance and contravariance in the same interface, but for different type parameters, as shown in the following code example.</span></span>

```csharp
interface IVariant<out R, in A>
{
    R GetSomething();
    void SetSomething(A sampleArg);
    R GetSetSomethings(A sampleArg);
}
```

## <a name="implementing-variant-generic-interfaces"></a><span data-ttu-id="8f07d-129">Реализация вариантных универсальных интерфейсов</span><span class="sxs-lookup"><span data-stu-id="8f07d-129">Implementing Variant Generic Interfaces</span></span>

<span data-ttu-id="8f07d-130">Для реализации вариантных универсальных интерфейсов в классах используется тот же синтаксис, что и для инвариантных интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="8f07d-130">You implement variant generic interfaces in classes by using the same syntax that is used for invariant interfaces.</span></span> <span data-ttu-id="8f07d-131">В следующем примере кода показана реализация ковариантного интерфейса в универсальном классе.</span><span class="sxs-lookup"><span data-stu-id="8f07d-131">The following code example shows how to implement a covariant interface in a generic class.</span></span>

```csharp
interface ICovariant<out R>
{
    R GetSomething();
}
class SampleImplementation<R> : ICovariant<R>
{
    public R GetSomething()
    {
        // Some code.
        return default(R);
    }
}
```

<span data-ttu-id="8f07d-132">Классы, которые реализуют вариантные интерфейсы, являются инвариантными.</span><span class="sxs-lookup"><span data-stu-id="8f07d-132">Classes that implement variant interfaces are invariant.</span></span> <span data-ttu-id="8f07d-133">Например, рассмотрим следующий код.</span><span class="sxs-lookup"><span data-stu-id="8f07d-133">For example, consider the following code.</span></span>

```csharp
// The interface is covariant.
ICovariant<Button> ibutton = new SampleImplementation<Button>();
ICovariant<Object> iobj = ibutton;

// The class is invariant.
SampleImplementation<Button> button = new SampleImplementation<Button>();
// The following statement generates a compiler error
// because classes are invariant.
// SampleImplementation<Object> obj = button;
```

## <a name="extending-variant-generic-interfaces"></a><span data-ttu-id="8f07d-134">Расширение вариантных универсальных интерфейсов</span><span class="sxs-lookup"><span data-stu-id="8f07d-134">Extending Variant Generic Interfaces</span></span>

<span data-ttu-id="8f07d-135">При расширении вариантных универсальных интерфейсов необходимо использовать ключевые слова `in` и `out` для явного указания того, поддерживает ли вариативность производный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="8f07d-135">When you extend a variant generic interface, you have to use the `in` and `out` keywords to explicitly specify whether the derived interface supports variance.</span></span> <span data-ttu-id="8f07d-136">Компилятор не подразумевает вариативность интерфейса, который расширяется.</span><span class="sxs-lookup"><span data-stu-id="8f07d-136">The compiler does not infer the variance from the interface that is being extended.</span></span> <span data-ttu-id="8f07d-137">Например, рассмотрим следующие интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="8f07d-137">For example, consider the following interfaces.</span></span>

```csharp
interface ICovariant<out T> { }
interface IInvariant<T> : ICovariant<T> { }
interface IExtCovariant<out T> : ICovariant<T> { }
```

<span data-ttu-id="8f07d-138">В интерфейсе `IInvariant<T>` параметр универсального типа `T` является инвариантным, тогда как в `IExtCovariant<out T>` параметр типа является ковариантным, хотя оба интерфейса расширяют один и тот же интерфейс.</span><span class="sxs-lookup"><span data-stu-id="8f07d-138">In the `IInvariant<T>` interface, the generic type parameter `T` is invariant, whereas in `IExtCovariant<out T>` the type parameter is covariant, although both interfaces extend the same interface.</span></span> <span data-ttu-id="8f07d-139">То же правило применяется к контравариантным параметрам универсального типа.</span><span class="sxs-lookup"><span data-stu-id="8f07d-139">The same rule is applied to contravariant generic type parameters.</span></span>

<span data-ttu-id="8f07d-140">Можно создать интерфейс, который расширяет и интерфейс, в котором параметр универсального типа `T` является ковариантным, и интерфейс, где он является контравариантным, если в расширяемом интерфейсе параметр универсального типа `T` является инвариантным.</span><span class="sxs-lookup"><span data-stu-id="8f07d-140">You can create an interface that extends both the interface where the generic type parameter `T` is covariant and the interface where it is contravariant if in the extending interface the generic type parameter `T` is invariant.</span></span> <span data-ttu-id="8f07d-141">Это показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="8f07d-141">This is illustrated in the following code example.</span></span>

```csharp
interface ICovariant<out T> { }
interface IContravariant<in T> { }
interface IInvariant<T> : ICovariant<T>, IContravariant<T> { }
```

<span data-ttu-id="8f07d-142">Тем не менее, если параметр универсального типа `T` объявлен ковариантным в одном интерфейсе, его нельзя объявить контравариантным в расширенном интерфейсе и наоборот.</span><span class="sxs-lookup"><span data-stu-id="8f07d-142">However, if a generic type parameter `T` is declared covariant in one interface, you cannot declare it contravariant in the extending interface, or vice versa.</span></span> <span data-ttu-id="8f07d-143">Это показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="8f07d-143">This is illustrated in the following code example.</span></span>

```csharp
interface ICovariant<out T> { }
// The following statement generates a compiler error.
// interface ICoContraVariant<in T> : ICovariant<T> { }
```

### <a name="avoiding-ambiguity"></a><span data-ttu-id="8f07d-144">Недопущение неоднозначности</span><span class="sxs-lookup"><span data-stu-id="8f07d-144">Avoiding Ambiguity</span></span>

<span data-ttu-id="8f07d-145">При реализации вариантных универсальных интерфейсов вариативность может приводить к неоднозначности.</span><span class="sxs-lookup"><span data-stu-id="8f07d-145">When you implement variant generic interfaces, variance can sometimes lead to ambiguity.</span></span> <span data-ttu-id="8f07d-146">Такой неоднозначности следует избегать.</span><span class="sxs-lookup"><span data-stu-id="8f07d-146">Such ambiguity should be avoided.</span></span>

<span data-ttu-id="8f07d-147">Например, если вы явно реализуете один вариантный универсальный интерфейс с разными параметрами универсального типа в одном классе, это может создавать неоднозначность.</span><span class="sxs-lookup"><span data-stu-id="8f07d-147">For example, if you explicitly implement the same variant generic interface with different generic type parameters in one class, it can create ambiguity.</span></span> <span data-ttu-id="8f07d-148">Компилятор не сообщает об ошибке в данном случае, но и не указывает, какая реализация интерфейса будет выбрана во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="8f07d-148">The compiler does not produce an error in this case, but it's not specified which interface implementation will be chosen at run time.</span></span> <span data-ttu-id="8f07d-149">Такая неоднозначность может привести к возникновению неявных ошибок в коде.</span><span class="sxs-lookup"><span data-stu-id="8f07d-149">This ambiguity could lead to subtle bugs in your code.</span></span> <span data-ttu-id="8f07d-150">Рассмотрим следующий пример кода:</span><span class="sxs-lookup"><span data-stu-id="8f07d-150">Consider the following code example.</span></span>

```csharp
// Simple class hierarchy.
class Animal { }
class Cat : Animal { }
class Dog : Animal { }

// This class introduces ambiguity
// because IEnumerable<out T> is covariant.
class Pets : IEnumerable<Cat>, IEnumerable<Dog>
{
    IEnumerator<Cat> IEnumerable<Cat>.GetEnumerator()
    {
        Console.WriteLine("Cat");
        // Some code.
        return null;
    }

    IEnumerator IEnumerable.GetEnumerator()
    {
        // Some code.
        return null;
    }

    IEnumerator<Dog> IEnumerable<Dog>.GetEnumerator()
    {
        Console.WriteLine("Dog");
        // Some code.
        return null;
    }
}
class Program
{
    public static void Test()
    {
        IEnumerable<Animal> pets = new Pets();
        pets.GetEnumerator();
    }
}
```

<span data-ttu-id="8f07d-151">В этом примере не указано, каким образом метод `pets.GetEnumerator` делает выбор между `Cat` и `Dog`.</span><span class="sxs-lookup"><span data-stu-id="8f07d-151">In this example, it is unspecified how the `pets.GetEnumerator` method chooses between `Cat` and `Dog`.</span></span> <span data-ttu-id="8f07d-152">Это может вызвать проблемы в вашем коде.</span><span class="sxs-lookup"><span data-stu-id="8f07d-152">This could cause problems in your code.</span></span>

## <a name="see-also"></a><span data-ttu-id="8f07d-153">См. также</span><span class="sxs-lookup"><span data-stu-id="8f07d-153">See also</span></span>

- [<span data-ttu-id="8f07d-154">Вариативность в универсальных интерфейсах (C#)</span><span class="sxs-lookup"><span data-stu-id="8f07d-154">Variance in Generic Interfaces (C#)</span></span>](./variance-in-generic-interfaces.md)
- [<span data-ttu-id="8f07d-155">Использование вариативности в универсальных методах-делегатах Func и Action (C#)</span><span class="sxs-lookup"><span data-stu-id="8f07d-155">Using Variance for Func and Action Generic Delegates (C#)</span></span>](./using-variance-for-func-and-action-generic-delegates.md)
