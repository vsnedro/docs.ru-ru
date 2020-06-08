---
title: Ввод XmlDocument в XslTransform
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 97115892-410a-4657-ab47-1e14dfba73f8
ms.openlocfilehash: e990c8ca3bb2a7145157fcedd06da4ea769c6ad3
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290257"
---
# <a name="xmldocument-input-to-xsltransform"></a><span data-ttu-id="bebd4-102">Ввод XmlDocument в XslTransform</span><span class="sxs-lookup"><span data-stu-id="bebd4-102">XmlDocument Input to XslTransform</span></span>
<span data-ttu-id="bebd4-103">Класс <xref:System.Xml.XmlDocument> представляет возможности изменения XML-документа.</span><span class="sxs-lookup"><span data-stu-id="bebd4-103">The <xref:System.Xml.XmlDocument> class provides editing capabilities for an XML document.</span></span> <span data-ttu-id="bebd4-104">Если нужно изменить XML-документ перед передачей методу <xref:System.Xml.Xsl.XslTransform.Transform%2A>, загрузите XML-документ в объект <xref:System.Xml.XmlDocument>, измените его и отправьте в объект <xref:System.Xml.Xsl.XslTransform>.</span><span class="sxs-lookup"><span data-stu-id="bebd4-104">If the XML needs to be edited or modified before being sent to the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method, load the XML into an <xref:System.Xml.XmlDocument>, edit it, and send it in to the <xref:System.Xml.Xsl.XslTransform>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bebd4-105">Класс <xref:System.Xml.Xsl.XslTransform> явлется устаревшим в версии .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="bebd4-105">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the .NET Framework 2.0.</span></span> <span data-ttu-id="bebd4-106">Можно выполнять XSLT-преобразование, используя класс <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="bebd4-106">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="bebd4-107">См. дополнительные сведения об [использовании класса XslCompiledTransform](using-the-xslcompiledtransform-class.md) и [миграции из класса XslTransform](migrating-from-the-xsltransform-class.md).</span><span class="sxs-lookup"><span data-stu-id="bebd4-107">See [Using the XslCompiledTransform Class](using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="bebd4-108">Класс <xref:System.Xml.XmlDocument> реализует интерфейс <xref:System.Xml.XPath.IXPathNavigable>, поэтому документ можно передать в метод <xref:System.Xml.Xsl.XslTransform.Transform%2A> после изменения.</span><span class="sxs-lookup"><span data-stu-id="bebd4-108">The <xref:System.Xml.XmlDocument> implements the <xref:System.Xml.XPath.IXPathNavigable> interface, so the document can be passed to the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method after editing.</span></span>  
  
 <span data-ttu-id="bebd4-109">Из-за возможности изменения объекта <xref:System.Xml.XmlDocument> при использовании класса <xref:System.Xml.XmlDocument> в качестве входных данных преобразования быстродействие ниже, чем при использовании класса <xref:System.Xml.XPath.XPathDocument> для XSLT-преобразований, так как класс <xref:System.Xml.XPath.XPathDocument> оптимизирован для запросов XPath благодаря внутреннему хранению.</span><span class="sxs-lookup"><span data-stu-id="bebd4-109">Due to the editing capability of the <xref:System.Xml.XmlDocument>, using the <xref:System.Xml.XmlDocument> class as input to a transformation is slower than using an <xref:System.Xml.XPath.XPathDocument> for the Extensible Stylesheet Language for Transformations (XSLT) transformations, as the <xref:System.Xml.XPath.XPathDocument> is optimized for XML Path Language (XPath) queries due to the internal storage.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bebd4-110">Пример</span><span class="sxs-lookup"><span data-stu-id="bebd4-110">Example</span></span>  
 <span data-ttu-id="bebd4-111">В следующем примере кода показано, как можно предоставить объект <xref:System.Xml.XmlDocument> объекту <xref:System.Xml.Xsl.XslTransform> и передать вывод в объект <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="bebd4-111">The following code example shows how an <xref:System.Xml.XmlDocument> can be supplied to the <xref:System.Xml.Xsl.XslTransform>, with the output sent to an <xref:System.Xml.XmlReader>.</span></span>  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
doc.Load("books.xml")  
Dim trans As XslTransform = new XslTransform()  
trans.Load("book.xsl")  
Dim rdr As XmlReader = trans.Transform(doc, Nothing, Nothing)  
while (rdr.Read())  
end while  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.Load("books.xml");  
XslTransform trans = new XslTransform();  
trans.Load("book.xsl");  
XmlReader rdr = trans.Transform(doc, null, null);  
while (rdr.Read()) {}  
```  
  
## <a name="see-also"></a><span data-ttu-id="bebd4-112">См. также</span><span class="sxs-lookup"><span data-stu-id="bebd4-112">See also</span></span>

- <xref:System.Xml.XmlDocument>
- [<span data-ttu-id="bebd4-113">XSLT-преобразования с помощью класса XslTransform</span><span class="sxs-lookup"><span data-stu-id="bebd4-113">XSLT Transformations with the XslTransform Class</span></span>](xslt-transformations-with-the-xsltransform-class.md)
- [<span data-ttu-id="bebd4-114">Реализация классом XslTransform XSLT-процессора</span><span class="sxs-lookup"><span data-stu-id="bebd4-114">XslTransform Class Implements the XSLT Processor</span></span>](xsltransform-class-implements-the-xslt-processor.md)
- [<span data-ttu-id="bebd4-115">XPathNavigator в преобразованиях</span><span class="sxs-lookup"><span data-stu-id="bebd4-115">XPathNavigator in Transformations</span></span>](xpathnavigator-in-transformations.md)
- [<span data-ttu-id="bebd4-116">XPathNodeIterator в преобразованиях</span><span class="sxs-lookup"><span data-stu-id="bebd4-116">XPathNodeIterator in Transformations</span></span>](xpathnodeiterator-in-transformations.md)
- [<span data-ttu-id="bebd4-117">Ввод XPathDocument в XslTransform</span><span class="sxs-lookup"><span data-stu-id="bebd4-117">XPathDocument Input to XslTransform</span></span>](xpathdocument-input-to-xsltransform.md)
- [<span data-ttu-id="bebd4-118">Ввод XmlDataDocument в XslTransform</span><span class="sxs-lookup"><span data-stu-id="bebd4-118">XmlDataDocument Input to XslTransform</span></span>](xmldatadocument-input-to-xsltransform.md)
