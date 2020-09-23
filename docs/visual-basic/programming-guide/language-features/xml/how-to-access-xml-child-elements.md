---
title: Практическое руководство. Доступ к дочерним XML-элементам
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 6689eb36-c471-469f-a82d-099ab8197b25
ms.openlocfilehash: 9c33bec9b9ea865d570bab08f27227129867cce9
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058304"
---
# <a name="how-to-access-xml-child-elements-visual-basic"></a><span data-ttu-id="fac61-102">Практическое руководство. Доступ к дочерним XML-элементам (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fac61-102">How to: Access XML Child Elements (Visual Basic)</span></span>

<span data-ttu-id="fac61-103">В этом примере показано, как использовать свойство дочерней оси для доступа ко всем дочерним элементам XML с указанным именем в элементе XML.</span><span class="sxs-lookup"><span data-stu-id="fac61-103">This example shows how to use a child axis property to access all XML child elements that have a specified name in an XML element.</span></span> <span data-ttu-id="fac61-104">В частности, он использует <xref:System.Xml.Linq.XElement.Value%2A> свойство для получения значения первого элемента в коллекции, `name` возвращаемого свойством дочерней оси.</span><span class="sxs-lookup"><span data-stu-id="fac61-104">In particular, it uses the <xref:System.Xml.Linq.XElement.Value%2A> property to get the value of the first element in the collection that the `name` child axis property returns.</span></span> <span data-ttu-id="fac61-105">`name`Свойство дочерней оси получает все дочерние элементы с именем `phone` в `contact` объекте.</span><span class="sxs-lookup"><span data-stu-id="fac61-105">The `name` child axis property gets all child elements named `phone` in the `contact` object.</span></span> <span data-ttu-id="fac61-106">В этом примере также используется `phone` свойство дочерней оси для доступа ко всем дочерним элементам с именем `phone` , содержащимся в `contact` объекте.</span><span class="sxs-lookup"><span data-stu-id="fac61-106">This example also uses the `phone` child axis property to access all child elements named `phone` that are contained in the `contact` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fac61-107">Пример</span><span class="sxs-lookup"><span data-stu-id="fac61-107">Example</span></span>  

 [!code-vb[VbXMLSamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#10)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="fac61-108">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="fac61-108">Compile the code</span></span>  

 <span data-ttu-id="fac61-109">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="fac61-109">This example requires:</span></span>  
  
- <span data-ttu-id="fac61-110">ссылка на пространство имен <xref:System.Xml.Linq>.</span><span class="sxs-lookup"><span data-stu-id="fac61-110">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fac61-111">См. также</span><span class="sxs-lookup"><span data-stu-id="fac61-111">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>
- [<span data-ttu-id="fac61-112">XML Child Axis Property</span><span class="sxs-lookup"><span data-stu-id="fac61-112">XML Child Axis Property</span></span>](../../../language-reference/xml-axis/xml-child-axis-property.md)
- [<span data-ttu-id="fac61-113">Свойство значения XML</span><span class="sxs-lookup"><span data-stu-id="fac61-113">XML Value Property</span></span>](../../../language-reference/xml-axis/xml-value-property.md)
- [<span data-ttu-id="fac61-114">Доступ к XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fac61-114">Accessing XML in Visual Basic</span></span>](accessing-xml.md)
- [<span data-ttu-id="fac61-115">XML</span><span class="sxs-lookup"><span data-stu-id="fac61-115">XML</span></span>](index.md)
