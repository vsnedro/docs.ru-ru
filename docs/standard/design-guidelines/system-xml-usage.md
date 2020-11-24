---
title: Использование System.Xml
ms.date: 10/22/2008
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
ms.openlocfilehash: 46282afa6548c731b04c40d8de91a1fed997c57c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677574"
---
# <a name="systemxml-usage"></a><span data-ttu-id="02a47-102">Использование System.Xml</span><span class="sxs-lookup"><span data-stu-id="02a47-102">System.Xml Usage</span></span>

<span data-ttu-id="02a47-103">В этом разделе рассказывается об использовании нескольких типов, находящихся в <xref:System.Xml?displayProperty=nameWithType> пространствах имен, которые могут использоваться для представления XML-данных.</span><span class="sxs-lookup"><span data-stu-id="02a47-103">This section talks about usage of several types residing in <xref:System.Xml?displayProperty=nameWithType> namespaces that can be used to represent XML data.</span></span>

 <span data-ttu-id="02a47-104">❌ НЕ используйте <xref:System.Xml.XmlNode> или <xref:System.Xml.XmlDocument> для представления XML-данных.</span><span class="sxs-lookup"><span data-stu-id="02a47-104">❌ DO NOT use <xref:System.Xml.XmlNode> or <xref:System.Xml.XmlDocument> to represent XML data.</span></span> <span data-ttu-id="02a47-105">Используйте <xref:System.Xml.XPath.IXPathNavigable> вместо этого экземпляры, <xref:System.Xml.XmlReader> , <xref:System.Xml.XmlWriter> или подтипы <xref:System.Xml.Linq.XNode> .</span><span class="sxs-lookup"><span data-stu-id="02a47-105">Favor using instances of <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, or subtypes of <xref:System.Xml.Linq.XNode> instead.</span></span> <span data-ttu-id="02a47-106">`XmlNode` и `XmlDocument` не предназначены для предоставления открытым API.</span><span class="sxs-lookup"><span data-stu-id="02a47-106">`XmlNode` and `XmlDocument` are not designed for exposing in public APIs.</span></span>

 <span data-ttu-id="02a47-107">✔️ использовать `XmlReader` `IXPathNavigable` подтипы, или `XNode` в качестве входных или выходных данных членов, принимающих или возвращающих XML.</span><span class="sxs-lookup"><span data-stu-id="02a47-107">✔️ DO use `XmlReader`, `IXPathNavigable`, or subtypes of `XNode` as input or output of members that accept or return XML.</span></span>

 <span data-ttu-id="02a47-108">Используйте эти абстракции вместо `XmlDocument` , `XmlNode` или <xref:System.Xml.XPath.XPathDocument> , так как это отделяет методы от конкретных реализаций XML-документа в памяти и позволяет им работать с виртуальными ИСТОЧНИКами данных XML, которые предоставляют `XNode` , `XmlReader` или <xref:System.Xml.XPath.XPathNavigator> .</span><span class="sxs-lookup"><span data-stu-id="02a47-108">Use these abstractions instead of `XmlDocument`, `XmlNode`, or <xref:System.Xml.XPath.XPathDocument>, because this decouples the methods from specific implementations of an in-memory XML document and allows them to work with virtual XML data sources that expose `XNode`, `XmlReader`, or <xref:System.Xml.XPath.XPathNavigator>.</span></span>

 <span data-ttu-id="02a47-109">❌ НЕ подклассировать, `XmlDocument` Если необходимо создать тип, представляющий представление XML базовой объектной модели или источника данных.</span><span class="sxs-lookup"><span data-stu-id="02a47-109">❌ DO NOT subclass `XmlDocument` if you want to create a type representing an XML view of an underlying object model or data source.</span></span>

 <span data-ttu-id="02a47-110">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="02a47-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="02a47-111">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="02a47-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="02a47-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="02a47-112">See also</span></span>

- [<span data-ttu-id="02a47-113">Рекомендации по проектированию платформы</span><span class="sxs-lookup"><span data-stu-id="02a47-113">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="02a47-114">Рекомендации по использованию</span><span class="sxs-lookup"><span data-stu-id="02a47-114">Usage Guidelines</span></span>](usage-guidelines.md)
