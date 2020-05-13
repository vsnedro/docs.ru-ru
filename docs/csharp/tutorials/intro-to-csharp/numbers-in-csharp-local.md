---
title: Числа в C#. Вводное руководство по C#
description: Изучите C# на примере числовых типов, их использования, свойств и методов.
ms.date: 10/31/2017
ms.custom: mvc
ms.openlocfilehash: 3dc2a5afc6321da45351525a632f586cb84bf7fe
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "82794616"
---
# <a name="manipulate-integral-and-floating-point-numbers-in-c"></a><span data-ttu-id="031e8-103">Управление целыми числами и числами с плавающей запятой в C\#</span><span class="sxs-lookup"><span data-stu-id="031e8-103">Manipulate integral and floating point numbers in C\#</span></span>

<span data-ttu-id="031e8-104">Это руководство поможет в интерактивном изучении числовых типов в C#.</span><span class="sxs-lookup"><span data-stu-id="031e8-104">This tutorial teaches you about the numeric types in C# interactively.</span></span> <span data-ttu-id="031e8-105">Вы напишете небольшие фрагменты кода, затем скомпилируете и выполните этот код.</span><span class="sxs-lookup"><span data-stu-id="031e8-105">You'll write small amounts of code, then you'll compile and run that code.</span></span> <span data-ttu-id="031e8-106">Руководство содержит ряд уроков, в которых рассматриваются числа и математические операции в C#.</span><span class="sxs-lookup"><span data-stu-id="031e8-106">The tutorial contains a series of lessons that explore numbers and math operations in C#.</span></span> <span data-ttu-id="031e8-107">В рамках этих занятий вы ознакомитесь с основами языка C#.</span><span class="sxs-lookup"><span data-stu-id="031e8-107">These lessons teach you the fundamentals of the C# language.</span></span>

<span data-ttu-id="031e8-108">Для работы с этим руководством вам потребуется компьютер, который можно использовать для разработки.</span><span class="sxs-lookup"><span data-stu-id="031e8-108">This tutorial expects you to have a machine you can use for development.</span></span> <span data-ttu-id="031e8-109">В руководстве .NET по созданию программы [Hello World за 10 минут](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) содержатся инструкции по настройке локальной среды разработки в macOS, Windows или Linux.</span><span class="sxs-lookup"><span data-stu-id="031e8-109">The .NET tutorial [Hello World in 10 minutes](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) has instructions for setting up your local development environment on Windows, Linux, or macOS.</span></span> <span data-ttu-id="031e8-110">Краткий обзор команд, которые будут здесь использоваться, и ссылки на дополнительные сведения представлены в статье, посвященной [средствам разработки для .NET](local-environment.md).</span><span class="sxs-lookup"><span data-stu-id="031e8-110">A quick overview of the commands you'll use is in the [Become familiar with the development tools](local-environment.md) with links to more details.</span></span>

## <a name="explore-integer-math"></a><span data-ttu-id="031e8-111">Вычисления с целыми числами</span><span class="sxs-lookup"><span data-stu-id="031e8-111">Explore integer math</span></span>

<span data-ttu-id="031e8-112">Создайте каталог с именем *numbers-quickstart*.</span><span class="sxs-lookup"><span data-stu-id="031e8-112">Create a directory named *numbers-quickstart*.</span></span> <span data-ttu-id="031e8-113">Сделайте его текущим, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="031e8-113">Make that the current directory and run the following command:</span></span>

```dotnetcli
dotnet new console -n NumbersInCSharp -o .
```

<span data-ttu-id="031e8-114">Откройте файл *Program.cs* в любом редакторе и замените строку `Console.WriteLine("Hello World!");` следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="031e8-114">Open *Program.cs* in your favorite editor, and replace the line `Console.WriteLine("Hello World!");` with the following code:</span></span>

```csharp
int a = 18;
int b = 6;
int c = a + b;
Console.WriteLine(c);
```

<span data-ttu-id="031e8-115">Чтобы выполнить этот код, введите `dotnet run` в окно командной строки.</span><span class="sxs-lookup"><span data-stu-id="031e8-115">Run this code by typing `dotnet run` in your command window.</span></span>

