---
title: Работа с коллекциями. Вводное руководство по C#
description: Это руководство по C# предоставляет для изучения примере коллекции списков.
ms.date: 10/13/2017
ms.custom: mvc
ms.openlocfilehash: e2282df21420630634911e07f4fb3b94f34a792b
ms.sourcegitcommit: b1f4756120deaecb8b554477bb040620f69a4209
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "89414687"
---
# <a name="learn-to-manage-data-collections-using-the-generic-list-type"></a><span data-ttu-id="cdeef-103">Научитесь управлять коллекциями данных с использованием универсального типа списка</span><span class="sxs-lookup"><span data-stu-id="cdeef-103">Learn to manage data collections using the generic list type</span></span>

<span data-ttu-id="cdeef-104">Это вводное руководство содержит общие сведения о языке C# и классе <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="cdeef-104">This introductory tutorial provides an introduction to the C# language and the basics of the <xref:System.Collections.Generic.List%601> class.</span></span>

<span data-ttu-id="cdeef-105">Для работы с этим руководством вам потребуется компьютер, который можно использовать для разработки.</span><span class="sxs-lookup"><span data-stu-id="cdeef-105">This tutorial expects you to have a machine you can use for development.</span></span> <span data-ttu-id="cdeef-106">В руководстве .NET по созданию программы [Hello World за 10 минут](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) содержатся инструкции по настройке локальной среды разработки в macOS, Windows или Linux.</span><span class="sxs-lookup"><span data-stu-id="cdeef-106">The .NET tutorial [Hello World in 10 minutes](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) has instructions for setting up your local development environment on Windows, Linux, or macOS.</span></span> <span data-ttu-id="cdeef-107">Краткий обзор команд, которые будут здесь использоваться, и ссылки на дополнительные сведения представлены в статье [Become familiar with the .NET development tools](local-environment.md) (Знакомство со средствами разработки для .NET).</span><span class="sxs-lookup"><span data-stu-id="cdeef-107">A quick overview of the commands you'll use is in [Become familiar with the development tools](local-environment.md), with links to more details.</span></span>

## <a name="a-basic-list-example"></a><span data-ttu-id="cdeef-108">Пример простого списка</span><span class="sxs-lookup"><span data-stu-id="cdeef-108">A basic list example</span></span>

<span data-ttu-id="cdeef-109">Создайте каталог с именем *list-tutorial*.</span><span class="sxs-lookup"><span data-stu-id="cdeef-109">Create a directory named *list-tutorial*.</span></span> <span data-ttu-id="cdeef-110">Откройте этот каталог и выполните команду `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="cdeef-110">Make that the current directory and run `dotnet new console`.</span></span>

<span data-ttu-id="cdeef-111">Откройте *Program.cs* в любом редакторе и замените существующий код следующим:</span><span class="sxs-lookup"><span data-stu-id="cdeef-111">Open *Program.cs* in your favorite editor, and replace the existing code with the following:</span></span>

```csharp
using System;
using System.Collections.Generic;

