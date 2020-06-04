---
title: Практическое руководство. Поиск атрибута родительского элемента (XPath-LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 9d2572fd-27d4-426c-b079-16854cb9ec7d
ms.openlocfilehash: 98b6e0e55390a2be13968e455321311661d81e84
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405304"
---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-visual-basic"></a>Как найти атрибут родителя (XPath-LINQ to XML) (Visual Basic)
Данный раздел показывает способ перехода к родительскому элементу и нахождения его атрибута.  
  
 Выражение XPath:  
  
 `../@id`  
  
## <a name="example"></a>Пример  
 Сначала в данном примере осуществляется поиск элемента `Author`. Затем в нем осуществляется поиск атрибута `id` родительского элемента.  
  
 В этом примере используется следующий XML-документ: [Пример XML-файла. Книги (LINQ to XML)](sample-xml-file-books-linq-to-xml.md).  
  
```vb  
Dim books As XDocument = XDocument.Load("Books.xml")  
Dim author As XElement = books.Root.<Book>.<Author>.FirstOrDefault()  
  
' LINQ to XML query  
Dim att1 As XAttribute = author.Parent.Attribute("id")  
  
' XPath expression  
Dim att2 As XAttribute = DirectCast(author.XPathEvaluate("../@id"),  _  
    IEnumerable).Cast(Of XAttribute)().First()  
  
If att1 Is att2 Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
Console.WriteLine(att1)  
```  
  
 В этом примере выводятся следующие данные:  
  
```console  
Results are identical  
id="bk101"  
```  
  
## <a name="see-also"></a>См. также

- [LINQ to XML для пользователей XPath (Visual Basic)](linq-to-xml-for-xpath-users.md)
