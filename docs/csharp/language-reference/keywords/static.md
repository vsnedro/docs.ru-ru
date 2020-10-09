---
description: Модификатор static. Справочник по C#
title: Модификатор static. Справочник по C#
ms.date: 09/25/2020
f1_keywords:
- static
- static_CSharpKeyword
helpviewer_keywords:
- static keyword [C#]
ms.assetid: 5509e215-2183-4da3-bab4-6b7e607a4fdf
ms.openlocfilehash: 239163fc2f91ccbfe8b1c111a358db87d36a8308
ms.sourcegitcommit: 4d45bda8cd9558ea8af4be591e3d5a29360c1ece
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2020
ms.locfileid: "91654643"
---
# <a name="static-c-reference"></a><span data-ttu-id="c3bfb-103">static (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="c3bfb-103">static (C# Reference)</span></span>

<span data-ttu-id="c3bfb-104">На этой странице приводятся сведения о ключевом слове модификатора `static`.</span><span class="sxs-lookup"><span data-stu-id="c3bfb-104">This page covers the `static` modifier keyword.</span></span> <span data-ttu-id="c3bfb-105">Ключевое слово `static` также является частью директивы [`using static`](using-static.md).</span><span class="sxs-lookup"><span data-stu-id="c3bfb-105">The `static` keyword is also part of the [`using static`](using-static.md) directive.</span></span>

<span data-ttu-id="c3bfb-106">Модификатор `static` используется для объявления статического члена, принадлежащего собственно типу, а не конкретному объекту.</span><span class="sxs-lookup"><span data-stu-id="c3bfb-106">Use the `static` modifier to declare a static member, which belongs to the type itself rather than to a specific object.</span></span> <span data-ttu-id="c3bfb-107">Модификатор `static` можно использовать для объявления классов `static`.</span><span class="sxs-lookup"><span data-stu-id="c3bfb-107">The `static` modifier can be used to declare `static` classes.</span></span> <span data-ttu-id="c3bfb-108">В классах, интерфейсах и структурах вы можете добавить модификатор `static` к полям, методам, свойствам, операторам, событиям и конструкторам.</span><span class="sxs-lookup"><span data-stu-id="c3bfb-108">In classes, interfaces, and structs, you may add the `static` modifier to fields, methods, properties, operators, events, and constructors.</span></span> <span data-ttu-id="c3bfb-109">Модификатор `static` запрещено использовать с индексаторами или методами завершения.</span><span class="sxs-lookup"><span data-stu-id="c3bfb-109">The `static` modifier can't be used with indexers or finalizers.</span></span> <span data-ttu-id="c3bfb-110">Дополнительные сведения см. в статье [Статические классы и члены статических классов](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="c3bfb-110">For more information, see [Static Classes and Static Class Members](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>

<span data-ttu-id="c3bfb-111">Начиная с C# 8.0 можно добавить модификатор `static` в [локальную функцию](../../programming-guide/classes-and-structs/local-functions.md).</span><span class="sxs-lookup"><span data-stu-id="c3bfb-111">Beginning with C# 8.0, you can add the `static` modifier to a [local function](../../programming-guide/classes-and-structs/local-functions.md).</span></span> <span data-ttu-id="c3bfb-112">Статическая локальная функция не может сохранять локальные переменные или состояние экземпляра.</span><span class="sxs-lookup"><span data-stu-id="c3bfb-112">A static local function can't capture local variables or instance state.</span></span>

<span data-ttu-id="c3bfb-113">Начиная с C# 9.0 можно добавить модификатор `static` в [лямбда-выражение](../operators/lambda-expressions.md) или [анонимный метод](../operators/delegate-operator.md).</span><span class="sxs-lookup"><span data-stu-id="c3bfb-113">Beginning with C# 9.0, you can add the `static` modifier to a [lambda expression](../operators/lambda-expressions.md) or [anonymous method](../operators/delegate-operator.md).</span></span> <span data-ttu-id="c3bfb-114">Статическое лямбда-выражение или анонимный метод не могут сохранять локальные переменные или состояние экземпляра.</span><span class="sxs-lookup"><span data-stu-id="c3bfb-114">A static lambda or anonymous method can't capture local variables or instance state.</span></span>

## <a name="example---static-class"></a><span data-ttu-id="c3bfb-115">Пример: статический класс</span><span class="sxs-lookup"><span data-stu-id="c3bfb-115">Example - static class</span></span>

<span data-ttu-id="c3bfb-116">Следующий класс объявляется как `static` и содержит только методы `static`:</span><span class="sxs-lookup"><span data-stu-id="c3bfb-116">The following class is declared as `static` and contains only `static` methods:</span></span>

[!code-csharp[csrefKeywordsModifiers#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#18)]

<span data-ttu-id="c3bfb-117">Объявление константы или типа неявно является членом `static`.</span><span class="sxs-lookup"><span data-stu-id="c3bfb-117">A constant or type declaration is implicitly a `static` member.</span></span> <span data-ttu-id="c3bfb-118">На член `static` невозможно ссылаться через экземпляр,</span><span class="sxs-lookup"><span data-stu-id="c3bfb-118">A `static` member can't be referenced through an instance.</span></span> <span data-ttu-id="c3bfb-119">а можно только через имя типа.</span><span class="sxs-lookup"><span data-stu-id="c3bfb-119">Instead, it's referenced through the type name.</span></span> <span data-ttu-id="c3bfb-120">Например, рассмотрим следующий класс.</span><span class="sxs-lookup"><span data-stu-id="c3bfb-120">For example, consider the following class:</span></span>

[!code-csharp[csrefKeywordsModifiers#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#19)]

<span data-ttu-id="c3bfb-121">Чтобы обратиться к члену `static` `x`, воспользуйтесь полным именем — `MyBaseC.MyStruct.x` (если только член не доступен из той же области действия).</span><span class="sxs-lookup"><span data-stu-id="c3bfb-121">To refer to the `static` member `x`, use the fully qualified name, `MyBaseC.MyStruct.x`, unless the member is accessible from the same scope:</span></span>

```csharp
Console.WriteLine(MyBaseC.MyStruct.x);
```

<span data-ttu-id="c3bfb-122">Так как экземпляр класса содержит отдельную копию всех полей экземпляра класса, каждому полю `static` соответствует только одна копия.</span><span class="sxs-lookup"><span data-stu-id="c3bfb-122">While an instance of a class contains a separate copy of all instance fields of the class, there's only one copy of each `static` field.</span></span>

<span data-ttu-id="c3bfb-123">Невозможно использовать [`this`](this.md) для ссылки на методы `static` или методы доступа к свойствам.</span><span class="sxs-lookup"><span data-stu-id="c3bfb-123">It isn't possible to use [`this`](this.md) to reference `static` methods or property accessors.</span></span>

<span data-ttu-id="c3bfb-124">Если к классу применяется ключевое слово `static`, все члены этого класса должны быть `static`.</span><span class="sxs-lookup"><span data-stu-id="c3bfb-124">If the `static` keyword is applied to a class, all the members of the class must be `static`.</span></span>

<span data-ttu-id="c3bfb-125">Классы, интерфейсы и классы `static` могут иметь конструкторы `static`.</span><span class="sxs-lookup"><span data-stu-id="c3bfb-125">Classes, interfaces, and `static` classes may have `static` constructors.</span></span> <span data-ttu-id="c3bfb-126">Конструктор `static` вызывается на определенном этапе между запуском программы и созданием экземпляра класса.</span><span class="sxs-lookup"><span data-stu-id="c3bfb-126">A `static` constructor is called at some point between when the program starts and the class is instantiated.</span></span>

> [!NOTE]
> <span data-ttu-id="c3bfb-127">Ключевое слово `static` имеет более ограниченное применение по сравнению с C++.</span><span class="sxs-lookup"><span data-stu-id="c3bfb-127">The `static` keyword has more limited uses than in C++.</span></span> <span data-ttu-id="c3bfb-128">Сведения о сравнении с ключевым словом С++ см. в статье [Классы хранения (C++)](/cpp/cpp/storage-classes-cpp#static).</span><span class="sxs-lookup"><span data-stu-id="c3bfb-128">To compare with the C++ keyword, see [Storage classes (C++)](/cpp/cpp/storage-classes-cpp#static).</span></span>

<span data-ttu-id="c3bfb-129">В качестве демонстрации членов `static` рассмотрим класс, представляющий сотрудника компании.</span><span class="sxs-lookup"><span data-stu-id="c3bfb-129">To demonstrate `static` members, consider a class that represents a company employee.</span></span> <span data-ttu-id="c3bfb-130">Предположим, что этот класс содержит метод для подсчета сотрудников и поле для хранения их числа.</span><span class="sxs-lookup"><span data-stu-id="c3bfb-130">Assume that the class contains a method to count employees and a field to store the number of employees.</span></span> <span data-ttu-id="c3bfb-131">И метод, и поле не принадлежат никакому экземпляру сотрудника.</span><span class="sxs-lookup"><span data-stu-id="c3bfb-131">Both the method and the field don't belong to any one employee instance.</span></span> <span data-ttu-id="c3bfb-132">Они принадлежат всему классу сотрудников.</span><span class="sxs-lookup"><span data-stu-id="c3bfb-132">Instead, they belong to the class of employees as a whole.</span></span> <span data-ttu-id="c3bfb-133">В связи с этим они должны объявляться как члены `static` класса.</span><span class="sxs-lookup"><span data-stu-id="c3bfb-133">They should be declared as `static` members of the class.</span></span>

## <a name="example---static-field-and-method"></a><span data-ttu-id="c3bfb-134">Пример: статическое поле и метод</span><span class="sxs-lookup"><span data-stu-id="c3bfb-134">Example - static field and method</span></span>

<span data-ttu-id="c3bfb-135">В этом примере выполняется чтение имени и идентификатора нового сотрудника, увеличение счетчика сотрудников на единицу, а также отображение сведений о новом сотруднике и новом числе сотрудников.</span><span class="sxs-lookup"><span data-stu-id="c3bfb-135">This example reads the name and ID of a new employee, increments the employee counter by one, and displays the information for the new employee and the new number of employees.</span></span> <span data-ttu-id="c3bfb-136">Эта программа считывает текущее число сотрудников с клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="c3bfb-136">This program reads the current number of employees from the keyboard.</span></span>

[!code-csharp[csrefKeywordsModifiers#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#20)]  

## <a name="example---static-initialization"></a><span data-ttu-id="c3bfb-137">Пример: статическая инициализация</span><span class="sxs-lookup"><span data-stu-id="c3bfb-137">Example - static initialization</span></span>

<span data-ttu-id="c3bfb-138">В этом примере показано, как можно инициализировать поле `static`, используя другое поле `static`, которое еще не объявлено.</span><span class="sxs-lookup"><span data-stu-id="c3bfb-138">This example shows that you can initialize a `static` field by using another `static` field that is not yet declared.</span></span> <span data-ttu-id="c3bfb-139">Результаты будут неопределенными до тех пор, пока вы явно не присвоите значение полю `static`.</span><span class="sxs-lookup"><span data-stu-id="c3bfb-139">The results will be undefined until you explicitly assign a value to the `static` field.</span></span>

[!code-csharp[csrefKeywordsModifiers#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#21)]  

## <a name="c-language-specification"></a><span data-ttu-id="c3bfb-140">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="c3bfb-140">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="c3bfb-141">См. также</span><span class="sxs-lookup"><span data-stu-id="c3bfb-141">See also</span></span>

- [<span data-ttu-id="c3bfb-142">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="c3bfb-142">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c3bfb-143">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="c3bfb-143">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c3bfb-144">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="c3bfb-144">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="c3bfb-145">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="c3bfb-145">Modifiers</span></span>](index.md)
- [<span data-ttu-id="c3bfb-146">Директива using static</span><span class="sxs-lookup"><span data-stu-id="c3bfb-146">using static directive</span></span>](using-static.md)
- [<span data-ttu-id="c3bfb-147">Статические классы и члены статических классов</span><span class="sxs-lookup"><span data-stu-id="c3bfb-147">Static Classes and Static Class Members</span></span>](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
