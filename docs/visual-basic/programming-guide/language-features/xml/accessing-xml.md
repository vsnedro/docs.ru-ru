---
title: Доступ к XML
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], accessing XML
- Visual Basic code, XML
- accessing XML [Visual Basic], axis properties
- XML [Visual Basic], axis properties
- XML [Visual Basic], accessing
ms.assetid: c47f88b2-3cbc-4bb1-b4b9-be60f71ffc6a
ms.openlocfilehash: 282b7d91ec7cfe2f587c67bc9a982f0da22ad925
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410313"
---
# <a name="accessing-xml-in-visual-basic"></a>Доступ к XML в Visual Basic
Visual Basic предоставляет свойства осей XML для доступа к структурам и навигации по ним [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] . Эти свойства используют специальный синтаксис, позволяющий получить доступ к элементам и атрибутам, указав имена XML.  
  
 В следующей таблице перечислены функции языка, позволяющие получать доступ к XML-элементам и атрибутам в Visual Basic.  
  
### <a name="xml-axis-properties"></a>Свойства оси XML  
  
|Описание свойства|Пример|Описание|  
|--------------------------|-------------|-----------------|  
|*дочерняя ось*|`contact.<phone>`|Возвращает все `phone` элементы, являющиеся дочерними элементами `contact` элемента.|  
|*attribute, ось*|`phone.@type`|Возвращает все `type` атрибуты `phone` элемента.|  
|*descendant, ось*|`contacts...<name>`|Возвращает все `name` элементы `contacts` элемента, независимо от того, насколько глубоко в иерархии они выполняются.|  
|*индексатор расширения*|`contacts...<name>(0)`|Возвращает первый `name` элемент из последовательности.|  
|*value*|`contacts...<name>.Value`|Возвращает строковое представление первого объекта в последовательности или `Nothing` значение, если последовательность пуста.|  
  
## <a name="in-this-section"></a>В этом разделе  
 [Практическое руководство. Доступ к элементам-потомкам XML](how-to-access-xml-descendant-elements.md)  
 Показывает, как использовать свойство оси потомков для доступа ко всем XML-элементам с указанным именем и содержащимся в указанном XML-элементе.  
  
 [Практическое руководство. Доступ к дочерним XML-элементам](how-to-access-xml-child-elements.md)  
 Показывает, как использовать свойство дочерней оси для доступа ко всем дочерним элементам XML с указанным именем в элементе XML.  
  
 [Практическое руководство. Доступ к XML-атрибутам](how-to-access-xml-attributes.md)  
 Показывает, как использовать свойство оси атрибута для доступа ко всем XML-атрибутам, имеющим указанное имя в элементе XML.  
  
 [Практическое руководство. Объявление и использование префиксов пространств имен XML](how-to-declare-and-use-xml-namespace-prefixes.md)  
 Показывает, как объявить префикс пространства имен XML и использовать его для создания и доступа к XML-элементам.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Свойства оси XML](../../../language-reference/xml-axis/index.md)  
 Содержит ссылки на разделы, описывающие различные свойства доступа к XML.  
  
 [Overview of LINQ to XML in Visual Basic](overview-of-linq-to-xml.md) (Общие сведения о LINQ to XML в Visual Basic)  
 Общие сведения об использовании [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] в Visual Basic.  
  
 [Создание XML в Visual Basic](creating-xml.md)  
 Общие сведения об использовании литералов XML в Visual Basic.  
  
 [Обработка XML в Visual Basic](manipulating-xml.md)  
 Содержит ссылки на разделы, посвященные загрузке и изменению XML в Visual Basic.  
  
 [XML](index.md)  
 Содержит ссылки на разделы, описывающие использование [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] в Visual Basic.
