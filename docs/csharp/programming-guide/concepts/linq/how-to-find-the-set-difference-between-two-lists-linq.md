---
title: Нахождение разности множеств между двумя списками (LINQ) (C#)
description: Узнайте, как использовать LINQ в C# для сравнения двух списков строк и вывода тех строк, которые содержатся в только в одном из этих списков.
ms.date: 07/20/2015
ms.assetid: 8e8945f0-4aba-439d-8d5d-c8d1eeef4e71
ms.openlocfilehash: 01aba16b3489e4bf21a76bc715b6d4d2c9d250dd
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91159063"
---
# <a name="how-to-find-the-set-difference-between-two-lists-linq-c"></a><span data-ttu-id="cb5af-103">Нахождение разности множеств между двумя списками (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="cb5af-103">How to find the set difference between two lists (LINQ) (C#)</span></span>

<span data-ttu-id="cb5af-104">В этом примере показано, как использовать LINQ для сравнения двух списков строк и вывода тех строк, которые содержатся в файле names1.txt, но не в файле names2.txt.</span><span class="sxs-lookup"><span data-stu-id="cb5af-104">This example shows how to use LINQ to compare two lists of strings and output those lines that are in names1.txt but not in names2.txt.</span></span>  
  
### <a name="to-create-the-data-files"></a><span data-ttu-id="cb5af-105">Создание файлов данных</span><span class="sxs-lookup"><span data-stu-id="cb5af-105">To create the data files</span></span>  
  
1. <span data-ttu-id="cb5af-106">Скопируйте файлы names1.txt и names2.txt в папку решения, как показано в разделе [Практическое руководство. Объединение и сравнение коллекций строк (LINQ) (C#)](./how-to-combine-and-compare-string-collections-linq.md).</span><span class="sxs-lookup"><span data-stu-id="cb5af-106">Copy names1.txt and names2.txt to your solution folder as shown in [How to combine and compare string collections (LINQ) (C#)](./how-to-combine-and-compare-string-collections-linq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb5af-107">Пример</span><span class="sxs-lookup"><span data-stu-id="cb5af-107">Example</span></span>  
  
```csharp  
class CompareLists  
{
    static void Main()  
    {  
        // Create the IEnumerable data sources.  
        string[] names1 = System.IO.File.ReadAllLines(@"../../../names1.txt");  
        string[] names2 = System.IO.File.ReadAllLines(@"../../../names2.txt");  
  
        // Create the query. Note that method syntax must be used here.  
        IEnumerable<string> differenceQuery =  
          names1.Except(names2);  
  
        // Execute the query.  
        Console.WriteLine("The following lines are in names1.txt but not names2.txt");  
        foreach (string s in differenceQuery)  
            Console.WriteLine(s);  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output:  
     The following lines are in names1.txt but not names2.txt  
    Potra, Cristina  
    Noriega, Fabricio  
    Aw, Kam Foo  
    Toyoshima, Tim  
    Guy, Wey Yuan  
    Garcia, Debra  
     */  
```  
  
 <span data-ttu-id="cb5af-108">Некоторые типы операторов запроса в C#, например <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Union%2A> и <xref:System.Linq.Enumerable.Concat%2A>, могут выражаться только с использованием синтаксиса на основе методов.</span><span class="sxs-lookup"><span data-stu-id="cb5af-108">Some types of query operations in C#, such as <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Union%2A>, and <xref:System.Linq.Enumerable.Concat%2A>, can only be expressed in method-based syntax.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cb5af-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="cb5af-109">Compiling the Code</span></span>  

 <span data-ttu-id="cb5af-110">Создайте проект консольного приложения C# с директивами `using` для пространств имен System.Linq и System.IO.</span><span class="sxs-lookup"><span data-stu-id="cb5af-110">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb5af-111">См. также</span><span class="sxs-lookup"><span data-stu-id="cb5af-111">See also</span></span>

- [<span data-ttu-id="cb5af-112">LINQ и строки (C#)</span><span class="sxs-lookup"><span data-stu-id="cb5af-112">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)
