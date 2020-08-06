---
title: Изменение элементов, атрибутов и узлов в дереве XML
description: Сведения о методах и свойствах, которые можно использовать для изменения элемента, его дочерних узлов или его атрибутов.
ms.date: 07/20/2015
ms.assetid: 0ed22e4e-4c6b-4eb1-b0eb-06685efd8c33
ms.openlocfilehash: bfff882dc57a4f6f4b228563ac923122097d88d0
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303170"
---
# <a name="modifying-elements-attributes-and-nodes-in-an-xml-tree"></a><span data-ttu-id="28be9-103">Изменение элементов, атрибутов и узлов в дереве XML</span><span class="sxs-lookup"><span data-stu-id="28be9-103">Modifying Elements, Attributes, and Nodes in an XML Tree</span></span>
<span data-ttu-id="28be9-104">В следующей таблице приведена сводка методов и свойств, используемых для изменения элемента, его дочерних элементов или его атрибутов.</span><span class="sxs-lookup"><span data-stu-id="28be9-104">The following table summarizes the methods and properties that you can use to modify an element, its child elements, or its attributes.</span></span>  
  
 <span data-ttu-id="28be9-105">Следующие методы используются для изменения <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="28be9-105">The following methods modify an <xref:System.Xml.Linq.XElement>.</span></span>  
  
|<span data-ttu-id="28be9-106">Метод</span><span class="sxs-lookup"><span data-stu-id="28be9-106">Method</span></span>|<span data-ttu-id="28be9-107">Описание</span><span class="sxs-lookup"><span data-stu-id="28be9-107">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>|<span data-ttu-id="28be9-108">Заменяет элемент проанализированным XML.</span><span class="sxs-lookup"><span data-stu-id="28be9-108">Replaces an element with parsed XML.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=nameWithType>|<span data-ttu-id="28be9-109">Удаляет все содержимое (дочерние узлы и атрибуты) элемента.</span><span class="sxs-lookup"><span data-stu-id="28be9-109">Removes all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="28be9-110">Удаляет атрибуты элемента.</span><span class="sxs-lookup"><span data-stu-id="28be9-110">Removes the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=nameWithType>|<span data-ttu-id="28be9-111">Заменяет все содержимое (дочерние узлы и атрибуты) элемента.</span><span class="sxs-lookup"><span data-stu-id="28be9-111">Replaces all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="28be9-112">Заменяет атрибуты элемента.</span><span class="sxs-lookup"><span data-stu-id="28be9-112">Replaces the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=nameWithType>|<span data-ttu-id="28be9-113">Устанавливает значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="28be9-113">Sets the value of an attribute.</span></span> <span data-ttu-id="28be9-114">Создает атрибут, если он не существует.</span><span class="sxs-lookup"><span data-stu-id="28be9-114">Creates the attribute if it doesn't exist.</span></span> <span data-ttu-id="28be9-115">Если значение устанавливается в `null`, удаляет атрибут.</span><span class="sxs-lookup"><span data-stu-id="28be9-115">If the value is set to `null`, removes the attribute.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=nameWithType>|<span data-ttu-id="28be9-116">Задает значение дочернего элемента.</span><span class="sxs-lookup"><span data-stu-id="28be9-116">Sets the value of a child element.</span></span> <span data-ttu-id="28be9-117">Создает элемент, если он не существует.</span><span class="sxs-lookup"><span data-stu-id="28be9-117">Creates the element if it doesn't exist.</span></span> <span data-ttu-id="28be9-118">Если значение устанавливается в `null`, удаляет элемент.</span><span class="sxs-lookup"><span data-stu-id="28be9-118">If the value is set to `null`, removes the element.</span></span>|  
|<xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="28be9-119">Заменяет содержимое (дочерние узлы) элемента заданным текстом.</span><span class="sxs-lookup"><span data-stu-id="28be9-119">Replaces the content (child nodes) of an element with the specified text.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="28be9-120">Задает значение элемента.</span><span class="sxs-lookup"><span data-stu-id="28be9-120">Sets the value of an element.</span></span>|  
  
 <span data-ttu-id="28be9-121">Следующие методы используются для изменения <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="28be9-121">The following methods modify an <xref:System.Xml.Linq.XAttribute>.</span></span>  
  
|<span data-ttu-id="28be9-122">Метод</span><span class="sxs-lookup"><span data-stu-id="28be9-122">Method</span></span>|<span data-ttu-id="28be9-123">Описание</span><span class="sxs-lookup"><span data-stu-id="28be9-123">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="28be9-124">Устанавливает значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="28be9-124">Sets the value of an attribute.</span></span>|  
|<xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="28be9-125">Устанавливает значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="28be9-125">Sets the value of an attribute.</span></span>|  
  
 <span data-ttu-id="28be9-126">Следующие методы предназначены для изменения <xref:System.Xml.Linq.XNode> (включая <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument>).</span><span class="sxs-lookup"><span data-stu-id="28be9-126">The following methods modify an <xref:System.Xml.Linq.XNode> (including an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="28be9-127">Метод</span><span class="sxs-lookup"><span data-stu-id="28be9-127">Method</span></span>|<span data-ttu-id="28be9-128">Описание</span><span class="sxs-lookup"><span data-stu-id="28be9-128">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=nameWithType>|<span data-ttu-id="28be9-129">Заменяет узел новым содержимым.</span><span class="sxs-lookup"><span data-stu-id="28be9-129">Replaces a node with new content.</span></span>|  
  
 <span data-ttu-id="28be9-130">Следующие методы предназначены для изменения <xref:System.Xml.Linq.XContainer> (<xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument>).</span><span class="sxs-lookup"><span data-stu-id="28be9-130">The following methods modify an <xref:System.Xml.Linq.XContainer> (an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="28be9-131">Метод</span><span class="sxs-lookup"><span data-stu-id="28be9-131">Method</span></span>|<span data-ttu-id="28be9-132">Описание</span><span class="sxs-lookup"><span data-stu-id="28be9-132">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=nameWithType>|<span data-ttu-id="28be9-133">Заменяет дочерние узлы новым содержимым.</span><span class="sxs-lookup"><span data-stu-id="28be9-133">Replaces the children nodes with new content.</span></span>|  
