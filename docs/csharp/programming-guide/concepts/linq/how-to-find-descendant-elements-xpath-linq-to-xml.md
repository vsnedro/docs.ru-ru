---
title: Практическое руководство. Поиск элементов-потомков (XPath-LINQ to XML) (C#)
description: Узнайте, как получить элементы-потомки с определенным именем, используя выражение XPath. Ознакомьтесь с примером кода, в котором используется пример XML-файла.
ms.date: 07/20/2015
ms.assetid: b318da39-bb8b-4c56-a019-e13b12b01831
ms.openlocfilehash: c5a998a05f866203f3b684b8847a4a5647c12e5b
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303274"
---
# <a name="how-to-find-descendant-elements-xpath-linq-to-xml-c"></a><span data-ttu-id="2ef89-104">Практическое руководство. Поиск элементов-потомков (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="2ef89-104">How to find descendant elements (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="2ef89-105">В этом разделе рассказывается, как возвращать элементы-потомки с определенным именем.</span><span class="sxs-lookup"><span data-stu-id="2ef89-105">This topic shows how to get the descendant elements with a particular name.</span></span>  
  
 <span data-ttu-id="2ef89-106">Выражение XPath - `//Name`.</span><span class="sxs-lookup"><span data-stu-id="2ef89-106">The XPath expression is `//Name`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ef89-107">Пример</span><span class="sxs-lookup"><span data-stu-id="2ef89-107">Example</span></span>  
 <span data-ttu-id="2ef89-108">В этом примере обнаруживаются все потомки с именем `Name`.</span><span class="sxs-lookup"><span data-stu-id="2ef89-108">This example finds all descendants named `Name`.</span></span>  
  
 <span data-ttu-id="2ef89-109">В этом примере используется следующий XML-документ: [Пример XML-файла. Несколько заказов на покупку (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="2ef89-109">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 = po.Root.Descendants("Name");  
  
// XPath expression  
IEnumerable<XElement> list2 = po.XPathSelectElements("//Name");  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="2ef89-110">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="2ef89-110">This example produces the following output:</span></span>  
  
```output  
Results are identical  
<Name>Ellen Adams</Name>  
<Name>Tai Yee</Name>  
<Name>Cristian Osorio</Name>  
<Name>Cristian Osorio</Name>  
<Name>Jessica Arnold</Name>  
<Name>Jessica Arnold</Name>  
```  
