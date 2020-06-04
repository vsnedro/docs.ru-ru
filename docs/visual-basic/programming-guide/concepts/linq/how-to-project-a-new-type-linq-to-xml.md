---
title: Практическое руководство. Проецирование нового типа (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 8cfb24f5-89b2-4cfb-b85d-e7963f8f1845
ms.openlocfilehash: 48fb82e870a4fc4fa16cfb48a127f364e6d81f13
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396510"
---
# <a name="how-to-project-a-new-type-linq-to-xml-visual-basic"></a>Руководство. проецирование нового типа (LINQ to XML) (Visual Basic)
В других примерах данного раздела показаны запросы, возвращающие результаты в виде значений <xref:System.Collections.Generic.IEnumerable%601> типа <xref:System.Xml.Linq.XElement>, значений <xref:System.Collections.Generic.IEnumerable%601> типа `string` и значений <xref:System.Collections.Generic.IEnumerable%601> типа `int`. Это наиболее распространенные типы результатов, но подходят не для всех сценариев. Во многих случаях требуется, чтобы запросы возвращали <xref:System.Collections.Generic.IEnumerable%601> какого-то другого типа.  
  
## <a name="example"></a>Пример  
 В данном примере показано, как создавать экземпляры объектов в предложении `Select`. Сначала в коде определяется новый класс с помощью конструктора, а затем модифицируется инструкция `Select`, чтобы это выражение представляло новый экземпляр нового класса.  
  
 В этом примере используется следующий XML-документ: [Пример XML-файла. Стандартный заказ на покупку (LINQ to XML)](sample-xml-file-typical-purchase-order-linq-to-xml.md).  
  
```vb  
Public Class NameQty  
    Public name As String  
    Public qty As Integer  
    Public Sub New(ByVal n As String, ByVal q As Integer)  
        name = n  
        qty = q  
    End Sub  
End Class  
  
Public Class Program  
    Shared Sub Main()  
        Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
  
        Dim nqList As IEnumerable(Of NameQty) = _  
            From n In po...<Item> _  
            Select New NameQty( _  
                n.<ProductName>.Value, CInt(n.<Quantity>.Value))  
  
        For Each n As NameQty In nqList  
            Console.WriteLine(n.name & ":" & n.qty)  
        Next  
    End Sub  
End Class  
```  
  
 В этом примере используется `M:System.Xml.Linq.XElement.Element` метод, представленный в разделе [как получить один дочерний элемент (LINQ to XML) (Visual Basic)](how-to-retrieve-a-single-child-element-linq-to-xml.md). В нем также используется приведение для получения значений элементов, возвращаемых методом `M:System.Xml.Linq.XElement.Element`.  
  
 В этом примере выводятся следующие данные:  
  
```console  
Lawnmower:1  
Baby Monitor:2  
```  
  
## <a name="see-also"></a>См. также

- [Проекции и преобразования (LINQ to XML) (Visual Basic)](projections-and-transformations-linq-to-xml.md)
