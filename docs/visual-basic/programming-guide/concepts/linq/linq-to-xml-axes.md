---
title: Оси LINQ to XML
ms.date: 07/20/2015
ms.assetid: ecd3bd00-28e5-4517-a59f-53bff39fd478
ms.openlocfilehash: 757c765062b1d1ca1cddb0c559fa46ef6a0fe796
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84368989"
---
# <a name="linq-to-xml-axes-visual-basic"></a>Оси LINQ to XML (Visual Basic)
После создания XML-дерева или загрузки XML-документа в XML-дерево можно опросить его для поиска элементов и атрибутов и извлечения их значений.  
  
 Перед составлением каких-либо запросов необходимо понять назначение осей [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]. Существует два вида методов оси. Во-первых, есть методы, вызываемые применительно к одному объекту <xref:System.Xml.Linq.XElement>, объекту <xref:System.Xml.Linq.XDocument> или объекту <xref:System.Xml.Linq.XNode>. Данные методы работают с одним объектом и возвращают коллекцию объектов <xref:System.Xml.Linq.XElement>, <xref:System.Xml.Linq.XAttribute> или <xref:System.Xml.Linq.XNode>. Во-вторых, существуют методы расширения, работающие с коллекциями и возвращающие коллекции. В этих методах расширения создается перечисление исходной коллекции, вызывается соответствующий метод оси применительно к каждому элементу коллекции и осуществляется объединение результатов.  
  
## <a name="in-this-section"></a>в этом разделе  
  
|Раздел|Описание|  
|-----------|-----------------|  
|[Общие сведения об осях LINQ to XML (Visual Basic)](linq-to-xml-axes-overview.md)|Определяет оси и содержит описание того, как они используются в контексте запросов [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].|  
|[Как получить коллекцию элементов (LINQ to XML) (Visual Basic)](how-to-retrieve-a-collection-of-elements-linq-to-xml.md)|Вводит метод <xref:System.Xml.Linq.XContainer.Elements%2A>. Этот метод получает коллекцию дочерних элементов того или иного элемента.|  
|[Как получить значение элемента (LINQ to XML) (Visual Basic)](how-to-retrieve-the-value-of-an-element-linq-to-xml.md)|Показывает способ получения значений элементов.|  
|[Как выполнить фильтрацию по именам элементов (LINQ to XML) (Visual Basic)](how-to-filter-on-element-names-linq-to-xml.md)|Показывает способ фильтрации по именам элементов при использовании осей.|  
|[Последовательное руководство. вызов метода оси (LINQ to XML) (Visual Basic)](how-to-chain-axis-method-calls-linq-to-xml.md)|Показывает, как соединять в цепочку вызовы для методов осей.|  
|[Пошаговое руководство. Извлечение одного дочернего элемента (LINQ to XML) (Visual Basic)](how-to-retrieve-a-single-child-element-linq-to-xml.md)|Показывает способ получения одного дочернего элемента того или иного элемента по имени тега дочернего элемента.|  
|[Как получить коллекцию атрибутов (LINQ to XML) (Visual Basic)](how-to-retrieve-a-collection-of-attributes-linq-to-xml.md)|Вводит метод <xref:System.Xml.Linq.XElement.Attributes%2A>. Этот метод извлекает атрибуты того или иного элемента.|  
|[Как получить один атрибут (LINQ to XML) (Visual Basic)](how-to-retrieve-a-single-attribute-linq-to-xml.md)|Показывает способ получения одного атрибута элемента по имени атрибута.|  
|[Как получить значение атрибута (LINQ to XML) (Visual Basic)](how-to-retrieve-the-value-of-an-attribute-linq-to-xml.md)|Показывает способ получения значений атрибутов.|  
|[Как извлечь неглубокое значение элемента (Visual Basic)](how-to-retrieve-the-shallow-value-of-an-element.md)|Показывает способ получения поверхностного значения элемента.|  
|[Загрузка встроенных в язык осей в Visual Basic (LINQ to XML)](language-integrated-axes.md)|Суммирует Visual Basic интегрированные оси.|  
  
## <a name="see-also"></a>См. также раздел

- [Руководством по программированию (LINQ to XML) (Visual Basic)](programming-guide-linq-to-xml.md)
