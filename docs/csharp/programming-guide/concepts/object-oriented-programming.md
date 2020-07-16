---
title: Объектно ориентированное программирование (C#)
ms.date: 05/13/2020
ms.assetid: 89574786-65ef-4335-88bc-fbacd094f183
ms.openlocfilehash: 83140a9dbd16f60f04f50ba18c71099cdd862f15
ms.sourcegitcommit: 67cf756b033c6173a1bbd1cbd5aef1fccac99e34
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2020
ms.locfileid: "86226638"
---
# <a name="object-oriented-programming-c"></a><span data-ttu-id="a79ed-102">Объектно-ориентированное программирование (C#)</span><span class="sxs-lookup"><span data-stu-id="a79ed-102">Object-Oriented programming (C#)</span></span>

<span data-ttu-id="a79ed-103">C# обеспечивает полную поддержку объектно ориентированного программирования, включая абстракцию, инкапсуляцию, наследование и полиморфизм.</span><span class="sxs-lookup"><span data-stu-id="a79ed-103">C# provides full support for object-oriented programming including abstraction, encapsulation, inheritance, and polymorphism.</span></span>

- <span data-ttu-id="a79ed-104">*Абстракция* означает скрытие ненужных сведений от потребителей типов.</span><span class="sxs-lookup"><span data-stu-id="a79ed-104">*Abstraction* means hiding the unnecessary details from type consumers.</span></span>
- <span data-ttu-id="a79ed-105">*Инкапсуляция* означает, что группа связанных свойств, методов и других членов рассматривается как единый элемент или объект.</span><span class="sxs-lookup"><span data-stu-id="a79ed-105">*Encapsulation* means that a group of related properties, methods, and other members are treated as a single unit or object.</span></span>
- <span data-ttu-id="a79ed-106">*Наследование* описывает возможность создания новых классов на основе существующих классов.</span><span class="sxs-lookup"><span data-stu-id="a79ed-106">*Inheritance* describes the ability to create new classes based on an existing class.</span></span>
- <span data-ttu-id="a79ed-107">*Полиморфизм* означает, что можно иметь несколько взаимозаменяемых классов, даже если каждый класс реализует одни и те же свойства или методы разными способами.</span><span class="sxs-lookup"><span data-stu-id="a79ed-107">*Polymorphism* means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.</span></span>

## <a name="classes-and-objects"></a><span data-ttu-id="a79ed-108">Классы и объекты</span><span class="sxs-lookup"><span data-stu-id="a79ed-108">Classes and objects</span></span>

<span data-ttu-id="a79ed-109">Термины *класс* и *объект* описывают *тип* объектов и *экземпляры* классов, соответственно.</span><span class="sxs-lookup"><span data-stu-id="a79ed-109">The terms *class* and *object* describe the *type* of objects, and the *instances* of classes, respectively.</span></span> <span data-ttu-id="a79ed-110">Поэтому процесс создания объекта называется *созданием экземпляра*.</span><span class="sxs-lookup"><span data-stu-id="a79ed-110">So, the act of creating an object is called *instantiation*.</span></span> <span data-ttu-id="a79ed-111">Если использовать сравнение с чертежом, то класс является чертежом, а объект является зданием, построенным по нему.</span><span class="sxs-lookup"><span data-stu-id="a79ed-111">Using the blueprint analogy, a class is a blueprint, and an object is a building made from that blueprint.</span></span>

<span data-ttu-id="a79ed-112">Определение класса:</span><span class="sxs-lookup"><span data-stu-id="a79ed-112">To define a class:</span></span>

```csharp
class SampleClass
{
}
```

<span data-ttu-id="a79ed-113">C# также предоставляет типы, называемые *структурами*, которые удобно использовать, когда не требуется поддержка наследования или полиморфизма.</span><span class="sxs-lookup"><span data-stu-id="a79ed-113">C# also provides types called *structures* that are useful when you don't need support for inheritance or polymorphism.</span></span> <span data-ttu-id="a79ed-114">Дополнительные сведения см. в статье [Выбор между классом и структурой](../../../standard/design-guidelines/choosing-between-class-and-struct.md).</span><span class="sxs-lookup"><span data-stu-id="a79ed-114">For more information, see [Choosing between class and struct](../../../standard/design-guidelines/choosing-between-class-and-struct.md).</span></span>

<span data-ttu-id="a79ed-115">Определение структуры:</span><span class="sxs-lookup"><span data-stu-id="a79ed-115">To define a structure:</span></span>

```csharp
struct SampleStruct
{
}
```

<span data-ttu-id="a79ed-116">Дополнительные сведения см. в статьях, посвященных ключевым словам [class](../../language-reference/keywords/class.md) и [struct](../../language-reference/builtin-types/struct.md).</span><span class="sxs-lookup"><span data-stu-id="a79ed-116">For more information, see the articles on the [class](../../language-reference/keywords/class.md) and [struct](../../language-reference/builtin-types/struct.md) keywords.</span></span>

### <a name="class-members"></a><span data-ttu-id="a79ed-117">Члены класса</span><span class="sxs-lookup"><span data-stu-id="a79ed-117">Class members</span></span>

<span data-ttu-id="a79ed-118">Каждый класс может состоять из различных *членов класса*, которые содержат свойства, описывающие данные класса, методы, задающие поведение класса, и события, обеспечивающие связь между различными классами и объектами.</span><span class="sxs-lookup"><span data-stu-id="a79ed-118">Each class can have different *class members* that include properties that describe class data, methods that define class behavior, and events that provide communication between different classes and objects.</span></span>

#### <a name="properties-and-fields"></a><span data-ttu-id="a79ed-119">Свойства и поля</span><span class="sxs-lookup"><span data-stu-id="a79ed-119">Properties and fields</span></span>

<span data-ttu-id="a79ed-120">Поля и свойства представляют сведения, содержащиеся в объекте.</span><span class="sxs-lookup"><span data-stu-id="a79ed-120">Fields and properties represent information that an object contains.</span></span> <span data-ttu-id="a79ed-121">Поля подобны переменным в том, что их можно прочитать или изменить напрямую с использованием применимых модификаторов доступа.</span><span class="sxs-lookup"><span data-stu-id="a79ed-121">Fields are like variables because they can be read or set directly, subject to applicable access modifiers.</span></span>

<span data-ttu-id="a79ed-122">Определение поля, доступ к которому можно получить из экземпляров класса:</span><span class="sxs-lookup"><span data-stu-id="a79ed-122">To define a field that can be accessed from within instances of the class:</span></span>

```csharp
public class SampleClass
{
    string sampleField;
}
```

<span data-ttu-id="a79ed-123">Для работы со свойствами используются методы доступа `get` и `set`, которые расширяют возможности управления способом задания и возврата значений.</span><span class="sxs-lookup"><span data-stu-id="a79ed-123">Properties have `get` and `set` accessors, which provide more control on how values are set or returned.</span></span>

<span data-ttu-id="a79ed-124">В языке C# для хранения значения свойства можно создать частное поле (private) или использовать автоматически реализуемые свойства, которые автоматически создают такое поле и обеспечивают базовую логику для процедур свойств.</span><span class="sxs-lookup"><span data-stu-id="a79ed-124">C# allows you either to create a private field for storing the property value or use auto-implemented properties that create this field automatically behind the scenes and provide the basic logic for the property procedures.</span></span>

<span data-ttu-id="a79ed-125">Определение автоматически реализуемого свойства:</span><span class="sxs-lookup"><span data-stu-id="a79ed-125">To define an auto-implemented property:</span></span>

```csharp
class SampleClass
{
    public int SampleProperty { get; set; }
}
```

<span data-ttu-id="a79ed-126">Если требуется выполнить дополнительные операции чтения и записи применительно к значению свойства, определите поле для хранения значения свойства и затем реализуйте базовую логику для хранения и извлечения этого значения:</span><span class="sxs-lookup"><span data-stu-id="a79ed-126">If you need to perform some additional operations for reading and writing the property value, define a field for storing the property value and provide the basic logic for storing and retrieving it:</span></span>

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

<span data-ttu-id="a79ed-127">У большинства свойств есть методы или процедуры для задания и возврата значения свойства.</span><span class="sxs-lookup"><span data-stu-id="a79ed-127">Most properties have methods or procedures to both set and get the property value.</span></span> <span data-ttu-id="a79ed-128">Однако можно создать свойства, доступные только для чтения или только на запись, чтобы запретить изменение или чтение значений свойств.</span><span class="sxs-lookup"><span data-stu-id="a79ed-128">However, you can create read-only or write-only properties to restrict them from being modified or read.</span></span> <span data-ttu-id="a79ed-129">В C# можно опустить метод свойства `get` или `set`.</span><span class="sxs-lookup"><span data-stu-id="a79ed-129">In C#, you can omit the `get` or `set` property method.</span></span> <span data-ttu-id="a79ed-130">Следует отметить, что автоматически реализуемые свойства не могут быть доступными только для записи.</span><span class="sxs-lookup"><span data-stu-id="a79ed-130">However, auto-implemented properties cannot be write-only.</span></span> <span data-ttu-id="a79ed-131">Автоматически реализуемые свойства, доступные только для чтения, можно задать в конструкторах содержащего класса.</span><span class="sxs-lookup"><span data-stu-id="a79ed-131">Read-only auto-implemented properties can be set in constructors of the containing class.</span></span>

<span data-ttu-id="a79ed-132">Дополнительные сведения можно найти в разделе</span><span class="sxs-lookup"><span data-stu-id="a79ed-132">For more information, see:</span></span>

- [<span data-ttu-id="a79ed-133">get</span><span class="sxs-lookup"><span data-stu-id="a79ed-133">get</span></span>](../../language-reference/keywords/get.md)
- [<span data-ttu-id="a79ed-134">set</span><span class="sxs-lookup"><span data-stu-id="a79ed-134">set</span></span>](../../language-reference/keywords/set.md)

#### <a name="methods"></a><span data-ttu-id="a79ed-135">Методы</span><span class="sxs-lookup"><span data-stu-id="a79ed-135">Methods</span></span>

<span data-ttu-id="a79ed-136">Действие, которое выполняет объект, называется *методом*.</span><span class="sxs-lookup"><span data-stu-id="a79ed-136">A *method* is an action that an object can perform.</span></span>

<span data-ttu-id="a79ed-137">Определение метода класса:</span><span class="sxs-lookup"><span data-stu-id="a79ed-137">To define a method of a class:</span></span>

```csharp
class SampleClass
{
    public int SampleMethod(string sampleParam)
    {
        // Insert code here
    }
}
```

<span data-ttu-id="a79ed-138">Класс может иметь несколько реализаций или *перегрузок* одного и того же метода, которые отличаются от других числом или типами параметров.</span><span class="sxs-lookup"><span data-stu-id="a79ed-138">A class can have several implementations, or *overloads*, of the same method that differ in the number of parameters or parameter types.</span></span>

<span data-ttu-id="a79ed-139">Перегрузка метода:</span><span class="sxs-lookup"><span data-stu-id="a79ed-139">To overload a method:</span></span>

```csharp
public int SampleMethod(string sampleParam) { }
public int SampleMethod(int sampleParam) { }
```

<span data-ttu-id="a79ed-140">Как правило, метод объявляется при определении класса.</span><span class="sxs-lookup"><span data-stu-id="a79ed-140">In most cases you declare a method within a class definition.</span></span> <span data-ttu-id="a79ed-141">Однако C# также поддерживает *методы расширения*, которые позволяют добавлять методы в существующий класс вне определения класса.</span><span class="sxs-lookup"><span data-stu-id="a79ed-141">However, C# also supports *extension methods* that allow you to add methods to an existing class outside the actual definition of the class.</span></span>

<span data-ttu-id="a79ed-142">Дополнительные сведения можно найти в разделе</span><span class="sxs-lookup"><span data-stu-id="a79ed-142">For more information, see:</span></span>

- [<span data-ttu-id="a79ed-143">Методы</span><span class="sxs-lookup"><span data-stu-id="a79ed-143">Methods</span></span>](../classes-and-structs/methods.md)
- [<span data-ttu-id="a79ed-144">Методы расширения</span><span class="sxs-lookup"><span data-stu-id="a79ed-144">Extension Methods</span></span>](../classes-and-structs/extension-methods.md)

#### <a name="constructors"></a><span data-ttu-id="a79ed-145">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="a79ed-145">Constructors</span></span>

<span data-ttu-id="a79ed-146">Конструкторы — это методы классов, выполняемые автоматически при создании объекта заданного типа.</span><span class="sxs-lookup"><span data-stu-id="a79ed-146">Constructors are class methods that are executed automatically when an object of a given type is created.</span></span> <span data-ttu-id="a79ed-147">Обычно конструкторы выполняют инициализацию членов данных нового объекта.</span><span class="sxs-lookup"><span data-stu-id="a79ed-147">Constructors usually initialize the data members of the new object.</span></span> <span data-ttu-id="a79ed-148">Конструктор можно запустить только один раз при создании класса.</span><span class="sxs-lookup"><span data-stu-id="a79ed-148">A constructor can run only once when a class is created.</span></span> <span data-ttu-id="a79ed-149">Кроме того, код конструктора всегда выполняется раньше всех остальных частей кода в классе.</span><span class="sxs-lookup"><span data-stu-id="a79ed-149">Furthermore, the code in the constructor always runs before any other code in a class.</span></span> <span data-ttu-id="a79ed-150">Следует отметить, что так же, как и для других методов, можно создать несколько перегрузок конструктора.</span><span class="sxs-lookup"><span data-stu-id="a79ed-150">However, you can create multiple constructor overloads in the same way as for any other method.</span></span>

<span data-ttu-id="a79ed-151">Определение конструктора для класса:</span><span class="sxs-lookup"><span data-stu-id="a79ed-151">To define a constructor for a class:</span></span>

```csharp
public class SampleClass
{
    public SampleClass()
    {
        // Add code here
    }
}
```

<span data-ttu-id="a79ed-152">Дополнительные сведения см. в разделе [Конструкторы](../classes-and-structs/constructors.md).</span><span class="sxs-lookup"><span data-stu-id="a79ed-152">For more information, see [Constructors](../classes-and-structs/constructors.md).</span></span>

#### <a name="finalizers"></a><span data-ttu-id="a79ed-153">Методы завершения</span><span class="sxs-lookup"><span data-stu-id="a79ed-153">Finalizers</span></span>

<span data-ttu-id="a79ed-154">Метод завершения используется для уничтожения экземпляров классов.</span><span class="sxs-lookup"><span data-stu-id="a79ed-154">A finalizer is used to destruct instances of classes.</span></span> <span data-ttu-id="a79ed-155">На платформе .NET сборщик мусора автоматически управляет распределением и освобождением памяти для управляемых объектов приложения.</span><span class="sxs-lookup"><span data-stu-id="a79ed-155">In .NET, the garbage collector automatically manages the allocation and release of memory for the managed objects in your application.</span></span> <span data-ttu-id="a79ed-156">Однако для очистки неуправляемых ресурсов, создаваемых приложением, могут потребоваться методы завершения.</span><span class="sxs-lookup"><span data-stu-id="a79ed-156">However, you may still need finalizers to clean up any unmanaged resources that your application creates.</span></span> <span data-ttu-id="a79ed-157">На один класс допускается только один метод завершения.</span><span class="sxs-lookup"><span data-stu-id="a79ed-157">There can be only one finalizer for a class.</span></span>

<span data-ttu-id="a79ed-158">Дополнительные сведения о методах завершения и сборке мусора в .NET см. в статье [Сборка мусора](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="a79ed-158">For more information about finalizers and garbage collection in .NET, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>

#### <a name="events"></a><span data-ttu-id="a79ed-159">События</span><span class="sxs-lookup"><span data-stu-id="a79ed-159">Events</span></span>

<span data-ttu-id="a79ed-160">События позволяют классу или объекту уведомлять другие классы или объекты о возникновении каких-либо ситуаций.</span><span class="sxs-lookup"><span data-stu-id="a79ed-160">Events enable a class or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="a79ed-161">Класс, отправляющий (или порождающий) событие, называется *издателем*, а классы, принимающие (или обрабатывающие) событие, называются *подписчиками*.</span><span class="sxs-lookup"><span data-stu-id="a79ed-161">The class that sends (or raises) the event is called the *publisher* and the classes that receive (or handle) the event are called *subscribers*.</span></span> <span data-ttu-id="a79ed-162">Дополнительные сведения о том, как порождаются и обрабатываются события, см. в разделе [События](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="a79ed-162">For more information about events, how they are raised and handled, see [Events](../../../standard/events/index.md).</span></span>

- <span data-ttu-id="a79ed-163">Чтобы объявить событие в классе, используйте ключевое слово [event](../../language-reference/keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="a79ed-163">To declare an event in a class, use the [event](../../language-reference/keywords/event.md) keyword.</span></span>
- <span data-ttu-id="a79ed-164">Чтобы породить событие, вызовите делегат события.</span><span class="sxs-lookup"><span data-stu-id="a79ed-164">To raise an event, invoke the event delegate.</span></span>
- <span data-ttu-id="a79ed-165">Чтобы подписаться на событие, используйте оператор `+=`. Чтобы отменить подписку на событие, воспользуйтесь оператором `-=`.</span><span class="sxs-lookup"><span data-stu-id="a79ed-165">To subscribe to an event, use the `+=` operator; to unsubscribe from an event, use the `-=` operator.</span></span>

#### <a name="nested-classes"></a><span data-ttu-id="a79ed-166">Вложенные классы</span><span class="sxs-lookup"><span data-stu-id="a79ed-166">Nested classes</span></span>

<span data-ttu-id="a79ed-167">Класс, определенный внутри другого класса, называется *вложенным*.</span><span class="sxs-lookup"><span data-stu-id="a79ed-167">A class defined within another class is called *nested*.</span></span> <span data-ttu-id="a79ed-168">По умолчанию вложенный класс является частным.</span><span class="sxs-lookup"><span data-stu-id="a79ed-168">By default, the nested class is private.</span></span>

```csharp
class Container
{
    class Nested
    {
        // Add code here.
    }
}
```

<span data-ttu-id="a79ed-169">Чтобы создать экземпляр вложенного класса, укажите имя класса контейнера и имя вложенного класса, используя в качестве разделителя точку:</span><span class="sxs-lookup"><span data-stu-id="a79ed-169">To create an instance of the nested class, use the name of the container class followed by the dot and then followed by the name of the nested class:</span></span>

```csharp
Container.Nested nestedInstance = new Container.Nested()
```

### <a name="access-modifiers-and-access-levels"></a><span data-ttu-id="a79ed-170">Модификаторы доступа и уровни доступа</span><span class="sxs-lookup"><span data-stu-id="a79ed-170">Access modifiers and access levels</span></span>

<span data-ttu-id="a79ed-171">С помощью *модификаторов доступа* все классы и члены классов могут указывать уровни доступа, предоставляемые другим классам.</span><span class="sxs-lookup"><span data-stu-id="a79ed-171">All classes and class members can specify what access level they provide to other classes by using *access modifiers*.</span></span>

<span data-ttu-id="a79ed-172">Имеющиеся модификаторы доступа указаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="a79ed-172">The following access modifiers are available:</span></span>

| <span data-ttu-id="a79ed-173">Модификатор C#</span><span class="sxs-lookup"><span data-stu-id="a79ed-173">C# Modifier</span></span> | <span data-ttu-id="a79ed-174">Определение</span><span class="sxs-lookup"><span data-stu-id="a79ed-174">Definition</span></span> |
|--|--|
| [<span data-ttu-id="a79ed-175">public</span><span class="sxs-lookup"><span data-stu-id="a79ed-175">public</span></span>](../../language-reference/keywords/public.md) | <span data-ttu-id="a79ed-176">Доступ к типу или члену возможен из любого другого кода в той же сборке или другой сборке, ссылающейся на него.</span><span class="sxs-lookup"><span data-stu-id="a79ed-176">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span> |
| [<span data-ttu-id="a79ed-177">private</span><span class="sxs-lookup"><span data-stu-id="a79ed-177">private</span></span>](../../language-reference/keywords/private.md) | <span data-ttu-id="a79ed-178">Доступ к типу или члену можно получить только из кода в том же классе.</span><span class="sxs-lookup"><span data-stu-id="a79ed-178">The type or member can only be accessed by code in the same class.</span></span> |
| [<span data-ttu-id="a79ed-179">protected</span><span class="sxs-lookup"><span data-stu-id="a79ed-179">protected</span></span>](../../language-reference/keywords/protected.md) | <span data-ttu-id="a79ed-180">Доступ к типу или члену можно получить только из кода в том же классе или в производном классе.</span><span class="sxs-lookup"><span data-stu-id="a79ed-180">The type or member can only be accessed by code in the same class or in a derived class.</span></span> |
| [<span data-ttu-id="a79ed-181">internal</span><span class="sxs-lookup"><span data-stu-id="a79ed-181">internal</span></span>](../../language-reference/keywords/internal.md) | <span data-ttu-id="a79ed-182">Доступ к типу или члену возможен из любого кода в той же сборке, но не из другой сборки.</span><span class="sxs-lookup"><span data-stu-id="a79ed-182">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span> |
| [<span data-ttu-id="a79ed-183">protected internal</span><span class="sxs-lookup"><span data-stu-id="a79ed-183">protected internal</span></span>](../../language-reference/keywords/protected-internal.md) | <span data-ttu-id="a79ed-184">Доступ к типу или члену возможен из любого кода в той же сборке, или из производного класса в другой сборке.</span><span class="sxs-lookup"><span data-stu-id="a79ed-184">The type or member can be accessed by any code in the same assembly, or by any derived class in another assembly.</span></span> |
| [<span data-ttu-id="a79ed-185">private protected</span><span class="sxs-lookup"><span data-stu-id="a79ed-185">private protected</span></span>](../../language-reference/keywords/private-protected.md) | <span data-ttu-id="a79ed-186">Доступ к типу или члену можно получить из кода в том же классе или в производном классе в сборке базового класса.</span><span class="sxs-lookup"><span data-stu-id="a79ed-186">The type or member can be accessed by code in the same class or in a derived class within the base class assembly.</span></span> |

<span data-ttu-id="a79ed-187">Дополнительные сведения см. в статье [Модификаторы доступа](../classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="a79ed-187">For more information, see [Access Modifiers](../classes-and-structs/access-modifiers.md).</span></span>

### <a name="instantiating-classes"></a><span data-ttu-id="a79ed-188">Создание экземпляров классов</span><span class="sxs-lookup"><span data-stu-id="a79ed-188">Instantiating classes</span></span>

<span data-ttu-id="a79ed-189">Чтобы создать объект, необходимо создать экземпляр класса.</span><span class="sxs-lookup"><span data-stu-id="a79ed-189">To create an object, you need to instantiate a class, or create a class instance.</span></span>

```csharp
SampleClass sampleObject = new SampleClass();
```

<span data-ttu-id="a79ed-190">После создания экземпляра класса можно присваивать значения свойствам и полям экземпляра и вызывать методы класса.</span><span class="sxs-lookup"><span data-stu-id="a79ed-190">After instantiating a class, you can assign values to the instance's properties and fields and invoke class methods.</span></span>

```csharp
// Set a property value.
sampleObject.sampleProperty = "Sample String";
// Call a method.
sampleObject.SampleMethod();
```

<span data-ttu-id="a79ed-191">Чтобы назначить значения свойствам в процессе создания экземпляра класса, используйте инициализаторы объектов:</span><span class="sxs-lookup"><span data-stu-id="a79ed-191">To assign values to properties during the class instantiation process, use object initializers:</span></span>

```csharp
// Set a property value.
var sampleObject = new SampleClass
{
    FirstProperty = "A",
    SecondProperty = "B"
};
```

<span data-ttu-id="a79ed-192">Дополнительные сведения можно найти в разделе</span><span class="sxs-lookup"><span data-stu-id="a79ed-192">For more information, see:</span></span>

- [<span data-ttu-id="a79ed-193">Оператор new</span><span class="sxs-lookup"><span data-stu-id="a79ed-193">new Operator</span></span>](../../language-reference/operators/new-operator.md)
- [<span data-ttu-id="a79ed-194">Инициализаторы объектов и коллекций</span><span class="sxs-lookup"><span data-stu-id="a79ed-194">Object and Collection Initializers</span></span>](../classes-and-structs/object-and-collection-initializers.md)

### <a name="static-classes-and-members"></a><span data-ttu-id="a79ed-195">статические классы и их члены;</span><span class="sxs-lookup"><span data-stu-id="a79ed-195">Static Classes and Members</span></span>

<span data-ttu-id="a79ed-196">Статический член класса — это свойство, процедура или поле, которое совместно используется всеми экземплярами класса.</span><span class="sxs-lookup"><span data-stu-id="a79ed-196">A static member of the class is a property, procedure, or field that is shared by all instances of a class.</span></span>

<span data-ttu-id="a79ed-197">Определение статического члена</span><span class="sxs-lookup"><span data-stu-id="a79ed-197">To define a static member:</span></span>

```csharp
static class SampleClass
{
    public static string SampleString = "Sample String";
}
```

<span data-ttu-id="a79ed-198">Чтобы получить доступ к статическому члену, используйте имя класса без создания объекта этого класса:</span><span class="sxs-lookup"><span data-stu-id="a79ed-198">To access the static member, use the name of the class without creating an object of this class:</span></span>

```csharp
Console.WriteLine(SampleClass.SampleString);
```

<span data-ttu-id="a79ed-199">Статические классы в C# имеют только статические члены и не могут быть созданы.</span><span class="sxs-lookup"><span data-stu-id="a79ed-199">Static  classes in C# have static members only and cannot be instantiated.</span></span> <span data-ttu-id="a79ed-200">Статические члены также не могут обращаться к нестатическим свойствам, полям или методам.</span><span class="sxs-lookup"><span data-stu-id="a79ed-200">Static members also cannot access non-static  properties, fields or methods</span></span>

<span data-ttu-id="a79ed-201">Дополнительные сведения см. в разделе [static](../../language-reference/keywords/static.md).</span><span class="sxs-lookup"><span data-stu-id="a79ed-201">For more information, see: [static](../../language-reference/keywords/static.md).</span></span>

### <a name="anonymous-types"></a><span data-ttu-id="a79ed-202">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="a79ed-202">Anonymous types</span></span>

<span data-ttu-id="a79ed-203">Анонимные типы позволяют создавать объекты без написания определения класса для типа данных.</span><span class="sxs-lookup"><span data-stu-id="a79ed-203">Anonymous types enable you to create objects without writing a class definition for the data type.</span></span> <span data-ttu-id="a79ed-204">Вместо этого компилятор создает класс для вас.</span><span class="sxs-lookup"><span data-stu-id="a79ed-204">Instead, the compiler generates a class for you.</span></span> <span data-ttu-id="a79ed-205">Данный класс не имеет имени и содержит свойства, которые указаны при объявлении объекта.</span><span class="sxs-lookup"><span data-stu-id="a79ed-205">The class has no usable name and contains the properties you specify in declaring the object.</span></span>

<span data-ttu-id="a79ed-206">Создание экземпляра анонимного типа:</span><span class="sxs-lookup"><span data-stu-id="a79ed-206">To create an instance of an anonymous type:</span></span>

```csharp
// sampleObject is an instance of a simple anonymous type.
var sampleObject = new
{
    FirstProperty = "A",
    SecondProperty = "B"
};
```

<span data-ttu-id="a79ed-207">Дополнительные сведения можно найти в разделе  [Анонимные типы](../classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="a79ed-207">For more information, see: [Anonymous Types](../classes-and-structs/anonymous-types.md).</span></span>

## <a name="inheritance"></a><span data-ttu-id="a79ed-208">Наследование</span><span class="sxs-lookup"><span data-stu-id="a79ed-208">Inheritance</span></span>

<span data-ttu-id="a79ed-209">Наследование позволяет создавать новые классы, которые повторно используют, расширяют и изменяют поведение, определенное в другом классе.</span><span class="sxs-lookup"><span data-stu-id="a79ed-209">Inheritance enables you to create a new class that reuses, extends, and modifies the behavior that is defined in another class.</span></span> <span data-ttu-id="a79ed-210">Класс, члены которого наследуются, называется *базовым классом*, а класс, который наследует эти члены, называется *производным классом*.</span><span class="sxs-lookup"><span data-stu-id="a79ed-210">The class whose members are inherited is called the *base class*, and the class that inherits those members is called the *derived class*.</span></span> <span data-ttu-id="a79ed-211">Следует учитывать, что все классы в C# неявно наследуются от класса <xref:System.Object>, который поддерживает иерархию классов .NET и предоставляет низкоуровневые службы для всех классов.</span><span class="sxs-lookup"><span data-stu-id="a79ed-211">However, all classes in C# implicitly inherit from the <xref:System.Object> class that supports .NET class hierarchy and provides low-level services to all classes.</span></span>

> [!NOTE]
> <span data-ttu-id="a79ed-212">C# не поддерживает множественное наследование.</span><span class="sxs-lookup"><span data-stu-id="a79ed-212">C# doesn't support multiple inheritance.</span></span> <span data-ttu-id="a79ed-213">То есть можно указать только один базовый класс для производного класса.</span><span class="sxs-lookup"><span data-stu-id="a79ed-213">That is, you can specify only one base class for a derived class.</span></span>

<span data-ttu-id="a79ed-214">Наследование от базового класса:</span><span class="sxs-lookup"><span data-stu-id="a79ed-214">To inherit from a base class:</span></span>

```csharp
class DerivedClass:BaseClass { }
```

<span data-ttu-id="a79ed-215">По умолчанию унаследовать класс можно от любого класса.</span><span class="sxs-lookup"><span data-stu-id="a79ed-215">By default all classes can be inherited.</span></span> <span data-ttu-id="a79ed-216">Однако можно указать, должен ли класс использоваться в качестве базового класса, или создать класс, который может использоваться только в качестве базового.</span><span class="sxs-lookup"><span data-stu-id="a79ed-216">However, you can specify whether a class must not be used as a base class, or create a class that can be used as a base class only.</span></span>

<span data-ttu-id="a79ed-217">Указание, что класс не может использоваться в качестве базового класса:</span><span class="sxs-lookup"><span data-stu-id="a79ed-217">To specify that a class cannot be used as a base class:</span></span>

```csharp
public sealed class A { }
```

<span data-ttu-id="a79ed-218">Указание, что класс может использоваться только в качестве базового класса и нельзя создать экземпляр этого класса:</span><span class="sxs-lookup"><span data-stu-id="a79ed-218">To specify that a class can be used as a base class only and cannot be instantiated:</span></span>

```csharp
public abstract class B { }
```

<span data-ttu-id="a79ed-219">Дополнительные сведения можно найти в разделе</span><span class="sxs-lookup"><span data-stu-id="a79ed-219">For more information, see:</span></span>

- [<span data-ttu-id="a79ed-220">sealed</span><span class="sxs-lookup"><span data-stu-id="a79ed-220">sealed</span></span>](../../language-reference/keywords/sealed.md)
- [<span data-ttu-id="a79ed-221">abstract</span><span class="sxs-lookup"><span data-stu-id="a79ed-221">abstract</span></span>](../../language-reference/keywords/abstract.md)

### <a name="overriding-members"></a><span data-ttu-id="a79ed-222">переопределение членов;</span><span class="sxs-lookup"><span data-stu-id="a79ed-222">Overriding Members</span></span>

<span data-ttu-id="a79ed-223">По умолчанию производный класс наследует все члены от своего базового класса.</span><span class="sxs-lookup"><span data-stu-id="a79ed-223">By default, a derived class inherits all members from its base class.</span></span> <span data-ttu-id="a79ed-224">Если необходимо изменить поведение унаследованного члена, необходимо переопределить его.</span><span class="sxs-lookup"><span data-stu-id="a79ed-224">If you want to change the behavior of the inherited member, you need to override it.</span></span> <span data-ttu-id="a79ed-225">Т. е. в производном классе можно определить новую реализацию метода, свойства или события.</span><span class="sxs-lookup"><span data-stu-id="a79ed-225">That is, you can define a new implementation of the method, property or event in the derived class.</span></span>

<span data-ttu-id="a79ed-226">Следующие модификаторы используются для управления переопределением свойств и методов.</span><span class="sxs-lookup"><span data-stu-id="a79ed-226">The following modifiers are used to control how properties and methods are overridden:</span></span>

| <span data-ttu-id="a79ed-227">Модификатор C#</span><span class="sxs-lookup"><span data-stu-id="a79ed-227">C# Modifier</span></span> | <span data-ttu-id="a79ed-228">Определение</span><span class="sxs-lookup"><span data-stu-id="a79ed-228">Definition</span></span> |
|--|--|
| [<span data-ttu-id="a79ed-229">virtual</span><span class="sxs-lookup"><span data-stu-id="a79ed-229">virtual</span></span>](../../language-reference/keywords/virtual.md) | <span data-ttu-id="a79ed-230">Разрешает переопределение члена класса в производном классе.</span><span class="sxs-lookup"><span data-stu-id="a79ed-230">Allows a class member to be overridden in a derived class.</span></span> |
| [<span data-ttu-id="a79ed-231">override</span><span class="sxs-lookup"><span data-stu-id="a79ed-231">override</span></span>](../../language-reference/keywords/override.md) | <span data-ttu-id="a79ed-232">Переопределяет виртуальный (переопределяемый) член в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="a79ed-232">Overrides a virtual (overridable) member defined in the base class.</span></span> |
| [<span data-ttu-id="a79ed-233">abstract</span><span class="sxs-lookup"><span data-stu-id="a79ed-233">abstract</span></span>](../../language-reference/keywords/abstract.md) | <span data-ttu-id="a79ed-234">Требует, чтобы член класса был переопределен в производном классе.</span><span class="sxs-lookup"><span data-stu-id="a79ed-234">Requires that a class member to be overridden in the derived class.</span></span> |
| [<span data-ttu-id="a79ed-235">Модификатор new</span><span class="sxs-lookup"><span data-stu-id="a79ed-235">new Modifier</span></span>](../../language-reference/keywords/new-modifier.md) | <span data-ttu-id="a79ed-236">Скрывает член, наследуемый от базового класса</span><span class="sxs-lookup"><span data-stu-id="a79ed-236">Hides a member inherited from a base class</span></span> |

## <a name="interfaces"></a><span data-ttu-id="a79ed-237">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="a79ed-237">Interfaces</span></span>

<span data-ttu-id="a79ed-238">Интерфейсы, как и классы, определяют набор свойств, методов и событий.</span><span class="sxs-lookup"><span data-stu-id="a79ed-238">Interfaces, like classes, define a set of properties, methods, and events.</span></span> <span data-ttu-id="a79ed-239">Но, в отличие от классов, интерфейсы не предоставляют реализацию.</span><span class="sxs-lookup"><span data-stu-id="a79ed-239">But unlike classes, interfaces do not provide implementation.</span></span> <span data-ttu-id="a79ed-240">Они реализуются классами, но определяются как отдельные от классов сущности.</span><span class="sxs-lookup"><span data-stu-id="a79ed-240">They are implemented by classes, and defined as separate entities from classes.</span></span> <span data-ttu-id="a79ed-241">Интерфейс представляет собой контракт, в котором класс, реализующий интерфейс, должен реализовывать каждый аспект этого интерфейса в точном соответствии с его определением.</span><span class="sxs-lookup"><span data-stu-id="a79ed-241">An interface represents a contract, in that a class that implements an interface must implement every aspect of that interface exactly as it is defined.</span></span>

<span data-ttu-id="a79ed-242">Определение интерфейса:</span><span class="sxs-lookup"><span data-stu-id="a79ed-242">To define an interface:</span></span>

```csharp
interface ISampleInterface
{
    void DoSomething();
}
```

<span data-ttu-id="a79ed-243">Реализация интерфейса в классе:</span><span class="sxs-lookup"><span data-stu-id="a79ed-243">To implement an interface in a class:</span></span>

```csharp
class SampleClass : ISampleInterface
{
    void ISampleInterface.DoSomething()
    {
        // Method implementation.
    }
}
```

<span data-ttu-id="a79ed-244">Дополнительные сведения см. в разделе руководства по программированию, посвященного [интерфейсам](../interfaces/index.md), и в статье справочника по языку, посвященной ключевому слову [interface](../../language-reference/keywords/interface.md).</span><span class="sxs-lookup"><span data-stu-id="a79ed-244">For more information, see the programming guide article on [Interfaces](../interfaces/index.md) and the language reference article on the [interface](../../language-reference/keywords/interface.md) keyword.</span></span>

## <a name="generics"></a><span data-ttu-id="a79ed-245">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="a79ed-245">Generics</span></span>

<span data-ttu-id="a79ed-246">Классы, структуры, интерфейсы и методы на платформе .NET могут иметь *параметры типа*, которые определяют типы объектов, которые они могут хранить или использовать.</span><span class="sxs-lookup"><span data-stu-id="a79ed-246">Classes, structures, interfaces, and methods in .NET can include *type parameters* that define types of objects that they can store or use.</span></span> <span data-ttu-id="a79ed-247">Наиболее распространенным примером универсального шаблона является коллекция, в которой можно указать тип объектов, которые могут в ней храниться.</span><span class="sxs-lookup"><span data-stu-id="a79ed-247">The most common example of generics is a collection, where you can specify the type of objects to be stored in a collection.</span></span>

<span data-ttu-id="a79ed-248">Определение универсального класса:</span><span class="sxs-lookup"><span data-stu-id="a79ed-248">To define a generic class:</span></span>

```csharp
public class SampleGeneric<T>
{
    public T Field;
}
```

<span data-ttu-id="a79ed-249">Создание экземпляра универсального класса:</span><span class="sxs-lookup"><span data-stu-id="a79ed-249">To create an instance of a generic class:</span></span>

```csharp
var sampleObject = new SampleGeneric<string>();
sampleObject.Field = "Sample string";
```

<span data-ttu-id="a79ed-250">Дополнительные сведения можно найти в разделе</span><span class="sxs-lookup"><span data-stu-id="a79ed-250">For more information, see:</span></span>

- [<span data-ttu-id="a79ed-251">Универсальные шаблоны в .NET</span><span class="sxs-lookup"><span data-stu-id="a79ed-251">Generics in .NET</span></span>](../../../standard/generics/index.md)
- [<span data-ttu-id="a79ed-252">Универсальные шаблоны. Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a79ed-252">Generics - C# Programming Guide</span></span>](../generics/index.md)

## <a name="delegates"></a><span data-ttu-id="a79ed-253">Делегаты</span><span class="sxs-lookup"><span data-stu-id="a79ed-253">Delegates</span></span>

<span data-ttu-id="a79ed-254">*Делегат* — это тип, который определяет сигнатуру метода и может обеспечивать связь с любым методом с совместимой сигнатурой.</span><span class="sxs-lookup"><span data-stu-id="a79ed-254">A *delegate* is a type that defines a method signature, and can provide a reference to any method with a compatible signature.</span></span> <span data-ttu-id="a79ed-255">Метод можно запустить (или вызвать) с помощью делегата.</span><span class="sxs-lookup"><span data-stu-id="a79ed-255">You can invoke (or call) the method through the delegate.</span></span> <span data-ttu-id="a79ed-256">Делегаты используются для передачи методов в качестве аргументов к другим методам.</span><span class="sxs-lookup"><span data-stu-id="a79ed-256">Delegates are used to pass methods as arguments to other methods.</span></span>

> [!NOTE]
> <span data-ttu-id="a79ed-257">Обработчики событий — это ничто иное, как методы, вызываемые с помощью делегатов.</span><span class="sxs-lookup"><span data-stu-id="a79ed-257">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="a79ed-258">Дополнительные сведения об использовании делегатов при обработке событий см. в разделе [События](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="a79ed-258">For more information about using delegates in event handling, see [Events](../../../standard/events/index.md).</span></span>

<span data-ttu-id="a79ed-259">Создание делегата:</span><span class="sxs-lookup"><span data-stu-id="a79ed-259">To create a delegate:</span></span>

```csharp
public delegate void SampleDelegate(string str);
```

<span data-ttu-id="a79ed-260">Создание ссылки на метод, сигнатура которого соответствует сигнатуре, указанной делегатом:</span><span class="sxs-lookup"><span data-stu-id="a79ed-260">To create a reference to a method that matches the signature specified by the delegate:</span></span>

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

<span data-ttu-id="a79ed-261">Дополнительные сведения см. в разделе руководства по программированию, посвященного [делегатам](../delegates/index.md), и в статье справочника по языку, посвященной ключевому слову [delegate](../../language-reference/builtin-types/reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="a79ed-261">For more information, see the programming guide article on [Delegates](../delegates/index.md) and the language reference article on the [delegate](../../language-reference/builtin-types/reference-types.md) keyword.</span></span>

## <a name="see-also"></a><span data-ttu-id="a79ed-262">См. также</span><span class="sxs-lookup"><span data-stu-id="a79ed-262">See also</span></span>

- [<span data-ttu-id="a79ed-263">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a79ed-263">C# Programming Guide</span></span>](../index.md)