<span data-ttu-id="031e8-116">Вы увидели одну из основных математических операций с целыми числами.</span><span class="sxs-lookup"><span data-stu-id="031e8-116">You've seen one of the fundamental math operations with integers.</span></span> <span data-ttu-id="031e8-117">Тип `int` представляет **целое** положительное или отрицательное число или ноль.</span><span class="sxs-lookup"><span data-stu-id="031e8-117">The `int` type represents an **integer**, a zero, positive, or negative whole number.</span></span> <span data-ttu-id="031e8-118">Для сложения используйте символ `+`.</span><span class="sxs-lookup"><span data-stu-id="031e8-118">You use the `+` symbol for addition.</span></span> <span data-ttu-id="031e8-119">Другие стандартные математические операции с целыми числами включают:</span><span class="sxs-lookup"><span data-stu-id="031e8-119">Other common mathematical operations for integers include:</span></span>

- <span data-ttu-id="031e8-120">`-` — вычитание;</span><span class="sxs-lookup"><span data-stu-id="031e8-120">`-` for subtraction</span></span>
- <span data-ttu-id="031e8-121">`*` — умножение;</span><span class="sxs-lookup"><span data-stu-id="031e8-121">`*` for multiplication</span></span>
- <span data-ttu-id="031e8-122">`/` — деление.</span><span class="sxs-lookup"><span data-stu-id="031e8-122">`/` for division</span></span>

<span data-ttu-id="031e8-123">Начните с ознакомления с различными операциями.</span><span class="sxs-lookup"><span data-stu-id="031e8-123">Start by exploring those different operations.</span></span> <span data-ttu-id="031e8-124">Добавьте следующие строки после строки, с помощью которой записывается значение `c`:</span><span class="sxs-lookup"><span data-stu-id="031e8-124">Add these lines after the line that writes the value of `c`:</span></span>

```csharp

// subtraction
c = a - b;
Console.WriteLine(c);

// multiplication
c = a * b;
Console.WriteLine(c);

// division
c = a / b;
Console.WriteLine(c);
```

<span data-ttu-id="031e8-125">Чтобы выполнить этот код, введите `dotnet run` в окно командной строки.</span><span class="sxs-lookup"><span data-stu-id="031e8-125">Run this code by typing `dotnet run` in your command window.</span></span>

<span data-ttu-id="031e8-126">Можно также поэкспериментировать, написав несколько математических операций в одной строке.</span><span class="sxs-lookup"><span data-stu-id="031e8-126">You can also experiment by writing multiple mathematics operations in the same line, if you'd like.</span></span> <span data-ttu-id="031e8-127">Например, выполните `c = a + b - 12 * 17;`.</span><span class="sxs-lookup"><span data-stu-id="031e8-127">Try `c = a + b - 12 * 17;` for example.</span></span> <span data-ttu-id="031e8-128">Допускается сочетание переменных и постоянных чисел.</span><span class="sxs-lookup"><span data-stu-id="031e8-128">Mixing variables and constant numbers is allowed.</span></span>

> [!TIP]
> <span data-ttu-id="031e8-129">Вероятнее всего, при изучении C# (как и любого другого языка программирования) вы будете допускать ошибки в коде.</span><span class="sxs-lookup"><span data-stu-id="031e8-129">As you explore C# (or any programming language), you'll make mistakes when you write code.</span></span> <span data-ttu-id="031e8-130">**Компилятор** найдет эти ошибки и сообщит вам о них.</span><span class="sxs-lookup"><span data-stu-id="031e8-130">The **compiler** will find those errors and report them to you.</span></span> <span data-ttu-id="031e8-131">Если результат содержит сообщения об ошибках, внимательно просмотрите пример кода и код в окне, чтобы понять, что нужно исправить.</span><span class="sxs-lookup"><span data-stu-id="031e8-131">When the output contains error messages, look closely at the example code and the code in your window to see what to fix.</span></span>
> <span data-ttu-id="031e8-132">Это упражнение поможет вам изучить структуру кода C#.</span><span class="sxs-lookup"><span data-stu-id="031e8-132">That exercise will help you learn the structure of C# code.</span></span>

