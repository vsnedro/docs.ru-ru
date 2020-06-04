---
title: Доступ к XML
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], accessing XML
- Visual Basic code, XML
- accessing XML [Visual Basic], axis properties
- XML [Visual Basic], axis properties
- XML [Visual Basic], accessing
ms.assetid: c47f88b2-3cbc-4bb1-b4b9-be60f71ffc6a
ms.openlocfilehash: 282b7d91ec7cfe2f587c67bc9a982f0da22ad925
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410313"
---
# <a name="accessing-xml-in-visual-basic"></a><span data-ttu-id="b9dee-102">Доступ к XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b9dee-102">Accessing XML in Visual Basic</span></span>
<span data-ttu-id="b9dee-103">Visual Basic предоставляет свойства осей XML для доступа к структурам и навигации по ним [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b9dee-103">Visual Basic provides XML axis properties for accessing and navigating [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] structures.</span></span> <span data-ttu-id="b9dee-104">Эти свойства используют специальный синтаксис, позволяющий получить доступ к элементам и атрибутам, указав имена XML.</span><span class="sxs-lookup"><span data-stu-id="b9dee-104">These properties use a special syntax to enable you to access elements and attributes by specifying the XML names.</span></span>  
  
 <span data-ttu-id="b9dee-105">В следующей таблице перечислены функции языка, позволяющие получать доступ к XML-элементам и атрибутам в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b9dee-105">The following table lists the language features that enable you to access XML elements and attributes in Visual Basic.</span></span>  
  
### <a name="xml-axis-properties"></a><span data-ttu-id="b9dee-106">Свойства оси XML</span><span class="sxs-lookup"><span data-stu-id="b9dee-106">XML Axis Properties</span></span>  
  
|<span data-ttu-id="b9dee-107">Описание свойства</span><span class="sxs-lookup"><span data-stu-id="b9dee-107">Property description</span></span>|<span data-ttu-id="b9dee-108">Пример</span><span class="sxs-lookup"><span data-stu-id="b9dee-108">Example</span></span>|<span data-ttu-id="b9dee-109">Описание</span><span class="sxs-lookup"><span data-stu-id="b9dee-109">Description</span></span>|  
|--------------------------|-------------|-----------------|  
|<span data-ttu-id="b9dee-110">*дочерняя ось*</span><span class="sxs-lookup"><span data-stu-id="b9dee-110">*child axis*</span></span>|`contact.<phone>`|<span data-ttu-id="b9dee-111">Возвращает все `phone` элементы, являющиеся дочерними элементами `contact` элемента.</span><span class="sxs-lookup"><span data-stu-id="b9dee-111">Gets all `phone` elements that are child elements of the `contact` element.</span></span>|  
|<span data-ttu-id="b9dee-112">*attribute, ось*</span><span class="sxs-lookup"><span data-stu-id="b9dee-112">*attribute axis*</span></span>|`phone.@type`|<span data-ttu-id="b9dee-113">Возвращает все `type` атрибуты `phone` элемента.</span><span class="sxs-lookup"><span data-stu-id="b9dee-113">Gets all `type` attributes of the `phone` element.</span></span>|  
|<span data-ttu-id="b9dee-114">*descendant, ось*</span><span class="sxs-lookup"><span data-stu-id="b9dee-114">*descendant axis*</span></span>|`contacts...<name>`|<span data-ttu-id="b9dee-115">Возвращает все `name` элементы `contacts` элемента, независимо от того, насколько глубоко в иерархии они выполняются.</span><span class="sxs-lookup"><span data-stu-id="b9dee-115">Gets all `name` elements of the `contacts` element, regardless of how deep in the hierarchy they occur.</span></span>|  
|<span data-ttu-id="b9dee-116">*индексатор расширения*</span><span class="sxs-lookup"><span data-stu-id="b9dee-116">*extension indexer*</span></span>|`contacts...<name>(0)`|<span data-ttu-id="b9dee-117">Возвращает первый `name` элемент из последовательности.</span><span class="sxs-lookup"><span data-stu-id="b9dee-117">Gets the first `name` element from the sequence.</span></span>|  
|<span data-ttu-id="b9dee-118">*value*</span><span class="sxs-lookup"><span data-stu-id="b9dee-118">*value*</span></span>|`contacts...<name>.Value`|<span data-ttu-id="b9dee-119">Возвращает строковое представление первого объекта в последовательности или `Nothing` значение, если последовательность пуста.</span><span class="sxs-lookup"><span data-stu-id="b9dee-119">Gets the string representation of the first object in the sequence, or `Nothing` if the sequence is empty.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="b9dee-120">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="b9dee-120">In This Section</span></span>  
 [<span data-ttu-id="b9dee-121">Практическое руководство. Доступ к элементам-потомкам XML</span><span class="sxs-lookup"><span data-stu-id="b9dee-121">How to: Access XML Descendant Elements</span></span>](how-to-access-xml-descendant-elements.md)  
 <span data-ttu-id="b9dee-122">Показывает, как использовать свойство оси потомков для доступа ко всем XML-элементам с указанным именем и содержащимся в указанном XML-элементе.</span><span class="sxs-lookup"><span data-stu-id="b9dee-122">Shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under a specified XML element.</span></span>  
  
 [<span data-ttu-id="b9dee-123">Практическое руководство. Доступ к дочерним XML-элементам</span><span class="sxs-lookup"><span data-stu-id="b9dee-123">How to: Access XML Child Elements</span></span>](how-to-access-xml-child-elements.md)  
 <span data-ttu-id="b9dee-124">Показывает, как использовать свойство дочерней оси для доступа ко всем дочерним элементам XML с указанным именем в элементе XML.</span><span class="sxs-lookup"><span data-stu-id="b9dee-124">Shows how to use a child axis property to access all XML child elements that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="b9dee-125">Практическое руководство. Доступ к XML-атрибутам</span><span class="sxs-lookup"><span data-stu-id="b9dee-125">How to: Access XML Attributes</span></span>](how-to-access-xml-attributes.md)  
 <span data-ttu-id="b9dee-126">Показывает, как использовать свойство оси атрибута для доступа ко всем XML-атрибутам, имеющим указанное имя в элементе XML.</span><span class="sxs-lookup"><span data-stu-id="b9dee-126">Shows how to use an attribute axis property to access all XML attributes that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="b9dee-127">Практическое руководство. Объявление и использование префиксов пространств имен XML</span><span class="sxs-lookup"><span data-stu-id="b9dee-127">How to: Declare and Use XML Namespace Prefixes</span></span>](how-to-declare-and-use-xml-namespace-prefixes.md)  
 <span data-ttu-id="b9dee-128">Показывает, как объявить префикс пространства имен XML и использовать его для создания и доступа к XML-элементам.</span><span class="sxs-lookup"><span data-stu-id="b9dee-128">Shows how to declare an XML namespace prefix and use it to create and access XML elements.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b9dee-129">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="b9dee-129">Related Sections</span></span>  
 [<span data-ttu-id="b9dee-130">Свойства оси XML</span><span class="sxs-lookup"><span data-stu-id="b9dee-130">XML Axis Properties</span></span>](../../../language-reference/xml-axis/index.md)  
 <span data-ttu-id="b9dee-131">Содержит ссылки на разделы, описывающие различные свойства доступа к XML.</span><span class="sxs-lookup"><span data-stu-id="b9dee-131">Provides links to sections describing the various XML access properties.</span></span>  
  
 <span data-ttu-id="b9dee-132">[Overview of LINQ to XML in Visual Basic](overview-of-linq-to-xml.md) (Общие сведения о LINQ to XML в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b9dee-132">[Overview of LINQ to XML in Visual Basic](overview-of-linq-to-xml.md)</span></span>  
 <span data-ttu-id="b9dee-133">Общие сведения об использовании [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b9dee-133">Provides an introduction to using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
 [<span data-ttu-id="b9dee-134">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b9dee-134">Creating XML in Visual Basic</span></span>](creating-xml.md)  
 <span data-ttu-id="b9dee-135">Общие сведения об использовании литералов XML в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b9dee-135">Provides an introduction to using XML literals in Visual Basic.</span></span>  
  
 [<span data-ttu-id="b9dee-136">Обработка XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b9dee-136">Manipulating XML in Visual Basic</span></span>](manipulating-xml.md)  
 <span data-ttu-id="b9dee-137">Содержит ссылки на разделы, посвященные загрузке и изменению XML в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b9dee-137">Provides links to sections about loading and modifying XML in Visual Basic.</span></span>  
  
 [<span data-ttu-id="b9dee-138">XML</span><span class="sxs-lookup"><span data-stu-id="b9dee-138">XML</span></span>](index.md)  
 <span data-ttu-id="b9dee-139">Содержит ссылки на разделы, описывающие использование [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b9dee-139">Provides links to sections describing how to use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>
