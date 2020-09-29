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
# <a name="how-to-find-the-set-difference-between-two-lists-linq-c"></a>Нахождение разности множеств между двумя списками (LINQ) (C#)

В этом примере показано, как использовать LINQ для сравнения двух списков строк и вывода тех строк, которые содержатся в файле names1.txt, но не в файле names2.txt.  
  
### <a name="to-create-the-data-files"></a>Создание файлов данных  
  
1. Скопируйте файлы names1.txt и names2.txt в папку решения, как показано в разделе [Практическое руководство. Объединение и сравнение коллекций строк (LINQ) (C#)](./how-to-combine-and-compare-string-collections-linq.md).  
  
## <a name="example"></a>Пример  
  
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
  
 Некоторые типы операторов запроса в C#, например <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Union%2A> и <xref:System.Linq.Enumerable.Concat%2A>, могут выражаться только с использованием синтаксиса на основе методов.  
  
## <a name="compiling-the-code"></a>Компиляция кода  

 Создайте проект консольного приложения C# с директивами `using` для пространств имен System.Linq и System.IO.  
  
## <a name="see-also"></a>См. также

- [LINQ и строки (C#)](./linq-and-strings.md)
