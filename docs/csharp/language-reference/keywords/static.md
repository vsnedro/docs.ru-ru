---
description: Модификатор static. Справочник по C#
title: Модификатор static. Справочник по C#
ms.date: 04/22/2020
f1_keywords:
- static
- static_CSharpKeyword
helpviewer_keywords:
- static keyword [C#]
ms.assetid: 5509e215-2183-4da3-bab4-6b7e607a4fdf
ms.openlocfilehash: f42636d1bbdf4342297f46f50ec6dfc2a70eacad
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142067"
---
# <a name="static-c-reference"></a><span data-ttu-id="94c5b-103">static (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="94c5b-103">static (C# Reference)</span></span>

<span data-ttu-id="94c5b-104">На этой странице приводятся сведения о ключевом слове модификатора `static`.</span><span class="sxs-lookup"><span data-stu-id="94c5b-104">This page covers the `static` modifier keyword.</span></span> <span data-ttu-id="94c5b-105">Ключевое слово `static` также является частью директивы [`using static`](using-static.md).</span><span class="sxs-lookup"><span data-stu-id="94c5b-105">The `static` keyword is also part of the [`using static`](using-static.md) directive.</span></span>

<span data-ttu-id="94c5b-106">Модификатор `static` используется для объявления статического члена, принадлежащего собственно типу, а не конкретному объекту.</span><span class="sxs-lookup"><span data-stu-id="94c5b-106">Use the `static` modifier to declare a static member, which belongs to the type itself rather than to a specific object.</span></span> <span data-ttu-id="94c5b-107">Модификатор `static` можно использовать для объявления классов `static`.</span><span class="sxs-lookup"><span data-stu-id="94c5b-107">The `static` modifier can be used to declare `static` classes.</span></span> <span data-ttu-id="94c5b-108">В классах, интерфейсах и структурах вы можете добавить модификатор `static` к полям, методам, свойствам, операторам, событиям и конструкторам.</span><span class="sxs-lookup"><span data-stu-id="94c5b-108">In classes, interfaces, and structs, you may add the `static` modifier to fields, methods, properties, operators, events, and constructors.</span></span> <span data-ttu-id="94c5b-109">Модификатор `static` запрещено использовать с индексаторами или методами завершения.</span><span class="sxs-lookup"><span data-stu-id="94c5b-109">The `static` modifier can't be used with indexers or finalizers.</span></span> <span data-ttu-id="94c5b-110">Дополнительные сведения см. в статье [Статические классы и члены статических классов](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="94c5b-110">For more information, see [Static Classes and Static Class Members](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>

## <a name="example---static-class"></a><span data-ttu-id="94c5b-111">Пример: статический класс</span><span class="sxs-lookup"><span data-stu-id="94c5b-111">Example - static class</span></span>

<span data-ttu-id="94c5b-112">Следующий класс объявляется как `static` и содержит только методы `static`:</span><span class="sxs-lookup"><span data-stu-id="94c5b-112">The following class is declared as `static` and contains only `static` methods:</span></span>

[!code-csharp[csrefKeywordsModifiers#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#18)]

<span data-ttu-id="94c5b-113">Объявление константы или типа неявно является членом `static`.</span><span class="sxs-lookup"><span data-stu-id="94c5b-113">A constant or type declaration is implicitly a `static` member.</span></span> <span data-ttu-id="94c5b-114">На член `static` невозможно ссылаться через экземпляр,</span><span class="sxs-lookup"><span data-stu-id="94c5b-114">A `static` member can't be referenced through an instance.</span></span> <span data-ttu-id="94c5b-115">а можно только через имя типа.</span><span class="sxs-lookup"><span data-stu-id="94c5b-115">Instead, it's referenced through the type name.</span></span> <span data-ttu-id="94c5b-116">Например, рассмотрим следующий класс.</span><span class="sxs-lookup"><span data-stu-id="94c5b-116">For example, consider the following class:</span></span>

[!code-csharp[csrefKeywordsModifiers#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#19)]

<span data-ttu-id="94c5b-117">Чтобы обратиться к члену `static` `x`, воспользуйтесь полным именем — `MyBaseC.MyStruct.x` (если только член не доступен из той же области действия).</span><span class="sxs-lookup"><span data-stu-id="94c5b-117">To refer to the `static` member `x`, use the fully qualified name, `MyBaseC.MyStruct.x`, unless the member is accessible from the same scope:</span></span>

```csharp
Console.WriteLine(MyBaseC.MyStruct.x);
```

<span data-ttu-id="94c5b-118">Так как экземпляр класса содержит отдельную копию всех полей экземпляра класса, каждому полю `static` соответствует только одна копия.</span><span class="sxs-lookup"><span data-stu-id="94c5b-118">While an instance of a class contains a separate copy of all instance fields of the class, there's only one copy of each `static` field.</span></span>

<span data-ttu-id="94c5b-119">Невозможно использовать [`this`](this.md) для ссылки на методы `static` или методы доступа к свойствам.</span><span class="sxs-lookup"><span data-stu-id="94c5b-119">It isn't possible to use [`this`](this.md) to reference `static` methods or property accessors.</span></span>

<span data-ttu-id="94c5b-120">Если к классу применяется ключевое слово `static`, все члены этого класса должны быть `static`.</span><span class="sxs-lookup"><span data-stu-id="94c5b-120">If the `static` keyword is applied to a class, all the members of the class must be `static`.</span></span>

<span data-ttu-id="94c5b-121">Классы, интерфейсы и классы `static` могут иметь конструкторы `static`.</span><span class="sxs-lookup"><span data-stu-id="94c5b-121">Classes, interfaces, and `static` classes may have `static` constructors.</span></span> <span data-ttu-id="94c5b-122">Конструктор `static` вызывается на определенном этапе между запуском программы и созданием экземпляра класса.</span><span class="sxs-lookup"><span data-stu-id="94c5b-122">A `static` constructor is called at some point between when the program starts and the class is instantiated.</span></span>

> [!NOTE]
> <span data-ttu-id="94c5b-123">Ключевое слово `static` имеет более ограниченное применение по сравнению с C++.</span><span class="sxs-lookup"><span data-stu-id="94c5b-123">The `static` keyword has more limited uses than in C++.</span></span> <span data-ttu-id="94c5b-124">Сведения о сравнении с ключевым словом С++ см. в статье [Классы хранения (C++)](/cpp/cpp/storage-classes-cpp#static).</span><span class="sxs-lookup"><span data-stu-id="94c5b-124">To compare with the C++ keyword, see [Storage classes (C++)](/cpp/cpp/storage-classes-cpp#static).</span></span>

<span data-ttu-id="94c5b-125">В качестве демонстрации членов `static` рассмотрим класс, представляющий сотрудника компании.</span><span class="sxs-lookup"><span data-stu-id="94c5b-125">To demonstrate `static` members, consider a class that represents a company employee.</span></span> <span data-ttu-id="94c5b-126">Предположим, что этот класс содержит метод для подсчета сотрудников и поле для хранения их числа.</span><span class="sxs-lookup"><span data-stu-id="94c5b-126">Assume that the class contains a method to count employees and a field to store the number of employees.</span></span> <span data-ttu-id="94c5b-127">И метод, и поле не принадлежат никакому экземпляру сотрудника.</span><span class="sxs-lookup"><span data-stu-id="94c5b-127">Both the method and the field don't belong to any one employee instance.</span></span> <span data-ttu-id="94c5b-128">Они принадлежат всему классу сотрудников.</span><span class="sxs-lookup"><span data-stu-id="94c5b-128">Instead, they belong to the class of employees as a whole.</span></span> <span data-ttu-id="94c5b-129">В связи с этим они должны объявляться как члены `static` класса.</span><span class="sxs-lookup"><span data-stu-id="94c5b-129">They should be declared as `static` members of the class.</span></span>

## <a name="example---static-field-and-method"></a><span data-ttu-id="94c5b-130">Пример: статическое поле и метод</span><span class="sxs-lookup"><span data-stu-id="94c5b-130">Example - static field and method</span></span>

<span data-ttu-id="94c5b-131">В этом примере выполняется чтение имени и идентификатора нового сотрудника, увеличение счетчика сотрудников на единицу, а также отображение сведений о новом сотруднике и новом числе сотрудников.</span><span class="sxs-lookup"><span data-stu-id="94c5b-131">This example reads the name and ID of a new employee, increments the employee counter by one, and displays the information for the new employee and the new number of employees.</span></span> <span data-ttu-id="94c5b-132">Эта программа считывает текущее число сотрудников с клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="94c5b-132">This program reads the current number of employees from the keyboard.</span></span>

[!code-csharp[csrefKeywordsModifiers#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#20)]  

## <a name="example---static-initialization"></a><span data-ttu-id="94c5b-133">Пример: статическая инициализация</span><span class="sxs-lookup"><span data-stu-id="94c5b-133">Example - static initialization</span></span>

<span data-ttu-id="94c5b-134">В этом примере показано, как можно инициализировать поле `static`, используя другое поле `static`, которое еще не объявлено.</span><span class="sxs-lookup"><span data-stu-id="94c5b-134">This example shows that you can initialize a `static` field by using another `static` field that is not yet declared.</span></span> <span data-ttu-id="94c5b-135">Результаты будут неопределенными до тех пор, пока вы явно не присвоите значение полю `static`.</span><span class="sxs-lookup"><span data-stu-id="94c5b-135">The results will be undefined until you explicitly assign a value to the `static` field.</span></span>

[!code-csharp[csrefKeywordsModifiers#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#21)]  

## <a name="c-language-specification"></a><span data-ttu-id="94c5b-136">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="94c5b-136">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="94c5b-137">См. также</span><span class="sxs-lookup"><span data-stu-id="94c5b-137">See also</span></span>

- [<span data-ttu-id="94c5b-138">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="94c5b-138">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="94c5b-139">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="94c5b-139">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="94c5b-140">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="94c5b-140">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="94c5b-141">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="94c5b-141">Modifiers</span></span>](index.md)
- [<span data-ttu-id="94c5b-142">Директива using static</span><span class="sxs-lookup"><span data-stu-id="94c5b-142">using static directive</span></span>](using-static.md)
- [<span data-ttu-id="94c5b-143">Статические классы и члены статических классов</span><span class="sxs-lookup"><span data-stu-id="94c5b-143">Static Classes and Static Class Members</span></span>](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
