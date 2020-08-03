---
title: Извлечение одного дочернего элемента (LINQ to XML) (C#)
description: Узнайте, как использовать LINQ to XML для извлечения одного дочернего элемента по имени. В этом примере C# метод Element возвращает первый указанный дочерний элемент.
ms.date: 07/20/2015
ms.assetid: ce37db9e-76fa-46eb-b4cc-e8f32d22ad90
ms.openlocfilehash: c3a044f30cf2e411bdff52586c7a370b626f41bc
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103282"
---
# <a name="how-to-retrieve-a-single-child-element-linq-to-xml-c"></a><span data-ttu-id="6230e-104">Извлечение одного дочернего элемента (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="6230e-104">How to retrieve a single child element (LINQ to XML) (C#)</span></span>
<span data-ttu-id="6230e-105">В этом разделе объясняется, как обеспечить получение отдельных дочерних элементов, когда известно имя этого дочернего элемента.</span><span class="sxs-lookup"><span data-stu-id="6230e-105">This topic explains how to retrieve a single child element, given the name of the child element.</span></span> <span data-ttu-id="6230e-106">Если известно имя дочернего элемента, а также то, что есть только один элемент с таким именем, удобнее получить один элемент, а не целую коллекцию.</span><span class="sxs-lookup"><span data-stu-id="6230e-106">When you know the name of the child element and that there is only one element that has this name, it can be convenient to retrieve just one element, instead of a collection.</span></span>  
  
 <span data-ttu-id="6230e-107">Метод <xref:System.Xml.Linq.XContainer.Element%2A> возвращает первый дочерний элемент <xref:System.Xml.Linq.XElement> с указанным именем <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="6230e-107">The <xref:System.Xml.Linq.XContainer.Element%2A> method returns the first child <xref:System.Xml.Linq.XElement> with the specified <xref:System.Xml.Linq.XName>.</span></span>  
  
 <span data-ttu-id="6230e-108">Если требуется получить отдельный дочерний элемент в Visual Basic, обычно используется XML-свойство, а затем происходит получение первого элемента при помощи обозначения индексатора массива.</span><span class="sxs-lookup"><span data-stu-id="6230e-108">If you want to retrieve a single child element in Visual Basic, a common approach is to use the XML property, and then retrieve the first element using array indexer notation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6230e-109">Пример</span><span class="sxs-lookup"><span data-stu-id="6230e-109">Example</span></span>  
 <span data-ttu-id="6230e-110">В следующем примере иллюстрируется использование метода <xref:System.Xml.Linq.XContainer.Element%2A>.</span><span class="sxs-lookup"><span data-stu-id="6230e-110">The following example demonstrates the use of the <xref:System.Xml.Linq.XContainer.Element%2A> method.</span></span> <span data-ttu-id="6230e-111">В этом примере берется XML-дерево `po` и осуществляется поиск первого элемента с именем `Comment`.</span><span class="sxs-lookup"><span data-stu-id="6230e-111">This example takes the XML tree named `po` and finds the first element named `Comment`.</span></span>  
  
 <span data-ttu-id="6230e-112">В примере по Visual Basic демонстрируется использование обозначения индексатора массива для получения отдельного элемента.</span><span class="sxs-lookup"><span data-stu-id="6230e-112">The Visual Basic example shows using array indexer notation to retrieve a single element.</span></span>  
  
 <span data-ttu-id="6230e-113">В этом примере используется следующий XML-документ: [Пример XML-файла. Типичный заказ на покупку (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="6230e-113">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
XElement po = XElement.Load("PurchaseOrder.xml");  
XElement e = po.Element("DeliveryNotes");  
Console.WriteLine(e);  
```  
  
 <span data-ttu-id="6230e-114">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="6230e-114">This example produces the following output:</span></span>  
  
```xml  
<DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
```  
  
## <a name="example"></a><span data-ttu-id="6230e-115">Пример</span><span class="sxs-lookup"><span data-stu-id="6230e-115">Example</span></span>  
 <span data-ttu-id="6230e-116">В следующем примере демонстрируется тот же код XML-документа, который находится в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="6230e-116">The following example shows the same code for XML that is in a namespace.</span></span> <span data-ttu-id="6230e-117">Дополнительные сведения см. в статье [Обзор пространств имен DFS (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="6230e-117">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="6230e-118">В этом примере используется следующий XML-документ: [Пример XML-файла. Типичный заказ на покупку в пространстве имен](./sample-xml-file-typical-purchase-order-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="6230e-118">This example uses the following XML document: [Sample XML File: Typical Purchase Order in a Namespace](./sample-xml-file-typical-purchase-order-in-a-namespace.md).</span></span>  
  
```csharp  
XElement po = XElement.Load("PurchaseOrderInNamespace.xml");  
XNamespace aw = "http://www.adventure-works.com";  
XElement e = po.Element(aw + "DeliveryNotes");  
Console.WriteLine(e);  
```  
  
 <span data-ttu-id="6230e-119">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="6230e-119">This example produces the following output:</span></span>  
  
```xml  
<aw:DeliveryNotes xmlns:aw="http://www.adventure-works.com">Please leave packages in shed by driveway.</aw:DeliveryNotes>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6230e-120">См. также</span><span class="sxs-lookup"><span data-stu-id="6230e-120">See also</span></span>

- [<span data-ttu-id="6230e-121">Оси LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="6230e-121">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
