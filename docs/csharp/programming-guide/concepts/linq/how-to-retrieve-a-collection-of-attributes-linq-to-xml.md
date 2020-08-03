---
title: Извлечение коллекции атрибутов (LINQ to XML) (C#)
description: Метод Attributes в C# извлекает атрибуты того или иного элемента. В этом примере LINQ to XML показано, как просматривать коллекцию атрибутов элемента.
ms.date: 07/20/2015
ms.assetid: a49ee7a3-b2c2-4d49-9b5c-b7c6c41f4f13
ms.openlocfilehash: 5994086db6133530e63eb1328a7b524d30a0797d
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103388"
---
# <a name="how-to-retrieve-a-collection-of-attributes-linq-to-xml-c"></a><span data-ttu-id="2dd83-104">Извлечение коллекции атрибутов (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="2dd83-104">How to retrieve a collection of attributes (LINQ to XML) (C#)</span></span>
<span data-ttu-id="2dd83-105">В этом разделе представлен метод <xref:System.Xml.Linq.XElement.Attributes%2A>.</span><span class="sxs-lookup"><span data-stu-id="2dd83-105">This topic introduces the <xref:System.Xml.Linq.XElement.Attributes%2A> method.</span></span> <span data-ttu-id="2dd83-106">Этот метод извлекает атрибуты того или иного элемента.</span><span class="sxs-lookup"><span data-stu-id="2dd83-106">This method retrieves the attributes of an element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2dd83-107">Пример</span><span class="sxs-lookup"><span data-stu-id="2dd83-107">Example</span></span>  
 <span data-ttu-id="2dd83-108">В следующем примере показано, как просматривать коллекцию атрибутов элемента.</span><span class="sxs-lookup"><span data-stu-id="2dd83-108">The following example shows how to iterate through the collection of attributes of an element.</span></span>  
  
```csharp  
XElement val = new XElement("Value",  
    new XAttribute("ID", "1243"),  
    new XAttribute("Type", "int"),  
    new XAttribute("ConvertableTo", "double"),  
    "100");  
IEnumerable<XAttribute> listOfAttributes =  
    from att in val.Attributes()  
    select att;  
foreach (XAttribute a in listOfAttributes)  
    Console.WriteLine(a);  
```  
  
 <span data-ttu-id="2dd83-109">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="2dd83-109">This code produces the following output:</span></span>  
  
```output  
ID="1243"  
Type="int"  
ConvertableTo="double"  
```  
  
## <a name="see-also"></a><span data-ttu-id="2dd83-110">См. также</span><span class="sxs-lookup"><span data-stu-id="2dd83-110">See also</span></span>

- [<span data-ttu-id="2dd83-111">Оси LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="2dd83-111">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