<span data-ttu-id="031e8-133">Вы завершили первый этап.</span><span class="sxs-lookup"><span data-stu-id="031e8-133">You've finished the first step.</span></span> <span data-ttu-id="031e8-134">Прежде чем перейти к следующему разделу, переместим текущий код в отдельный метод.</span><span class="sxs-lookup"><span data-stu-id="031e8-134">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="031e8-135">Это упростит начало работы с новым примером.</span><span class="sxs-lookup"><span data-stu-id="031e8-135">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="031e8-136">Переименуйте метод `Main` в `WorkingWithIntegers` и запишите новый метод `Main`, который вызывает `WorkingWithIntegers`.</span><span class="sxs-lookup"><span data-stu-id="031e8-136">Rename your `Main` method to `WorkingWithIntegers` and write a new `Main` method that calls `WorkingWithIntegers`.</span></span> <span data-ttu-id="031e8-137">В результате ваш код должен выглядеть примерно следующим образом:</span><span class="sxs-lookup"><span data-stu-id="031e8-137">When you finish, your code should look like this:</span></span>

```csharp
using System;

namespace NumbersInCSharp
{
    class Program
    {
        static void WorkingWithIntegers()
        {
            int a = 18;
            int b = 6;

            // addition
            int c = a + b;
            Console.WriteLine(c);

            // subtraction
            c = a - b;
            Console.WriteLine(c);

            // multiplication
            c = a * b;
            Console.WriteLine(c);

            // division
            c = a / b;
            Console.WriteLine(c);
        }

        static void Main(string[] args)
        {
            WorkingWithIntegers();
        }
    }
}
```

## <a name="explore-order-of-operations"></a><span data-ttu-id="031e8-138">Изучение порядка операций</span><span class="sxs-lookup"><span data-stu-id="031e8-138">Explore order of operations</span></span>

<span data-ttu-id="031e8-139">Закомментируйте вызов `WorkingWithIntegers()`.</span><span class="sxs-lookup"><span data-stu-id="031e8-139">Comment out the call to `WorkingWithIntegers()`.</span></span> <span data-ttu-id="031e8-140">Это поможет упорядочить выходные данные в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="031e8-140">It will make the output less cluttered as you work in this section:</span></span>

```csharp
//WorkingWithIntegers();
```

<span data-ttu-id="031e8-141">`//` запускает **комментарий** в C#.</span><span class="sxs-lookup"><span data-stu-id="031e8-141">The `//` starts a **comment** in C#.</span></span> <span data-ttu-id="031e8-142">Комментарии — это любой текст, который должен быть сохранен в исходном коде, но не должен выполняться как код.</span><span class="sxs-lookup"><span data-stu-id="031e8-142">Comments are any text you want to keep in your source code but not execute as code.</span></span> <span data-ttu-id="031e8-143">Компилятор не создает исполняемый код из комментариев.</span><span class="sxs-lookup"><span data-stu-id="031e8-143">The compiler doesn't generate any executable code from comments.</span></span>

<span data-ttu-id="031e8-144">Язык C# определяет приоритет математических операций в соответствии с правилами математики.</span><span class="sxs-lookup"><span data-stu-id="031e8-144">The C# language defines the precedence of different mathematics operations with rules consistent with the rules you learned in mathematics.</span></span>
<span data-ttu-id="031e8-145">Умножение и деление имеют приоритет над сложением и вычитанием.</span><span class="sxs-lookup"><span data-stu-id="031e8-145">Multiplication and division take precedence over addition and subtraction.</span></span>
<span data-ttu-id="031e8-146">Чтобы удостовериться в этом, добавьте следующий код в метод `Main` и выполните команду `dotnet run`:</span><span class="sxs-lookup"><span data-stu-id="031e8-146">Explore that by adding the following code to your `Main` method, and executing `dotnet run`:</span></span>

```csharp
int a = 5;
int b = 4;
int c = 2;
int d = a + b * c;
Console.WriteLine(d);
 ```

<span data-ttu-id="031e8-147">В выходных данных видно, что умножение выполняется раньше сложения.</span><span class="sxs-lookup"><span data-stu-id="031e8-147">The output demonstrates that the multiplication is performed before the addition.</span></span>

<span data-ttu-id="031e8-148">Можно применить другую последовательность операций. Для этого операции, которые должны выполняться первыми, нужно заключить в скобки.</span><span class="sxs-lookup"><span data-stu-id="031e8-148">You can force a different order of operation by adding parentheses around the operation or operations you want performed first.</span></span> <span data-ttu-id="031e8-149">Добавьте приведенные ниже строки и выполните код еще раз.</span><span class="sxs-lookup"><span data-stu-id="031e8-149">Add the following lines and run again:</span></span>

```csharp
d = (a + b) * c;
Console.WriteLine(d);
```

