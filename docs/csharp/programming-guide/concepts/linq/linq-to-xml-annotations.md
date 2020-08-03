---
title: Примечания LINQ to XML
description: Узнайте, как использовать заметки в LINQ to XML для ассоциации любого произвольного объекта любого произвольного типа с любым XML-компонентом XML-дерева.
ms.date: 07/20/2015
ms.assetid: 54e7b9d0-07f5-488f-9065-b6e6b870f810
ms.openlocfilehash: e7da666139c10b26de37816693202d96498f52d8
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165579"
---
# <a name="linq-to-xml-annotations"></a><span data-ttu-id="51d68-103">Примечания LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="51d68-103">LINQ to XML Annotations</span></span>

<span data-ttu-id="51d68-104">Заметки в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] позволяют ассоциировать любой произвольный объект любого произвольного типа с любым XML-компонентом XML-дерева.</span><span class="sxs-lookup"><span data-stu-id="51d68-104">Annotations in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] enable you to associate any arbitrary object of any arbitrary type with any XML component in an XML tree.</span></span>

<span data-ttu-id="51d68-105">Чтобы добавить заметку к компоненту XML, например <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XAttribute>, следует вызвать метод <xref:System.Xml.Linq.XObject.AddAnnotation%2A>.</span><span class="sxs-lookup"><span data-stu-id="51d68-105">To add an annotation to an XML component, such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute>, you call the <xref:System.Xml.Linq.XObject.AddAnnotation%2A> method.</span></span> <span data-ttu-id="51d68-106">Заметки получаются по типу.</span><span class="sxs-lookup"><span data-stu-id="51d68-106">You retrieve annotations by type.</span></span>

<span data-ttu-id="51d68-107">Обратите внимание, что заметки не являются частью набора сведений XML, они не могут быть сериализованы или десериализованы.</span><span class="sxs-lookup"><span data-stu-id="51d68-107">Note that annotations are not part of the XML infoset; they are not serialized or deserialized.</span></span>

## <a name="methods"></a><span data-ttu-id="51d68-108">Методы</span><span class="sxs-lookup"><span data-stu-id="51d68-108">Methods</span></span>

<span data-ttu-id="51d68-109">При работе с заметками можно использовать следующие методы.</span><span class="sxs-lookup"><span data-stu-id="51d68-109">You can use the following methods when working with annotations:</span></span>

|<span data-ttu-id="51d68-110">Метод</span><span class="sxs-lookup"><span data-stu-id="51d68-110">Method</span></span>|<span data-ttu-id="51d68-111">Описание</span><span class="sxs-lookup"><span data-stu-id="51d68-111">Description</span></span>|
|------------|-----------------|
|<xref:System.Xml.Linq.XObject.AddAnnotation%2A>|<span data-ttu-id="51d68-112">Добавляет объект к списку заметок <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="51d68-112">Adds an object to the annotation list of an <xref:System.Xml.Linq.XObject>.</span></span>|
|<xref:System.Xml.Linq.XObject.Annotation%2A>|<span data-ttu-id="51d68-113">Извлекает первый объект заметки указанного типа из <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="51d68-113">Gets the first annotation object of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|
|<xref:System.Xml.Linq.XObject.Annotations%2A>|<span data-ttu-id="51d68-114">Извлекает коллекцию заметок указанного типа для <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="51d68-114">Gets a collection of annotations of the specified type for an <xref:System.Xml.Linq.XObject>.</span></span>|
|<xref:System.Xml.Linq.XObject.RemoveAnnotations%2A>|<span data-ttu-id="51d68-115">Удаляет заметки указанного типа из <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="51d68-115">Removes the annotations of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|
