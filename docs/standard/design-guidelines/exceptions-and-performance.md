---
title: Исключения и производительность
ms.date: 10/22/2008
helpviewer_keywords:
- tester-doer pattern
- TryParse pattern
- exceptions, throwing
- exceptions, performance
- throwing exceptions, performance
ms.assetid: 3ad6aad9-08e6-4232-b336-0e301f2493e6
ms.openlocfilehash: babe378e0d61357709006e08f71ff578492f116c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734755"
---
# <a name="exceptions-and-performance"></a><span data-ttu-id="fd143-102">Исключения и производительность</span><span class="sxs-lookup"><span data-stu-id="fd143-102">Exceptions and Performance</span></span>

<span data-ttu-id="fd143-103">Одной из распространенных проблем, связанных с исключениями, является то, что если исключения используются для кода, который обычно завершается ошибкой, производительность реализации будет неприемлемой.</span><span class="sxs-lookup"><span data-stu-id="fd143-103">One common concern related to exceptions is that if exceptions are used for code that routinely fails, the performance of the implementation will be unacceptable.</span></span> <span data-ttu-id="fd143-104">Это является действительной проблемой.</span><span class="sxs-lookup"><span data-stu-id="fd143-104">This is a valid concern.</span></span> <span data-ttu-id="fd143-105">Когда член создает исключение, его производительность может быть меньше.</span><span class="sxs-lookup"><span data-stu-id="fd143-105">When a member throws an exception, its performance can be orders of magnitude slower.</span></span> <span data-ttu-id="fd143-106">Однако можно достичь хорошей производительности, при этом строго придерживаться правил исключения, которые не позволяют использовать коды ошибок.</span><span class="sxs-lookup"><span data-stu-id="fd143-106">However, it is possible to achieve good performance while strictly adhering to the exception guidelines that disallow using error codes.</span></span> <span data-ttu-id="fd143-107">Два шаблона, описанные в этом разделе, предлагают способы этого.</span><span class="sxs-lookup"><span data-stu-id="fd143-107">Two patterns described in this section suggest ways to do this.</span></span>

 <span data-ttu-id="fd143-108">❌ НЕ используйте коды ошибок из-за проблем, с которыми исключения могут негативно сказаться на производительности.</span><span class="sxs-lookup"><span data-stu-id="fd143-108">❌ DO NOT use error codes because of concerns that exceptions might affect performance negatively.</span></span>

 <span data-ttu-id="fd143-109">Чтобы повысить производительность, можно использовать шаблон Tester-Doer или шаблон Try-Parse, как описано в следующих двух разделах.</span><span class="sxs-lookup"><span data-stu-id="fd143-109">To improve performance, it is possible to use either the Tester-Doer Pattern or the Try-Parse Pattern, described in the next two sections.</span></span>

## <a name="tester-doer-pattern"></a><span data-ttu-id="fd143-110">Шаблон Tester-Doer</span><span class="sxs-lookup"><span data-stu-id="fd143-110">Tester-Doer Pattern</span></span>

 <span data-ttu-id="fd143-111">Иногда производительность члена, вызывающего исключение, может быть улучшена путем разбиения члена на два.</span><span class="sxs-lookup"><span data-stu-id="fd143-111">Sometimes performance of an exception-throwing member can be improved by breaking the member into two.</span></span> <span data-ttu-id="fd143-112">Рассмотрим <xref:System.Collections.Generic.ICollection%601.Add%2A> метод <xref:System.Collections.Generic.ICollection%601> интерфейса.</span><span class="sxs-lookup"><span data-stu-id="fd143-112">Let’s look at the <xref:System.Collections.Generic.ICollection%601.Add%2A> method of the <xref:System.Collections.Generic.ICollection%601> interface.</span></span>

```csharp
ICollection<int> numbers = ...
numbers.Add(1);
```

 <span data-ttu-id="fd143-113">Метод `Add` вызывает исключение, если коллекция доступна только для чтения.</span><span class="sxs-lookup"><span data-stu-id="fd143-113">The method `Add` throws if the collection is read-only.</span></span> <span data-ttu-id="fd143-114">Это может быть проблемой с производительностью в сценариях, когда ожидается, что вызов метода будет выполняться часто.</span><span class="sxs-lookup"><span data-stu-id="fd143-114">This can be a performance problem in scenarios where the method call is expected to fail often.</span></span> <span data-ttu-id="fd143-115">Один из способов устранения проблемы заключается в том, чтобы проверить, является ли коллекция доступной для записи, прежде чем пытаться добавить значение.</span><span class="sxs-lookup"><span data-stu-id="fd143-115">One of the ways to mitigate the problem is to test whether the collection is writable before trying to add a value.</span></span>