<span data-ttu-id="031e8-150">Поэкспериментируйте, объединяя различные операции.</span><span class="sxs-lookup"><span data-stu-id="031e8-150">Explore more by combining many different operations.</span></span> <span data-ttu-id="031e8-151">Добавьте в конец метода `Main` строки, подобные приведенным ниже.</span><span class="sxs-lookup"><span data-stu-id="031e8-151">Add something like the following lines at the bottom of your `Main` method.</span></span> <span data-ttu-id="031e8-152">Выполните `dotnet run` еще раз.</span><span class="sxs-lookup"><span data-stu-id="031e8-152">Try `dotnet run` again.</span></span>

```csharp
d = (a + b) - 6 * c + (12 * 4) / 3 + 12;
Console.WriteLine(d);
```

<span data-ttu-id="031e8-153">Возможно, вы заметили интересное поведение целых чисел.</span><span class="sxs-lookup"><span data-stu-id="031e8-153">You may have noticed an interesting behavior for integers.</span></span> <span data-ttu-id="031e8-154">Деление целых чисел всегда дает результат в виде целого числа, даже если ожидаемый результат содержит десятичную или дробную часть.</span><span class="sxs-lookup"><span data-stu-id="031e8-154">Integer division always produces an integer result, even when you'd expect the result to include a decimal or fractional portion.</span></span>

<span data-ttu-id="031e8-155">Если вы еще не видели пример такого поведения, добавьте следующий код в конец метода `Main`:</span><span class="sxs-lookup"><span data-stu-id="031e8-155">If you haven't seen this behavior, try the following code at the end of your `Main` method:</span></span>

```csharp
int e = 7;
int f = 4;
int g = 3;
int h = (e + f) / g;
Console.WriteLine(h);
```

<span data-ttu-id="031e8-156">Выполните `dotnet run` еще раз, чтобы просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="031e8-156">Type `dotnet run` again to see the results.</span></span>

<span data-ttu-id="031e8-157">Прежде чем продолжить, давайте поместив весь код, который вы написали в этом разделе, в новый метод.</span><span class="sxs-lookup"><span data-stu-id="031e8-157">Before moving on, let's take all the code you've written in this section and put it in a new method.</span></span> <span data-ttu-id="031e8-158">Вызовите этот новый метод `OrderPrecedence`.</span><span class="sxs-lookup"><span data-stu-id="031e8-158">Call that new method `OrderPrecedence`.</span></span>
<span data-ttu-id="031e8-159">Результат должен быть примерно таким:</span><span class="sxs-lookup"><span data-stu-id="031e8-159">You should write something like this:</span></span>

```csharp
using System;

namespace NumbersInCSharp
{
    class Program
    {
        static void WorkingWithIntegers()
        {
            int a = 18;
            int b = 6;

            // addition
            int c = a + b;
            Console.WriteLine(c);

            // subtraction
            c = a - b;
            Console.WriteLine(c);

            // multiplication
            c = a * b;
            Console.WriteLine(c);

            // division
            c = a / b;
            Console.WriteLine(c);
        }

        static void OrderPrecedence()
        {
            int a = 5;
            int b = 4;
            int c = 2;
            int d = a + b * c;
            Console.WriteLine(d);

            d = (a + b) * c;
            Console.WriteLine(d);

            d = (a + b) - 6 * c + (12 * 4) / 3 + 12;
            Console.WriteLine(d);

            int e = 7;
            int f = 4;
            int g = 3;
            int h = (e  + f) / g;
            Console.WriteLine(h);
        }

        static void Main(string[] args)
        {
            WorkingWithIntegers();

            OrderPrecedence();

        }
    }
}
```

## <a name="explore-integer-precision-and-limits"></a><span data-ttu-id="031e8-160">Изучение точности и ограничений для целых чисел</span><span class="sxs-lookup"><span data-stu-id="031e8-160">Explore integer precision and limits</span></span>

<span data-ttu-id="031e8-161">В последнем примере вы увидели, что при делении целых чисел результат усекается.</span><span class="sxs-lookup"><span data-stu-id="031e8-161">That last sample showed you that integer division truncates the result.</span></span>
<span data-ttu-id="031e8-162">Вы можете получить **остаток** с помощью оператора **остатка от деления**, который обозначается символом `%`.</span><span class="sxs-lookup"><span data-stu-id="031e8-162">You can get the **remainder** by using the **modulo** operator, the `%` character.</span></span> <span data-ttu-id="031e8-163">Попробуйте добавить приведенный ниже код в метод `Main`.</span><span class="sxs-lookup"><span data-stu-id="031e8-163">Try the following code in your `Main` method:</span></span>

