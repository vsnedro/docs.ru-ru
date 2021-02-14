---
description: 'Узнайте подробнее о: Использование System.Xml'
title: Использование System.Xml
ms.date: 10/22/2008
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
ms.openlocfilehash: 51886c07f0b68bb329c258daa93e809d94839341
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99641854"
---
# <a name="systemxml-usage"></a>Использование System.Xml

В этом разделе описывается использование нескольких типов, располагающихся в пространствах имен <xref:System.Xml?displayProperty=nameWithType>, с помощью которых можно представлять XML-данные.

 ❌ НЕ СЛЕДУЕТ использовать <xref:System.Xml.XmlNode> или <xref:System.Xml.XmlDocument> для представления XML-данных. Предпочтительнее использовать экземпляры <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> или подтипы <xref:System.Xml.Linq.XNode>. `XmlNode` и `XmlDocument` не предназначены для предоставления в общедоступных API.

 ✔️ СЛЕДУЕТ использовать `XmlReader`, `IXPathNavigable` или подтипы `XNode` в качестве входных или выходных данных членов, которые принимают или возвращают XML-данные.

 Используйте эти абстракции вместо `XmlDocument`, `XmlNode` или <xref:System.Xml.XPath.XPathDocument>, так как это позволяет отделить методы от конкретных реализаций XML-документа в памяти и позволяет им работать с виртуальными источниками XML-данных, которые предоставляют `XNode`, `XmlReader` или <xref:System.Xml.XPath.XPathNavigator>.

 ❌ НЕ СЛЕДУЕТ создавать подкласс `XmlDocument`, если вы хотите создать тип, представляющий представление XML-данных для базовой модели объектов или источника данных.

 *Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*

 *Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*

## <a name="see-also"></a>См. также

- [Рекомендации по проектированию на основе Framework](index.md)
- [Правила использования](usage-guidelines.md)
