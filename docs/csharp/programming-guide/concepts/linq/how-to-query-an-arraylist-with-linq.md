---
title: Выполнение запроса к ArrayList с помощью LINQ (C#)
description: В этом примере выполнение запроса к ArrayList в C# осуществляется с помощью LINQ. Необходимо объявить тип переменной диапазона, чтобы отразить тип объектов в коллекции.
ms.date: 07/20/2015
ms.assetid: 2bfb471c-6e9a-4e60-bd83-4a1778abde11
ms.openlocfilehash: 5c251e17de062a4578f06fc1a40ea3ede9f3ab67
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104609"
---
# <a name="how-to-query-an-arraylist-with-linq-c"></a><span data-ttu-id="7d205-104">Выполнение запроса к ArrayList с помощью LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="7d205-104">How to query an ArrayList with LINQ (C#)</span></span>
<span data-ttu-id="7d205-105">При использовании LINQ для запросов к неуниверсальным коллекциям <xref:System.Collections.IEnumerable>, таким как <xref:System.Collections.ArrayList>, необходимо явно объявить тип переменной диапазона, чтобы отразить конкретный тип объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="7d205-105">When using LINQ to query non-generic <xref:System.Collections.IEnumerable> collections such as <xref:System.Collections.ArrayList>, you must explicitly declare the type of the range variable to reflect the specific type of the objects in the collection.</span></span> <span data-ttu-id="7d205-106">Например, если у вас есть список <xref:System.Collections.ArrayList> объектов `Student`, [предложение from](../../../language-reference/keywords/from-clause.md) должно иметь следующий вид:</span><span class="sxs-lookup"><span data-stu-id="7d205-106">For example, if you have an <xref:System.Collections.ArrayList> of `Student` objects, your [from clause](../../../language-reference/keywords/from-clause.md) should look like this:</span></span>  
  
```csharp
var query = from Student s in arrList  
//...
```  
  
 <span data-ttu-id="7d205-107">Указав тип переменной диапазона, вы приводите каждый элемент в <xref:System.Collections.ArrayList> к `Student`.</span><span class="sxs-lookup"><span data-stu-id="7d205-107">By specifying the type of the range variable, you are casting each item in the <xref:System.Collections.ArrayList> to a `Student`.</span></span>  
  
 <span data-ttu-id="7d205-108">Использование явным образом типизированной переменной диапазона в выражении запроса эквивалентно вызову метода <xref:System.Linq.Enumerable.Cast%2A>.</span><span class="sxs-lookup"><span data-stu-id="7d205-108">The use of an explicitly typed range variable in a query expression is equivalent to calling the <xref:System.Linq.Enumerable.Cast%2A> method.</span></span> <span data-ttu-id="7d205-109">Если выполнить приведение не удается, <xref:System.Linq.Enumerable.Cast%2A> создает исключение.</span><span class="sxs-lookup"><span data-stu-id="7d205-109"><xref:System.Linq.Enumerable.Cast%2A> throws an exception if the specified cast cannot be performed.</span></span> <span data-ttu-id="7d205-110">Методы <xref:System.Linq.Enumerable.Cast%2A> и <xref:System.Linq.Enumerable.OfType%2A> стандартного оператора запроса используются для работы с неуниверсальными типами <xref:System.Collections.IEnumerable>.</span><span class="sxs-lookup"><span data-stu-id="7d205-110"><xref:System.Linq.Enumerable.Cast%2A> and <xref:System.Linq.Enumerable.OfType%2A> are the two Standard Query Operator methods that operate on non-generic <xref:System.Collections.IEnumerable> types.</span></span> <span data-ttu-id="7d205-111">Дополнительные сведения см. в разделе [Связи типов в операциях запроса LINQ](./type-relationships-in-linq-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="7d205-111">For more information, see [Type Relationships in LINQ Query Operations](./type-relationships-in-linq-query-operations.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d205-112">Пример</span><span class="sxs-lookup"><span data-stu-id="7d205-112">Example</span></span>  
 <span data-ttu-id="7d205-113">В следующем примере показан простой запрос к объекту <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="7d205-113">The following example shows a simple query over an <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="7d205-114">Обратите внимание на то, что в этом примере инициализаторы объектов используются, когда код вызывает метод <xref:System.Collections.ArrayList.Add%2A>, но это не обязательно.</span><span class="sxs-lookup"><span data-stu-id="7d205-114">Note that this example uses object initializers when the code calls the <xref:System.Collections.ArrayList.Add%2A> method, but this is not a requirement.</span></span>  
  
```csharp  
using System;  
using System.Collections;  
using System.Linq;  
  
namespace NonGenericLINQ  
{  
    public class Student  
    {  
        public string FirstName { get; set; }  
        public string LastName { get; set; }  
        public int[] Scores { get; set; }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            ArrayList arrList = new ArrayList();  
            arrList.Add(  
                new Student  
                    {  
                        FirstName = "Svetlana", LastName = "Omelchenko", Scores = new int[] { 98, 92, 81, 60 }  
                    });  
            arrList.Add(  
                new Student  
                    {  
                        FirstName = "Claire", LastName = "O’Donnell", Scores = new int[] { 75, 84, 91, 39 }  
                    });  
            arrList.Add(  
                new Student  
                    {  
                        FirstName = "Sven", LastName = "Mortensen", Scores = new int[] { 88, 94, 65, 91 }  
                    });  
            arrList.Add(  
                new Student  
                    {  
                        FirstName = "Cesar", LastName = "Garcia", Scores = new int[] { 97, 89, 85, 82 }  
                    });  
  
            var query = from Student student in arrList  
                        where student.Scores[0] > 95  
                        select student;  
  
            foreach (Student s in query)  
                Console.WriteLine(s.LastName + ": " + s.Scores[0]);  
  
            // Keep the console window open in debug mode.  
            Console.WriteLine("Press any key to exit.");  
            Console.ReadKey();  
        }  
    }  
}  
/* Output:
    Omelchenko: 98  
    Garcia: 97  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="7d205-115">См. также</span><span class="sxs-lookup"><span data-stu-id="7d205-115">See also</span></span>

- [<span data-ttu-id="7d205-116">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="7d205-116">LINQ to Objects (C#)</span></span>](./linq-to-objects.md)
