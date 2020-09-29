---
title: Запрос символов в строке (LINQ) (C#)
description: В LINQ вы можете запрашивать строку как последовательность символов. В этом примере C# запрашивается строка, чтобы определить количество содержащихся в ней цифр.
ms.date: 07/20/2015
ms.assetid: 727a1be7-dbec-4ab8-b414-bc2d56feb6ff
ms.openlocfilehash: 73288924d057e720a744b853998a52437b9db481
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153941"
---
# <a name="how-to-query-for-characters-in-a-string-linq-c"></a>Запрос символов в строке (LINQ) (C#)

Поскольку класс <xref:System.String> реализует универсальный интерфейс <xref:System.Collections.Generic.IEnumerable%601>, любая строка может запрашиваться как последовательность символов. Однако это не слишком распространенный пример использования LINQ. Для сложных операций сопоставления шаблонов используйте класс <xref:System.Text.RegularExpressions.Regex>.  
  
## <a name="example"></a>Пример  

 В следующем примере запрашивается строка, чтобы определить количество содержащихся в ней цифр. Обратите внимание, что запрос "используется повторно" после первоначального выполнения. Это становится возможным, поскольку сам запрос не хранит фактические результаты.  
  
```csharp  
class QueryAString  
{  
    static void Main()  
    {  
        string aString = "ABCDE99F-J74-12-89A";  
  
        // Select only those characters that are numbers  
        IEnumerable<char> stringQuery =  
          from ch in aString  
          where Char.IsDigit(ch)  
          select ch;  
  
        // Execute the query  
        foreach (char c in stringQuery)  
            Console.Write(c + " ");  
  
        // Call the Count method on the existing query.  
        int count = stringQuery.Count();  
        Console.WriteLine("Count = {0}", count);  
  
        // Select all characters before the first '-'  
        IEnumerable<char> stringQuery2 = aString.TakeWhile(c => c != '-');  
  
        // Execute the second query  
        foreach (char c in stringQuery2)  
            Console.Write(c);  
  
        Console.WriteLine(System.Environment.NewLine + "Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output:  
  Output: 9 9 7 4 1 2 8 9  
  Count = 8  
  ABCDE99F  
*/  
```  
  
## <a name="compiling-the-code"></a>Компиляция кода  

 Создайте проект консольного приложения C# с директивами `using` для пространств имен System.Linq и System.IO.  
  
## <a name="see-also"></a>См. также

- [LINQ и строки (C#)](./linq-and-strings.md)
- [Практическое руководство. Объединение запросов LINQ с помощью регулярных выражений (C#)](./how-to-combine-linq-queries-with-regular-expressions.md)
