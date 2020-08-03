---
title: Как проецировать новый тип (LINQ to XML) (C#)
description: Узнайте, как создавать запросы в LINQ to XML в C#, возвращающие результаты в виде значений IEnumerable<T> типов, помимо XElement, string или int, которые описаны в других примерах.
ms.date: 07/20/2015
ms.assetid: 48145cf9-1e0b-4e73-bbfd-28fc04800dc4
ms.openlocfilehash: 013ea852a64b77c04ac583b4d9b71e8006cd4976
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104640"
---
# <a name="how-to-project-a-new-type-linq-to-xml-c"></a><span data-ttu-id="8d711-103">Как проецировать новый тип (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="8d711-103">How to project a new type (LINQ to XML) (C#)</span></span>

<span data-ttu-id="8d711-104">В других примерах данного раздела показаны запросы, возвращающие результаты в виде значений <xref:System.Collections.Generic.IEnumerable%601> типа <xref:System.Xml.Linq.XElement>, значений <xref:System.Collections.Generic.IEnumerable%601> типа `string` и значений <xref:System.Collections.Generic.IEnumerable%601> типа `int`.</span><span class="sxs-lookup"><span data-stu-id="8d711-104">Other examples in this section have shown queries that return results as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601> of `string`, and <xref:System.Collections.Generic.IEnumerable%601> of `int`.</span></span> <span data-ttu-id="8d711-105">Это наиболее распространенные типы результатов, но подходят не для всех сценариев.</span><span class="sxs-lookup"><span data-stu-id="8d711-105">These are common result types, but they are not appropriate for every scenario.</span></span> <span data-ttu-id="8d711-106">Во многих случаях требуется, чтобы запросы возвращали <xref:System.Collections.Generic.IEnumerable%601> какого-то другого типа.</span><span class="sxs-lookup"><span data-stu-id="8d711-106">In many cases you will want your queries to return an <xref:System.Collections.Generic.IEnumerable%601> of some other type.</span></span>

## <a name="example"></a><span data-ttu-id="8d711-107">Пример</span><span class="sxs-lookup"><span data-stu-id="8d711-107">Example</span></span>

<span data-ttu-id="8d711-108">В данном примере показано, как создавать экземпляры объектов в предложении `select`.</span><span class="sxs-lookup"><span data-stu-id="8d711-108">This example shows how to instantiate objects in the `select` clause.</span></span> <span data-ttu-id="8d711-109">Сначала в коде определяется новый класс с помощью конструктора, а затем модифицируется инструкция `select`, чтобы это выражение представляло новый экземпляр нового класса.</span><span class="sxs-lookup"><span data-stu-id="8d711-109">The code first defines a new class with a constructor, and then modifies the `select` statement so that the expression is a new instance of the new class.</span></span>

<span data-ttu-id="8d711-110">В этом примере используется следующий XML-документ: [Пример XML-файла. Типичный заказ на покупку (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="8d711-110">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>

```csharp
class NameQty
{
    public string name;
    public int qty;
    public NameQty(string n, int q)
    {
        name = n;
        qty = q;
    }
};

class Program {
    public static void Main()
    {
        XElement po = XElement.Load("PurchaseOrder.xml");
  
        IEnumerable<NameQty> nqList =
            from n in po.Descendants("Item")
            select new NameQty(
                    (string)n.Element("ProductName"),
                    (int)n.Element("Quantity")
                );
  
        foreach (NameQty n in nqList)
            Console.WriteLine(n.name + ":" + n.qty);
    }
}
```

<span data-ttu-id="8d711-111">В этом примере используется метод <xref:System.Xml.Linq.XContainer.Element%2A>, который был представлен в руководстве по [извлечению одного дочернего элемента (LINQ to XML) (C#)](how-to-retrieve-a-single-child-element-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="8d711-111">This example uses the <xref:System.Xml.Linq.XContainer.Element%2A> method that was introduced in the topic [How to retrieve a single child element (LINQ to XML) (C#)](how-to-retrieve-a-single-child-element-linq-to-xml.md).</span></span> <span data-ttu-id="8d711-112">В нем также используется приведение для получения значений элементов, возвращаемых методом <xref:System.Xml.Linq.XContainer.Element%2A>.</span><span class="sxs-lookup"><span data-stu-id="8d711-112">It also uses casts to retrieve the values of the elements that are returned by the <xref:System.Xml.Linq.XContainer.Element%2A> method.</span></span>  

<span data-ttu-id="8d711-113">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="8d711-113">This example produces the following output:</span></span>

```output
Lawnmower:1
Baby Monitor:2
```
