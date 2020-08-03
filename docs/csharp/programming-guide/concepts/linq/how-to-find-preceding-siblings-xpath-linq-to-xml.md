---
title: Практическое руководство. Поиск предшествующих элементов того же уровня (XPath-LINQ to XML) (C#)
description: В этом примере в C# сравнивается ось XPath preceding-sibling с дочерней для LINQ to XML осью XNode.ElementsBeforeSelf.
ms.date: 07/20/2015
ms.assetid: b281ff99-d08a-43d0-bea1-eff831b2f8ae
ms.openlocfilehash: 4150c94fe1e30e7a72bb53b4c6c12481ee0bad19
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103460"
---
# <a name="how-to-find-preceding-siblings-xpath-linq-to-xml-c"></a><span data-ttu-id="b9c08-103">Практическое руководство. Поиск предшествующих элементов того же уровня (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="b9c08-103">How to find preceding siblings (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="b9c08-104">В этом разделе сравнивается ось XPath `preceding-sibling` с дочерней для [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] осью <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b9c08-104">This topic compares the XPath `preceding-sibling` axis to the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] child <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType> axis.</span></span>  
  
 <span data-ttu-id="b9c08-105">Выражение XPath:</span><span class="sxs-lookup"><span data-stu-id="b9c08-105">The XPath expression is:</span></span>  
  
 `preceding-sibling::*`  
  
 <span data-ttu-id="b9c08-106">Обратите внимание, что результаты как <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A>, так и <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType> соответствуют структуре документа.</span><span class="sxs-lookup"><span data-stu-id="b9c08-106">Note that the results of both <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> and <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType> are in document order.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9c08-107">Пример</span><span class="sxs-lookup"><span data-stu-id="b9c08-107">Example</span></span>  
 <span data-ttu-id="b9c08-108">В следующем примере находится элемент `FullAddress`, после чего при помощи оси `preceding-sibling` получаются предыдущие элементы.</span><span class="sxs-lookup"><span data-stu-id="b9c08-108">The following example finds the `FullAddress` element, and then retrieves the previous elements using the `preceding-sibling` axis.</span></span>  
  
 <span data-ttu-id="b9c08-109">В этом примере используется следующий XML-документ: [Пример XML-файла. Заказчики и заказы (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span><span class="sxs-lookup"><span data-stu-id="b9c08-109">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>  
  
```csharp  
XElement co = XElement.Load("CustomersOrders.xml");  
  
XElement add = co.Element("Customers").Element("Customer").Element("FullAddress");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 = add.ElementsBeforeSelf();  
  
// XPath expression  
IEnumerable<XElement> list2 = add.XPathSelectElements("preceding-sibling::*");  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list2)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="b9c08-110">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="b9c08-110">This example produces the following output:</span></span>  
  
```output  
Results are identical  
<CompanyName>Great Lakes Food Market</CompanyName>  
<ContactName>Howard Snyder</ContactName>  
<ContactTitle>Marketing Manager</ContactTitle>  
<Phone>(503) 555-7555</Phone>  
```  
