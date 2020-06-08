---
title: Динамические обновления объектов NodeList и NamedNodeMap
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 76c511fd-6704-4ca4-8078-860a68d898ad
ms.openlocfilehash: 0199f24e9ef8dd28f91976edd50f78399dc893ef
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84292089"
---
# <a name="dynamic-updates-to-nodelists-and-namednodemaps"></a><span data-ttu-id="285ca-102">Динамические обновления объектов NodeList и NamedNodeMap</span><span class="sxs-lookup"><span data-stu-id="285ca-102">Dynamic Updates to NodeLists and NamedNodeMaps</span></span>
<span data-ttu-id="285ca-103">Так как объекты **XmlNodeList** и **XmlNamedNodeMap** содержат набор узлов, но XML-документ загружается в память и изменяется, консорциум W3C требует, чтобы такие объекты, содержащие наборы узлов, были динамическими.</span><span class="sxs-lookup"><span data-stu-id="285ca-103">Because the **XmlNodeList** and the **XmlNamedNodeMap** contain a set of nodes, yet the XML document is loaded into memory and is being modified, the World Wide Web Consortium (W3C) states that these objects that contain sets of nodes need to be dynamic.</span></span> <span data-ttu-id="285ca-104">Это значит, что изменение базового документа должно вызывать изменение этих двух объектов.</span><span class="sxs-lookup"><span data-stu-id="285ca-104">That is, if the underlying document changes, then the data in these two objects should change also.</span></span> <span data-ttu-id="285ca-105">Таким образом, если у вас есть объект **XmlNodeList**, содержащий все дочерние элементы некоторого элемента (например, элемента X), и затем в документ добавляется дополнительный элемент Q, дочерний относительно элемента X, то в коллекцию объекта **XmlNodeList** также должен быть добавлен новый элемент Q.</span><span class="sxs-lookup"><span data-stu-id="285ca-105">Therefore, if you have an **XmlNodeList** that contains all the child elements of a particular element (for example, element X), then you add an additional element, element Q, to the document under element X. The **XmlNodeList** should also have that new element Q added to its collection.</span></span> <span data-ttu-id="285ca-106">Правило работает и в обратном направлении:</span><span class="sxs-lookup"><span data-stu-id="285ca-106">The same is true in reverse.</span></span> <span data-ttu-id="285ca-107">если узел добавляется в объект **XmlNodeList**, необходимо обновить базовый документ.</span><span class="sxs-lookup"><span data-stu-id="285ca-107">If a node is added to the **XmlNodeList**, the underlying document is updated as well.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="285ca-108">См. также</span><span class="sxs-lookup"><span data-stu-id="285ca-108">See also</span></span>

- [<span data-ttu-id="285ca-109">Модель объектов документов XML (DOM)</span><span class="sxs-lookup"><span data-stu-id="285ca-109">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