namespace list_tutorial
{
    class Program
    {
        static void Main(string[] args)
        {
            var names = new List<string> { "<name>", "Ana", "Felipe" };
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }
        }
    }
}
```

<span data-ttu-id="cdeef-112">Замените `<name>` собственным именем.</span><span class="sxs-lookup"><span data-stu-id="cdeef-112">Replace `<name>` with your name.</span></span> <span data-ttu-id="cdeef-113">Сохраните *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="cdeef-113">Save *Program.cs*.</span></span> <span data-ttu-id="cdeef-114">Введите в окне консоли команду `dotnet run` для тестирования.</span><span class="sxs-lookup"><span data-stu-id="cdeef-114">Type `dotnet run` in your console window to try it.</span></span>

<span data-ttu-id="cdeef-115">Вы создали список строк, добавили три имени в этот список и вывели имена прописными буквами.</span><span class="sxs-lookup"><span data-stu-id="cdeef-115">You've created a list of strings, added three names to that list, and printed out the names in all CAPS.</span></span> <span data-ttu-id="cdeef-116">Для циклического прохода по списку вы примените концепции, которые изучили в предыдущих руководствах.</span><span class="sxs-lookup"><span data-stu-id="cdeef-116">You're using concepts that you've learned in earlier tutorials to loop through the list.</span></span>

<span data-ttu-id="cdeef-117">В коде для отображения имен используется функция [интерполяции строк](../../language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="cdeef-117">The code to display names makes use of the [string interpolation](../../language-reference/tokens/interpolated.md) feature.</span></span>  <span data-ttu-id="cdeef-118">Если перед `string` добавить символ `$`, код C# можно внедрять в объявление строки.</span><span class="sxs-lookup"><span data-stu-id="cdeef-118">When you precede a `string` with the `$` character, you can embed C# code in the string declaration.</span></span> <span data-ttu-id="cdeef-119">Фактическая строка заменяет код C# генерируемым значением.</span><span class="sxs-lookup"><span data-stu-id="cdeef-119">The actual string replaces that C# code with the value it generates.</span></span> <span data-ttu-id="cdeef-120">В этом примере она заменяет `{name.ToUpper()}` именами, буквы каждого из которых преобразованы в прописные, так как вызван метод <xref:System.String.ToUpper%2A>.</span><span class="sxs-lookup"><span data-stu-id="cdeef-120">In this example, it replaces the `{name.ToUpper()}` with each name, converted to capital letters, because you called the <xref:System.String.ToUpper%2A> method.</span></span>

<span data-ttu-id="cdeef-121">Продолжим изучение.</span><span class="sxs-lookup"><span data-stu-id="cdeef-121">Let's keep exploring.</span></span>

## <a name="modify-list-contents"></a><span data-ttu-id="cdeef-122">Изменение содержимого списка</span><span class="sxs-lookup"><span data-stu-id="cdeef-122">Modify list contents</span></span>

<span data-ttu-id="cdeef-123">В созданной коллекции используется тип <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="cdeef-123">The collection you created uses the <xref:System.Collections.Generic.List%601> type.</span></span> <span data-ttu-id="cdeef-124">При применении такого типа сохраняются последовательности элементов.</span><span class="sxs-lookup"><span data-stu-id="cdeef-124">This type stores sequences of elements.</span></span> <span data-ttu-id="cdeef-125">Тип элементов указывается в угловых скобках.</span><span class="sxs-lookup"><span data-stu-id="cdeef-125">You specify the type of the elements between the angle brackets.</span></span>

<span data-ttu-id="cdeef-126">Важный аспект типа <xref:System.Collections.Generic.List%601> — возможность увеличения или уменьшения, что позволяет добавлять или удалять элементы.</span><span class="sxs-lookup"><span data-stu-id="cdeef-126">One important aspect of this <xref:System.Collections.Generic.List%601> type is that it can grow or shrink, enabling you to add or remove elements.</span></span> <span data-ttu-id="cdeef-127">Добавьте следующий код в метод `Main` перед закрывающей фигурной скобкой `}`:</span><span class="sxs-lookup"><span data-stu-id="cdeef-127">Add this code before the closing `}` in the `Main` method:</span></span>

```csharp
Console.WriteLine();
names.Add("Maria");
names.Add("Bill");
names.Remove("Ana");
foreach (var name in names)
{
    Console.WriteLine($"Hello {name.ToUpper()}!");
}
```

<span data-ttu-id="cdeef-128">В конец списка добавлены еще два имени.</span><span class="sxs-lookup"><span data-stu-id="cdeef-128">You've added two more names to the end of the list.</span></span> <span data-ttu-id="cdeef-129">При этом одно имя удалено.</span><span class="sxs-lookup"><span data-stu-id="cdeef-129">You've also removed one as well.</span></span> <span data-ttu-id="cdeef-130">Сохраните файл и введите `dotnet run` для тестирования.</span><span class="sxs-lookup"><span data-stu-id="cdeef-130">Save the file, and type `dotnet run` to try it.</span></span>

<span data-ttu-id="cdeef-131"><xref:System.Collections.Generic.List%601> позволяет добавлять ссылки на отдельные элементы по **индексу**.</span><span class="sxs-lookup"><span data-stu-id="cdeef-131">The <xref:System.Collections.Generic.List%601> enables you to reference individual items by **index** as well.</span></span> <span data-ttu-id="cdeef-132">Поместите индекс между токенами `[` и `]` после имени списка.</span><span class="sxs-lookup"><span data-stu-id="cdeef-132">You place the index between `[` and `]` tokens following the list name.</span></span> <span data-ttu-id="cdeef-133">Для первого индекса в C# используется значение 0.</span><span class="sxs-lookup"><span data-stu-id="cdeef-133">C# uses 0 for the first index.</span></span> <span data-ttu-id="cdeef-134">Добавьте следующий код сразу после добавленного фрагмента и протестируйте его:</span><span class="sxs-lookup"><span data-stu-id="cdeef-134">Add this code directly below the code you just added and try it:</span></span>

```csharp
Console.WriteLine($"My name is {names[0]}");
Console.WriteLine($"I've added {names[2]} and {names[3]} to the list");
```

<span data-ttu-id="cdeef-135">Доступ к индексу за пределами списка получить невозможно.</span><span class="sxs-lookup"><span data-stu-id="cdeef-135">You can't access an index beyond the end of the list.</span></span> <span data-ttu-id="cdeef-136">Помните, что индексы начинаются с 0, поэтому максимальный допустимый индекс меньше, чем число элементов в списке.</span><span class="sxs-lookup"><span data-stu-id="cdeef-136">Remember that indices start at 0, so the largest valid index is one less than the number of items in the list.</span></span> <span data-ttu-id="cdeef-137">Вы можете проверить, как долго в списке используется свойство <xref:System.Collections.Generic.List%601.Count%2A>.</span><span class="sxs-lookup"><span data-stu-id="cdeef-137">You can check how long the list is using the <xref:System.Collections.Generic.List%601.Count%2A> property.</span></span> <span data-ttu-id="cdeef-138">Добавьте следующий код в конец метода Main:</span><span class="sxs-lookup"><span data-stu-id="cdeef-138">Add the following code at the end of the Main method:</span></span>

```csharp
Console.WriteLine($"The list has {names.Count} people in it");
 ```

<span data-ttu-id="cdeef-139">Сохраните файл и еще раз введите `dotnet run`, чтобы просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="cdeef-139">Save the file, and type `dotnet run` again to see the results.</span></span>

## <a name="search-and-sort-lists"></a><span data-ttu-id="cdeef-140">Поиск по спискам и их сортировка</span><span class="sxs-lookup"><span data-stu-id="cdeef-140">Search and sort lists</span></span>

<span data-ttu-id="cdeef-141">В наших примерах используются сравнительно небольшие списки. Но приложения часто создают списки с гораздо большим количеством элементов, иногда они исчисляются в тысячах.</span><span class="sxs-lookup"><span data-stu-id="cdeef-141">Our samples use relatively small lists, but your applications may often create lists with many more elements, sometimes numbering in the thousands.</span></span> <span data-ttu-id="cdeef-142">Чтобы найти элементы в таких больших коллекциях, необходимо выполнить поиск различных элементов по списку.</span><span class="sxs-lookup"><span data-stu-id="cdeef-142">To find elements in these larger collections, you need to search the list for different items.</span></span> <span data-ttu-id="cdeef-143">Метод <xref:System.Collections.Generic.List%601.IndexOf%2A> выполняет поиск элемента и возвращает его индекс.</span><span class="sxs-lookup"><span data-stu-id="cdeef-143">The <xref:System.Collections.Generic.List%601.IndexOf%2A> method searches for an item and returns the index of the item.</span></span> <span data-ttu-id="cdeef-144">Если элемент отсутствует в списке, `IndexOf` возвращает `-1`.</span><span class="sxs-lookup"><span data-stu-id="cdeef-144">If the item isn't in the list, `IndexOf` returns `-1`.</span></span> <span data-ttu-id="cdeef-145">Добавьте следующий код в конец метода `Main`:</span><span class="sxs-lookup"><span data-stu-id="cdeef-145">Add this code to the bottom of your `Main` method:</span></span>

```csharp
var index = names.IndexOf("Felipe");
if (index == -1)
{
    Console.WriteLine($"When an item is not found, IndexOf returns {index}");
}
else
{
    Console.WriteLine($"The name {names[index]} is at index {index}");
}