```csharp
ICollection<int> numbers = ...
...
if (!numbers.IsReadOnly)
{
    numbers.Add(1);
}
```

 <span data-ttu-id="fd143-116">Элемент, используемый для проверки условия, которое в нашем примере является свойством `IsReadOnly` , называется инженером-тестировщиком.</span><span class="sxs-lookup"><span data-stu-id="fd143-116">The member used to test a condition, which in our example is the property `IsReadOnly`, is referred to as the tester.</span></span> <span data-ttu-id="fd143-117">Элемент, используемый для выполнения потенциального вызова операции, `Add` метод в нашем примере, называется злодея.</span><span class="sxs-lookup"><span data-stu-id="fd143-117">The member used to perform a potentially throwing operation, the `Add` method in our example, is referred to as the doer.</span></span>

 <span data-ttu-id="fd143-118">✔️ Рассмотрите шаблон Tester-Doer для членов, которые могут создавать исключения в распространенных сценариях, чтобы избежать проблем с производительностью, связанных с исключениями.</span><span class="sxs-lookup"><span data-stu-id="fd143-118">✔️ CONSIDER the Tester-Doer Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>

## <a name="try-parse-pattern"></a><span data-ttu-id="fd143-119">Шаблон Try-Parse</span><span class="sxs-lookup"><span data-stu-id="fd143-119">Try-Parse Pattern</span></span>

 <span data-ttu-id="fd143-120">Для очень чувствительных к производительности интерфейсов API следует использовать еще более быстрый шаблон, чем шаблон Tester-Doer, описанный в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="fd143-120">For extremely performance-sensitive APIs, an even faster pattern than the Tester-Doer Pattern described in the previous section should be used.</span></span> <span data-ttu-id="fd143-121">Шаблон вызывает метод для настройки имени элемента, чтобы сделать строго определенный тестовый случай частью семантики элемента.</span><span class="sxs-lookup"><span data-stu-id="fd143-121">The pattern calls for adjusting the member name to make a well-defined test case a part of the member semantics.</span></span> <span data-ttu-id="fd143-122">Например, <xref:System.DateTime> определяет <xref:System.DateTime.Parse%2A> метод, который создает исключение, если синтаксический анализ строки завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="fd143-122">For example, <xref:System.DateTime> defines a <xref:System.DateTime.Parse%2A> method that throws an exception if parsing of a string fails.</span></span> <span data-ttu-id="fd143-123">Он также определяет соответствующий <xref:System.DateTime.TryParse%2A> метод, который пытается выполнить синтаксический анализ, но возвращает значение false, если синтаксический анализ завершается неудачно, и возвращает результат успешного анализа с помощью `out` параметра.</span><span class="sxs-lookup"><span data-stu-id="fd143-123">It also defines a corresponding <xref:System.DateTime.TryParse%2A> method that attempts to parse, but returns false if parsing is unsuccessful and returns the result of a successful parsing using an `out` parameter.</span></span>

```csharp
public struct DateTime
{
    public static DateTime Parse(string dateTime)
    {
        ...
    }
    public static bool TryParse(string dateTime, out DateTime result)
    {
        ...
    }
}
```

 <span data-ttu-id="fd143-124">При использовании этого шаблона важно определить функциональность Try в условиях ограниченного использования.</span><span class="sxs-lookup"><span data-stu-id="fd143-124">When using this pattern, it is important to define the try functionality in strict terms.</span></span> <span data-ttu-id="fd143-125">Если элемент завершается ошибкой по какой-либо причине, отличной от правильно определенной, член должен по-прежнему вызывать соответствующее исключение.</span><span class="sxs-lookup"><span data-stu-id="fd143-125">If the member fails for any reason other than the well-defined try, the member must still throw a corresponding exception.</span></span>

 <span data-ttu-id="fd143-126">✔️ Рассмотрите шаблон Try-Parse для членов, которые могут создавать исключения в распространенных сценариях, чтобы избежать проблем с производительностью, связанных с исключениями.</span><span class="sxs-lookup"><span data-stu-id="fd143-126">✔️ CONSIDER the Try-Parse Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>

 <span data-ttu-id="fd143-127">✔️ использовать префикс "try" и логический тип возвращаемого значения для методов, реализующих этот шаблон.</span><span class="sxs-lookup"><span data-stu-id="fd143-127">✔️ DO use the prefix "Try" and Boolean return type for methods implementing this pattern.</span></span>

 <span data-ttu-id="fd143-128">✔️ предоставить элемент, создающий исключения, для каждого члена, используя шаблон Try-Parse.</span><span class="sxs-lookup"><span data-stu-id="fd143-128">✔️ DO provide an exception-throwing member for each member using the Try-Parse Pattern.</span></span>

 <span data-ttu-id="fd143-129">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="fd143-129">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="fd143-130">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="fd143-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="fd143-131">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="fd143-131">See also</span></span>

- [<span data-ttu-id="fd143-132">Рекомендации по проектированию платформы</span><span class="sxs-lookup"><span data-stu-id="fd143-132">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="fd143-133">Правила разработки исключений</span><span class="sxs-lookup"><span data-stu-id="fd143-133">Design Guidelines for Exceptions</span></span>](exceptions.md)
