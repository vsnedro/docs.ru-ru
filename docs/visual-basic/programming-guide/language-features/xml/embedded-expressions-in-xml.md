---
title: Встроенные выражения в XML
ms.date: 07/20/2015
f1_keywords:
- vb.XmlEmbeddedExpression
helpviewer_keywords:
- embedded expressions [Visual Basic]
- LINQ to XML [Visual Basic], embedded expressions
- XML literals [Visual Basic], embedded expressions
ms.assetid: bf2eb779-b751-4b7c-854f-9f2161482352
ms.openlocfilehash: d4ff9442aa82a3eb46d56500159562174646ea58
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410261"
---
# <a name="embedded-expressions-in-xml-visual-basic"></a>Встроенные выражения в XML (Visual Basic)
Внедренные выражения позволяют создавать XML-литералы, содержащие выражения, вычисляемые во время выполнения. Синтаксис для внедренного выражения — это `<%=` `expression` `%>` то же, что и синтаксис, используемый в ASP.NET.  
  
 Например, можно создать литерал XML-элемента, объединяющий внедренные выражения с текстовым содержимым.  
  
 [!code-vb[VbXMLSamples#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#27)]  
  
 Если `isbnNumber` содержит целое число 12345 и `modifiedDate` содержит дату 3/5/2006, то при выполнении этого кода значение `book` равно:  
  
```xml  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## <a name="embedded-expression-location-and-validation"></a>Расположение и проверка внедренных выражений  
 Встроенные выражения могут использоваться только в определенных местах в выражениях литералов XML. Расположение выражения определяет, какие типы могут быть возвращены выражением и как `Nothing` обрабатывается. В следующей таблице описаны допустимые расположения и типы внедренных выражений.  
  
|Расположение в литерале|Тип выражения|Обработка`Nothing`|  
|---|---|---|  
|Имя XML-элемента|<xref:System.Xml.Linq.XName>|Ошибка|  
|Содержимое XML-элемента|`Object`или массив`Object`|Не учитывается|  
|Имя атрибута XML-элемента|<xref:System.Xml.Linq.XName>|Ошибка, если значение атрибута также не равно`Nothing`|  
|Значение атрибута XML-элемента|`Object`|Объявление атрибута пропущено|  
|Атрибут XML-элемента|<xref:System.Xml.Linq.XAttribute>или коллекция<xref:System.Xml.Linq.XAttribute>|Не учитывается|  
|Корневой элемент XML-документа|<xref:System.Xml.Linq.XElement>или коллекция из одного <xref:System.Xml.Linq.XElement> объекта и произвольное число <xref:System.Xml.Linq.XProcessingInstruction> <xref:System.Xml.Linq.XComment> объектов и|Не учитывается|  
  
- Пример внедренного выражения в имени XML-элемента:  
  
     [!code-vb[VbXMLSamples#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#32)]  
  
- Пример внедренного выражения в содержимом XML-элемента:  
  
     [!code-vb[VbXMLSamples#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#33)]  
  
- Пример внедренного выражения в имени атрибута XML-элемента:  
  
     [!code-vb[VbXMLSamples#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#34)]  
  
- Пример внедренного выражения в значении атрибута XML-элемента:  
  
     [!code-vb[VbXMLSamples#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#35)]  
  
- Пример внедренного выражения в атрибуте XML-элемента:  
  
     [!code-vb[VbXMLSamples#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#36)]  
  
- Пример внедренного выражения в корневом элементе XML-документа:  
  
     [!code-vb[VbXMLSamples#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#37)]  
  
 Если включить `Option Strict` , компилятор проверяет, что тип каждого внедренного выражения расширяется до требуемого типа. Единственным исключением является корневой элемент XML-документа, который проверяется при выполнении кода. При компиляции без `Option Strict` можно внедрить выражения типа `Object` и их тип проверяется во время выполнения.  
  
 В расположениях, где содержимое является необязательным, внедренные выражения, содержащие, `Nothing` игнорируются. Это означает, что нет необходимости проверять содержимое элемента, значения атрибутов и элементы массива `Nothing` перед использованием XML-литерала. Обязательные значения, такие как имена элементов и атрибутов, не могут иметь значение `Nothing` .  
  
 Дополнительные сведения об использовании внедренных выражений в определенном типе литерала см. в разделе [литерал XML-документа](../../../language-reference/xml-literals/xml-document-literal.md), [литерал XML-элемента](../../../language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="scoping-rules"></a>Правила области видимости  
 Компилятор преобразует каждый XML-литерал в вызов конструктора для соответствующего типа литерала. Литеральное содержимое и внедренные выражения в XML-литерале передаются в качестве аргументов в конструктор. Это означает, что все элементы программирования Visual Basic, доступные для XML-литерала, также доступны для внедренных выражений.  
  
 В XML-литерале можно получить доступ к префиксам пространства имен XML, объявленным с помощью `Imports` инструкции. Можно объявить новый префикс пространства имен XML или затенить существующий префикс пространства имен XML в элементе с помощью `xmlns` атрибута. Новое пространство имен доступно для дочерних узлов этого элемента, но не для XML-литералов во внедренных выражениях.  
  
> [!NOTE]
> При объявлении префикса пространства имен XML с помощью `xmlns` атрибута Namespace значение атрибута должно быть строковой константой. В этом отношении использование `xmlns` атрибута аналогично использованию `Imports` оператора для объявления пространства имен XML. Нельзя использовать внедренное выражение для указания значения пространства имен XML.  
  
## <a name="see-also"></a>См. также раздел

- [Создание XML в Visual Basic](creating-xml.md)
- [XML-литерал документа](../../../language-reference/xml-literals/xml-document-literal.md)
- [XML-литерал элемента](../../../language-reference/xml-literals/xml-element-literal.md)
- [Оператор Option Strict](../../../language-reference/statements/option-strict-statement.md)
- [Оператор Imports (пространство имен .NET и тип)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Общие сведения об XML-литералах](xml-literals-overview.md)
