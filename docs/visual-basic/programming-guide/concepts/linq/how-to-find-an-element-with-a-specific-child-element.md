---
title: Практическое руководство. Поиск элементов с определенным дочерним элементом
ms.date: 07/20/2015
ms.assetid: b0d0a463-6a85-46c3-8453-ad25b0ecf93c
ms.openlocfilehash: a05504070fe3d2ea5eb6135fd3bf697b131686c6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405291"
---
# <a name="how-to-find-an-element-with-a-specific-child-element-visual-basic"></a>Как найти элемент с указанным дочерним элементом (Visual Basic)
В этом разделе показан определенный элемент, имеющий дочерний элемент с заданным значением.  
  
## <a name="example"></a>Пример  
 В этом примере осуществляется поиск элемента `Test`, имеющего дочерний элемент `CommandLine` со значением «Examp2.EXE».  
  
 В этом примере используется следующий XML-документ: [Пример XML-файла. Конфигурация тестирования (LINQ to XML)](sample-xml-file-test-configuration-linq-to-xml.md).  
  
```vb  
Dim root As XElement = XElement.Load("TestConfig.xml")  
Dim tests As IEnumerable(Of XElement) = _  
    From el In root.<Test> _  
    Where el.<CommandLine>.Value = "Examp2.EXE" _  
    Select el  
For Each el as XElement In tests  
    Console.WriteLine(el.@TestId)  
Next  
```  
  
 Этот код выводит следующие результаты:  
  
```console  
0002  
0006  
```  
  
 Обратите внимание, что в этом примере используется [свойство дочерней оси XML](../../../language-reference/xml-axis/xml-child-axis-property.md), [свойство оси атрибутов XML](../../../language-reference/xml-axis/xml-attribute-axis-property.md)и [свойство XML value](../../../language-reference/xml-axis/xml-value-property.md).  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует тот же запрос XML, что и в пространстве имен. Дополнительные сведения см. в разделе [Общие сведения о пространствах имен (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).  
  
 В этом примере используется следующий XML-документ: [Пример XML-файла. Конфигурация тестирования в пространстве имен](sample-xml-file-test-configuration-in-a-namespace.md).  
  
```vb  
Imports <xmlns='http://www.adatum.com'>  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = XElement.Load("TestConfigInNamespace.xml")  
        Dim tests As IEnumerable(Of XElement) = _  
            From el In root.<Test> _  
            Where el.<CommandLine>.Value = "Examp2.EXE" _  
            Select el  
        For Each el As XElement In tests  
            Console.WriteLine(el.@TestId)  
        Next  
    End Sub  
End Module  
```  
  
 Этот код выводит следующие результаты:  
  
```console  
0002  
0006  
```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [Основные запросы (LINQ to XML) (Visual Basic)](basic-queries-linq-to-xml.md)
- [Общие сведения о стандартных операторах запроса (Visual Basic)](standard-query-operators-overview.md)
- [Операции проекции (Visual Basic)](projection-operations.md)
