---
title: Поиск корневого элемента (XPath-LINQ to XML) (C#)
description: В этом примере C# сравнивается поиск корневого элемента для образца XML-документа в XPath и LINQ to XML.
ms.date: 07/20/2015
ms.assetid: 4fd824e0-4d39-429b-b092-f6a5c046ee6c
ms.openlocfilehash: 220899823210c5cd6e9834541ca87e4d8394b4ff
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105183"
---
# <a name="how-to-find-the-root-element-xpath-linq-to-xml-c"></a><span data-ttu-id="f3fd9-103">Поиск корневого элемента (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="f3fd9-103">How to find the root element (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="f3fd9-104">В этом разделе показан поиск корневого элемента с помощью XPath и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f3fd9-104">This topic shows how to get the root element with XPath and [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="f3fd9-105">Выражение XPath:</span><span class="sxs-lookup"><span data-stu-id="f3fd9-105">The XPath expression is:</span></span>  
  
 `/PurchaseOrders`  
  
## <a name="example"></a><span data-ttu-id="f3fd9-106">Пример</span><span class="sxs-lookup"><span data-stu-id="f3fd9-106">Example</span></span>  
 <span data-ttu-id="f3fd9-107">В этом примере осуществляется поиск корневого элемента.</span><span class="sxs-lookup"><span data-stu-id="f3fd9-107">This example finds the root element.</span></span>  
  
 <span data-ttu-id="f3fd9-108">В этом примере используется следующий XML-документ: [Пример XML-файла. Несколько заказов на покупку (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="f3fd9-108">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
// LINQ to XML query  
XElement el1 = po.Root;  
  
// XPath expression  
XElement el2 = po.XPathSelectElement("/PurchaseOrders");  
  
if (el1 == el2)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(el1.Name);  
```  
  
 <span data-ttu-id="f3fd9-109">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="f3fd9-109">This example produces the following output:</span></span>  
  
```output  
Results are identical  
PurchaseOrders  
```  
