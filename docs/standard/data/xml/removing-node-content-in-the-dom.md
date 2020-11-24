---
title: Удаление содержимого узла в DOM
ms.date: 03/30/2017
ms.assetid: 615d81a7-f44f-416c-a9ab-bfe03f85e6e4
ms.openlocfilehash: 7b33ebfea244dbe81879c61be3809adcb2a1f5d3
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828872"
---
# <a name="removing-node-content-in-the-dom"></a><span data-ttu-id="c3d00-102">Удаление содержимого узла в DOM</span><span class="sxs-lookup"><span data-stu-id="c3d00-102">Removing Node Content in the DOM</span></span>
<span data-ttu-id="c3d00-103">Для типов узлов, наследующих от <xref:System.Xml.XmlCharacterData>, являющихся типами узлов <xref:System.Xml.XmlComment>,<xref:System.Xml.XmlText>,<xref:System.Xml.XmlCDataSection>,<xref:System.Xml.XmlWhitespace> и <xref:System.Xml.XmlSignificantWhitespace>, можно удалить символы с помощью метода <xref:System.Xml.XmlCharacterData.DeleteData%2A>, который удаляет диапазон символов из узла.</span><span class="sxs-lookup"><span data-stu-id="c3d00-103">For node types that inherit from <xref:System.Xml.XmlCharacterData>, which are the <xref:System.Xml.XmlComment>, <xref:System.Xml.XmlText>, <xref:System.Xml.XmlCDataSection>, <xref:System.Xml.XmlWhitespace>, and <xref:System.Xml.XmlSignificantWhitespace> node types, you can remove characters using the <xref:System.Xml.XmlCharacterData.DeleteData%2A> method, which removes a range of characters from the node.</span></span> <span data-ttu-id="c3d00-104">Если требуется полностью удалить содержимое, нужно удалить узел, содержащий содержимое.</span><span class="sxs-lookup"><span data-stu-id="c3d00-104">If you want to remove content completely, you remove the node that contains the content.</span></span> <span data-ttu-id="c3d00-105">Если требуется сохранить узел, содержимое которого неверно, нужно изменить содержимое.</span><span class="sxs-lookup"><span data-stu-id="c3d00-105">If you want to keep the node, but the content is incorrect, then modify the content.</span></span> <span data-ttu-id="c3d00-106">См. дополнительные сведения об [изменении узлов, содержимого и значений в документе XML](modifying-nodes-content-and-values-in-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="c3d00-106">For information on modifying the content of a node, see [Modifying Nodes, Content, and Values in an XML Document](modifying-nodes-content-and-values-in-an-xml-document.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3d00-107">См. также</span><span class="sxs-lookup"><span data-stu-id="c3d00-107">See also</span></span>

- [<span data-ttu-id="c3d00-108">Модель объектов документов XML (DOM)</span><span class="sxs-lookup"><span data-stu-id="c3d00-108">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
