---
title: Извлечение коллекции элементов (LINQ to XML) (C#)
description: Метод Elements в C# получает коллекцию дочерних элементов того или иного элемента. В этом примере LINQ to XML выполняется итерация по дочерним элементам элемента.
ms.date: 07/20/2015
ms.assetid: b849668c-7976-4974-b8e1-1cd587d34258
ms.openlocfilehash: 4f9b6ae4713af9ce1a4eeb5257f57cd9724f68b2
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103353"
---
# <a name="how-to-retrieve-a-collection-of-elements-linq-to-xml-c"></a><span data-ttu-id="f0135-104">Извлечение коллекции элементов (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="f0135-104">How to retrieve a collection of elements (LINQ to XML) (C#)</span></span>
<span data-ttu-id="f0135-105">В этом разделе показан метод <xref:System.Xml.Linq.XContainer.Elements%2A>.</span><span class="sxs-lookup"><span data-stu-id="f0135-105">This topic demonstrates the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span> <span data-ttu-id="f0135-106">Этот метод получает коллекцию дочерних элементов того или иного элемента.</span><span class="sxs-lookup"><span data-stu-id="f0135-106">This method retrieves a collection of the child elements of an element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0135-107">Пример</span><span class="sxs-lookup"><span data-stu-id="f0135-107">Example</span></span>  
 <span data-ttu-id="f0135-108">В этом примере выполняется итерация по дочерним элементам элемента `purchaseOrder`.</span><span class="sxs-lookup"><span data-stu-id="f0135-108">This example iterates through the child elements of the `purchaseOrder` element.</span></span>  
  
 <span data-ttu-id="f0135-109">В этом примере используется следующий XML-документ: [Пример XML-файла. Типичный заказ на покупку (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="f0135-109">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
XElement po = XElement.Load("PurchaseOrder.xml");  
IEnumerable<XElement> childElements =  
    from el in po.Elements()  
    select el;  
foreach (XElement el in childElements)  
    Console.WriteLine("Name: " + el.Name);  
```  
  
 <span data-ttu-id="f0135-110">В этом примере формируются следующие данные:</span><span class="sxs-lookup"><span data-stu-id="f0135-110">This example produces the following output.</span></span>  
  
```output  
Name: Address  
Name: Address  
Name: DeliveryNotes  
Name: Items  
```  
  
## <a name="see-also"></a><span data-ttu-id="f0135-111">См. также</span><span class="sxs-lookup"><span data-stu-id="f0135-111">See also</span></span>

- [<span data-ttu-id="f0135-112">Оси LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="f0135-112">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
