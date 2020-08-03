---
title: Практическое руководство. Поиск связанных элементов (XPath-LINQ to XML) (C#)
description: В этом примере C# сравниваются способы получения элемента по атрибуту, на который ссылается значение другого элемента, в XPath и LINQ to XML.
ms.date: 07/20/2015
ms.assetid: 41b386ee-562d-4841-bd6b-e44a7eb69f26
ms.openlocfilehash: 4423e7d719d39e71bcbcc9e88d052c6aff4ffb05
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105251"
---
# <a name="how-to-find-related-elements-xpath-linq-to-xml-c"></a><span data-ttu-id="d46ae-103">Практическое руководство. Поиск связанных элементов (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="d46ae-103">How to find related elements (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="d46ae-104">В этом разделе показано, как возвращать элемент, выбирая атрибут, обращение к которому осуществляется с помощью значения другого элемента.</span><span class="sxs-lookup"><span data-stu-id="d46ae-104">This topic shows how to get an element selecting on an attribute that is referred to by the value of another element.</span></span>  
  
 <span data-ttu-id="d46ae-105">Выражение XPath:</span><span class="sxs-lookup"><span data-stu-id="d46ae-105">The XPath expression is:</span></span>  
  
 `.//Customer[@CustomerID=/Root/Orders/Order[12]/CustomerID]`  
  
## <a name="example"></a><span data-ttu-id="d46ae-106">Пример</span><span class="sxs-lookup"><span data-stu-id="d46ae-106">Example</span></span>  
 <span data-ttu-id="d46ae-107">В этом примере обнаруживается 12-й элемент `Order`, а затем определяется клиент, сделавший этот заказ.</span><span class="sxs-lookup"><span data-stu-id="d46ae-107">This example finds the 12th `Order` element, and then finds the customer for that order.</span></span>  
  
 <span data-ttu-id="d46ae-108">Обратите внимание, что индексирование в списках .NET начинается с нуля.</span><span class="sxs-lookup"><span data-stu-id="d46ae-108">Note that indexing into a list in .NET is 'zero' based.</span></span> <span data-ttu-id="d46ae-109">Индексирование в коллекции узлов в предикате XPath начинается с единицы.</span><span class="sxs-lookup"><span data-stu-id="d46ae-109">Indexing into a collection of nodes in an XPath predicate is 'one' based.</span></span> <span data-ttu-id="d46ae-110">Данное различие находит отражение в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d46ae-110">This example reflects this difference.</span></span>  
  
 <span data-ttu-id="d46ae-111">В этом примере используется следующий XML-документ: [Пример XML-файла. Заказчики и заказы (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span><span class="sxs-lookup"><span data-stu-id="d46ae-111">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>  
  
```csharp  
XDocument co = XDocument.Load("CustomersOrders.xml");  
  
// LINQ to XML query  
XElement customer1 =  
    (from el in co.Descendants("Customer")  
     where (string)el.Attribute("CustomerID") ==  
          (string)(co  
              .Element("Root")  
              .Element("Orders")  
              .Elements("Order")  
              .ToList()[11]  
              .Element("CustomerID"))  
    select el)  
    .First();  
  
// An alternate way to write the query that avoids creation  
// of a System.Collections.Generic.List:  
XElement customer2 =  
    (from el in co.Descendants("Customer")  
     where (string)el.Attribute("CustomerID") ==  
          (string)(co  
              .Element("Root")  
              .Element("Orders")  
              .Elements("Order")  
              .Skip(11).First()  
              .Element("CustomerID"))  
    select el)  
    .First();  
  
// XPath expression  
XElement customer3 = co.XPathSelectElement(  
  ".//Customer[@CustomerID=/Root/Orders/Order[12]/CustomerID]");  
  
if (customer1 == customer2 && customer1 == customer3)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(customer1);  
```  
  
 <span data-ttu-id="d46ae-112">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="d46ae-112">This example produces the following output:</span></span>  
  
```output  
Results are identical  
<Customer CustomerID="HUNGC">  
  <CompanyName>Hungry Coyote Import Store</CompanyName>  
  <ContactName>Yoshi Latimer</ContactName>  
  <ContactTitle>Sales Representative</ContactTitle>  
  <Phone>(503) 555-6874</Phone>  
  <Fax>(503) 555-2376</Fax>  
  <FullAddress>  
    <Address>City Center Plaza 516 Main St.</Address>  
    <City>Elgin</City>  
    <Region>OR</Region>  
    <PostalCode>97827</PostalCode>  
    <Country>USA</Country>  
  </FullAddress>  
</Customer>  
```  
