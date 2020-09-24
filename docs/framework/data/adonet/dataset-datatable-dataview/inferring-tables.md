---
title: Определение таблиц
ms.date: 03/30/2017
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
ms.openlocfilehash: 4a3d7b239dbc405cf2acae967b5be401dc772e38
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177557"
---
# <a name="inferring-tables"></a><span data-ttu-id="bd494-102">Определение таблиц</span><span class="sxs-lookup"><span data-stu-id="bd494-102">Inferring Tables</span></span>

<span data-ttu-id="bd494-103">При выведении схемы для <xref:System.Data.DataSet> из XML-документа ADO.NET сначала определяет, какой из XML-элементов представляет таблицы.</span><span class="sxs-lookup"><span data-stu-id="bd494-103">When inferring a schema for a <xref:System.Data.DataSet> from an XML document, ADO.NET first determines which XML elements represent tables.</span></span> <span data-ttu-id="bd494-104">Следующие XML-структуры приводят к созданию таблицы для схемы **набора данных** :</span><span class="sxs-lookup"><span data-stu-id="bd494-104">The following XML structures result in a table for the **DataSet** schema:</span></span>  
  
- <span data-ttu-id="bd494-105">Элементы с атрибутами.</span><span class="sxs-lookup"><span data-stu-id="bd494-105">Elements with attributes</span></span>  
  
- <span data-ttu-id="bd494-106">Элементы с дочерними элементами.</span><span class="sxs-lookup"><span data-stu-id="bd494-106">Elements with child elements</span></span>  
  
- <span data-ttu-id="bd494-107">Повторяющиеся элементы.</span><span class="sxs-lookup"><span data-stu-id="bd494-107">Repeating elements</span></span>  
  
## <a name="elements-with-attributes"></a><span data-ttu-id="bd494-108">Элементы с атрибутами</span><span class="sxs-lookup"><span data-stu-id="bd494-108">Elements with Attributes</span></span>  

 <span data-ttu-id="bd494-109">Элементы с заданными атрибутами приводятся в выведенных таблицах.</span><span class="sxs-lookup"><span data-stu-id="bd494-109">Elements that have attributes specified in them result in inferred tables.</span></span> <span data-ttu-id="bd494-110">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="bd494-110">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="bd494-111">В процессе вывода создается таблица с именем Element1.</span><span class="sxs-lookup"><span data-stu-id="bd494-111">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="bd494-112">**Набор данных:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="bd494-112">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="bd494-113">**Таблица:** Element1</span><span class="sxs-lookup"><span data-stu-id="bd494-113">**Table:** Element1</span></span>  
  
|<span data-ttu-id="bd494-114">attr1</span><span class="sxs-lookup"><span data-stu-id="bd494-114">attr1</span></span>|<span data-ttu-id="bd494-115">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="bd494-115">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="bd494-116">value1</span><span class="sxs-lookup"><span data-stu-id="bd494-116">value1</span></span>||  
|<span data-ttu-id="bd494-117">value2</span><span class="sxs-lookup"><span data-stu-id="bd494-117">value2</span></span>|<span data-ttu-id="bd494-118">Text1</span><span class="sxs-lookup"><span data-stu-id="bd494-118">Text1</span></span>|  
  
