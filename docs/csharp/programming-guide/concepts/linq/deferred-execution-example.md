---
title: Пример отложенного выполнения (C#)
description: Узнайте, как отложенное выполнение и отложенное вычисление влияют на запросы LINQ to XML в C#.
ms.date: 07/20/2015
ms.assetid: 50f4fbac-81fe-4f26-aedf-506e21419b19
ms.openlocfilehash: 65ba4cc150f2fc9d8f44aee352987ea0eeaab0a5
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103960"
---
# <a name="deferred-execution-example-c"></a><span data-ttu-id="3c14d-103">Пример отложенного выполнения (C#)</span><span class="sxs-lookup"><span data-stu-id="3c14d-103">Deferred Execution Example (C#)</span></span>
<span data-ttu-id="3c14d-104">В данном разделе показано влияние отложенного выполнения и отложенного вычисления на запросы LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="3c14d-104">This topic shows how deferred execution and lazy evaluation affect the execution of your LINQ to XML queries.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c14d-105">Пример</span><span class="sxs-lookup"><span data-stu-id="3c14d-105">Example</span></span>  
 <span data-ttu-id="3c14d-106">В следующем примере демонстрируется порядок выполнения при использовании метода расширения, в котором применяется отложенное выполнение.</span><span class="sxs-lookup"><span data-stu-id="3c14d-106">The following example shows the order of execution when using an extension method that uses deferred execution.</span></span> <span data-ttu-id="3c14d-107">В этом примере объявляется массив из трех строк.</span><span class="sxs-lookup"><span data-stu-id="3c14d-107">The example declares an array of three strings.</span></span> <span data-ttu-id="3c14d-108">Затем в нем производится итерация по коллекции, возвращенной `ConvertCollectionToUpperCase`.</span><span class="sxs-lookup"><span data-stu-id="3c14d-108">It then iterates through the collection returned by `ConvertCollectionToUpperCase`.</span></span>  
  
```csharp  
public static class LocalExtensions  
{  
    public static IEnumerable<string>  
      ConvertCollectionToUpperCase(this IEnumerable<string> source)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("ToUpper: source {0}", str);  
            yield return str.ToUpper();  
        }  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        string[] stringArray = { "abc", "def", "ghi" };  
  
        var q = from str in stringArray.ConvertCollectionToUpperCase()  
                select str;  
  
        foreach (string str in q)  
            Console.WriteLine("Main: str {0}", str);  
    }  
}  
```  
  
 <span data-ttu-id="3c14d-109">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="3c14d-109">This example produces the following output:</span></span>  
  
```output  
ToUpper: source abc  
Main: str ABC  
ToUpper: source def  
Main: str DEF  
ToUpper: source ghi  
Main: str GHI  
```  
  
 <span data-ttu-id="3c14d-110">Обратите внимание, что во время итерации по коллекции, возвращенной `ConvertCollectionToUpperCase`, происходит получение каждого элемента из исходного массива строк и преобразование символов в верхний регистр до получения следующего элемента из исходного массива строк.</span><span class="sxs-lookup"><span data-stu-id="3c14d-110">Notice that when iterating through the collection returned by `ConvertCollectionToUpperCase`, each item is retrieved from the source string array and converted to uppercase before the next item is retrieved from the source string array.</span></span>  
  
 <span data-ttu-id="3c14d-111">Видно, что весь массив строк не преобразуется в символы верхнего регистра, пока каждый элемент возвращенной коллекции не будет обработан циклом `foreach` в `Main`.</span><span class="sxs-lookup"><span data-stu-id="3c14d-111">You can see that the entire array of strings is not converted to uppercase before each item in the returned collection is processed in the `foreach` loop in `Main`.</span></span>  
  
 <span data-ttu-id="3c14d-112">Следующий раздел учебника иллюстрирует объединение запросов в цепочки:</span><span class="sxs-lookup"><span data-stu-id="3c14d-112">The next topic in this tutorial illustrates chaining queries together:</span></span>  
  
- [<span data-ttu-id="3c14d-113">Пример связывания запросов (C#)</span><span class="sxs-lookup"><span data-stu-id="3c14d-113">Chaining Queries Example (C#)</span></span>](./chaining-queries-example.md)  
  
## <a name="see-also"></a><span data-ttu-id="3c14d-114">См. также</span><span class="sxs-lookup"><span data-stu-id="3c14d-114">See also</span></span>

- [<span data-ttu-id="3c14d-115">Учебник. Объединение запросов в цепочки (C#)</span><span class="sxs-lookup"><span data-stu-id="3c14d-115">Tutorial: Chaining Queries Together (C#)</span></span>](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
