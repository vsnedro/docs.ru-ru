---
title: Пробелы в XML-литералах
ms.date: 07/20/2015
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
ms.openlocfilehash: b3caf7ac052f3fed3fe5427da0cc96bbdd955ea6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84360479"
---
# <a name="white-space-in-xml-literals-visual-basic"></a><span data-ttu-id="d2dbc-102">Пробелы в XML-литералах (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d2dbc-102">White Space in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="d2dbc-103">Компилятор Visual Basic включает только значащие символы пробела из XML-литерала при создании [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объекта.</span><span class="sxs-lookup"><span data-stu-id="d2dbc-103">The Visual Basic compiler incorporates only the significant white space characters from an XML literal when it creates a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object.</span></span> <span data-ttu-id="d2dbc-104">Незначащие символы пробела не включаются.</span><span class="sxs-lookup"><span data-stu-id="d2dbc-104">The insignificant white space characters are not incorporated.</span></span>  
  
## <a name="significant-and-insignificant-white-space"></a><span data-ttu-id="d2dbc-105">Значительные и незначащие пробелы</span><span class="sxs-lookup"><span data-stu-id="d2dbc-105">Significant and Insignificant White Space</span></span>  
 <span data-ttu-id="d2dbc-106">Символы пробелов в XML-литералах являются значимыми только в трех областях:</span><span class="sxs-lookup"><span data-stu-id="d2dbc-106">White space characters in XML literals are significant in only three areas:</span></span>  
  
- <span data-ttu-id="d2dbc-107">Если они находятся в значении атрибута.</span><span class="sxs-lookup"><span data-stu-id="d2dbc-107">When they are in an attribute value.</span></span>  
  
- <span data-ttu-id="d2dbc-108">Если они являются частью текстового содержимого элемента, а текст также содержит другие символы.</span><span class="sxs-lookup"><span data-stu-id="d2dbc-108">When they are part of an element's text content and the text also contains other characters.</span></span>  
  
- <span data-ttu-id="d2dbc-109">Если они находятся в внедренном выражении для текстового содержимого элемента.</span><span class="sxs-lookup"><span data-stu-id="d2dbc-109">When they are in an embedded expression for an element's text content.</span></span>  
  
 <span data-ttu-id="d2dbc-110">В противном случае компилятор рассматривает символы пробела как незначащие и не включает в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объект для литерала.</span><span class="sxs-lookup"><span data-stu-id="d2dbc-110">Otherwise, the compiler treats white space characters as insignificant and does not include then in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object for the literal.</span></span>  
  
 <span data-ttu-id="d2dbc-111">Чтобы включить незначащие пробелы в XML-литерал, используйте внедренное выражение, содержащее строковый литерал с пробелом.</span><span class="sxs-lookup"><span data-stu-id="d2dbc-111">To include insignificant white space in an XML literal, use an embedded expression that contains a string literal with the white space.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d2dbc-112">Если `xml:space` атрибут отображается в литерале XML-элемента, Visual Basic компилятор включает атрибут в <xref:System.Xml.Linq.XElement> объект, но добавление этого атрибута не влияет на то, как компилятор обрабатывает пробелы.</span><span class="sxs-lookup"><span data-stu-id="d2dbc-112">If the `xml:space` attribute appears in an XML element literal, the Visual Basic compiler includes the attribute in the <xref:System.Xml.Linq.XElement> object, but adding this attribute does not change how the compiler treats white space.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="d2dbc-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="d2dbc-113">Examples</span></span>  
 <span data-ttu-id="d2dbc-114">В следующем примере содержатся два XML-элемента: OUTER и Inner.</span><span class="sxs-lookup"><span data-stu-id="d2dbc-114">The following example contains two XML elements, outer and inner.</span></span> <span data-ttu-id="d2dbc-115">Оба элемента содержат пробелы в текстовом содержимом.</span><span class="sxs-lookup"><span data-stu-id="d2dbc-115">Both elements contain white space in their text content.</span></span> <span data-ttu-id="d2dbc-116">Пробелы во внешнем элементе являются незначащими, так как содержат только пробелы и XML-элементы.</span><span class="sxs-lookup"><span data-stu-id="d2dbc-116">The white space in the outer element is insignificant because it contains only white space and an XML element.</span></span> <span data-ttu-id="d2dbc-117">Пробел во внутреннем элементе важен, так как он содержит пробелы и текст.</span><span class="sxs-lookup"><span data-stu-id="d2dbc-117">The white space in the inner element is significant because it contains white space and text.</span></span>  
  
 [!code-vb[VbXMLSamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#29)]  
  
 <span data-ttu-id="d2dbc-118">При запуске этот код отображает следующий текст.</span><span class="sxs-lookup"><span data-stu-id="d2dbc-118">When run, this code displays the following text.</span></span>  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d2dbc-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d2dbc-119">See also</span></span>

- [<span data-ttu-id="d2dbc-120">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d2dbc-120">Creating XML in Visual Basic</span></span>](creating-xml.md)