```csharp
int a = 7;
int b = 4;
int c = 3;
int d = (a + b) / c;
int e = (a + b) % c;
Console.WriteLine($"quotient: {d}");
Console.WriteLine($"remainder: {e}");
```

<span data-ttu-id="031e8-164">Тип целых чисел C# характеризуется еще одним отличием от математических целых: тип `int` имеет минимальные и максимальные ограничения.</span><span class="sxs-lookup"><span data-stu-id="031e8-164">The C# integer type differs from mathematical integers in one other way: the `int` type has minimum and maximum limits.</span></span> <span data-ttu-id="031e8-165">Добавьте следующий код в метод `Main`, чтобы просмотреть эти ограничения:</span><span class="sxs-lookup"><span data-stu-id="031e8-165">Add this code to your `Main` method to see those limits:</span></span>

```csharp
int max = int.MaxValue;
int min = int.MinValue;
Console.WriteLine($"The range of integers is {min} to {max}");
```

<span data-ttu-id="031e8-166">Если при вычислении выводится значение вне этих пределов, возникает условие **потери значимости** или **переполнения**.</span><span class="sxs-lookup"><span data-stu-id="031e8-166">If a calculation produces a value that exceeds those limits, you have an **underflow** or **overflow** condition.</span></span> <span data-ttu-id="031e8-167">Ответ должен находиться в диапазоне от минимального до максимального значения.</span><span class="sxs-lookup"><span data-stu-id="031e8-167">The answer appears to wrap from one limit to the other.</span></span> <span data-ttu-id="031e8-168">Добавьте следующие две строки в метод `Main`, чтобы увидеть пример:</span><span class="sxs-lookup"><span data-stu-id="031e8-168">Add these two lines to your `Main` method to see an example:</span></span>

```csharp
int what = max + 3;
Console.WriteLine($"An example of overflow: {what}");
```

<span data-ttu-id="031e8-169">Обратите внимание, что ответ очень близок к минимальному целому числу (отрицательное значение).</span><span class="sxs-lookup"><span data-stu-id="031e8-169">Notice that the answer is very close to the minimum (negative) integer.</span></span> <span data-ttu-id="031e8-170">Он совпадает со значением `min + 2`.</span><span class="sxs-lookup"><span data-stu-id="031e8-170">It's the same as `min + 2`.</span></span>
<span data-ttu-id="031e8-171">Оператор сложения **вызвал переполнение** допустимых значений для целых чисел.</span><span class="sxs-lookup"><span data-stu-id="031e8-171">The addition operation **overflowed** the allowed values for integers.</span></span>
<span data-ttu-id="031e8-172">Ответ является очень большим отрицательным числом, так как переполнение покрывает диапазон от наибольшего целого числа до наименьшего.</span><span class="sxs-lookup"><span data-stu-id="031e8-172">The answer is a very large negative number because an overflow "wraps around" from the largest possible integer value to the smallest.</span></span>

<span data-ttu-id="031e8-173">Существуют другие числовые типы с различными ограничениями и точностью, которые можно использовать, если тип `int` не соответствует вашим требованиям.</span><span class="sxs-lookup"><span data-stu-id="031e8-173">There are other numeric types with different limits and precision that you would use when the `int` type doesn't meet your needs.</span></span> <span data-ttu-id="031e8-174">Далее рассмотрим другие типы.</span><span class="sxs-lookup"><span data-stu-id="031e8-174">Let's explore those other types next.</span></span>

<span data-ttu-id="031e8-175">Давайте еще раз переместим код, написанный в этом разделе, в отдельный метод.</span><span class="sxs-lookup"><span data-stu-id="031e8-175">Once again, let's move the code you wrote in this section into a separate method.</span></span> <span data-ttu-id="031e8-176">Присвойте обработчику события имя `TestLimits`.</span><span class="sxs-lookup"><span data-stu-id="031e8-176">Name it `TestLimits`.</span></span>

## <a name="work-with-the-double-type"></a><span data-ttu-id="031e8-177">Работа с типом double</span><span class="sxs-lookup"><span data-stu-id="031e8-177">Work with the double type</span></span>

