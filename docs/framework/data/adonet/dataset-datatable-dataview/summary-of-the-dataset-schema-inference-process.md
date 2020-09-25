---
title: Общие сведения о процессе определения схемы набора данных
ms.date: 03/30/2017
ms.assetid: fd0891c8-d068-4e30-a76f-7c375f078bf7
ms.openlocfilehash: 8d517487b96aa7f204ea9f25d326500db7df413a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198513"
---
# <a name="summary-of-the-dataset-schema-inference-process"></a><span data-ttu-id="c78d5-102">Общие сведения о процессе определения схемы набора данных</span><span class="sxs-lookup"><span data-stu-id="c78d5-102">Summary of the DataSet Schema Inference Process</span></span>

<span data-ttu-id="c78d5-103">Процесс вывода схемы из XML-документа вначале определяет, какие элементы будут выведены как таблицы.</span><span class="sxs-lookup"><span data-stu-id="c78d5-103">The inference process first determines, from the XML document, which elements will be inferred as tables.</span></span> <span data-ttu-id="c78d5-104">Из оставшегося XML процесс вывода схемы определяет столбцы этих таблиц.</span><span class="sxs-lookup"><span data-stu-id="c78d5-104">From the remaining XML, the inference process determines the columns for those tables.</span></span> <span data-ttu-id="c78d5-105">Для вложенных таблиц процесс вывода формирует вложенные объекты <xref:System.Data.DataRelation> и <xref:System.Data.ForeignKeyConstraint>.</span><span class="sxs-lookup"><span data-stu-id="c78d5-105">For nested tables, the inference process generates nested <xref:System.Data.DataRelation> and <xref:System.Data.ForeignKeyConstraint> objects.</span></span>  
  
 <span data-ttu-id="c78d5-106">Ниже приведен краткий обзор правил вывода.</span><span class="sxs-lookup"><span data-stu-id="c78d5-106">The following is a brief summary of inference rules:</span></span>  
  
- <span data-ttu-id="c78d5-107">Элементы с атрибутами выводятся как таблицы.</span><span class="sxs-lookup"><span data-stu-id="c78d5-107">Elements that have attributes are inferred as tables.</span></span>  
  
- <span data-ttu-id="c78d5-108">Элементы, имеющие дочерние элементы, выводятся как таблицы.</span><span class="sxs-lookup"><span data-stu-id="c78d5-108">Elements that have child elements are inferred as tables.</span></span>  
  
- <span data-ttu-id="c78d5-109">Повторяющиеся элементы выводятся как одна таблица.</span><span class="sxs-lookup"><span data-stu-id="c78d5-109">Elements that repeat are inferred as a single table.</span></span>  
  
- <span data-ttu-id="c78d5-110">Если элемент документа (корневой элемент) не имеет ни атрибутов, ни дочерних элементов, которые выводились бы как столбцы, он выводится как <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="c78d5-110">If the document, or root, element has no attributes, and no child elements that would be inferred as columns, it is inferred as a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="c78d5-111">В противном случае элемент документа выводится как таблица.</span><span class="sxs-lookup"><span data-stu-id="c78d5-111">Otherwise, the document element is inferred as a table.</span></span>  
  
- <span data-ttu-id="c78d5-112">Атрибуты выводятся как столбцы.</span><span class="sxs-lookup"><span data-stu-id="c78d5-112">Attributes are inferred as columns.</span></span>  
  
- <span data-ttu-id="c78d5-113">Элементы, которые не повторяются и не имеют ни атрибутов, ни дочерних элементов, выводятся как столбцы.</span><span class="sxs-lookup"><span data-stu-id="c78d5-113">Elements that have no attributes or child elements, and that do not repeat, are inferred as columns.</span></span>  
  
- <span data-ttu-id="c78d5-114">Для элементов, которые выводятся в виде вложенных таблиц в других элементах, которые также выводятся в виде таблиц, между двумя таблицами создается вложенная **связь DataRelation** .</span><span class="sxs-lookup"><span data-stu-id="c78d5-114">For elements that are inferred as nested tables within other elements that are also inferred as tables, a nested **DataRelation** is created between the two tables.</span></span> <span data-ttu-id="c78d5-115">Новый первичный ключевой столбец с именем **TableName_Id** добавляется в обе таблицы и используется **DataRelation**.</span><span class="sxs-lookup"><span data-stu-id="c78d5-115">A new, primary key column named **TableName_Id** is added to both tables and used by the **DataRelation**.</span></span> <span data-ttu-id="c78d5-116">Объект **ForeignKeyConstraint** создается между двумя таблицами, использующими столбец **TableName_Id** .</span><span class="sxs-lookup"><span data-stu-id="c78d5-116">A **ForeignKeyConstraint** is created between the two tables using the **TableName_Id** column.</span></span>  
  
- <span data-ttu-id="c78d5-117">Для элементов, которые выводятся в виде таблиц и содержат текст, но не имеют дочерних элементов, для текста каждого элемента создается новый столбец с именем **TableName_Text** .</span><span class="sxs-lookup"><span data-stu-id="c78d5-117">For elements that are inferred as tables and that contain text but have no child elements, a new column named **TableName_Text** is created for the text of each of the elements.</span></span> <span data-ttu-id="c78d5-118">Если элемент выводится как таблица и имеет текст, но при этом имеет дочерние элементы, текст пропускается.</span><span class="sxs-lookup"><span data-stu-id="c78d5-118">If an element is inferred as a table and has text, but also has child elements, the text is ignored.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c78d5-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c78d5-119">See also</span></span>

- [<span data-ttu-id="c78d5-120">Определение реляционной структуры набора данных из XML</span><span class="sxs-lookup"><span data-stu-id="c78d5-120">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="c78d5-121">Загрузка набора данных из XML</span><span class="sxs-lookup"><span data-stu-id="c78d5-121">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="c78d5-122">Загрузка сведений о схеме набора данных из XML</span><span class="sxs-lookup"><span data-stu-id="c78d5-122">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="c78d5-123">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="c78d5-123">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="c78d5-124">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="c78d5-124">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="c78d5-125">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c78d5-125">ADO.NET Overview</span></span>](../ado-net-overview.md)