## <a name="elements-with-child-elements"></a><span data-ttu-id="bd494-119">Элементы с дочерними элементами</span><span class="sxs-lookup"><span data-stu-id="bd494-119">Elements with Child Elements</span></span>  

 <span data-ttu-id="bd494-120">Элементы, имеющие дочерние элементы, приводятся в выведенных таблицах.</span><span class="sxs-lookup"><span data-stu-id="bd494-120">Elements that have child elements result in inferred tables.</span></span> <span data-ttu-id="bd494-121">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="bd494-121">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="bd494-122">В процессе вывода создается таблица с именем Element1.</span><span class="sxs-lookup"><span data-stu-id="bd494-122">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="bd494-123">**Набор данных:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="bd494-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="bd494-124">**Таблица:** Element1</span><span class="sxs-lookup"><span data-stu-id="bd494-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="bd494-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="bd494-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="bd494-126">Text1</span><span class="sxs-lookup"><span data-stu-id="bd494-126">Text1</span></span>|  
  
 <span data-ttu-id="bd494-127">Элемент документа или корневой элемент приводится в выведенной таблице, если он имеет атрибуты или дочерние элементы, которые выводятся в виде столбцов.</span><span class="sxs-lookup"><span data-stu-id="bd494-127">The document, or root, element result in an inferred table if it has attributes or child elements that are inferred as columns.</span></span> <span data-ttu-id="bd494-128">Если элемент документа не имеет атрибутов и не содержит дочерних элементов, которые будут выводиться как столбцы, то элемент выводится как **набор данных**.</span><span class="sxs-lookup"><span data-stu-id="bd494-128">If the document element has no attributes and no child elements that would be inferred as columns, the element is inferred as a **DataSet**.</span></span> <span data-ttu-id="bd494-129">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="bd494-129">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 <span data-ttu-id="bd494-130">В процессе вывода создается таблица с именем DocumentElement.</span><span class="sxs-lookup"><span data-stu-id="bd494-130">The inference process produces a table named "DocumentElement."</span></span>  
  
 <span data-ttu-id="bd494-131">**Набор данных:** невдатасет</span><span class="sxs-lookup"><span data-stu-id="bd494-131">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="bd494-132">**Таблица:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="bd494-132">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="bd494-133">Element1</span><span class="sxs-lookup"><span data-stu-id="bd494-133">Element1</span></span>|<span data-ttu-id="bd494-134">Element2</span><span class="sxs-lookup"><span data-stu-id="bd494-134">Element2</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="bd494-135">Text1</span><span class="sxs-lookup"><span data-stu-id="bd494-135">Text1</span></span>|<span data-ttu-id="bd494-136">Text2</span><span class="sxs-lookup"><span data-stu-id="bd494-136">Text2</span></span>|  
  
 <span data-ttu-id="bd494-137">В качестве альтернативы рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="bd494-137">Alternatively, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="bd494-138">Процесс вывода создает **набор данных** с именем «documentElement», содержащий таблицу с именем «Element1».</span><span class="sxs-lookup"><span data-stu-id="bd494-138">The inference process produces a **DataSet** named "DocumentElement" that contains a table named "Element1."</span></span>  
  
 <span data-ttu-id="bd494-139">**Набор данных:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="bd494-139">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="bd494-140">**Таблица:** Element1</span><span class="sxs-lookup"><span data-stu-id="bd494-140">**Table:** Element1</span></span>  
  
|<span data-ttu-id="bd494-141">attr1</span><span class="sxs-lookup"><span data-stu-id="bd494-141">attr1</span></span>|<span data-ttu-id="bd494-142">attr2</span><span class="sxs-lookup"><span data-stu-id="bd494-142">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="bd494-143">value1</span><span class="sxs-lookup"><span data-stu-id="bd494-143">value1</span></span>|<span data-ttu-id="bd494-144">value2</span><span class="sxs-lookup"><span data-stu-id="bd494-144">value2</span></span>|  
  
## <a name="repeating-elements"></a><span data-ttu-id="bd494-145">Повторяющиеся элементы</span><span class="sxs-lookup"><span data-stu-id="bd494-145">Repeating Elements</span></span>  

 <span data-ttu-id="bd494-146">Повторяющиеся элементы приводятся в выведенной таблице.</span><span class="sxs-lookup"><span data-stu-id="bd494-146">Elements that repeat result in a single inferred table.</span></span> <span data-ttu-id="bd494-147">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="bd494-147">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="bd494-148">В процессе вывода создается таблица с именем Element1.</span><span class="sxs-lookup"><span data-stu-id="bd494-148">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="bd494-149">**Набор данных:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="bd494-149">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="bd494-150">**Таблица:** Element1</span><span class="sxs-lookup"><span data-stu-id="bd494-150">**Table:** Element1</span></span>  
  
|<span data-ttu-id="bd494-151">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="bd494-151">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="bd494-152">Text1</span><span class="sxs-lookup"><span data-stu-id="bd494-152">Text1</span></span>|  
|<span data-ttu-id="bd494-153">Text2</span><span class="sxs-lookup"><span data-stu-id="bd494-153">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bd494-154">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bd494-154">See also</span></span>

- [<span data-ttu-id="bd494-155">Определение реляционной структуры набора данных из XML</span><span class="sxs-lookup"><span data-stu-id="bd494-155">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="bd494-156">Загрузка набора данных из XML</span><span class="sxs-lookup"><span data-stu-id="bd494-156">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="bd494-157">Загрузка сведений о схеме набора данных из XML</span><span class="sxs-lookup"><span data-stu-id="bd494-157">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="bd494-158">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="bd494-158">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="bd494-159">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="bd494-159">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="bd494-160">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="bd494-160">ADO.NET Overview</span></span>](../ado-net-overview.md)