<span data-ttu-id="031e8-178">Числовой тип `double` представляет число с плавающей запятой двойной точности.</span><span class="sxs-lookup"><span data-stu-id="031e8-178">The `double` numeric type represents a double-precision floating point number.</span></span> <span data-ttu-id="031e8-179">Эти термины могут быть новыми для вас.</span><span class="sxs-lookup"><span data-stu-id="031e8-179">Those terms may be new to you.</span></span> <span data-ttu-id="031e8-180">Число **с плавающей запятой** можно использовать для представления нецелых чисел, которые могут быть очень большими или малыми.</span><span class="sxs-lookup"><span data-stu-id="031e8-180">A **floating point** number is useful to represent non-integral numbers that may be very large or small in magnitude.</span></span> <span data-ttu-id="031e8-181">**Число двойной точности** — это относительный термин, описывающий количество двоичных разрядов, используемых для хранения значения.</span><span class="sxs-lookup"><span data-stu-id="031e8-181">**Double-precision** is a relative term that describes the number of binary digits used to store the value.</span></span> <span data-ttu-id="031e8-182">**Числа двойной точности** имеют в два раза больше двоичных символов по сравнению с **числами одиночной точности**.</span><span class="sxs-lookup"><span data-stu-id="031e8-182">**Double precision** numbers have twice the number of binary digits as **single-precision**.</span></span> <span data-ttu-id="031e8-183">На современных компьютерах числа двойной точности используются чаще, чем одиночной.</span><span class="sxs-lookup"><span data-stu-id="031e8-183">On modern computers, it's more common to use double precision than single precision numbers.</span></span> <span data-ttu-id="031e8-184">**Числа одиночной точности** объявляются с помощью ключевого слова `float`.</span><span class="sxs-lookup"><span data-stu-id="031e8-184">**Single precision** numbers are declared using the `float` keyword.</span></span>
<span data-ttu-id="031e8-185">Рассмотрим их.</span><span class="sxs-lookup"><span data-stu-id="031e8-185">Let's explore.</span></span> <span data-ttu-id="031e8-186">Добавьте следующий код и просмотрите результат:</span><span class="sxs-lookup"><span data-stu-id="031e8-186">Add the following code and see the result:</span></span>

```csharp
double a = 5;
double b = 4;
double c = 2;
double d = (a + b) / c;
Console.WriteLine(d);
```

<span data-ttu-id="031e8-187">Обратите внимание, что ответ включает десятичную долю частного.</span><span class="sxs-lookup"><span data-stu-id="031e8-187">Notice that the answer includes the decimal portion of the quotient.</span></span> <span data-ttu-id="031e8-188">Попробуйте более сложное выражение с типом double:</span><span class="sxs-lookup"><span data-stu-id="031e8-188">Try a slightly more complicated expression with doubles:</span></span>

```csharp
double e = 19;
double f = 23;
double g = 8;
double h = (e + f) / g;
Console.WriteLine(h);
```

<span data-ttu-id="031e8-189">Диапазон значений типа double гораздо больше, чем диапазон значений целых чисел.</span><span class="sxs-lookup"><span data-stu-id="031e8-189">The range of a double value is much greater than integer values.</span></span> <span data-ttu-id="031e8-190">Добавьте следующий фрагмент после написанного кода:</span><span class="sxs-lookup"><span data-stu-id="031e8-190">Try the following code below what you've written so far:</span></span>

```csharp
double max = double.MaxValue;
double min = double.MinValue;
Console.WriteLine($"The range of double is {min} to {max}");
```

<span data-ttu-id="031e8-191">Значения выводятся в экспоненциальном представлении.</span><span class="sxs-lookup"><span data-stu-id="031e8-191">These values are printed out in scientific notation.</span></span> <span data-ttu-id="031e8-192">Число слева от символа `E` является значащим.</span><span class="sxs-lookup"><span data-stu-id="031e8-192">The number to the left of the `E` is the significand.</span></span> <span data-ttu-id="031e8-193">Число справа — это показатель степени, который равен 10.</span><span class="sxs-lookup"><span data-stu-id="031e8-193">The number to the right is the exponent, as a power of 10.</span></span>

<span data-ttu-id="031e8-194">Так же, как десятичные числа в математике, значения double в C# могут содержать ошибки округления.</span><span class="sxs-lookup"><span data-stu-id="031e8-194">Just like decimal numbers in math, doubles in C# can have rounding errors.</span></span> <span data-ttu-id="031e8-195">Выполните этот код:</span><span class="sxs-lookup"><span data-stu-id="031e8-195">Try this code:</span></span>

