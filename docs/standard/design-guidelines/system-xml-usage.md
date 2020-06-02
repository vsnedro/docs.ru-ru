---
title: Использование System.Xml
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
ms.openlocfilehash: 07828219f2e17be925d060fa3bb33a9209ecb62b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291673"
---
# <a name="systemxml-usage"></a>Использование System.Xml
В этом разделе рассказывается об использовании нескольких типов, находящихся в <xref:System.Xml?displayProperty=nameWithType> пространствах имен, которые могут использоваться для представления XML-данных.

 ❌НЕ используйте <xref:System.Xml.XmlNode> или <xref:System.Xml.XmlDocument> для представления XML-данных. Используйте <xref:System.Xml.XPath.IXPathNavigable> вместо этого экземпляры, <xref:System.Xml.XmlReader> , <xref:System.Xml.XmlWriter> или подтипы <xref:System.Xml.Linq.XNode> . `XmlNode`и `XmlDocument` не предназначены для предоставления открытым API.

 ✔️ использовать `XmlReader` `IXPathNavigable` подтипы, или `XNode` в качестве входных или выходных данных членов, принимающих или возвращающих XML.

 Используйте эти абстракции вместо `XmlDocument` , `XmlNode` или <xref:System.Xml.XPath.XPathDocument> , так как это отделяет методы от конкретных реализаций XML-документа в памяти и позволяет им работать с виртуальными ИСТОЧНИКами данных XML, которые предоставляют `XNode` , `XmlReader` или <xref:System.Xml.XPath.XPathNavigator> .

 ❌НЕ подклассировать, `XmlDocument` Если необходимо создать тип, представляющий представление XML базовой объектной модели или источника данных.

 *Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*

 *Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*

## <a name="see-also"></a>См. также

- [Рекомендации по проектированию платформы](index.md)
- [Рекомендации по использованию](usage-guidelines.md)
