---
title: Практическое руководство. Преобразование фрагмента узла
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73a6c582-b9d7-4fa7-9a05-6d931e1f3de8
ms.openlocfilehash: 5c69a35497feced92a05e124307d3be584ab86b7
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829444"
---
# <a name="how-to-transform-a-node-fragment"></a><span data-ttu-id="f5bca-102">Практическое руководство. Преобразование фрагмента узла</span><span class="sxs-lookup"><span data-stu-id="f5bca-102">How to: Transform a Node Fragment</span></span>
<span data-ttu-id="f5bca-103">Во время преобразования данных, содержащихся в объекте <xref:System.Xml.XmlDocument> или <xref:System.Xml.XPath.XPathDocument>, преобразования XSLT применяются к документу в целом.</span><span class="sxs-lookup"><span data-stu-id="f5bca-103">When you transform data contained in an <xref:System.Xml.XmlDocument> or <xref:System.Xml.XPath.XPathDocument> object the XSLT transformations apply to a document as a whole.</span></span> <span data-ttu-id="f5bca-104">Иными словами, если передать узел, отличный от корневого узла документа, это не помешает процессу преобразования обратиться ко всем узлам загружаемого документа.</span><span class="sxs-lookup"><span data-stu-id="f5bca-104">In other words, if you pass in a node other than the document root node, this does not prevent the transformation process from accessing all nodes in the loaded document.</span></span> <span data-ttu-id="f5bca-105">Чтобы преобразовать фрагмент узла, необходимо создать отдельный объект, содержащий только этот фрагмент, и передать его методу <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>.</span><span class="sxs-lookup"><span data-stu-id="f5bca-105">To transform a node fragment, you must create a separate object containing just the node fragment, and pass that object to the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="f5bca-106">Процедуры</span><span class="sxs-lookup"><span data-stu-id="f5bca-106">Procedures</span></span>  
  
#### <a name="to-transform-a-node-fragment"></a><span data-ttu-id="f5bca-107">Преобразование фрагмента узла</span><span class="sxs-lookup"><span data-stu-id="f5bca-107">To transform a node fragment</span></span>  
  
1. <span data-ttu-id="f5bca-108">Создайте объект, содержащий исходный документ.</span><span class="sxs-lookup"><span data-stu-id="f5bca-108">Create an object containing the source document.</span></span>  
  
2. <span data-ttu-id="f5bca-109">Определите расположение фрагмента узла для преобразования.</span><span class="sxs-lookup"><span data-stu-id="f5bca-109">Locate the node fragment you wish to transform.</span></span>  
  
3. <span data-ttu-id="f5bca-110">Создайте отдельный объект, содержащий только фрагмент узла.</span><span class="sxs-lookup"><span data-stu-id="f5bca-110">Create separate object with just the node fragment.</span></span>  
  
4. <span data-ttu-id="f5bca-111">Передайте фрагмент узла методу <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>.</span><span class="sxs-lookup"><span data-stu-id="f5bca-111">Pass the node fragment to the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5bca-112">Пример</span><span class="sxs-lookup"><span data-stu-id="f5bca-112">Example</span></span>  
 <span data-ttu-id="f5bca-113">В следующем примере преобразуется фрагмент узла, а результаты выводятся на консоль.</span><span class="sxs-lookup"><span data-stu-id="f5bca-113">The following example transforms a node fragment and outputs the results to the console.</span></span>  
  
 [!code-csharp[XSLT_NodeFrag#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XSLT_NodeFrag/CS/xslt_frag.cs#1)]
 [!code-vb[XSLT_NodeFrag#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XSLT_NodeFrag/VB/xslt_frag.vb#1)]  
  
### <a name="input"></a><span data-ttu-id="f5bca-114">Входные данные</span><span class="sxs-lookup"><span data-stu-id="f5bca-114">Input</span></span>  
  
##### <a name="booksxml"></a><span data-ttu-id="f5bca-115">books.xml</span><span class="sxs-lookup"><span data-stu-id="f5bca-115">books.xml</span></span>  
 [!code-xml[XML_Core_Files#1](../../../../samples/snippets/xml/VS_Snippets_Data/XML_Core_Files/XML/books.xml#1)]  
  
##### <a name="singlexsl"></a><span data-ttu-id="f5bca-116">single.xsl</span><span class="sxs-lookup"><span data-stu-id="f5bca-116">single.xsl</span></span>  
 [!code-xml[XSLT_NodeFrag#2](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_NodeFrag/XML/single.xsl#2)]  
  
### <a name="output"></a><span data-ttu-id="f5bca-117">Вывод</span><span class="sxs-lookup"><span data-stu-id="f5bca-117">Output</span></span>  
 <span data-ttu-id="f5bca-118">Заголовок книги — The Confidence Man.</span><span class="sxs-lookup"><span data-stu-id="f5bca-118">Book title is The Confidence Man.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5bca-119">См. также</span><span class="sxs-lookup"><span data-stu-id="f5bca-119">See also</span></span>

- [<span data-ttu-id="f5bca-120">Использование класса XslCompiledTransform</span><span class="sxs-lookup"><span data-stu-id="f5bca-120">Using the XslCompiledTransform Class</span></span>](using-the-xslcompiledtransform-class.md)
