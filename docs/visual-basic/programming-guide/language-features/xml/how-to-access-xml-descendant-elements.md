---
title: Практическое руководство. Доступ к элементам-потомкам XML
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: dcbaf1f9022d86f40a90ef6a1e0033f627caeef2
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058213"
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a><span data-ttu-id="d4091-102">Практическое руководство. Доступ к производным XML элементам (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d4091-102">How to: Access XML Descendant Elements (Visual Basic)</span></span>

<span data-ttu-id="d4091-103">В этом примере показано, как использовать свойство оси потомков для доступа ко всем XML-элементам с указанным именем и содержащимся в XML-элементе.</span><span class="sxs-lookup"><span data-stu-id="d4091-103">This example shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under an XML element.</span></span> <span data-ttu-id="d4091-104">В частности, он использует `Value` свойство для получения значения первого элемента в коллекции, `name` возвращаемого свойством дочерней оси.</span><span class="sxs-lookup"><span data-stu-id="d4091-104">In particular, it uses the `Value` property to get the value of the first element in the collection that the `name` descendant axis property returns.</span></span> <span data-ttu-id="d4091-105">`name`Свойство дочерняя ось получает все элементы с именем `name` , содержащиеся в `contacts` объекте.</span><span class="sxs-lookup"><span data-stu-id="d4091-105">The `name` descendant axis property gets all elements named `name` that are contained in the `contacts` object.</span></span> <span data-ttu-id="d4091-106">В этом примере также используется `phone` свойство оси потомков для доступа ко всем потомкам `phone` , имена которых содержатся в `contacts` объекте.</span><span class="sxs-lookup"><span data-stu-id="d4091-106">This example also uses the `phone` descendant axis property to access all descendants named `phone` that are contained in the `contacts` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4091-107">Пример</span><span class="sxs-lookup"><span data-stu-id="d4091-107">Example</span></span>  

 [!code-vb[VbXMLSamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#31)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="d4091-108">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="d4091-108">Compile the code</span></span>  

 <span data-ttu-id="d4091-109">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="d4091-109">This example requires:</span></span>  
  
- <span data-ttu-id="d4091-110">ссылка на пространство имен <xref:System.Xml.Linq>.</span><span class="sxs-lookup"><span data-stu-id="d4091-110">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4091-111">См. также</span><span class="sxs-lookup"><span data-stu-id="d4091-111">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>
- [<span data-ttu-id="d4091-112">XML Descendant Axis Property</span><span class="sxs-lookup"><span data-stu-id="d4091-112">XML Descendant Axis Property</span></span>](../../../language-reference/xml-axis/xml-descendant-axis-property.md)
- [<span data-ttu-id="d4091-113">Свойство значения XML</span><span class="sxs-lookup"><span data-stu-id="d4091-113">XML Value Property</span></span>](../../../language-reference/xml-axis/xml-value-property.md)
- [<span data-ttu-id="d4091-114">Доступ к XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d4091-114">Accessing XML in Visual Basic</span></span>](accessing-xml.md)
- [<span data-ttu-id="d4091-115">XML</span><span class="sxs-lookup"><span data-stu-id="d4091-115">XML</span></span>](index.md)
