---
title: Общие сведения о классе XDocument (C#)
description: Класс XDocument в C# содержит сведения, необходимые для использования допустимого XML-документа, включая XML-декларацию, инструкции по обработке и комментарии.
ms.date: 07/20/2015
ms.assetid: 63305603-ab54-49fc-84e4-f76eecc59549
ms.openlocfilehash: 6d522cef25e99e4a5ea54e644855c8dfa7a05f4a
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302195"
---
# <a name="xdocument-class-overview-c"></a><span data-ttu-id="ad3e8-103">Общие сведения о классе XDocument (C#)</span><span class="sxs-lookup"><span data-stu-id="ad3e8-103">XDocument Class Overview (C#)</span></span>
<span data-ttu-id="ad3e8-104">В этом разделе представлен класс <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-104">This topic introduces the <xref:System.Xml.Linq.XDocument> class.</span></span>  
  
## <a name="overview-of-the-xdocument-class"></a><span data-ttu-id="ad3e8-105">Общие сведения о классе XDocument</span><span class="sxs-lookup"><span data-stu-id="ad3e8-105">Overview of the XDocument class</span></span>  
 <span data-ttu-id="ad3e8-106">Класс <xref:System.Xml.Linq.XDocument> содержит сведения, необходимые для допустимого XML-документа.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-106">The <xref:System.Xml.Linq.XDocument> class contains the information necessary for a valid XML document.</span></span> <span data-ttu-id="ad3e8-107">К ним относятся XML-декларация, инструкции по обработке и комментарии.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-107">This includes an XML declaration, processing instructions, and comments.</span></span>  
  
 <span data-ttu-id="ad3e8-108">Отметим, что, если требуются только конкретные функции, обеспечиваемые классом <xref:System.Xml.Linq.XDocument>, необходимо создавать только объекты <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-108">Note that you only have to create <xref:System.Xml.Linq.XDocument> objects if you require the specific functionality provided by the <xref:System.Xml.Linq.XDocument> class.</span></span> <span data-ttu-id="ad3e8-109">Во многих случаях пользователь может работать непосредственно с <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-109">In many circumstances, you can work directly with <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="ad3e8-110">Непосредственная работа с <xref:System.Xml.Linq.XElement> реализует более простую модель программирования.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-110">Working directly with <xref:System.Xml.Linq.XElement> is a simpler programming model.</span></span>  
  
 <span data-ttu-id="ad3e8-111">Интерфейс <xref:System.Xml.Linq.XDocument> является производным от интерфейса <xref:System.Xml.Linq.XContainer>.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-111"><xref:System.Xml.Linq.XDocument> derives from <xref:System.Xml.Linq.XContainer>.</span></span> <span data-ttu-id="ad3e8-112">Поэтому он может содержать дочерние узлы.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-112">Therefore, it can contain child nodes.</span></span> <span data-ttu-id="ad3e8-113">Однако объекты <xref:System.Xml.Linq.XDocument> могут иметь только по одному дочернему узлу <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-113">However, <xref:System.Xml.Linq.XDocument> objects can have only one child <xref:System.Xml.Linq.XElement> node.</span></span> <span data-ttu-id="ad3e8-114">Это обстоятельство отражает стандарт XML, согласно которому в XML-документе может содержаться лишь один корневой элемент.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-114">This reflects the XML standard that there can be only one root element in an XML document.</span></span>  
  
## <a name="components-of-xdocument"></a><span data-ttu-id="ad3e8-115">Компоненты XDocument</span><span class="sxs-lookup"><span data-stu-id="ad3e8-115">Components of XDocument</span></span>  
 <span data-ttu-id="ad3e8-116">Документ <xref:System.Xml.Linq.XDocument> может включать в себя следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="ad3e8-116">An <xref:System.Xml.Linq.XDocument> can contain the following elements:</span></span>  
  
- <span data-ttu-id="ad3e8-117">Один объект <xref:System.Xml.Linq.XDeclaration>.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-117">One <xref:System.Xml.Linq.XDeclaration> object.</span></span> <span data-ttu-id="ad3e8-118"><xref:System.Xml.Linq.XDeclaration> позволяет указать соответствующие части XML-объявления: версию XML, кодировку документа, а также то, является ли этот XML-документ изолированным.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-118"><xref:System.Xml.Linq.XDeclaration> enables you to specify the pertinent parts of an XML declaration: the XML version, the encoding of the document, and whether the XML document is stand-alone.</span></span>  
  
- <span data-ttu-id="ad3e8-119">Один объект <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-119">One <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="ad3e8-120">Это корневой узел XML-документа.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-120">This is the root node of the XML document.</span></span>  
  
- <span data-ttu-id="ad3e8-121">Любое количество объектов <xref:System.Xml.Linq.XProcessingInstruction>.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-121">Any number of <xref:System.Xml.Linq.XProcessingInstruction> objects.</span></span> <span data-ttu-id="ad3e8-122">Инструкция по обработке передает сведения в приложение, обрабатывающее XML-код.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-122">A processing instruction communicates information to an application that processes the XML.</span></span>  
  
- <span data-ttu-id="ad3e8-123">Любое количество объектов <xref:System.Xml.Linq.XComment>.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-123">Any number of <xref:System.Xml.Linq.XComment> objects.</span></span> <span data-ttu-id="ad3e8-124">Комментарии и корневой элемент находятся на одном уровне.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-124">The comments will be siblings to the root element.</span></span> <span data-ttu-id="ad3e8-125">Объект <xref:System.Xml.Linq.XComment> не может быть первым аргументом в списке, так как XML-документ не может начинаться с комментария.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-125">The <xref:System.Xml.Linq.XComment> object cannot be the first argument in the list, because it is not valid for an XML document to start with a comment.</span></span>  
  
- <span data-ttu-id="ad3e8-126">Один тип документа <xref:System.Xml.Linq.XDocumentType> для DTD.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-126">One <xref:System.Xml.Linq.XDocumentType> for the DTD.</span></span>  
  
 <span data-ttu-id="ad3e8-127">При сериализации документа <xref:System.Xml.Linq.XDocument>, даже если значением декларации `XDocument.Declaration` является `null`, выходные данные будут иметь XML-декларацию, если для свойства `Writer.Settings.OmitXmlDeclaration` автор указал значение `false` (применяется по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="ad3e8-127">When you serialize an <xref:System.Xml.Linq.XDocument>, even if `XDocument.Declaration` is `null`, the output will have an XML declaration if the writer has `Writer.Settings.OmitXmlDeclaration` set to `false` (the default).</span></span>  
  
 <span data-ttu-id="ad3e8-128">По умолчанию [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] указывает для версии значение «1.0», а для кодировки значение «utf-8».</span><span class="sxs-lookup"><span data-stu-id="ad3e8-128">By default, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] sets the version to "1.0", and sets the encoding to "utf-8".</span></span>  
  
## <a name="using-xelement-without-xdocument"></a><span data-ttu-id="ad3e8-129">Использование XElement без XDocument</span><span class="sxs-lookup"><span data-stu-id="ad3e8-129">Using XElement without XDocument</span></span>  
 <span data-ttu-id="ad3e8-130">Как уже отмечалось, класс <xref:System.Xml.Linq.XElement> является основным классом интерфейса программирования [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad3e8-130">As previously mentioned, the <xref:System.Xml.Linq.XElement> class is the main class in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] programming interface.</span></span> <span data-ttu-id="ad3e8-131">Во многих случаях приложение не требует создания документа.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-131">In many cases, your application will not require that you create a document.</span></span> <span data-ttu-id="ad3e8-132">Класс <xref:System.Xml.Linq.XElement> позволяет создавать XML-дерево, добавлять к нему другие XML-деревья, изменять XML-дерево и сохранять его.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-132">By using the <xref:System.Xml.Linq.XElement> class, you can create an XML tree, add other XML trees to it, modify the XML tree, and save it.</span></span>  
  
## <a name="using-xdocument"></a><span data-ttu-id="ad3e8-133">Использование XDocument</span><span class="sxs-lookup"><span data-stu-id="ad3e8-133">Using XDocument</span></span>  
 <span data-ttu-id="ad3e8-134">При создании объектов <xref:System.Xml.Linq.XDocument> используется функциональное построение, так же как и при создании объектов <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-134">To construct an <xref:System.Xml.Linq.XDocument>, use functional construction, just like you do to construct <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="ad3e8-135">Следующий фрагмент кода создает объект <xref:System.Xml.Linq.XDocument> и ассоциированные с ним вложенные объекты.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-135">The following code creates an <xref:System.Xml.Linq.XDocument> object and its associated contained objects.</span></span>  
  
```csharp  
XDocument d = new XDocument(  
    new XComment("This is a comment."),  
    new XProcessingInstruction("xml-stylesheet",  
        "href='mystyle.css' title='Compact' type='text/css'"),  
    new XElement("Pubs",  
        new XElement("Book",  
            new XElement("Title", "Artifacts of Roman Civilization"),  
            new XElement("Author", "Moreno, Jordao")  
        ),  
        new XElement("Book",  
            new XElement("Title", "Midieval Tools and Implements"),  
            new XElement("Author", "Gazit, Inbar")  
        )  
    ),  
    new XComment("This is another comment.")  
);  
d.Declaration = new XDeclaration("1.0", "utf-8", "true");  
Console.WriteLine(d);  
  
d.Save("test.xml");  
```  
  
 <span data-ttu-id="ad3e8-136">В результате анализа файла test.xml получается следующий выход:</span><span class="sxs-lookup"><span data-stu-id="ad3e8-136">When you examine the file test.xml, you get the following output:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<!--This is a comment.-->  
<?xml-stylesheet href='mystyle.css' title='Compact' type='text/css'?>  
<Pubs>  
  <Book>  
    <Title>Artifacts of Roman Civilization</Title>  
    <Author>Moreno, Jordao</Author>  
  </Book>  
  <Book>  
    <Title>Midieval Tools and Implements</Title>  
    <Author>Gazit, Inbar</Author>  
  </Book>  
</Pubs>  
<!--This is another comment.-->  
```  
  
## <a name="see-also"></a><span data-ttu-id="ad3e8-137">См. также</span><span class="sxs-lookup"><span data-stu-id="ad3e8-137">See also</span></span>

- [<span data-ttu-id="ad3e8-138">Общие сведения о программировании LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="ad3e8-138">LINQ to XML Programming Overview (C#)</span></span>](./linq-to-xml-overview.md)
