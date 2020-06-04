---
title: Изменение элементов, атрибутов и узлов в XML-Tree1
ms.date: 07/20/2015
ms.assetid: 865cf54e-f8ac-4871-863b-a3e6fc61a4b9
ms.openlocfilehash: 002e87d58ad1a3730889225bf4b3e50448431f2d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84360934"
---
# <a name="modifying-elements-attributes-and-nodes-in-an-xml-tree"></a><span data-ttu-id="58b47-102">Изменение элементов, атрибутов и узлов в дереве XML</span><span class="sxs-lookup"><span data-stu-id="58b47-102">Modifying Elements, Attributes, and Nodes in an XML Tree</span></span>
<span data-ttu-id="58b47-103">В следующей таблице приведена сводка методов и свойств, используемых для изменения элемента, его дочерних элементов или его атрибутов.</span><span class="sxs-lookup"><span data-stu-id="58b47-103">The following table summarizes the methods and properties that you can use to modify an element, its child elements, or its attributes.</span></span>  
  
 <span data-ttu-id="58b47-104">Следующие методы используются для изменения <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="58b47-104">The following methods modify an <xref:System.Xml.Linq.XElement>.</span></span>  
  
|<span data-ttu-id="58b47-105">Метод</span><span class="sxs-lookup"><span data-stu-id="58b47-105">Method</span></span>|<span data-ttu-id="58b47-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="58b47-106">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>|<span data-ttu-id="58b47-107">Заменяет элемент проанализированным XML.</span><span class="sxs-lookup"><span data-stu-id="58b47-107">Replaces an element with parsed XML.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=nameWithType>|<span data-ttu-id="58b47-108">Удаляет все содержимое (дочерние узлы и атрибуты) элемента.</span><span class="sxs-lookup"><span data-stu-id="58b47-108">Removes all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="58b47-109">Удаляет атрибуты элемента.</span><span class="sxs-lookup"><span data-stu-id="58b47-109">Removes the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=nameWithType>|<span data-ttu-id="58b47-110">Заменяет все содержимое (дочерние узлы и атрибуты) элемента.</span><span class="sxs-lookup"><span data-stu-id="58b47-110">Replaces all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="58b47-111">Заменяет атрибуты элемента.</span><span class="sxs-lookup"><span data-stu-id="58b47-111">Replaces the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=nameWithType>|<span data-ttu-id="58b47-112">Устанавливает значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="58b47-112">Sets the value of an attribute.</span></span> <span data-ttu-id="58b47-113">Создает атрибут, если он не существует.</span><span class="sxs-lookup"><span data-stu-id="58b47-113">Creates the attribute if it doesn't exist.</span></span> <span data-ttu-id="58b47-114">Если значение устанавливается в `null`, удаляет атрибут.</span><span class="sxs-lookup"><span data-stu-id="58b47-114">If the value is set to `null`, removes the attribute.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=nameWithType>|<span data-ttu-id="58b47-115">Задает значение дочернего элемента.</span><span class="sxs-lookup"><span data-stu-id="58b47-115">Sets the value of a child element.</span></span> <span data-ttu-id="58b47-116">Создает элемент, если он не существует.</span><span class="sxs-lookup"><span data-stu-id="58b47-116">Creates the element if it doesn't exist.</span></span> <span data-ttu-id="58b47-117">Если значение устанавливается в `null`, удаляет элемент.</span><span class="sxs-lookup"><span data-stu-id="58b47-117">If the value is set to `null`, removes the element.</span></span>|  
|<xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="58b47-118">Заменяет содержимое (дочерние узлы) элемента заданным текстом.</span><span class="sxs-lookup"><span data-stu-id="58b47-118">Replaces the content (child nodes) of an element with the specified text.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="58b47-119">Задает значение элемента.</span><span class="sxs-lookup"><span data-stu-id="58b47-119">Sets the value of an element.</span></span>|  
  
 <span data-ttu-id="58b47-120">Следующие методы используются для изменения <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="58b47-120">The following methods modify an <xref:System.Xml.Linq.XAttribute>.</span></span>  
  
|<span data-ttu-id="58b47-121">Метод</span><span class="sxs-lookup"><span data-stu-id="58b47-121">Method</span></span>|<span data-ttu-id="58b47-122">Описание:</span><span class="sxs-lookup"><span data-stu-id="58b47-122">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="58b47-123">Устанавливает значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="58b47-123">Sets the value of an attribute.</span></span>|  
|<xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="58b47-124">Устанавливает значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="58b47-124">Sets the value of an attribute.</span></span>|  
  
 <span data-ttu-id="58b47-125">Следующие методы предназначены для изменения <xref:System.Xml.Linq.XNode> (включая <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument>).</span><span class="sxs-lookup"><span data-stu-id="58b47-125">The following methods modify an <xref:System.Xml.Linq.XNode> (including an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="58b47-126">Метод</span><span class="sxs-lookup"><span data-stu-id="58b47-126">Method</span></span>|<span data-ttu-id="58b47-127">Описание:</span><span class="sxs-lookup"><span data-stu-id="58b47-127">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=nameWithType>|<span data-ttu-id="58b47-128">Заменяет узел новым содержимым.</span><span class="sxs-lookup"><span data-stu-id="58b47-128">Replaces a node with new content.</span></span>|  
  
 <span data-ttu-id="58b47-129">Следующие методы предназначены для изменения <xref:System.Xml.Linq.XContainer> (<xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument>).</span><span class="sxs-lookup"><span data-stu-id="58b47-129">The following methods modify an <xref:System.Xml.Linq.XContainer> (an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="58b47-130">Метод</span><span class="sxs-lookup"><span data-stu-id="58b47-130">Method</span></span>|<span data-ttu-id="58b47-131">Описание:</span><span class="sxs-lookup"><span data-stu-id="58b47-131">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=nameWithType>|<span data-ttu-id="58b47-132">Заменяет дочерние узлы новым содержимым.</span><span class="sxs-lookup"><span data-stu-id="58b47-132">Replaces the children nodes with new content.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="58b47-133">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="58b47-133">See also</span></span>

- [<span data-ttu-id="58b47-134">Изменение деревьев XML (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="58b47-134">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>](modifying-xml-trees-linq-to-xml.md)
