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
# <a name="how-to-retrieve-a-collection-of-attributes-linq-to-xml-c"></a>Извлечение коллекции атрибутов (LINQ to XML) (C#)
В этом разделе представлен метод <xref:System.Xml.Linq.XElement.Attributes%2A>. Этот метод извлекает атрибуты того или иного элемента.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как просматривать коллекцию атрибутов элемента.  
  
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
  
 Этот код выводит следующие результаты:  
  
```output  
ID="1243"  
Type="int"  
ConvertableTo="double"  
```  
  
## <a name="see-also"></a>См. также

- [Оси LINQ to XML (C#)](./linq-to-xml-axes-overview.md)
