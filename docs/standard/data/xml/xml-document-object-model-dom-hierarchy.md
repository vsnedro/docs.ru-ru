---
title: Иерархия модели объектов (DOM) XML-документа
ms.date: 03/30/2017
ms.assetid: 9d187d4f-c76e-4223-a670-cc290783ce47
ms.openlocfilehash: 2a8bbd4f7cb3feb2a555af9862632a2fa493be32
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94819257"
---
# <a name="xml-document-object-model-dom-hierarchy"></a><span data-ttu-id="f72db-102">Иерархия модели объектов (DOM) XML-документа</span><span class="sxs-lookup"><span data-stu-id="f72db-102">XML Document Object Model (DOM) Hierarchy</span></span>
<span data-ttu-id="f72db-103">Следующая иллюстрация показывает иерархию классов для модели XML DOM с именем W3C в скобках наряду с именем класса, где это уместно.</span><span class="sxs-lookup"><span data-stu-id="f72db-103">The following illustration shows the class hierarchy for the XML Document Object Model (DOM), with the World Wide Web Consortium (W3C) name in parenthesis along with the class name where it is relevant.</span></span>  
  
 <span data-ttu-id="f72db-104">![Иерархия объектной модели (DOM) XML-документа](media/dom-class-hierarchy.gif "Dom_class_hierarchy")</span><span class="sxs-lookup"><span data-stu-id="f72db-104">![XML Document Object Model &#40;DOM&#41; hierarchy](media/dom-class-hierarchy.gif "Dom_class_hierarchy")</span></span>  
<span data-ttu-id="f72db-105">Иерархия объектной модели (DOM) XML-документа</span><span class="sxs-lookup"><span data-stu-id="f72db-105">XML Document Object Model (DOM) hierarchy</span></span>  
  
 <span data-ttu-id="f72db-106">Следующие классы не наследуют от класса **XmlNode**:</span><span class="sxs-lookup"><span data-stu-id="f72db-106">The following classes do not inherit from the **XmlNode**:</span></span>  
  
- <span data-ttu-id="f72db-107">**XmlImplementation**</span><span class="sxs-lookup"><span data-stu-id="f72db-107">**XmlImplementation**</span></span>  
  
- <span data-ttu-id="f72db-108">**XmlNamedNodeMap**</span><span class="sxs-lookup"><span data-stu-id="f72db-108">**XmlNamedNodeMap**</span></span>  
  
- <span data-ttu-id="f72db-109">**XmlNodeList**</span><span class="sxs-lookup"><span data-stu-id="f72db-109">**XmlNodeList**</span></span>  
  
- <span data-ttu-id="f72db-110">**XmlNodeChangedEventArgs**</span><span class="sxs-lookup"><span data-stu-id="f72db-110">**XmlNodeChangedEventArgs**</span></span>  
  
 <span data-ttu-id="f72db-111">Класс **XmlImplementation** используется для создания XML-документа.</span><span class="sxs-lookup"><span data-stu-id="f72db-111">The **XmlImplementation** class is used to create an XML document.</span></span> <span data-ttu-id="f72db-112">Дополнительные сведения см. в статье [Создание XML-документа](xml-document-creation.md).</span><span class="sxs-lookup"><span data-stu-id="f72db-112">For more information, see [XML Document Creation](xml-document-creation.md).</span></span>  
  
 <span data-ttu-id="f72db-113">Класс **XmlNamedNodeMap** обрабатывает неупорядоченный набор узлов.</span><span class="sxs-lookup"><span data-stu-id="f72db-113">The **XmlNamedNodeMap** class handles an unordered set of nodes.</span></span> <span data-ttu-id="f72db-114">Дополнительные сведения см. в статье [Неупорядоченное извлечение узлов по имени или индексу](unordered-node-retrieval-by-name-or-index.md).</span><span class="sxs-lookup"><span data-stu-id="f72db-114">For more information, see [Unordered Node Retrieval by Name or Index](unordered-node-retrieval-by-name-or-index.md).</span></span>  
  
 <span data-ttu-id="f72db-115">Класс **XmlNamedNodeMap** обрабатывает упорядоченный набор узлов.</span><span class="sxs-lookup"><span data-stu-id="f72db-115">The **XmlNodeList** class handles an ordered list of nodes.</span></span> <span data-ttu-id="f72db-116">Дополнительные сведения см. в статье [Упорядоченное извлечение узлов по индексу](ordered-node-retrieval-by-index.md).</span><span class="sxs-lookup"><span data-stu-id="f72db-116">For more information, see [Ordered Node Retrieval by Index](ordered-node-retrieval-by-index.md).</span></span>  
  
 <span data-ttu-id="f72db-117">Класс **XmlNodeChangedEventArgs** управляет обработчиками событий, которые зарегистрированы в объекте **XmlDocument**.</span><span class="sxs-lookup"><span data-stu-id="f72db-117">The **XmlNodeChangedEventArgs** class handles event handlers registered on the **XmlDocument**.</span></span> <span data-ttu-id="f72db-118">Дополнительные сведения см. в статье [Обработка событий в XML-документе с помощью XmlNodeChangedEventArgs](event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).</span><span class="sxs-lookup"><span data-stu-id="f72db-118">For more information, see [Event Handling in an XML Document using the XmlNodeChangedEventArgs](event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).</span></span>  
  
 <span data-ttu-id="f72db-119">Класс **XmlLinkedNode** наследует от класса **XmlNode**.</span><span class="sxs-lookup"><span data-stu-id="f72db-119">The **XmlLinkedNode** class inherits from **XmlNode**.</span></span> <span data-ttu-id="f72db-120">Он предназначен для того, чтобы переопределять два метода **XmlNode**, а именно: **PreviousSibling** и **NextSibling**.</span><span class="sxs-lookup"><span data-stu-id="f72db-120">Its purpose is to override two methods from **XmlNode**: the **PreviousSibling** and **NextSibling** methods.</span></span> <span data-ttu-id="f72db-121">Эти переопределенные методы затем наследуются и используются классами **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference** и **XmlProcessingInstruction**, для которых существуют предыдущие и следующие одноуровневые элементы.</span><span class="sxs-lookup"><span data-stu-id="f72db-121">These overridden methods are then inherited and used by **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference**, and **XmlProcessingInstruction**, which are classes that have previous and next siblings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f72db-122">См. также</span><span class="sxs-lookup"><span data-stu-id="f72db-122">See also</span></span>

- [<span data-ttu-id="f72db-123">Модель объектов документов XML (DOM)</span><span class="sxs-lookup"><span data-stu-id="f72db-123">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
