---
title: Практическое руководство. Создание XML-литералов
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], creating
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
ms.openlocfilehash: c7ad8d684dde31550b6e1b74c098d152b227f6c1
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058226"
---
# <a name="how-to-create-xml-literals-visual-basic"></a><span data-ttu-id="c5226-102">Практическое руководство. Создание XML-литералов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c5226-102">How to: Create XML Literals (Visual Basic)</span></span>

<span data-ttu-id="c5226-103">XML-документ, фрагмент или элемент можно создать непосредственно в коде с помощью XML-литерала.</span><span class="sxs-lookup"><span data-stu-id="c5226-103">You can create an XML document, fragment, or element directly in code by using an XML literal.</span></span> <span data-ttu-id="c5226-104">В примерах этого раздела показано, как создать XML-элемент с тремя дочерними элементами и как создать XML-документ.</span><span class="sxs-lookup"><span data-stu-id="c5226-104">The examples in this topic demonstrate how to create an XML element that has three child elements, and how to create an XML document.</span></span>  
  
 <span data-ttu-id="c5226-105">Вы также можете использовать [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] API для создания [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объектов.</span><span class="sxs-lookup"><span data-stu-id="c5226-105">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="c5226-106">Для получения дополнительной информации см. <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="c5226-106">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
### <a name="to-create-an-xml-element"></a><span data-ttu-id="c5226-107">Создание XML-элемента</span><span class="sxs-lookup"><span data-stu-id="c5226-107">To create an XML element</span></span>  
  
- <span data-ttu-id="c5226-108">Создайте встроенный XML-файл с помощью синтаксиса XML-литерала, который совпадает с фактическим синтаксисом XML.</span><span class="sxs-lookup"><span data-stu-id="c5226-108">Create the XML inline by using the XML literal syntax, which is the same as the actual XML syntax.</span></span>  
  
     [!code-vb[VbXMLSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
     <span data-ttu-id="c5226-109">Выполните код.</span><span class="sxs-lookup"><span data-stu-id="c5226-109">Run the code.</span></span> <span data-ttu-id="c5226-110">Выходные данные этого кода:</span><span class="sxs-lookup"><span data-stu-id="c5226-110">The output of this code is:</span></span>  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### <a name="to-create-an-xml-document"></a><span data-ttu-id="c5226-111">Создание XML-документа</span><span class="sxs-lookup"><span data-stu-id="c5226-111">To create an XML document</span></span>  
  
- <span data-ttu-id="c5226-112">Создайте встроенный XML-документ.</span><span class="sxs-lookup"><span data-stu-id="c5226-112">Create the XML document inline.</span></span> <span data-ttu-id="c5226-113">Следующий код создает XML-документ с литеральным синтаксисом, объявлением XML, инструкцией по обработке, комментарием и элементом, содержащим другой элемент.</span><span class="sxs-lookup"><span data-stu-id="c5226-113">The following code creates an XML document that has literal syntax, an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
     [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
     <span data-ttu-id="c5226-114">Выполните код.</span><span class="sxs-lookup"><span data-stu-id="c5226-114">Run the code.</span></span> <span data-ttu-id="c5226-115">Выходные данные этого кода:</span><span class="sxs-lookup"><span data-stu-id="c5226-115">The output of this code is:</span></span>  
  
     `<?xml-stylesheet type="text/xsl" href="show_book.xsl"?>`  
  
     `<!-- Tests that the application works. -->`  
  
     `<books>`  
  
     `<book/>`  
  
     `</books>`  
  
## <a name="see-also"></a><span data-ttu-id="c5226-116">См. также</span><span class="sxs-lookup"><span data-stu-id="c5226-116">See also</span></span>

- [<span data-ttu-id="c5226-117">XML</span><span class="sxs-lookup"><span data-stu-id="c5226-117">XML</span></span>](index.md)
- [<span data-ttu-id="c5226-118">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c5226-118">Creating XML in Visual Basic</span></span>](creating-xml.md)
- [<span data-ttu-id="c5226-119">XML-литерал элемента</span><span class="sxs-lookup"><span data-stu-id="c5226-119">XML Element Literal</span></span>](../../../language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="c5226-120">XML-литерал документа</span><span class="sxs-lookup"><span data-stu-id="c5226-120">XML Document Literal</span></span>](../../../language-reference/xml-literals/xml-document-literal.md)
