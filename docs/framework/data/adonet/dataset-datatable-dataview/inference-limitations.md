---
title: Ограничения определения
ms.date: 03/30/2017
ms.assetid: 78517994-5d57-44f8-9d20-38812977de09
ms.openlocfilehash: 9d8191be137661200e1a6b84d68328c1202880ca
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172779"
---
# <a name="inference-limitations"></a><span data-ttu-id="d2005-102">Ограничения определения</span><span class="sxs-lookup"><span data-stu-id="d2005-102">Inference Limitations</span></span>

<span data-ttu-id="d2005-103">Процесс вывода схемы <xref:System.Data.DataSet> из XML-кода может приводиться в различных схемах в зависимости от XML-элементов в каждом документе.</span><span class="sxs-lookup"><span data-stu-id="d2005-103">The process of inferring a <xref:System.Data.DataSet> schema from XML can result in different schemas depending on the XML elements in each document.</span></span> <span data-ttu-id="d2005-104">Например, рассмотрим следующие XML-документы.</span><span class="sxs-lookup"><span data-stu-id="d2005-104">For example, consider the following XML documents.</span></span>  
  
 <span data-ttu-id="d2005-105">Document1:</span><span class="sxs-lookup"><span data-stu-id="d2005-105">Document1:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="d2005-106">Document2:</span><span class="sxs-lookup"><span data-stu-id="d2005-106">Document2:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="d2005-107">Для "document1" процесс вывода создает **набор данных** с именем "documentElement" и таблицу с именем "Element1", так как "Element1" является повторяющимся элементом.</span><span class="sxs-lookup"><span data-stu-id="d2005-107">For "Document1," the inference process produces a **DataSet** named "DocumentElement" and a table named "Element1," because "Element1" is a repeating element.</span></span>  
  
 <span data-ttu-id="d2005-108">**Набор данных:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="d2005-108">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="d2005-109">**Таблица:** Element1</span><span class="sxs-lookup"><span data-stu-id="d2005-109">**Table:** Element1</span></span>  
  
|<span data-ttu-id="d2005-110">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="d2005-110">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="d2005-111">Text1</span><span class="sxs-lookup"><span data-stu-id="d2005-111">Text1</span></span>|  
|<span data-ttu-id="d2005-112">Text2</span><span class="sxs-lookup"><span data-stu-id="d2005-112">Text2</span></span>|  
  
 <span data-ttu-id="d2005-113">Однако для "Document2" процесс вывода создает **набор данных** с именем "невдатасет" и таблицу с именем "documentElement".</span><span class="sxs-lookup"><span data-stu-id="d2005-113">However, for "Document2," the inference process produces a **DataSet** named "NewDataSet" and a table named "DocumentElement."</span></span> <span data-ttu-id="d2005-114">Element1 выводится в виде столбца, потому что не имеет атрибутов и дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="d2005-114">"Element1" is inferred as a column because it has no attributes and no child elements.</span></span>  
  
 <span data-ttu-id="d2005-115">**Набор данных:** невдатасет</span><span class="sxs-lookup"><span data-stu-id="d2005-115">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="d2005-116">**Таблица:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="d2005-116">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="d2005-117">Element1</span><span class="sxs-lookup"><span data-stu-id="d2005-117">Element1</span></span>|  
|--------------|  
|<span data-ttu-id="d2005-118">Text1</span><span class="sxs-lookup"><span data-stu-id="d2005-118">Text1</span></span>|  
  
 <span data-ttu-id="d2005-119">Эти два XML-документа, возможно, должны были выдавать одну и ту же схему, но процесс вывода дает значительно различающиеся результаты в зависимости от элементов, содержащихся в каждом документе.</span><span class="sxs-lookup"><span data-stu-id="d2005-119">These two XML documents may have been intended to produce the same schema, but the inference process produces very different results based on the elements contained in each document.</span></span>  
  
 <span data-ttu-id="d2005-120">Чтобы избежать расхождений, которые могут возникнуть при формировании схемы из XML-документа, рекомендуется явно указать схему с помощью языка определения схемы XML (XSD) или сокращенных данных XML (XDR) при загрузке **набора данных** из XML.</span><span class="sxs-lookup"><span data-stu-id="d2005-120">To avoid the discrepancies that can occur when generating schema from an XML document, we recommend that you explicitly specify a schema using XML Schema definition language (XSD) or XML-Data Reduced (XDR) when loading a **DataSet** from XML.</span></span> <span data-ttu-id="d2005-121">Дополнительные сведения о явном указании схемы **набора данных** с XML-схемой см. [в разделе Наследование реляционной структуры набора данных из схемы XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span><span class="sxs-lookup"><span data-stu-id="d2005-121">For more information about explicitly specifying a **DataSet** schema with XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2005-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d2005-122">See also</span></span>

- [<span data-ttu-id="d2005-123">Определение реляционной структуры набора данных из XML</span><span class="sxs-lookup"><span data-stu-id="d2005-123">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="d2005-124">Загрузка набора данных из XML</span><span class="sxs-lookup"><span data-stu-id="d2005-124">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="d2005-125">Загрузка сведений о схеме набора данных из XML</span><span class="sxs-lookup"><span data-stu-id="d2005-125">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="d2005-126">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="d2005-126">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="d2005-127">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="d2005-127">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="d2005-128">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d2005-128">ADO.NET Overview</span></span>](../ado-net-overview.md)
