---
title: Практическое руководство. Создание XML-литералов
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], creating
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
ms.openlocfilehash: 61b138c0851c747ed30eedc10cb882cc3b03c4d4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392614"
---
# <a name="how-to-create-xml-literals-visual-basic"></a><span data-ttu-id="4a24d-102">Практическое руководство. Создание XML-литералов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4a24d-102">How to: Create XML Literals (Visual Basic)</span></span>
<span data-ttu-id="4a24d-103">XML-документ, фрагмент или элемент можно создать непосредственно в коде с помощью XML-литерала.</span><span class="sxs-lookup"><span data-stu-id="4a24d-103">You can create an XML document, fragment, or element directly in code by using an XML literal.</span></span> <span data-ttu-id="4a24d-104">В примерах этого раздела показано, как создать XML-элемент с тремя дочерними элементами и как создать XML-документ.</span><span class="sxs-lookup"><span data-stu-id="4a24d-104">The examples in this topic demonstrate how to create an XML element that has three child elements, and how to create an XML document.</span></span>  
  
 <span data-ttu-id="4a24d-105">Вы также можете использовать [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] API для создания [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объектов.</span><span class="sxs-lookup"><span data-stu-id="4a24d-105">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="4a24d-106">Дополнительные сведения см. в разделе <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="4a24d-106">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
### <a name="to-create-an-xml-element"></a><span data-ttu-id="4a24d-107">Создание XML-элемента</span><span class="sxs-lookup"><span data-stu-id="4a24d-107">To create an XML element</span></span>  
  
- <span data-ttu-id="4a24d-108">Создайте встроенный XML-файл с помощью синтаксиса XML-литерала, который совпадает с фактическим синтаксисом XML.</span><span class="sxs-lookup"><span data-stu-id="4a24d-108">Create the XML inline by using the XML literal syntax, which is the same as the actual XML syntax.</span></span>  
  
     [!code-vb[VbXMLSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
     <span data-ttu-id="4a24d-109">Выполните код.</span><span class="sxs-lookup"><span data-stu-id="4a24d-109">Run the code.</span></span> <span data-ttu-id="4a24d-110">Выходные данные этого кода:</span><span class="sxs-lookup"><span data-stu-id="4a24d-110">The output of this code is:</span></span>  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### <a name="to-create-an-xml-document"></a><span data-ttu-id="4a24d-111">Создание XML-документа</span><span class="sxs-lookup"><span data-stu-id="4a24d-111">To create an XML document</span></span>  
  
- <span data-ttu-id="4a24d-112">Создайте встроенный XML-документ.</span><span class="sxs-lookup"><span data-stu-id="4a24d-112">Create the XML document inline.</span></span> <span data-ttu-id="4a24d-113">Следующий код создает XML-документ с литеральным синтаксисом, объявлением XML, инструкцией по обработке, комментарием и элементом, содержащим другой элемент.</span><span class="sxs-lookup"><span data-stu-id="4a24d-113">The following code creates an XML document that has literal syntax, an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
     [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
     <span data-ttu-id="4a24d-114">Выполните код.</span><span class="sxs-lookup"><span data-stu-id="4a24d-114">Run the code.</span></span> <span data-ttu-id="4a24d-115">Выходные данные этого кода:</span><span class="sxs-lookup"><span data-stu-id="4a24d-115">The output of this code is:</span></span>  
  
     `<?xml-stylesheet type="text/xsl" href="show_book.xsl"?>`  
  
     `<!-- Tests that the application works. -->`  
  
     `<books>`  
  
     `<book/>`  
  
     `</books>`  
  
## <a name="see-also"></a><span data-ttu-id="4a24d-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4a24d-116">See also</span></span>

- [<span data-ttu-id="4a24d-117">XML</span><span class="sxs-lookup"><span data-stu-id="4a24d-117">XML</span></span>](index.md)
- [<span data-ttu-id="4a24d-118">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4a24d-118">Creating XML in Visual Basic</span></span>](creating-xml.md)
- [<span data-ttu-id="4a24d-119">XML-литерал элемента</span><span class="sxs-lookup"><span data-stu-id="4a24d-119">XML Element Literal</span></span>](../../../language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="4a24d-120">XML-литерал документа</span><span class="sxs-lookup"><span data-stu-id="4a24d-120">XML Document Literal</span></span>](../../../language-reference/xml-literals/xml-document-literal.md)
