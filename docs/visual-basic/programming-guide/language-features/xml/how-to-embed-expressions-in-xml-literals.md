---
title: Практическое руководство. Внедрение выражений в XML-литералы
ms.date: 07/20/2015
helpviewer_keywords:
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
ms.openlocfilehash: 5ce1386e6a1ff8ffce296f5cea694499633eb011
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071213"
---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a><span data-ttu-id="6c51b-102">Практическое руководство. Внедрение выражений в XML-литералы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6c51b-102">How to: Embed Expressions in XML Literals (Visual Basic)</span></span>

<span data-ttu-id="6c51b-103">Литералы XML можно объединять с внедренными выражениями для создания XML-документа, фрагмента или элемента, содержащего содержимое, созданное во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="6c51b-103">You can combine XML literals with embedded expressions to create an XML document, fragment, or element that contains content created at run time.</span></span> <span data-ttu-id="6c51b-104">В следующих примерах показано, как использовать внедренные выражения для заполнения содержимого, атрибутов и имен элементов во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="6c51b-104">The following examples demonstrate how to use embedded expressions to populate element content, attributes, and element names at run time.</span></span>  
  
 <span data-ttu-id="6c51b-105">Синтаксис для внедренного выражения — это тот `<%=` `exp` `%>` же синтаксис, который используется ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="6c51b-105">The syntax for an embedded expression is `<%=` `exp` `%>`, which is the same syntax that ASP.NET uses.</span></span> <span data-ttu-id="6c51b-106">Дополнительные сведения см. [в разделе внедренные выражения в XML](embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="6c51b-106">For more information, see [Embedded Expressions in XML](embedded-expressions-in-xml.md).</span></span>  
  
 <span data-ttu-id="6c51b-107">Вы также можете использовать [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] API для создания [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объектов.</span><span class="sxs-lookup"><span data-stu-id="6c51b-107">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="6c51b-108">Для получения дополнительной информации см. <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="6c51b-108">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="6c51b-109">Процедуры</span><span class="sxs-lookup"><span data-stu-id="6c51b-109">Procedures</span></span>  
  
#### <a name="to-insert-text-as-element-content"></a><span data-ttu-id="6c51b-110">Вставка текста в качестве содержимого элемента</span><span class="sxs-lookup"><span data-stu-id="6c51b-110">To insert text as element content</span></span>  
  
- <span data-ttu-id="6c51b-111">В следующем примере показано, как вставить текст, содержащийся в переменной, `contactName` между открывающим и закрывающим элементами Name.</span><span class="sxs-lookup"><span data-stu-id="6c51b-111">The following example shows how to insert the text that is contained in the `contactName` variable between the opening and closing name elements.</span></span>  
  
     [!code-vb[VbXMLSamples#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#39)]  
  
     <span data-ttu-id="6c51b-112">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="6c51b-112">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a><span data-ttu-id="6c51b-113">Вставка текста в качестве значения атрибута</span><span class="sxs-lookup"><span data-stu-id="6c51b-113">To insert text as an attribute value</span></span>  
  
- <span data-ttu-id="6c51b-114">В следующем примере показано, как вставить текст, содержащийся в переменной, в `phoneType` качестве значения `type` атрибута.</span><span class="sxs-lookup"><span data-stu-id="6c51b-114">The following example shows how to insert the text that is contained in the `phoneType` variable as the value of the `type` attribute.</span></span>  
  
     [!code-vb[VbXMLSamples#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#40)]  
  
     <span data-ttu-id="6c51b-115">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="6c51b-115">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a><span data-ttu-id="6c51b-116">Вставка текста для имени элемента</span><span class="sxs-lookup"><span data-stu-id="6c51b-116">To insert text for an element name</span></span>  
  
- <span data-ttu-id="6c51b-117">В следующем примере показано, как вставить текст, содержащийся в переменной, в `elementName` качестве имени элемента.</span><span class="sxs-lookup"><span data-stu-id="6c51b-117">The following example shows how to insert the text that is contained in the `elementName` variable as the name of an element.</span></span>  
  
     <span data-ttu-id="6c51b-118">При создании элементов с помощью этого метода их необходимо закрыть с помощью \</> тега.</span><span class="sxs-lookup"><span data-stu-id="6c51b-118">When creating elements by using this technique, you must close them with the \</> tag.</span></span>  
  
     [!code-vb[VbXMLSamples#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#41)]  
  
     <span data-ttu-id="6c51b-119">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="6c51b-119">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6c51b-120">См. также</span><span class="sxs-lookup"><span data-stu-id="6c51b-120">See also</span></span>

- [<span data-ttu-id="6c51b-121">Практическое руководство. Создание XML-литералов</span><span class="sxs-lookup"><span data-stu-id="6c51b-121">How to: Create XML Literals</span></span>](how-to-create-xml-literals.md)
- [<span data-ttu-id="6c51b-122">Встроенные выражения в XML</span><span class="sxs-lookup"><span data-stu-id="6c51b-122">Embedded Expressions in XML</span></span>](embedded-expressions-in-xml.md)
- [<span data-ttu-id="6c51b-123">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6c51b-123">Creating XML in Visual Basic</span></span>](creating-xml.md)
- [<span data-ttu-id="6c51b-124">XML</span><span class="sxs-lookup"><span data-stu-id="6c51b-124">XML</span></span>](index.md)