index = names.IndexOf("Not Found");
if (index == -1)
{
    Console.WriteLine($"When an item is not found, IndexOf returns {index}");
}
else
{
    Console.WriteLine($"The name {names[index]} is at index {index}");

}
```

<span data-ttu-id="cdeef-146">Кроме того, можно сортировать элементы в списке.</span><span class="sxs-lookup"><span data-stu-id="cdeef-146">The items in your list can be sorted as well.</span></span> <span data-ttu-id="cdeef-147">Метод <xref:System.Collections.Generic.List%601.Sort%2A> сортирует все элементы списка в обычном порядке (строки — в алфавитном).</span><span class="sxs-lookup"><span data-stu-id="cdeef-147">The <xref:System.Collections.Generic.List%601.Sort%2A> method sorts all the items in the list in their normal order (alphabetically for strings).</span></span> <span data-ttu-id="cdeef-148">Добавьте следующий код в конец метода `Main`:</span><span class="sxs-lookup"><span data-stu-id="cdeef-148">Add this code to the bottom of our `Main` method:</span></span>

```csharp
names.Sort();
foreach (var name in names)
{
    Console.WriteLine($"Hello {name.ToUpper()}!");
}
```

<span data-ttu-id="cdeef-149">Сохраните файл и введите `dotnet run`, чтобы протестировать последнюю версию.</span><span class="sxs-lookup"><span data-stu-id="cdeef-149">Save the file and type `dotnet run` to try this latest version.</span></span>

<span data-ttu-id="cdeef-150">Прежде чем перейти к следующему разделу, переместим текущий код в отдельный метод.</span><span class="sxs-lookup"><span data-stu-id="cdeef-150">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="cdeef-151">Это упростит начало работы с новым примером.</span><span class="sxs-lookup"><span data-stu-id="cdeef-151">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="cdeef-152">Переименуйте метод `Main` в `WorkingWithStrings` и запишите новый метод `Main`, который вызывает `WorkingWithStrings`.</span><span class="sxs-lookup"><span data-stu-id="cdeef-152">Rename your `Main` method to `WorkingWithStrings` and write a new `Main` method that calls `WorkingWithStrings`.</span></span> <span data-ttu-id="cdeef-153">В результате ваш код должен выглядеть примерно так:</span><span class="sxs-lookup"><span data-stu-id="cdeef-153">When you've finished, your code should look like this:</span></span>

```csharp
using System;
using System.Collections.Generic;

