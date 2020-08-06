---
title: Рефакторинг в чистые функции (C#)
description: Сведения о рефакторинге кода с использованием чистых функций. Изучите примеры кода и ознакомьтесь с дополнительными ресурсами.
ms.date: 07/20/2015
ms.assetid: 2944a0d4-fd33-4e2e-badd-abb0f9be2fcc
ms.openlocfilehash: cc5dd26923e2edaed34c8f1b742b3dfa1e935e68
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87300232"
---
# <a name="refactoring-into-pure-functions-c"></a><span data-ttu-id="4f75e-104">Рефакторинг в чистые функции (C#)</span><span class="sxs-lookup"><span data-stu-id="4f75e-104">Refactoring Into Pure Functions (C#)</span></span>

<span data-ttu-id="4f75e-105">Важным аспектом чисто функциональных преобразований является освоение способов оптимизации существующего кода для получения чистых функций.</span><span class="sxs-lookup"><span data-stu-id="4f75e-105">An important aspect of pure functional transformations is learning how to refactor code using pure functions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4f75e-106">Общим подходом к функциональному программированию является оптимизация кода программ для получения чистых функций.</span><span class="sxs-lookup"><span data-stu-id="4f75e-106">The common nomenclature in functional programming is that you refactor programs using pure functions.</span></span> <span data-ttu-id="4f75e-107">В Visual Basic и C++ это равносильно использованию функций.</span><span class="sxs-lookup"><span data-stu-id="4f75e-107">In Visual Basic and C++, this aligns with the use of functions in the respective languages.</span></span> <span data-ttu-id="4f75e-108">Но в C# функции называются методами.</span><span class="sxs-lookup"><span data-stu-id="4f75e-108">However, in C#, functions are called methods.</span></span> <span data-ttu-id="4f75e-109">В данном случае чистая функция в C# реализуется как метод.</span><span class="sxs-lookup"><span data-stu-id="4f75e-109">For the purposes of this discussion, a pure function is implemented as a method in C#.</span></span>  
  
 <span data-ttu-id="4f75e-110">Как отмечалось ранее в этом разделе, чистые функции имеют две полезные характеристики.</span><span class="sxs-lookup"><span data-stu-id="4f75e-110">As noted previously in this section, a pure function has two useful characteristics:</span></span>  
  
- <span data-ttu-id="4f75e-111">У них отсутствуют побочные эффекты.</span><span class="sxs-lookup"><span data-stu-id="4f75e-111">It has no side effects.</span></span> <span data-ttu-id="4f75e-112">Функции не изменяют значения или данные любого типа, не входящие в область их определения.</span><span class="sxs-lookup"><span data-stu-id="4f75e-112">The function does not change any variables or the data of any type outside of the function.</span></span>  
  
- <span data-ttu-id="4f75e-113">Функции действуют единообразно.</span><span class="sxs-lookup"><span data-stu-id="4f75e-113">It is consistent.</span></span> <span data-ttu-id="4f75e-114">После получения того же набора входных данных они всегда возвращают одно и то же выходное значение.</span><span class="sxs-lookup"><span data-stu-id="4f75e-114">Given the same set of input data, it will always return the same output value.</span></span>  
  
 <span data-ttu-id="4f75e-115">Одним из способов перехода к функциональному программированию является оптимизация существующего кода с целью устранения ненужных побочных эффектов и внешних зависимостей.</span><span class="sxs-lookup"><span data-stu-id="4f75e-115">One way of transitioning to functional programming is to refactor existing code to eliminate unnecessary side effects and external dependencies.</span></span> <span data-ttu-id="4f75e-116">Таким образом, из существующего кода создаются чистые функции.</span><span class="sxs-lookup"><span data-stu-id="4f75e-116">In this way, you can create pure function versions of existing code.</span></span>  
  
 <span data-ttu-id="4f75e-117">В этом разделе объясняется, что представляет собой чистая функция и чем она не является.</span><span class="sxs-lookup"><span data-stu-id="4f75e-117">This topic discusses what a pure function is and what it is not.</span></span> <span data-ttu-id="4f75e-118">В разделе [Учебник. Управление содержимым в документе WordprocessingML (C#)](./shape-of-wordprocessingml-documents.md) показано управление документом WordprocessingML и содержатся два примера рефакторинга с помощью чистых функций.</span><span class="sxs-lookup"><span data-stu-id="4f75e-118">The [Tutorial: Manipulating Content in a WordprocessingML Document (C#)](./shape-of-wordprocessingml-documents.md) tutorial shows how to manipulate a WordprocessingML document, and includes two examples of how to refactor using a pure function.</span></span>  
  
## <a name="eliminating-side-effects-and-external-dependencies"></a><span data-ttu-id="4f75e-119">Устранение побочных эффектов и внешних зависимостей</span><span class="sxs-lookup"><span data-stu-id="4f75e-119">Eliminating Side Effects and External Dependencies</span></span>  
 <span data-ttu-id="4f75e-120">В следующих примерах сравниваются обычные и чистые функции.</span><span class="sxs-lookup"><span data-stu-id="4f75e-120">The following examples contrast two non-pure functions and a pure function.</span></span>  
  
### <a name="non-pure-function-that-changes-a-class-member"></a><span data-ttu-id="4f75e-121">Обычная функция, изменяющая член класса</span><span class="sxs-lookup"><span data-stu-id="4f75e-121">Non-Pure Function that Changes a Class Member</span></span>  
 <span data-ttu-id="4f75e-122">В следующем примере кода функция `HyphenatedConcat` представляет собой обычную функцию, поскольку изменяет элемент данных `aMember` в классе.</span><span class="sxs-lookup"><span data-stu-id="4f75e-122">In the following code, the `HyphenatedConcat` function is not a pure function, because it modifies the `aMember` data member in the class:</span></span>  
  
```csharp  
public class Program  
{  
    private static string aMember = "StringOne";  
  
    public static void HyphenatedConcat(string appendStr)  
    {  
        aMember += '-' + appendStr;  
    }  
  
    public static void Main()  
    {  
        HyphenatedConcat("StringTwo");  
        Console.WriteLine(aMember);  
    }  
}  
```  
  
 <span data-ttu-id="4f75e-123">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="4f75e-123">This code produces the following output:</span></span>  
  
```output  
StringOne-StringTwo  
```  
  
 <span data-ttu-id="4f75e-124">Обратите внимание, что неважно, какой доступ имеют изменяемые данные, `public` или `private`, и являются ли они членом класса `static` или элементом экземпляра.</span><span class="sxs-lookup"><span data-stu-id="4f75e-124">Note that it is irrelevant whether the data being modified has `public` or `private` access, or is a `static` member or an instance member.</span></span> <span data-ttu-id="4f75e-125">Чистая функция не изменяет не относящиеся к ней данные.</span><span class="sxs-lookup"><span data-stu-id="4f75e-125">A pure function does not change any data outside of the function.</span></span>  
  
### <a name="non-pure-function-that-changes-an-argument"></a><span data-ttu-id="4f75e-126">Обычная функция, изменяющая аргумент</span><span class="sxs-lookup"><span data-stu-id="4f75e-126">Non-Pure Function that Changes an Argument</span></span>  
 <span data-ttu-id="4f75e-127">Более того, следующая версия той же функции представляет собой обычную функцию, поскольку изменяет содержимое своего параметра `sb`.</span><span class="sxs-lookup"><span data-stu-id="4f75e-127">Furthermore, the following version of this same function is not pure because it modifies the contents of its parameter, `sb`.</span></span>  
  
```csharp  
public class Program  
{  
    public static void HyphenatedConcat(StringBuilder sb, String appendStr)  
    {  
        sb.Append('-' + appendStr);  
    }  
  
    public static void Main()  
    {  
        StringBuilder sb1 = new StringBuilder("StringOne");  
        HyphenatedConcat(sb1, "StringTwo");  
        Console.WriteLine(sb1);  
    }  
}  
```  
  
 <span data-ttu-id="4f75e-128">Эта версия программы дает те же выходные данные, что и первая версия, поскольку функция `HyphenatedConcat` изменила значение (состояние) своего первого параметра, вызвав функцию-член <xref:System.Text.StringBuilder.Append%2A>.</span><span class="sxs-lookup"><span data-stu-id="4f75e-128">This version of the program produces the same output as the first version, because the `HyphenatedConcat` function has changed the value (state) of its first parameter by invoking the <xref:System.Text.StringBuilder.Append%2A> member function.</span></span> <span data-ttu-id="4f75e-129">Обратите внимание, что это изменение происходит несмотря на то, что функция `HyphenatedConcat` использует передачу параметра по значению.</span><span class="sxs-lookup"><span data-stu-id="4f75e-129">Note that this alteration occurs despite that fact that `HyphenatedConcat` uses call-by-value parameter passing.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="4f75e-130">Передача параметров по значению для ссылочных типов приводит к созданию копии ссылки на передаваемый объект.</span><span class="sxs-lookup"><span data-stu-id="4f75e-130">For reference types, if you pass a parameter by value, it results in a copy of the reference to an object being passed.</span></span> <span data-ttu-id="4f75e-131">Эта копия все еще связана с теми же данными экземпляра, что и первоначальная ссылка (пока ссылочная переменная не будет присвоена новому объекту).</span><span class="sxs-lookup"><span data-stu-id="4f75e-131">This copy is still associated with the same instance data as the original reference (until the reference variable is assigned to a new object).</span></span> <span data-ttu-id="4f75e-132">Вызов по значению необязательно требуется функции для изменения параметра.</span><span class="sxs-lookup"><span data-stu-id="4f75e-132">Call-by-reference is not necessarily required for a function to modify a parameter.</span></span>  
  
### <a name="pure-function"></a><span data-ttu-id="4f75e-133">Чистая функция</span><span class="sxs-lookup"><span data-stu-id="4f75e-133">Pure Function</span></span>  
<span data-ttu-id="4f75e-134">Следующая версия этой программы реализует функцию `HyphenatedConcat` в виде чистой функции.</span><span class="sxs-lookup"><span data-stu-id="4f75e-134">This next version of the program shows how to implement the `HyphenatedConcat` function as a pure function.</span></span>  
  
```csharp  
class Program  
{  
    public static string HyphenatedConcat(string s, string appendStr)  
    {  
        return (s + '-' + appendStr);  
    }  
  
    public static void Main(string[] args)  
    {  
        string s1 = "StringOne";  
        string s2 = HyphenatedConcat(s1, "StringTwo");  
        Console.WriteLine(s2);  
    }  
}  
```  
  
 <span data-ttu-id="4f75e-135">И снова она дает ту же строку вывода: `StringOne-StringTwo`.</span><span class="sxs-lookup"><span data-stu-id="4f75e-135">Again, this version produces the same line of output: `StringOne-StringTwo`.</span></span> <span data-ttu-id="4f75e-136">Обратите внимание, что для сохранения соединенного значения оно сохраняется в промежуточной переменной `s2`.</span><span class="sxs-lookup"><span data-stu-id="4f75e-136">Note that to retain the concatenated value, it is stored in the intermediate variable `s2`.</span></span>  
  
 <span data-ttu-id="4f75e-137">Одним из полезных подходов является написание функций, которые локально являются обычными (то есть в них объявляются и изменяются локальные переменные), но глобально остаются чистыми.</span><span class="sxs-lookup"><span data-stu-id="4f75e-137">One approach that can be very useful is to write functions that are locally impure (that is, they declare and modify local variables) but are globally pure.</span></span> <span data-ttu-id="4f75e-138">Такие функции имеют многие характеристики, благоприятные с точки зрения компоновки, но позволяют обойтись без использования некоторых более сложных средств функционального программирования, тех, что диктуют, например, необходимость использовать рекурсию, невзирая на возможность добиться того же результата с помощью простого цикла.</span><span class="sxs-lookup"><span data-stu-id="4f75e-138">Such functions have many of the desirable composability characteristics, but avoid some of the more convoluted functional programming idioms, such as having to use recursion when a simple loop would accomplish the same thing.</span></span>  
  
## <a name="standard-query-operators"></a><span data-ttu-id="4f75e-139">Стандартные операторы запроса</span><span class="sxs-lookup"><span data-stu-id="4f75e-139">Standard Query Operators</span></span>  
 <span data-ttu-id="4f75e-140">Важной характеристикой стандартных операторов запросов является то, что они реализуются как чистые функции.</span><span class="sxs-lookup"><span data-stu-id="4f75e-140">An important characteristic of the standard query operators is that they are implemented as pure functions.</span></span>  
  
 <span data-ttu-id="4f75e-141">Дополнительные сведения см. в разделе [Общие сведения о стандартных операторах запроса (C#)](./standard-query-operators-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4f75e-141">For more information, see [Standard Query Operators Overview (C#)](./standard-query-operators-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f75e-142">См. также</span><span class="sxs-lookup"><span data-stu-id="4f75e-142">See also</span></span>

- [<span data-ttu-id="4f75e-143">Введение в чистые функциональные преобразования (C#)</span><span class="sxs-lookup"><span data-stu-id="4f75e-143">Introduction to Pure Functional Transformations (C#)</span></span>](./introduction-to-pure-functional-transformations.md)
- [<span data-ttu-id="4f75e-144">Сравнение функционального и императивного программирования (C#)</span><span class="sxs-lookup"><span data-stu-id="4f75e-144">Functional Programming vs. Imperative Programming (C#)</span></span>](./functional-programming-vs-imperative-programming.md)
