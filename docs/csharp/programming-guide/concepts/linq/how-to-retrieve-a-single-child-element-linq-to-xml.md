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
# <a name="how-to-retrieve-a-single-child-element-linq-to-xml-c"></a>Извлечение одного дочернего элемента (LINQ to XML) (C#)
В этом разделе объясняется, как обеспечить получение отдельных дочерних элементов, когда известно имя этого дочернего элемента. Если известно имя дочернего элемента, а также то, что есть только один элемент с таким именем, удобнее получить один элемент, а не целую коллекцию.  
  
 Метод <xref:System.Xml.Linq.XContainer.Element%2A> возвращает первый дочерний элемент <xref:System.Xml.Linq.XElement> с указанным именем <xref:System.Xml.Linq.XName>.  
  
 Если требуется получить отдельный дочерний элемент в Visual Basic, обычно используется XML-свойство, а затем происходит получение первого элемента при помощи обозначения индексатора массива.  
  
## <a name="example"></a>Пример  
 В следующем примере иллюстрируется использование метода <xref:System.Xml.Linq.XContainer.Element%2A>. В этом примере берется XML-дерево `po` и осуществляется поиск первого элемента с именем `Comment`.  
  
 В примере по Visual Basic демонстрируется использование обозначения индексатора массива для получения отдельного элемента.  
  
 В этом примере используется следующий XML-документ: [Пример XML-файла. Типичный заказ на покупку (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).  
  
```csharp  
XElement po = XElement.Load("PurchaseOrder.xml");  
XElement e = po.Element("DeliveryNotes");  
Console.WriteLine(e);  
```  
  
 В этом примере выводятся следующие данные:  
  
```xml  
<DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
```  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется тот же код XML-документа, который находится в пространстве имен. Дополнительные сведения см. в статье [Обзор пространств имен DFS (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).  
  
 В этом примере используется следующий XML-документ: [Пример XML-файла. Типичный заказ на покупку в пространстве имен](./sample-xml-file-typical-purchase-order-in-a-namespace.md).  
  
```csharp  
XElement po = XElement.Load("PurchaseOrderInNamespace.xml");  
XNamespace aw = "http://www.adventure-works.com";  
XElement e = po.Element(aw + "DeliveryNotes");  
Console.WriteLine(e);  
```  
  
 В этом примере выводятся следующие данные:  
  
```xml  
<aw:DeliveryNotes xmlns:aw="http://www.adventure-works.com">Please leave packages in shed by driveway.</aw:DeliveryNotes>  
```  
  
## <a name="see-also"></a>См. также

- [Оси LINQ to XML (C#)](./linq-to-xml-axes-overview.md)