namespace list_tutorial
{
    class Program
    {
        static void Main(string[] args)
        {
            WorkingWithStrings();
        }

        static void WorkingWithStrings()
        {
            var names = new List<string> { "<name>", "Ana", "Felipe" };
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }

            Console.WriteLine();
            names.Add("Maria");
            names.Add("Bill");
            names.Remove("Ana");
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }

            Console.WriteLine($"My name is {names[0]}");
            Console.WriteLine($"I've added {names[2]} and {names[3]} to the list");

            Console.WriteLine($"The list has {names.Count} people in it");

            var index = names.IndexOf("Felipe");
            if (index == -1)
            {
                Console.WriteLine($"When an item is not found, IndexOf returns {index}");
            }
            else
            {
                Console.WriteLine($"The name {names[index]} is at index {index}");
            }

            index = names.IndexOf("Not Found");
            if (index == -1)
            {
                Console.WriteLine($"When an item is not found, IndexOf returns {index}");
            }
            else
            {
                Console.WriteLine($"The name {names[index]} is at index {index}");

            }

            names.Sort();
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }
        }
    }
}
```

## <a name="lists-of-other-types"></a><span data-ttu-id="cdeef-154">Списки других типов</span><span class="sxs-lookup"><span data-stu-id="cdeef-154">Lists of other types</span></span>

<span data-ttu-id="cdeef-155">Вы уже использовали в списках тип `string`.</span><span class="sxs-lookup"><span data-stu-id="cdeef-155">You've been using the `string` type in lists so far.</span></span> <span data-ttu-id="cdeef-156">Создадим <xref:System.Collections.Generic.List%601> с использованием другого типа.</span><span class="sxs-lookup"><span data-stu-id="cdeef-156">Let's make a <xref:System.Collections.Generic.List%601> using a different type.</span></span> <span data-ttu-id="cdeef-157">Сначала создадим набор чисел.</span><span class="sxs-lookup"><span data-stu-id="cdeef-157">Let's build a set of numbers.</span></span>

<span data-ttu-id="cdeef-158">Добавьте следующий код в конец нового метода `Main`:</span><span class="sxs-lookup"><span data-stu-id="cdeef-158">Add the following to the bottom of your new `Main` method:</span></span>

```csharp
var fibonacciNumbers = new List<int> {1, 1};
```

<span data-ttu-id="cdeef-159">Будет создан список целых чисел. Для первых двух целых чисел будет задано значение 1.</span><span class="sxs-lookup"><span data-stu-id="cdeef-159">That creates a list of integers, and sets the first two integers to the value 1.</span></span> <span data-ttu-id="cdeef-160">Это два первых значения *последовательности Фибоначчи*.</span><span class="sxs-lookup"><span data-stu-id="cdeef-160">These are the first two values of a *Fibonacci Sequence*, a sequence of numbers.</span></span> <span data-ttu-id="cdeef-161">Каждое следующее число Фибоначчи — это сумма двух предыдущих чисел.</span><span class="sxs-lookup"><span data-stu-id="cdeef-161">Each next Fibonacci number is found by taking the sum of the previous two numbers.</span></span> <span data-ttu-id="cdeef-162">Добавьте этот код:</span><span class="sxs-lookup"><span data-stu-id="cdeef-162">Add this code:</span></span>

```csharp
var previous = fibonacciNumbers[fibonacciNumbers.Count - 1];
var previous2 = fibonacciNumbers[fibonacciNumbers.Count - 2];

