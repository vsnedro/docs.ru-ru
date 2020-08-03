---
title: Объектно ориентированное программирование (C#)
description: C# обеспечивает полную поддержку объектно ориентированного программирования, включая абстракцию, инкапсуляцию, наследование и полиморфизм.
ms.date: 05/13/2020
ms.assetid: 89574786-65ef-4335-88bc-fbacd094f183
ms.openlocfilehash: 0c5495aefad73a2916ad6e2bd2bf3701d0868f24
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302819"
---
# <a name="object-oriented-programming-c"></a><span data-ttu-id="df5b8-103">Объектно-ориентированное программирование (C#)</span><span class="sxs-lookup"><span data-stu-id="df5b8-103">Object-Oriented programming (C#)</span></span>

<span data-ttu-id="df5b8-104">C# обеспечивает полную поддержку объектно ориентированного программирования, включая абстракцию, инкапсуляцию, наследование и полиморфизм.</span><span class="sxs-lookup"><span data-stu-id="df5b8-104">C# provides full support for object-oriented programming including abstraction, encapsulation, inheritance, and polymorphism.</span></span>

- <span data-ttu-id="df5b8-105">*Абстракция* означает скрытие ненужных сведений от потребителей типов.</span><span class="sxs-lookup"><span data-stu-id="df5b8-105">*Abstraction* means hiding the unnecessary details from type consumers.</span></span>
- <span data-ttu-id="df5b8-106">*Инкапсуляция* означает, что группа связанных свойств, методов и других членов рассматривается как единый элемент или объект.</span><span class="sxs-lookup"><span data-stu-id="df5b8-106">*Encapsulation* means that a group of related properties, methods, and other members are treated as a single unit or object.</span></span>
- <span data-ttu-id="df5b8-107">*Наследование* описывает возможность создания новых классов на основе существующих классов.</span><span class="sxs-lookup"><span data-stu-id="df5b8-107">*Inheritance* describes the ability to create new classes based on an existing class.</span></span>
- <span data-ttu-id="df5b8-108">*Полиморфизм* означает, что можно иметь несколько взаимозаменяемых классов, даже если каждый класс реализует одни и те же свойства или методы разными способами.</span><span class="sxs-lookup"><span data-stu-id="df5b8-108">*Polymorphism* means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.</span></span>

## <a name="classes-and-objects"></a><span data-ttu-id="df5b8-109">Классы и объекты</span><span class="sxs-lookup"><span data-stu-id="df5b8-109">Classes and objects</span></span>

<span data-ttu-id="df5b8-110">Термины *класс* и *объект* описывают *тип* объектов и *экземпляры* классов, соответственно.</span><span class="sxs-lookup"><span data-stu-id="df5b8-110">The terms *class* and *object* describe the *type* of objects, and the *instances* of classes, respectively.</span></span> <span data-ttu-id="df5b8-111">Поэтому процесс создания объекта называется *созданием экземпляра*.</span><span class="sxs-lookup"><span data-stu-id="df5b8-111">So, the act of creating an object is called *instantiation*.</span></span> <span data-ttu-id="df5b8-112">Если использовать сравнение с чертежом, то класс является чертежом, а объект является зданием, построенным по нему.</span><span class="sxs-lookup"><span data-stu-id="df5b8-112">Using the blueprint analogy, a class is a blueprint, and an object is a building made from that blueprint.</span></span>

<span data-ttu-id="df5b8-113">Определение класса:</span><span class="sxs-lookup"><span data-stu-id="df5b8-113">To define a class:</span></span>

```csharp
class SampleClass
{
}
```

<span data-ttu-id="df5b8-114">C# также предоставляет типы, называемые *структурами*, которые удобно использовать, когда не требуется поддержка наследования или полиморфизма.</span><span class="sxs-lookup"><span data-stu-id="df5b8-114">C# also provides types called *structures* that are useful when you don't need support for inheritance or polymorphism.</span></span> <span data-ttu-id="df5b8-115">Дополнительные сведения см. в статье [Выбор между классом и структурой](../../../standard/design-guidelines/choosing-between-class-and-struct.md).</span><span class="sxs-lookup"><span data-stu-id="df5b8-115">For more information, see [Choosing between class and struct](../../../standard/design-guidelines/choosing-between-class-and-struct.md).</span></span>

<span data-ttu-id="df5b8-116">Определение структуры:</span><span class="sxs-lookup"><span data-stu-id="df5b8-116">To define a structure:</span></span>

```csharp
struct SampleStruct
{
}
```

<span data-ttu-id="df5b8-117">Дополнительные сведения см. в статьях, посвященных ключевым словам [class](../../language-reference/keywords/class.md) и [struct](../../language-reference/builtin-types/struct.md).</span><span class="sxs-lookup"><span data-stu-id="df5b8-117">For more information, see the articles on the [class](../../language-reference/keywords/class.md) and [struct](../../language-reference/builtin-types/struct.md) keywords.</span></span>

### <a name="class-members"></a><span data-ttu-id="df5b8-118">Члены класса</span><span class="sxs-lookup"><span data-stu-id="df5b8-118">Class members</span></span>

<span data-ttu-id="df5b8-119">Каждый класс может состоять из различных *членов класса*, которые содержат свойства, описывающие данные класса, методы, задающие поведение класса, и события, обеспечивающие связь между различными классами и объектами.</span><span class="sxs-lookup"><span data-stu-id="df5b8-119">Each class can have different *class members* that include properties that describe class data, methods that define class behavior, and events that provide communication between different classes and objects.</span></span>

#### <a name="properties-and-fields"></a><span data-ttu-id="df5b8-120">Свойства и поля</span><span class="sxs-lookup"><span data-stu-id="df5b8-120">Properties and fields</span></span>

<span data-ttu-id="df5b8-121">Поля и свойства представляют сведения, содержащиеся в объекте.</span><span class="sxs-lookup"><span data-stu-id="df5b8-121">Fields and properties represent information that an object contains.</span></span> <span data-ttu-id="df5b8-122">Поля подобны переменным в том, что их можно прочитать или изменить напрямую с использованием применимых модификаторов доступа.</span><span class="sxs-lookup"><span data-stu-id="df5b8-122">Fields are like variables because they can be read or set directly, subject to applicable access modifiers.</span></span>

<span data-ttu-id="df5b8-123">Определение поля, доступ к которому можно получить из экземпляров класса:</span><span class="sxs-lookup"><span data-stu-id="df5b8-123">To define a field that can be accessed from within instances of the class:</span></span>

```csharp
public class SampleClass
{
    string sampleField;
}
```

<span data-ttu-id="df5b8-124">Для работы со свойствами используются методы доступа `get` и `set`, которые расширяют возможности управления способом задания и возврата значений.</span><span class="sxs-lookup"><span data-stu-id="df5b8-124">Properties have `get` and `set` accessors, which provide more control on how values are set or returned.</span></span>

<span data-ttu-id="df5b8-125">В языке C# для хранения значения свойства можно создать частное поле (private) или использовать автоматически реализуемые свойства, которые автоматически создают такое поле и обеспечивают базовую логику для процедур свойств.</span><span class="sxs-lookup"><span data-stu-id="df5b8-125">C# allows you either to create a private field for storing the property value or use auto-implemented properties that create this field automatically behind the scenes and provide the basic logic for the property procedures.</span></span>

<span data-ttu-id="df5b8-126">Определение автоматически реализуемого свойства:</span><span class="sxs-lookup"><span data-stu-id="df5b8-126">To define an auto-implemented property:</span></span>

```csharp
class SampleClass
{
    public int SampleProperty { get; set; }
}
```

<span data-ttu-id="df5b8-127">Если требуется выполнить дополнительные операции чтения и записи применительно к значению свойства, определите поле для хранения значения свойства и затем реализуйте базовую логику для хранения и извлечения этого значения:</span><span class="sxs-lookup"><span data-stu-id="df5b8-127">If you need to perform some additional operations for reading and writing the property value, define a field for storing the property value and provide the basic logic for storing and retrieving it:</span></span>

```csharp
class SampleClass
{
    private int _sample;
    public int Sample
    {
        // Return the value stored in a field.
        get => _sample;
        // Store the value in the field.
        set =>  _sample = value;
    }
}
```

<span data-ttu-id="df5b8-128">У большинства свойств есть методы или процедуры для задания и возврата значения свойства.</span><span class="sxs-lookup"><span data-stu-id="df5b8-128">Most properties have methods or procedures to both set and get the property value.</span></span> <span data-ttu-id="df5b8-129">Однако можно создать свойства, доступные только для чтения или только на запись, чтобы запретить изменение или чтение значений свойств.</span><span class="sxs-lookup"><span data-stu-id="df5b8-129">However, you can create read-only or write-only properties to restrict them from being modified or read.</span></span> <span data-ttu-id="df5b8-130">В C# можно опустить метод свойства `get` или `set`.</span><span class="sxs-lookup"><span data-stu-id="df5b8-130">In C#, you can omit the `get` or `set` property method.</span></span> <span data-ttu-id="df5b8-131">Следует отметить, что автоматически реализуемые свойства не могут быть доступными только для записи.</span><span class="sxs-lookup"><span data-stu-id="df5b8-131">However, auto-implemented properties cannot be write-only.</span></span> <span data-ttu-id="df5b8-132">Автоматически реализуемые свойства, доступные только для чтения, можно задать в конструкторах содержащего класса.</span><span class="sxs-lookup"><span data-stu-id="df5b8-132">Read-only auto-implemented properties can be set in constructors of the containing class.</span></span>

<span data-ttu-id="df5b8-133">Дополнительные сведения можно найти в разделе</span><span class="sxs-lookup"><span data-stu-id="df5b8-133">For more information, see:</span></span>

- [<span data-ttu-id="df5b8-134">get</span><span class="sxs-lookup"><span data-stu-id="df5b8-134">get</span></span>](../../language-reference/keywords/get.md)
- [<span data-ttu-id="df5b8-135">set</span><span class="sxs-lookup"><span data-stu-id="df5b8-135">set</span></span>](../../language-reference/keywords/set.md)

#### <a name="methods"></a><span data-ttu-id="df5b8-136">Методы</span><span class="sxs-lookup"><span data-stu-id="df5b8-136">Methods</span></span>

<span data-ttu-id="df5b8-137">Действие, которое выполняет объект, называется *методом*.</span><span class="sxs-lookup"><span data-stu-id="df5b8-137">A *method* is an action that an object can perform.</span></span>

<span data-ttu-id="df5b8-138">Определение метода класса:</span><span class="sxs-lookup"><span data-stu-id="df5b8-138">To define a method of a class:</span></span>

```csharp
class SampleClass
{
    public int SampleMethod(string sampleParam)
    {
        // Insert code here
    }
}
```

<span data-ttu-id="df5b8-139">Класс может иметь несколько реализаций или *перегрузок* одного и того же метода, которые отличаются от других числом или типами параметров.</span><span class="sxs-lookup"><span data-stu-id="df5b8-139">A class can have several implementations, or *overloads*, of the same method that differ in the number of parameters or parameter types.</span></span>

<span data-ttu-id="df5b8-140">Перегрузка метода:</span><span class="sxs-lookup"><span data-stu-id="df5b8-140">To overload a method:</span></span>

```csharp
public int SampleMethod(string sampleParam) { }
public int SampleMethod(int sampleParam) { }
```

<span data-ttu-id="df5b8-141">Как правило, метод объявляется при определении класса.</span><span class="sxs-lookup"><span data-stu-id="df5b8-141">In most cases you declare a method within a class definition.</span></span> <span data-ttu-id="df5b8-142">Однако C# также поддерживает *методы расширения*, которые позволяют добавлять методы в существующий класс вне определения класса.</span><span class="sxs-lookup"><span data-stu-id="df5b8-142">However, C# also supports *extension methods* that allow you to add methods to an existing class outside the actual definition of the class.</span></span>

<span data-ttu-id="df5b8-143">Дополнительные сведения можно найти в разделе</span><span class="sxs-lookup"><span data-stu-id="df5b8-143">For more information, see:</span></span>

- [<span data-ttu-id="df5b8-144">Методы</span><span class="sxs-lookup"><span data-stu-id="df5b8-144">Methods</span></span>](../classes-and-structs/methods.md)
- [<span data-ttu-id="df5b8-145">Методы расширения</span><span class="sxs-lookup"><span data-stu-id="df5b8-145">Extension Methods</span></span>](../classes-and-structs/extension-methods.md)

#### <a name="constructors"></a><span data-ttu-id="df5b8-146">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="df5b8-146">Constructors</span></span>

<span data-ttu-id="df5b8-147">Конструкторы — это методы классов, выполняемые автоматически при создании объекта заданного типа.</span><span class="sxs-lookup"><span data-stu-id="df5b8-147">Constructors are class methods that are executed automatically when an object of a given type is created.</span></span> <span data-ttu-id="df5b8-148">Обычно конструкторы выполняют инициализацию членов данных нового объекта.</span><span class="sxs-lookup"><span data-stu-id="df5b8-148">Constructors usually initialize the data members of the new object.</span></span> <span data-ttu-id="df5b8-149">Конструктор можно запустить только один раз при создании класса.</span><span class="sxs-lookup"><span data-stu-id="df5b8-149">A constructor can run only once when a class is created.</span></span> <span data-ttu-id="df5b8-150">Кроме того, код конструктора всегда выполняется раньше всех остальных частей кода в классе.</span><span class="sxs-lookup"><span data-stu-id="df5b8-150">Furthermore, the code in the constructor always runs before any other code in a class.</span></span> <span data-ttu-id="df5b8-151">Следует отметить, что так же, как и для других методов, можно создать несколько перегрузок конструктора.</span><span class="sxs-lookup"><span data-stu-id="df5b8-151">However, you can create multiple constructor overloads in the same way as for any other method.</span></span>

<span data-ttu-id="df5b8-152">Определение конструктора для класса:</span><span class="sxs-lookup"><span data-stu-id="df5b8-152">To define a constructor for a class:</span></span>

```csharp
public class SampleClass
{
    public SampleClass()
    {
        // Add code here
    }
}
```

<span data-ttu-id="df5b8-153">Дополнительные сведения см. в разделе [Конструкторы](../classes-and-structs/constructors.md).</span><span class="sxs-lookup"><span data-stu-id="df5b8-153">For more information, see [Constructors](../classes-and-structs/constructors.md).</span></span>

#### <a name="finalizers"></a><span data-ttu-id="df5b8-154">Методы завершения</span><span class="sxs-lookup"><span data-stu-id="df5b8-154">Finalizers</span></span>

<span data-ttu-id="df5b8-155">Метод завершения используется для уничтожения экземпляров классов.</span><span class="sxs-lookup"><span data-stu-id="df5b8-155">A finalizer is used to destruct instances of classes.</span></span> <span data-ttu-id="df5b8-156">На платформе .NET сборщик мусора автоматически управляет распределением и освобождением памяти для управляемых объектов приложения.</span><span class="sxs-lookup"><span data-stu-id="df5b8-156">In .NET, the garbage collector automatically manages the allocation and release of memory for the managed objects in your application.</span></span> <span data-ttu-id="df5b8-157">Однако для очистки неуправляемых ресурсов, создаваемых приложением, могут потребоваться методы завершения.</span><span class="sxs-lookup"><span data-stu-id="df5b8-157">However, you may still need finalizers to clean up any unmanaged resources that your application creates.</span></span> <span data-ttu-id="df5b8-158">На один класс допускается только один метод завершения.</span><span class="sxs-lookup"><span data-stu-id="df5b8-158">There can be only one finalizer for a class.</span></span>

<span data-ttu-id="df5b8-159">Дополнительные сведения о методах завершения и сборке мусора в .NET см. в статье [Сборка мусора](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="df5b8-159">For more information about finalizers and garbage collection in .NET, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>

#### <a name="events"></a><span data-ttu-id="df5b8-160">События</span><span class="sxs-lookup"><span data-stu-id="df5b8-160">Events</span></span>

<span data-ttu-id="df5b8-161">События позволяют классу или объекту уведомлять другие классы или объекты о возникновении каких-либо ситуаций.</span><span class="sxs-lookup"><span data-stu-id="df5b8-161">Events enable a class or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="df5b8-162">Класс, отправляющий (или порождающий) событие, называется *издателем*, а классы, принимающие (или обрабатывающие) событие, называются *подписчиками*.</span><span class="sxs-lookup"><span data-stu-id="df5b8-162">The class that sends (or raises) the event is called the *publisher* and the classes that receive (or handle) the event are called *subscribers*.</span></span> <span data-ttu-id="df5b8-163">Дополнительные сведения о том, как порождаются и обрабатываются события, см. в разделе [События](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="df5b8-163">For more information about events, how they are raised and handled, see [Events](../../../standard/events/index.md).</span></span>

- <span data-ttu-id="df5b8-164">Чтобы объявить событие в классе, используйте ключевое слово [event](../../language-reference/keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="df5b8-164">To declare an event in a class, use the [event](../../language-reference/keywords/event.md) keyword.</span></span>
- <span data-ttu-id="df5b8-165">Чтобы породить событие, вызовите делегат события.</span><span class="sxs-lookup"><span data-stu-id="df5b8-165">To raise an event, invoke the event delegate.</span></span>
- <span data-ttu-id="df5b8-166">Чтобы подписаться на событие, используйте оператор `+=`. Чтобы отменить подписку на событие, воспользуйтесь оператором `-=`.</span><span class="sxs-lookup"><span data-stu-id="df5b8-166">To subscribe to an event, use the `+=` operator; to unsubscribe from an event, use the `-=` operator.</span></span>

#### <a name="nested-classes"></a><span data-ttu-id="df5b8-167">Вложенные классы</span><span class="sxs-lookup"><span data-stu-id="df5b8-167">Nested classes</span></span>

<span data-ttu-id="df5b8-168">Класс, определенный внутри другого класса, называется *вложенным*.</span><span class="sxs-lookup"><span data-stu-id="df5b8-168">A class defined within another class is called *nested*.</span></span> <span data-ttu-id="df5b8-169">По умолчанию вложенный класс является частным.</span><span class="sxs-lookup"><span data-stu-id="df5b8-169">By default, the nested class is private.</span></span>

```csharp
class Container
{
    class Nested
    {
        // Add code here.
    }
}
```

<span data-ttu-id="df5b8-170">Чтобы создать экземпляр вложенного класса, укажите имя класса контейнера и имя вложенного класса, используя в качестве разделителя точку:</span><span class="sxs-lookup"><span data-stu-id="df5b8-170">To create an instance of the nested class, use the name of the container class followed by the dot and then followed by the name of the nested class:</span></span>

```csharp
Container.Nested nestedInstance = new Container.Nested()
```

### <a name="access-modifiers-and-access-levels"></a><span data-ttu-id="df5b8-171">Модификаторы доступа и уровни доступа</span><span class="sxs-lookup"><span data-stu-id="df5b8-171">Access modifiers and access levels</span></span>

<span data-ttu-id="df5b8-172">С помощью *модификаторов доступа* все классы и члены классов могут указывать уровни доступа, предоставляемые другим классам.</span><span class="sxs-lookup"><span data-stu-id="df5b8-172">All classes and class members can specify what access level they provide to other classes by using *access modifiers*.</span></span>

<span data-ttu-id="df5b8-173">Имеющиеся модификаторы доступа указаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="df5b8-173">The following access modifiers are available:</span></span>

| <span data-ttu-id="df5b8-174">Модификатор C#</span><span class="sxs-lookup"><span data-stu-id="df5b8-174">C# Modifier</span></span> | <span data-ttu-id="df5b8-175">Определение</span><span class="sxs-lookup"><span data-stu-id="df5b8-175">Definition</span></span> |
|--|--|
| [<span data-ttu-id="df5b8-176">public</span><span class="sxs-lookup"><span data-stu-id="df5b8-176">public</span></span>](../../language-reference/keywords/public.md) | <span data-ttu-id="df5b8-177">Доступ к типу или члену возможен из любого другого кода в той же сборке или другой сборке, ссылающейся на него.</span><span class="sxs-lookup"><span data-stu-id="df5b8-177">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span> |
| [<span data-ttu-id="df5b8-178">private</span><span class="sxs-lookup"><span data-stu-id="df5b8-178">private</span></span>](../../language-reference/keywords/private.md) | <span data-ttu-id="df5b8-179">Доступ к типу или члену можно получить только из кода в том же классе.</span><span class="sxs-lookup"><span data-stu-id="df5b8-179">The type or member can only be accessed by code in the same class.</span></span> |
| [<span data-ttu-id="df5b8-180">protected</span><span class="sxs-lookup"><span data-stu-id="df5b8-180">protected</span></span>](../../language-reference/keywords/protected.md) | <span data-ttu-id="df5b8-181">Доступ к типу или члену можно получить только из кода в том же классе или в производном классе.</span><span class="sxs-lookup"><span data-stu-id="df5b8-181">The type or member can only be accessed by code in the same class or in a derived class.</span></span> |
| [<span data-ttu-id="df5b8-182">internal</span><span class="sxs-lookup"><span data-stu-id="df5b8-182">internal</span></span>](../../language-reference/keywords/internal.md) | <span data-ttu-id="df5b8-183">Доступ к типу или члену возможен из любого кода в той же сборке, но не из другой сборки.</span><span class="sxs-lookup"><span data-stu-id="df5b8-183">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span> |
| [<span data-ttu-id="df5b8-184">protected internal</span><span class="sxs-lookup"><span data-stu-id="df5b8-184">protected internal</span></span>](../../language-reference/keywords/protected-internal.md) | <span data-ttu-id="df5b8-185">Доступ к типу или члену возможен из любого кода в той же сборке, или из производного класса в другой сборке.</span><span class="sxs-lookup"><span data-stu-id="df5b8-185">The type or member can be accessed by any code in the same assembly, or by any derived class in another assembly.</span></span> |
| [<span data-ttu-id="df5b8-186">private protected</span><span class="sxs-lookup"><span data-stu-id="df5b8-186">private protected</span></span>](../../language-reference/keywords/private-protected.md) | <span data-ttu-id="df5b8-187">Доступ к типу или члену можно получить из кода в том же классе или в производном классе в сборке базового класса.</span><span class="sxs-lookup"><span data-stu-id="df5b8-187">The type or member can be accessed by code in the same class or in a derived class within the base class assembly.</span></span> |

<span data-ttu-id="df5b8-188">Дополнительные сведения см. в статье [Модификаторы доступа](../classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="df5b8-188">For more information, see [Access Modifiers](../classes-and-structs/access-modifiers.md).</span></span>

### <a name="instantiating-classes"></a><span data-ttu-id="df5b8-189">Создание экземпляров классов</span><span class="sxs-lookup"><span data-stu-id="df5b8-189">Instantiating classes</span></span>

<span data-ttu-id="df5b8-190">Чтобы создать объект, необходимо создать экземпляр класса.</span><span class="sxs-lookup"><span data-stu-id="df5b8-190">To create an object, you need to instantiate a class, or create a class instance.</span></span>

```csharp
SampleClass sampleObject = new SampleClass();
```

<span data-ttu-id="df5b8-191">После создания экземпляра класса можно присваивать значения свойствам и полям экземпляра и вызывать методы класса.</span><span class="sxs-lookup"><span data-stu-id="df5b8-191">After instantiating a class, you can assign values to the instance's properties and fields and invoke class methods.</span></span>

```csharp
// Set a property value.
sampleObject.sampleProperty = "Sample String";
// Call a method.
sampleObject.SampleMethod();
```

<span data-ttu-id="df5b8-192">Чтобы назначить значения свойствам в процессе создания экземпляра класса, используйте инициализаторы объектов:</span><span class="sxs-lookup"><span data-stu-id="df5b8-192">To assign values to properties during the class instantiation process, use object initializers:</span></span>

```csharp
// Set a property value.
var sampleObject = new SampleClass
{
    FirstProperty = "A",
    SecondProperty = "B"
};
```

<span data-ttu-id="df5b8-193">Дополнительные сведения можно найти в разделе</span><span class="sxs-lookup"><span data-stu-id="df5b8-193">For more information, see:</span></span>

- [<span data-ttu-id="df5b8-194">Оператор new</span><span class="sxs-lookup"><span data-stu-id="df5b8-194">new Operator</span></span>](../../language-reference/operators/new-operator.md)
- [<span data-ttu-id="df5b8-195">Инициализаторы объектов и коллекций</span><span class="sxs-lookup"><span data-stu-id="df5b8-195">Object and Collection Initializers</span></span>](../classes-and-structs/object-and-collection-initializers.md)

### <a name="static-classes-and-members"></a><span data-ttu-id="df5b8-196">статические классы и их члены;</span><span class="sxs-lookup"><span data-stu-id="df5b8-196">Static Classes and Members</span></span>

<span data-ttu-id="df5b8-197">Статический член класса — это свойство, процедура или поле, которое совместно используется всеми экземплярами класса.</span><span class="sxs-lookup"><span data-stu-id="df5b8-197">A static member of the class is a property, procedure, or field that is shared by all instances of a class.</span></span>

<span data-ttu-id="df5b8-198">Определение статического члена</span><span class="sxs-lookup"><span data-stu-id="df5b8-198">To define a static member:</span></span>

```csharp
static class SampleClass
{
    public static string SampleString = "Sample String";
}
```

<span data-ttu-id="df5b8-199">Чтобы получить доступ к статическому члену, используйте имя класса без создания объекта этого класса:</span><span class="sxs-lookup"><span data-stu-id="df5b8-199">To access the static member, use the name of the class without creating an object of this class:</span></span>

```csharp
Console.WriteLine(SampleClass.SampleString);
```

<span data-ttu-id="df5b8-200">Статические классы в C# имеют только статические члены и не могут быть созданы.</span><span class="sxs-lookup"><span data-stu-id="df5b8-200">Static  classes in C# have static members only and cannot be instantiated.</span></span> <span data-ttu-id="df5b8-201">Статические члены также не могут обращаться к нестатическим свойствам, полям или методам.</span><span class="sxs-lookup"><span data-stu-id="df5b8-201">Static members also cannot access non-static  properties, fields or methods</span></span>

<span data-ttu-id="df5b8-202">Дополнительные сведения см. в разделе [static](../../language-reference/keywords/static.md).</span><span class="sxs-lookup"><span data-stu-id="df5b8-202">For more information, see: [static](../../language-reference/keywords/static.md).</span></span>

### <a name="anonymous-types"></a><span data-ttu-id="df5b8-203">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="df5b8-203">Anonymous types</span></span>

<span data-ttu-id="df5b8-204">Анонимные типы позволяют создавать объекты без написания определения класса для типа данных.</span><span class="sxs-lookup"><span data-stu-id="df5b8-204">Anonymous types enable you to create objects without writing a class definition for the data type.</span></span> <span data-ttu-id="df5b8-205">Вместо этого компилятор создает класс для вас.</span><span class="sxs-lookup"><span data-stu-id="df5b8-205">Instead, the compiler generates a class for you.</span></span> <span data-ttu-id="df5b8-206">Данный класс не имеет имени и содержит свойства, которые указаны при объявлении объекта.</span><span class="sxs-lookup"><span data-stu-id="df5b8-206">The class has no usable name and contains the properties you specify in declaring the object.</span></span>

<span data-ttu-id="df5b8-207">Создание экземпляра анонимного типа:</span><span class="sxs-lookup"><span data-stu-id="df5b8-207">To create an instance of an anonymous type:</span></span>

```csharp
// sampleObject is an instance of a simple anonymous type.
var sampleObject = new
{
    FirstProperty = "A",
    SecondProperty = "B"
};
```

<span data-ttu-id="df5b8-208">Дополнительные сведения можно найти в разделе  [Анонимные типы](../classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="df5b8-208">For more information, see: [Anonymous Types](../classes-and-structs/anonymous-types.md).</span></span>

## <a name="inheritance"></a><span data-ttu-id="df5b8-209">Наследование</span><span class="sxs-lookup"><span data-stu-id="df5b8-209">Inheritance</span></span>

<span data-ttu-id="df5b8-210">Наследование позволяет создавать новые классы, которые повторно используют, расширяют и изменяют поведение, определенное в другом классе.</span><span class="sxs-lookup"><span data-stu-id="df5b8-210">Inheritance enables you to create a new class that reuses, extends, and modifies the behavior that is defined in another class.</span></span> <span data-ttu-id="df5b8-211">Класс, члены которого наследуются, называется *базовым классом*, а класс, который наследует эти члены, называется *производным классом*.</span><span class="sxs-lookup"><span data-stu-id="df5b8-211">The class whose members are inherited is called the *base class*, and the class that inherits those members is called the *derived class*.</span></span> <span data-ttu-id="df5b8-212">Следует учитывать, что все классы в C# неявно наследуются от класса <xref:System.Object>, который поддерживает иерархию классов .NET и предоставляет низкоуровневые службы для всех классов.</span><span class="sxs-lookup"><span data-stu-id="df5b8-212">However, all classes in C# implicitly inherit from the <xref:System.Object> class that supports .NET class hierarchy and provides low-level services to all classes.</span></span>

> [!NOTE]
> <span data-ttu-id="df5b8-213">C# не поддерживает множественное наследование.</span><span class="sxs-lookup"><span data-stu-id="df5b8-213">C# doesn't support multiple inheritance.</span></span> <span data-ttu-id="df5b8-214">То есть можно указать только один базовый класс для производного класса.</span><span class="sxs-lookup"><span data-stu-id="df5b8-214">That is, you can specify only one base class for a derived class.</span></span>

<span data-ttu-id="df5b8-215">Наследование от базового класса:</span><span class="sxs-lookup"><span data-stu-id="df5b8-215">To inherit from a base class:</span></span>

```csharp
class DerivedClass:BaseClass { }
```

<span data-ttu-id="df5b8-216">По умолчанию унаследовать класс можно от любого класса.</span><span class="sxs-lookup"><span data-stu-id="df5b8-216">By default all classes can be inherited.</span></span> <span data-ttu-id="df5b8-217">Однако можно указать, должен ли класс использоваться в качестве базового класса, или создать класс, который может использоваться только в качестве базового.</span><span class="sxs-lookup"><span data-stu-id="df5b8-217">However, you can specify whether a class must not be used as a base class, or create a class that can be used as a base class only.</span></span>

<span data-ttu-id="df5b8-218">Указание, что класс не может использоваться в качестве базового класса:</span><span class="sxs-lookup"><span data-stu-id="df5b8-218">To specify that a class cannot be used as a base class:</span></span>

```csharp
public sealed class A { }
```

<span data-ttu-id="df5b8-219">Указание, что класс может использоваться только в качестве базового класса и нельзя создать экземпляр этого класса:</span><span class="sxs-lookup"><span data-stu-id="df5b8-219">To specify that a class can be used as a base class only and cannot be instantiated:</span></span>

```csharp
public abstract class B { }
```

<span data-ttu-id="df5b8-220">Дополнительные сведения можно найти в разделе</span><span class="sxs-lookup"><span data-stu-id="df5b8-220">For more information, see:</span></span>

- [<span data-ttu-id="df5b8-221">sealed</span><span class="sxs-lookup"><span data-stu-id="df5b8-221">sealed</span></span>](../../language-reference/keywords/sealed.md)
- [<span data-ttu-id="df5b8-222">abstract</span><span class="sxs-lookup"><span data-stu-id="df5b8-222">abstract</span></span>](../../language-reference/keywords/abstract.md)

### <a name="overriding-members"></a><span data-ttu-id="df5b8-223">переопределение членов;</span><span class="sxs-lookup"><span data-stu-id="df5b8-223">Overriding Members</span></span>

<span data-ttu-id="df5b8-224">По умолчанию производный класс наследует все члены от своего базового класса.</span><span class="sxs-lookup"><span data-stu-id="df5b8-224">By default, a derived class inherits all members from its base class.</span></span> <span data-ttu-id="df5b8-225">Если необходимо изменить поведение унаследованного члена, необходимо переопределить его.</span><span class="sxs-lookup"><span data-stu-id="df5b8-225">If you want to change the behavior of the inherited member, you need to override it.</span></span> <span data-ttu-id="df5b8-226">Т. е. в производном классе можно определить новую реализацию метода, свойства или события.</span><span class="sxs-lookup"><span data-stu-id="df5b8-226">That is, you can define a new implementation of the method, property or event in the derived class.</span></span>

<span data-ttu-id="df5b8-227">Следующие модификаторы используются для управления переопределением свойств и методов.</span><span class="sxs-lookup"><span data-stu-id="df5b8-227">The following modifiers are used to control how properties and methods are overridden:</span></span>

| <span data-ttu-id="df5b8-228">Модификатор C#</span><span class="sxs-lookup"><span data-stu-id="df5b8-228">C# Modifier</span></span> | <span data-ttu-id="df5b8-229">Определение</span><span class="sxs-lookup"><span data-stu-id="df5b8-229">Definition</span></span> |
|--|--|
| [<span data-ttu-id="df5b8-230">virtual</span><span class="sxs-lookup"><span data-stu-id="df5b8-230">virtual</span></span>](../../language-reference/keywords/virtual.md) | <span data-ttu-id="df5b8-231">Разрешает переопределение члена класса в производном классе.</span><span class="sxs-lookup"><span data-stu-id="df5b8-231">Allows a class member to be overridden in a derived class.</span></span> |
| [<span data-ttu-id="df5b8-232">override</span><span class="sxs-lookup"><span data-stu-id="df5b8-232">override</span></span>](../../language-reference/keywords/override.md) | <span data-ttu-id="df5b8-233">Переопределяет виртуальный (переопределяемый) член в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="df5b8-233">Overrides a virtual (overridable) member defined in the base class.</span></span> |
| [<span data-ttu-id="df5b8-234">abstract</span><span class="sxs-lookup"><span data-stu-id="df5b8-234">abstract</span></span>](../../language-reference/keywords/abstract.md) | <span data-ttu-id="df5b8-235">Требует, чтобы член класса был переопределен в производном классе.</span><span class="sxs-lookup"><span data-stu-id="df5b8-235">Requires that a class member to be overridden in the derived class.</span></span> |
| [<span data-ttu-id="df5b8-236">Модификатор new</span><span class="sxs-lookup"><span data-stu-id="df5b8-236">new Modifier</span></span>](../../language-reference/keywords/new-modifier.md) | <span data-ttu-id="df5b8-237">Скрывает член, наследуемый от базового класса</span><span class="sxs-lookup"><span data-stu-id="df5b8-237">Hides a member inherited from a base class</span></span> |

## <a name="interfaces"></a><span data-ttu-id="df5b8-238">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="df5b8-238">Interfaces</span></span>

<span data-ttu-id="df5b8-239">Интерфейсы, как и классы, определяют набор свойств, методов и событий.</span><span class="sxs-lookup"><span data-stu-id="df5b8-239">Interfaces, like classes, define a set of properties, methods, and events.</span></span> <span data-ttu-id="df5b8-240">Но, в отличие от классов, интерфейсы не предоставляют реализацию.</span><span class="sxs-lookup"><span data-stu-id="df5b8-240">But unlike classes, interfaces do not provide implementation.</span></span> <span data-ttu-id="df5b8-241">Они реализуются классами, но определяются как отдельные от классов сущности.</span><span class="sxs-lookup"><span data-stu-id="df5b8-241">They are implemented by classes, and defined as separate entities from classes.</span></span> <span data-ttu-id="df5b8-242">Интерфейс представляет собой контракт, в котором класс, реализующий интерфейс, должен реализовывать каждый аспект этого интерфейса в точном соответствии с его определением.</span><span class="sxs-lookup"><span data-stu-id="df5b8-242">An interface represents a contract, in that a class that implements an interface must implement every aspect of that interface exactly as it is defined.</span></span>

<span data-ttu-id="df5b8-243">Определение интерфейса:</span><span class="sxs-lookup"><span data-stu-id="df5b8-243">To define an interface:</span></span>

```csharp
interface ISampleInterface
{
    void DoSomething();
}
```

<span data-ttu-id="df5b8-244">Реализация интерфейса в классе:</span><span class="sxs-lookup"><span data-stu-id="df5b8-244">To implement an interface in a class:</span></span>

```csharp
class SampleClass : ISampleInterface
{
    void ISampleInterface.DoSomething()
    {
        // Method implementation.
    }
}
```

<span data-ttu-id="df5b8-245">Дополнительные сведения см. в разделе руководства по программированию, посвященного [интерфейсам](../interfaces/index.md), и в статье справочника по языку, посвященной ключевому слову [interface](../../language-reference/keywords/interface.md).</span><span class="sxs-lookup"><span data-stu-id="df5b8-245">For more information, see the programming guide article on [Interfaces](../interfaces/index.md) and the language reference article on the [interface](../../language-reference/keywords/interface.md) keyword.</span></span>

## <a name="generics"></a><span data-ttu-id="df5b8-246">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="df5b8-246">Generics</span></span>

<span data-ttu-id="df5b8-247">Классы, структуры, интерфейсы и методы на платформе .NET могут иметь *параметры типа*, которые определяют типы объектов, которые они могут хранить или использовать.</span><span class="sxs-lookup"><span data-stu-id="df5b8-247">Classes, structures, interfaces, and methods in .NET can include *type parameters* that define types of objects that they can store or use.</span></span> <span data-ttu-id="df5b8-248">Наиболее распространенным примером универсального шаблона является коллекция, в которой можно указать тип объектов, которые могут в ней храниться.</span><span class="sxs-lookup"><span data-stu-id="df5b8-248">The most common example of generics is a collection, where you can specify the type of objects to be stored in a collection.</span></span>

<span data-ttu-id="df5b8-249">Определение универсального класса:</span><span class="sxs-lookup"><span data-stu-id="df5b8-249">To define a generic class:</span></span>

```csharp
public class SampleGeneric<T>
{
    public T Field;
}
```

<span data-ttu-id="df5b8-250">Создание экземпляра универсального класса:</span><span class="sxs-lookup"><span data-stu-id="df5b8-250">To create an instance of a generic class:</span></span>

```csharp
var sampleObject = new SampleGeneric<string>();
sampleObject.Field = "Sample string";
```

<span data-ttu-id="df5b8-251">Дополнительные сведения можно найти в разделе</span><span class="sxs-lookup"><span data-stu-id="df5b8-251">For more information, see:</span></span>

- [<span data-ttu-id="df5b8-252">Универсальные шаблоны в .NET</span><span class="sxs-lookup"><span data-stu-id="df5b8-252">Generics in .NET</span></span>](../../../standard/generics/index.md)
- [<span data-ttu-id="df5b8-253">Универсальные шаблоны. Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="df5b8-253">Generics - C# Programming Guide</span></span>](../generics/index.md)

## <a name="delegates"></a><span data-ttu-id="df5b8-254">Делегаты</span><span class="sxs-lookup"><span data-stu-id="df5b8-254">Delegates</span></span>

<span data-ttu-id="df5b8-255">*Делегат* — это тип, который определяет сигнатуру метода и может обеспечивать связь с любым методом с совместимой сигнатурой.</span><span class="sxs-lookup"><span data-stu-id="df5b8-255">A *delegate* is a type that defines a method signature, and can provide a reference to any method with a compatible signature.</span></span> <span data-ttu-id="df5b8-256">Метод можно запустить (или вызвать) с помощью делегата.</span><span class="sxs-lookup"><span data-stu-id="df5b8-256">You can invoke (or call) the method through the delegate.</span></span> <span data-ttu-id="df5b8-257">Делегаты используются для передачи методов в качестве аргументов к другим методам.</span><span class="sxs-lookup"><span data-stu-id="df5b8-257">Delegates are used to pass methods as arguments to other methods.</span></span>

> [!NOTE]
> <span data-ttu-id="df5b8-258">Обработчики событий — это ничто иное, как методы, вызываемые с помощью делегатов.</span><span class="sxs-lookup"><span data-stu-id="df5b8-258">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="df5b8-259">Дополнительные сведения об использовании делегатов при обработке событий см. в разделе [События](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="df5b8-259">For more information about using delegates in event handling, see [Events](../../../standard/events/index.md).</span></span>

<span data-ttu-id="df5b8-260">Создание делегата:</span><span class="sxs-lookup"><span data-stu-id="df5b8-260">To create a delegate:</span></span>

```csharp
public delegate void SampleDelegate(string str);
```

<span data-ttu-id="df5b8-261">Создание ссылки на метод, сигнатура которого соответствует сигнатуре, указанной делегатом:</span><span class="sxs-lookup"><span data-stu-id="df5b8-261">To create a reference to a method that matches the signature specified by the delegate:</span></span>

```csharp
class SampleClass
{
    // Method that matches the SampleDelegate signature.
    public static void SampleMethod(string message)
    {
        // Add code here.
    }

    // Method that instantiates the delegate.
    void SampleDelegate()
    {
        SampleDelegate sd = sampleMethod;
        sd("Sample string");
    }
}
```

<span data-ttu-id="df5b8-262">Дополнительные сведения см. в разделе руководства по программированию, посвященного [делегатам](../delegates/index.md), и в статье справочника по языку, посвященной ключевому слову [delegate](../../language-reference/builtin-types/reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="df5b8-262">For more information, see the programming guide article on [Delegates](../delegates/index.md) and the language reference article on the [delegate](../../language-reference/builtin-types/reference-types.md) keyword.</span></span>

## <a name="see-also"></a><span data-ttu-id="df5b8-263">См. также</span><span class="sxs-lookup"><span data-stu-id="df5b8-263">See also</span></span>

- [<span data-ttu-id="df5b8-264">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="df5b8-264">C# Programming Guide</span></span>](../index.md)
