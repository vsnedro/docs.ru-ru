---
title: Запрос символов в строке (LINQ) (C#)
description: В LINQ вы можете запрашивать строку как последовательность символов. В этом примере C# запрашивается строка, чтобы определить количество содержащихся в ней цифр.
ms.date: 07/20/2015
ms.assetid: 727a1be7-dbec-4ab8-b414-bc2d56feb6ff
ms.openlocfilehash: 3512be7c30843fcd8e881eab59761706a84a3ac8
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104551"
---
# <a name="how-to-query-for-characters-in-a-string-linq-c"></a><span data-ttu-id="0890d-104">Запрос символов в строке (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="0890d-104">How to query for characters in a string (LINQ) (C#)</span></span>
<span data-ttu-id="0890d-105">Поскольку класс <xref:System.String> реализует универсальный интерфейс <xref:System.Collections.Generic.IEnumerable%601>, любая строка может запрашиваться как последовательность символов.</span><span class="sxs-lookup"><span data-stu-id="0890d-105">Because the <xref:System.String> class implements the generic <xref:System.Collections.Generic.IEnumerable%601> interface, any string can be queried as a sequence of characters.</span></span> <span data-ttu-id="0890d-106">Однако это не слишком распространенный пример использования LINQ.</span><span class="sxs-lookup"><span data-stu-id="0890d-106">However, this is not a common use of LINQ.</span></span> <span data-ttu-id="0890d-107">Для сложных операций сопоставления шаблонов используйте класс <xref:System.Text.RegularExpressions.Regex>.</span><span class="sxs-lookup"><span data-stu-id="0890d-107">For complex pattern matching operations, use the <xref:System.Text.RegularExpressions.Regex> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0890d-108">Пример</span><span class="sxs-lookup"><span data-stu-id="0890d-108">Example</span></span>  
 <span data-ttu-id="0890d-109">В следующем примере запрашивается строка, чтобы определить количество содержащихся в ней цифр.</span><span class="sxs-lookup"><span data-stu-id="0890d-109">The following example queries a string to determine the number of numeric digits it contains.</span></span> <span data-ttu-id="0890d-110">Обратите внимание, что запрос "используется повторно" после первоначального выполнения.</span><span class="sxs-lookup"><span data-stu-id="0890d-110">Note that the query is "reused" after it is executed the first time.</span></span> <span data-ttu-id="0890d-111">Это становится возможным, поскольку сам запрос не хранит фактические результаты.</span><span class="sxs-lookup"><span data-stu-id="0890d-111">This is possible because the query itself does not store any actual results.</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="0890d-112">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="0890d-112">Compiling the Code</span></span>  
 <span data-ttu-id="0890d-113">Создайте проект консольного приложения C# с директивами `using` для пространств имен System.Linq и System.IO.</span><span class="sxs-lookup"><span data-stu-id="0890d-113">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0890d-114">См. также</span><span class="sxs-lookup"><span data-stu-id="0890d-114">See also</span></span>

- [<span data-ttu-id="0890d-115">LINQ и строки (C#)</span><span class="sxs-lookup"><span data-stu-id="0890d-115">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)
- [<span data-ttu-id="0890d-116">Практическое руководство. Объединение запросов LINQ с помощью регулярных выражений (C#)</span><span class="sxs-lookup"><span data-stu-id="0890d-116">How to combine LINQ queries with regular expressions (C#)</span></span>](./how-to-combine-linq-queries-with-regular-expressions.md)