fibonacciNumbers.Add(previous + previous2);

foreach (var item in fibonacciNumbers)
    Console.WriteLine(item);
```

<span data-ttu-id="cdeef-163">Сохраните файл и введите `dotnet run`, чтобы просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="cdeef-163">Save the file and type `dotnet run` to see the results.</span></span>

> [!TIP]
> <span data-ttu-id="cdeef-164">Для задач этого раздела вы можете закомментировать код, который вызывает `WorkingWithStrings();`.</span><span class="sxs-lookup"><span data-stu-id="cdeef-164">To concentrate on just this section, you can comment out the code that calls `WorkingWithStrings();`.</span></span> <span data-ttu-id="cdeef-165">Просто поместите два символа `/` перед вызовом. Например: `// WorkingWithStrings();`.</span><span class="sxs-lookup"><span data-stu-id="cdeef-165">Just put two `/` characters in front of the call like this:  `// WorkingWithStrings();`.</span></span>

## <a name="challenge"></a><span data-ttu-id="cdeef-166">Задача</span><span class="sxs-lookup"><span data-stu-id="cdeef-166">Challenge</span></span>

<span data-ttu-id="cdeef-167">Попробуйте объединить некоторые идеи из этого и предыдущих занятий.</span><span class="sxs-lookup"><span data-stu-id="cdeef-167">See if you can put together some of the concepts from this and earlier lessons.</span></span> <span data-ttu-id="cdeef-168">Расширьте код с числами Фибоначчи, который вы создали.</span><span class="sxs-lookup"><span data-stu-id="cdeef-168">Expand on what you've built so far with Fibonacci Numbers.</span></span> <span data-ttu-id="cdeef-169">Попробуйте написать код для создания первых 20 чисел в последовательности.</span><span class="sxs-lookup"><span data-stu-id="cdeef-169">Try to write the code to generate the first 20 numbers in the sequence.</span></span> <span data-ttu-id="cdeef-170">Подсказка: 20-е число Фибоначчи — 6765.</span><span class="sxs-lookup"><span data-stu-id="cdeef-170">(As a hint, the 20th Fibonacci number is 6765.)</span></span>

## <a name="complete-challenge"></a><span data-ttu-id="cdeef-171">Выполнение задачи</span><span class="sxs-lookup"><span data-stu-id="cdeef-171">Complete challenge</span></span>

<span data-ttu-id="cdeef-172">Пример решения можно [просмотреть в готовом примере кода на GitHub](https://github.com/dotnet/samples/tree/master/csharp/list-quickstart/Program.cs#L13-L23).</span><span class="sxs-lookup"><span data-stu-id="cdeef-172">You can see an example solution by [looking at the finished sample code on GitHub](https://github.com/dotnet/samples/tree/master/csharp/list-quickstart/Program.cs#L13-L23).</span></span>

<span data-ttu-id="cdeef-173">При каждой итерации цикла суммируются два последних целых числа в списке. Полученное значение добавляется в список.</span><span class="sxs-lookup"><span data-stu-id="cdeef-173">With each iteration of the loop, you're taking the last two integers in the list, summing them, and adding that value to the list.</span></span> <span data-ttu-id="cdeef-174">Цикл повторяется, пока в список не будут добавлены 20 элементов.</span><span class="sxs-lookup"><span data-stu-id="cdeef-174">The loop repeats until you've added 20 items to the list.</span></span>

<span data-ttu-id="cdeef-175">Поздравляем! Вы выполнили задачи в руководстве по спискам.</span><span class="sxs-lookup"><span data-stu-id="cdeef-175">Congratulations, you've completed the list tutorial.</span></span> <span data-ttu-id="cdeef-176">Теперь вы можете выполнить задачи [вводного руководства по классам](introduction-to-classes.md) в своей среде разработки.</span><span class="sxs-lookup"><span data-stu-id="cdeef-176">You can continue with the [Introduction to classes](introduction-to-classes.md) tutorial in your own development environment.</span></span>

<span data-ttu-id="cdeef-177">Дополнительные сведения о работе с типом `List` см. в статье [Коллекции и структуры данных](../../../standard/collections/index.md).</span><span class="sxs-lookup"><span data-stu-id="cdeef-177">You can learn more about working with the `List` type in the .NET fundamentals article on [collections](../../../standard/collections/index.md).</span></span> <span data-ttu-id="cdeef-178">Также в нем описаны многие другие типы коллекций.</span><span class="sxs-lookup"><span data-stu-id="cdeef-178">You'll also learn about many other collection types.</span></span>