```csharp
double third = 1.0 / 3.0;
Console.WriteLine(third);
```

<span data-ttu-id="031e8-196">Вы знаете, что периодическая десятичная дробь `0.3` не равняется `1/3`.</span><span class="sxs-lookup"><span data-stu-id="031e8-196">You know that `0.3` repeating isn't exactly the same as `1/3`.</span></span>

<span data-ttu-id="031e8-197">***Задача***</span><span class="sxs-lookup"><span data-stu-id="031e8-197">***Challenge***</span></span>

<span data-ttu-id="031e8-198">Выполните другие вычисления с большими числами, малыми числами, умножением и делением с помощью типа `double`.</span><span class="sxs-lookup"><span data-stu-id="031e8-198">Try other calculations with large numbers, small numbers, multiplication, and division using the `double` type.</span></span> <span data-ttu-id="031e8-199">Попробуйте выполнить более сложные вычисления.</span><span class="sxs-lookup"><span data-stu-id="031e8-199">Try more complicated calculations.</span></span>

<span data-ttu-id="031e8-200">После того как вы решите сложную задачу, поместите написанный код в новый метод.</span><span class="sxs-lookup"><span data-stu-id="031e8-200">After you've spent some time with the challenge, take the code you've written and place it in a new method.</span></span> <span data-ttu-id="031e8-201">Присвойте этому методу имя `WorkWithDoubles`.</span><span class="sxs-lookup"><span data-stu-id="031e8-201">Name that new method `WorkWithDoubles`.</span></span>

## <a name="work-with-decimal-types"></a><span data-ttu-id="031e8-202">Работа с десятичными типами</span><span class="sxs-lookup"><span data-stu-id="031e8-202">Work with decimal types</span></span>

<span data-ttu-id="031e8-203">Вы уже ознакомились с базовыми числовыми типами в C# — целыми числами и числами типа double.</span><span class="sxs-lookup"><span data-stu-id="031e8-203">You've seen the basic numeric types in C#: integers and doubles.</span></span>  <span data-ttu-id="031e8-204">Осталось изучить еще один тип: `decimal`.</span><span class="sxs-lookup"><span data-stu-id="031e8-204">There's one other type to learn: the `decimal` type.</span></span> <span data-ttu-id="031e8-205">Тип `decimal` имеет меньший диапазон, но большую точность, чем `double`.</span><span class="sxs-lookup"><span data-stu-id="031e8-205">The `decimal` type has a smaller range but greater precision than `double`.</span></span> <span data-ttu-id="031e8-206">Например:</span><span class="sxs-lookup"><span data-stu-id="031e8-206">Let's take a look:</span></span>

```csharp
decimal min = decimal.MinValue;
decimal max = decimal.MaxValue;
Console.WriteLine($"The range of the decimal type is {min} to {max}");
```

<span data-ttu-id="031e8-207">Обратите внимание, что диапазон меньше, чем для типа `double`.</span><span class="sxs-lookup"><span data-stu-id="031e8-207">Notice that the range is smaller than the `double` type.</span></span> <span data-ttu-id="031e8-208">Вы можете убедиться в повышении точности при использовании типа decimal, выполнив следующий код:</span><span class="sxs-lookup"><span data-stu-id="031e8-208">You can see the greater precision with the decimal type by trying the following code:</span></span>

```csharp
double a = 1.0;
double b = 3.0;
Console.WriteLine(a / b);

decimal c = 1.0M;
decimal d = 3.0M;
Console.WriteLine(c / d);
```

<span data-ttu-id="031e8-209">Суффикс `M` возле чисел указывает, что для константы должен использоваться тип `decimal`.</span><span class="sxs-lookup"><span data-stu-id="031e8-209">The `M` suffix on the numbers is how you indicate that a constant should use the `decimal` type.</span></span> <span data-ttu-id="031e8-210">В противном случае компилятор предполагает тип `double`.</span><span class="sxs-lookup"><span data-stu-id="031e8-210">Otherwise, the compiler assumes the `double` type.</span></span>

> [!NOTE]
> <span data-ttu-id="031e8-211">Буква `M` была выбрана потому, что визуально показывает различия между ключевыми словами `double` и `decimal`.</span><span class="sxs-lookup"><span data-stu-id="031e8-211">The letter `M` was chosen as the most visually distinct letter between the `double` and `decimal` keywords.</span></span>

