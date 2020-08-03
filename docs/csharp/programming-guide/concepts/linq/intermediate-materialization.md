---
title: Промежуточная материализация (C#)
description: В этом примере C# показана промежуточная материализация, при которой запрос вынуждает метод AppendString сформировать перечисление по всему источнику, прежде чем возвратить первый элемент.
ms.date: 07/20/2015
ms.assetid: 7922d38f-5044-41cf-8e17-7173d6553a5e
ms.openlocfilehash: 30951aaeea261efbd414205bcc54b63106324344
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165718"
---
# <a name="intermediate-materialization-c"></a><span data-ttu-id="01bd5-103">Промежуточная материализация (C#)</span><span class="sxs-lookup"><span data-stu-id="01bd5-103">Intermediate Materialization (C#)</span></span>
<span data-ttu-id="01bd5-104">Если не соблюдать осторожность, то в некоторых ситуациях может происходить преждевременная материализация коллекций в запросах, что приводит к радикальному изменению характера использования памяти и снижению производительности приложения.</span><span class="sxs-lookup"><span data-stu-id="01bd5-104">If you are not careful, in some situations you can drastically alter the memory and performance profile of your application by causing premature materialization of collections in your queries.</span></span> <span data-ttu-id="01bd5-105">Некоторые стандартные операторы запросов материализуют свою исходную коллекцию еще до получения хотя бы одного элемента.</span><span class="sxs-lookup"><span data-stu-id="01bd5-105">Some standard query operators cause materialization of their source collection before yielding a single element.</span></span> <span data-ttu-id="01bd5-106">Например, при выполнении оператора <xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType> вначале происходит итерация по всей исходной коллекции, затем сортировка всех элементов и лишь после этого осуществляется возврат первого элемента.</span><span class="sxs-lookup"><span data-stu-id="01bd5-106">For example, <xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType> first iterates through its entire source collection, then sorts all items, and then finally yields the first item.</span></span> <span data-ttu-id="01bd5-107">Это означает, что самой дорогостоящей операцией является получение первого элемента упорядоченной коллекции, после чего затраты ресурсов на каждый последующий элемент становятся меньше.</span><span class="sxs-lookup"><span data-stu-id="01bd5-107">This means that it is expensive to get the first item of an ordered collection; each item thereafter is not expensive.</span></span> <span data-ttu-id="01bd5-108">Это имеет смысл: сделать иначе оператор запроса не мог бы.</span><span class="sxs-lookup"><span data-stu-id="01bd5-108">This makes sense: It would be impossible for that query operator to do otherwise.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01bd5-109">Пример</span><span class="sxs-lookup"><span data-stu-id="01bd5-109">Example</span></span>  
 <span data-ttu-id="01bd5-110">В этом примере внесены изменения по сравнению с предыдущим примером.</span><span class="sxs-lookup"><span data-stu-id="01bd5-110">This example alters the previous example.</span></span> <span data-ttu-id="01bd5-111">В методе `AppendString` осуществляется вызов <xref:System.Linq.Enumerable.ToList%2A> до начала итераций по данным источника.</span><span class="sxs-lookup"><span data-stu-id="01bd5-111">The `AppendString` method calls <xref:System.Linq.Enumerable.ToList%2A> before iterating through the source.</span></span> <span data-ttu-id="01bd5-112">Это становится причиной материализации.</span><span class="sxs-lookup"><span data-stu-id="01bd5-112">This causes materialization.</span></span>  
  
```csharp  
public static class LocalExtensions  
{  
    public static IEnumerable<string>  
      ConvertCollectionToUpperCase(this IEnumerable<string> source)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("ToUpper: source >{0}<", str);  
            yield return str.ToUpper();  
        }  
    }  
  
    public static IEnumerable<string>  
      AppendString(this IEnumerable<string> source, string stringToAppend)  
    {  
        // the following statement materializes the source collection in a List<T>  
        // before iterating through it  
        foreach (string str in source.ToList())  
        {  
            Console.WriteLine("AppendString: source >{0}<", str);  
            yield return str + stringToAppend;  
        }  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        string[] stringArray = { "abc", "def", "ghi" };  
  
        IEnumerable<string> q1 =  
            from s in stringArray.ConvertCollectionToUpperCase()  
            select s;  
  
        IEnumerable<string> q2 =  
            from s in q1.AppendString("!!!")  
            select s;  
  
        foreach (string str in q2)  
        {  
            Console.WriteLine("Main: str >{0}<", str);  
            Console.WriteLine();  
        }  
    }  
}  
```  
  
 <span data-ttu-id="01bd5-113">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="01bd5-113">This example produces the following output:</span></span>  
  
```output  
ToUpper: source >abc<  
ToUpper: source >def<  
ToUpper: source >ghi<  
AppendString: source >ABC<  
Main: str >ABC!!!<  
  
AppendString: source >DEF<  
Main: str >DEF!!!<  
  
AppendString: source >GHI<  
Main: str >GHI!!!<  
```  
  
 <span data-ttu-id="01bd5-114">В этом примере можно видеть, что применение вызова <xref:System.Linq.Enumerable.ToList%2A> вынуждает метод `AppendString` сформировать перечисление по всему источнику, прежде чем возвратить первый элемент.</span><span class="sxs-lookup"><span data-stu-id="01bd5-114">In this example, you can see that the call to <xref:System.Linq.Enumerable.ToList%2A> causes `AppendString` to enumerate its entire source before yielding the first item.</span></span> <span data-ttu-id="01bd5-115">Если источник представляет собой большой массив, то в результате характер использования памяти приложением существенно изменится.</span><span class="sxs-lookup"><span data-stu-id="01bd5-115">If the source were a large array, this would significantly alter the memory profile of the application.</span></span>  
  
 <span data-ttu-id="01bd5-116">Стандартные операторы запроса можно также соединять в виде цепочки.</span><span class="sxs-lookup"><span data-stu-id="01bd5-116">Standard query operators can also be chained together.</span></span> <span data-ttu-id="01bd5-117">Это показано в последнем разделе учебника.</span><span class="sxs-lookup"><span data-stu-id="01bd5-117">The final topic in this tutorial illustrates this.</span></span>  
  
- [<span data-ttu-id="01bd5-118">Связывание стандартных операторов запросов (C#)</span><span class="sxs-lookup"><span data-stu-id="01bd5-118">Chaining Standard Query Operators Together (C#)</span></span>](./chaining-standard-query-operators-together.md)  
  
## <a name="see-also"></a><span data-ttu-id="01bd5-119">См. также</span><span class="sxs-lookup"><span data-stu-id="01bd5-119">See also</span></span>

- [<span data-ttu-id="01bd5-120">Учебник. Объединение запросов в цепочки (C#)</span><span class="sxs-lookup"><span data-stu-id="01bd5-120">Tutorial: Chaining Queries Together (C#)</span></span>](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
