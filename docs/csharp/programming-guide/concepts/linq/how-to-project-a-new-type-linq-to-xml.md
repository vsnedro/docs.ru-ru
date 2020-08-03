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
# <a name="how-to-project-a-new-type-linq-to-xml-c"></a>Как проецировать новый тип (LINQ to XML) (C#)

В других примерах данного раздела показаны запросы, возвращающие результаты в виде значений <xref:System.Collections.Generic.IEnumerable%601> типа <xref:System.Xml.Linq.XElement>, значений <xref:System.Collections.Generic.IEnumerable%601> типа `string` и значений <xref:System.Collections.Generic.IEnumerable%601> типа `int`. Это наиболее распространенные типы результатов, но подходят не для всех сценариев. Во многих случаях требуется, чтобы запросы возвращали <xref:System.Collections.Generic.IEnumerable%601> какого-то другого типа.

## <a name="example"></a>Пример

В данном примере показано, как создавать экземпляры объектов в предложении `select`. Сначала в коде определяется новый класс с помощью конструктора, а затем модифицируется инструкция `select`, чтобы это выражение представляло новый экземпляр нового класса.

В этом примере используется следующий XML-документ: [Пример XML-файла. Типичный заказ на покупку (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).

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

В этом примере используется метод <xref:System.Xml.Linq.XContainer.Element%2A>, который был представлен в руководстве по [извлечению одного дочернего элемента (LINQ to XML) (C#)](how-to-retrieve-a-single-child-element-linq-to-xml.md). В нем также используется приведение для получения значений элементов, возвращаемых методом <xref:System.Xml.Linq.XContainer.Element%2A>.  

В этом примере выводятся следующие данные:

```output
Lawnmower:1
Baby Monitor:2
```