<span data-ttu-id="031e8-212">Обратите внимание, что при вычислении с использованием типа decimal справа от запятой содержится больше цифр.</span><span class="sxs-lookup"><span data-stu-id="031e8-212">Notice that the math using the decimal type has more digits to the right of the decimal point.</span></span>

<span data-ttu-id="031e8-213">***Задача***</span><span class="sxs-lookup"><span data-stu-id="031e8-213">***Challenge***</span></span>

<span data-ttu-id="031e8-214">Теперь, когда вы ознакомились с разными числовыми типами, напишите код, который позволяет вычислить площадь круга с радиусом 2,50 см.</span><span class="sxs-lookup"><span data-stu-id="031e8-214">Now that you've seen the different numeric types, write code that calculates the area of a circle whose radius is 2.50 centimeters.</span></span> <span data-ttu-id="031e8-215">Помните, что площадь круга равна квадрату радиуса, умноженному на число пи.</span><span class="sxs-lookup"><span data-stu-id="031e8-215">Remember that the area of a circle is the radius squared multiplied by PI.</span></span> <span data-ttu-id="031e8-216">Подсказка: в .NET есть константа пи <xref:System.Math.PI?displayProperty=nameWithType>, которую можно использовать.</span><span class="sxs-lookup"><span data-stu-id="031e8-216">One hint: .NET contains a constant for PI, <xref:System.Math.PI?displayProperty=nameWithType> that you can use for that value.</span></span> <span data-ttu-id="031e8-217"><xref:System.Math.PI?displayProperty=nameWithType>, как и все константы, объявленные в пространстве имен `System.Math`, — это значение `double`.</span><span class="sxs-lookup"><span data-stu-id="031e8-217"><xref:System.Math.PI?displayProperty=nameWithType>, like all constants declared in the `System.Math` namespace, is a `double` value.</span></span> <span data-ttu-id="031e8-218">По этой причине вместо значений `decimal` для этой задачи следует использовать `double`.</span><span class="sxs-lookup"><span data-stu-id="031e8-218">For that reason, you should use `double` instead of `decimal` values for this challenge.</span></span>

<span data-ttu-id="031e8-219">Вы должны получить ответ от 19 до 20.</span><span class="sxs-lookup"><span data-stu-id="031e8-219">You should get an answer between 19 and 20.</span></span>
<span data-ttu-id="031e8-220">Ответ можно [просмотреть в готовом примере кода на GitHub](https://github.com/dotnet/samples/tree/master/csharp/numbers-quickstart/Program.cs#L104-L106).</span><span class="sxs-lookup"><span data-stu-id="031e8-220">You can check your answer by [looking at the finished sample code on GitHub](https://github.com/dotnet/samples/tree/master/csharp/numbers-quickstart/Program.cs#L104-L106).</span></span>

<span data-ttu-id="031e8-221">При желании поэкспериментируйте с другими формулами.</span><span class="sxs-lookup"><span data-stu-id="031e8-221">Try some other formulas if you'd like.</span></span>

<span data-ttu-id="031e8-222">Вы выполнили все задачи краткого руководства по числам в C#.</span><span class="sxs-lookup"><span data-stu-id="031e8-222">You've completed the "Numbers in C#" quickstart.</span></span> <span data-ttu-id="031e8-223">Теперь вы можете выполнить руководство по [ветвям и циклам](branches-and-loops-local.md) в своей среде разработки.</span><span class="sxs-lookup"><span data-stu-id="031e8-223">You can continue with the [Branches and loops](branches-and-loops-local.md) quickstart in your own development environment.</span></span>

<span data-ttu-id="031e8-224">Дополнительные сведения о числах в C# см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="031e8-224">You can learn more about numbers in C# in the following articles:</span></span>

- [<span data-ttu-id="031e8-225">Целочисленные типы</span><span class="sxs-lookup"><span data-stu-id="031e8-225">Integral numeric types</span></span>](../../language-reference/builtin-types/integral-numeric-types.md)
- [<span data-ttu-id="031e8-226">Числовые типы с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="031e8-226">Floating-point numeric types</span></span>](../../language-reference/builtin-types/floating-point-numeric-types.md)
- [<span data-ttu-id="031e8-227">Встроенные числовые преобразования</span><span class="sxs-lookup"><span data-stu-id="031e8-227">Built-in numeric conversions</span></span>](../../language-reference/builtin-types/numeric-conversions.md)
