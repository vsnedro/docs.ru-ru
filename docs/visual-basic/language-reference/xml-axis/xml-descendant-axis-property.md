---
title: XML Descendant Axis Property
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyDescendantsAxis
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML descendant axis property [Visual Basic]
- descendant axis property [Visual Basic]
- XML axis [Visual Basic], descendant
- XML [Visual Basic], accessing
ms.assetid: a178f85b-5d54-438f-8479-40b62af6fe76
ms.openlocfilehash: 52544619171dbc7034baeb5feb61395d81096387
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400257"
---
# <a name="xml-descendant-axis-property-visual-basic"></a>Свойство дочерней оси XML (Visual Basic)

Предоставляет доступ к потомкам следующих объектов: <xref:System.Xml.Linq.XElement> объекту, <xref:System.Xml.Linq.XDocument> объекту, коллекции <xref:System.Xml.Linq.XElement> объектов или коллекции <xref:System.Xml.Linq.XDocument> объектов.

## <a name="syntax"></a>Синтаксис

```vb
object...<descendant>
```

## <a name="parts"></a>Компоненты

`object` Обязательный. Объект <xref:System.Xml.Linq.XElement>, объект <xref:System.Xml.Linq.XDocument>, коллекция объектов <xref:System.Xml.Linq.XElement> или коллекция объектов <xref:System.Xml.Linq.XDocument>.

`...<` Обязательный. Обозначает начало свойства дочерней оси.

`descendant` Обязательный. Имя узлов-потомков для доступа к форме [ `prefix:]name` .

|Часть|Описание|
|----------|-----------------|
|`prefix`|Необязательный элемент. Префикс пространства имен XML для узла-потомка. Должно быть глобальным пространством имен XML, которое определяется с помощью `Imports` инструкции.|
|`name`|Обязательный. Локальное имя дочернего узла. См. [Имена объявленных XML-элементов и атрибутов](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|

`>` Обязательный. Обозначает конец свойства дочерней оси.

## <a name="return-value"></a>Возвращаемое значение

Коллекция объектов <xref:System.Xml.Linq.XElement>.

## <a name="remarks"></a>Комментарии

Свойство дочерней оси XML можно использовать для доступа к узлам-потомкам по имени из <xref:System.Xml.Linq.XElement> объекта или или <xref:System.Xml.Linq.XDocument> из коллекции <xref:System.Xml.Linq.XElement> объектов или <xref:System.Xml.Linq.XDocument> . Используйте свойство XML `Value` для доступа к значению первого узла-потомка в возвращаемой коллекции. Дополнительные сведения см. в разделе [свойство значения XML](xml-value-property.md).

Компилятор Visual Basic преобразует свойства оси потомков в вызовы <xref:System.Xml.Linq.XContainer.Descendants%2A> метода.

## <a name="xml-namespaces"></a>Пространства имен XML

Имя в свойстве дочерней оси может использовать только пространства имен XML, объявленные глобально с помощью `Imports` инструкции. Нельзя использовать пространства имен XML, объявленные локально в литералах XML-элементов. Дополнительные сведения см. в разделе [оператор Imports (пространство имен XML)](../statements/imports-statement-xml-namespace.md).

## <a name="example"></a>Пример

В следующем примере показано, как получить доступ к значению первого узла-потомка с именем `name` и значения всех узлов-потомков, названных `phone` из `contacts` объекта.

[!code-vb[VbXMLSamples#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#25)]

Этот пример кода отображает следующий текст:

`Name: Patrick Hines`

`Home Phone = 206-555-0144`

## <a name="example"></a>Пример

В следующем примере `ns` объявляется как префикс пространства имен XML. Затем он использует префикс пространства имен, чтобы создать XML-литерал и получить доступ к значению первого дочернего узла с полным именем `ns:name` .

[!code-vb[VbXMLSamples#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples12.vb#26)]

Этот пример кода отображает следующий текст:

`Name: Patrick Hines`

## <a name="see-also"></a>См. также раздел

- <xref:System.Xml.Linq.XElement>
- [Свойства оси XML](index.md)
- [XML-литералы](../xml-literals/index.md)
- [Создание XML в Visual Basic](../../programming-guide/language-features/xml/creating-xml.md)
- [Имена объявленных элементов и атрибутов XML](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
