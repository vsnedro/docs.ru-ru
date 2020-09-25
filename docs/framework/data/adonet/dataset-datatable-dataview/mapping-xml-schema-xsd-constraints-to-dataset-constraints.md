---
title: Сопоставление ограничений XML-схемы (XSD) с ограничениями набора данных
ms.date: 03/30/2017
ms.assetid: 3d0d1a4b-9104-434f-ac04-6c01ab5716b5
ms.openlocfilehash: a2b28b0dcb2e2858c7328854650667f51e83166a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185292"
---
# <a name="mapping-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="b89c6-102">Сопоставление ограничений XML-схемы (XSD) с ограничениями набора данных</span><span class="sxs-lookup"><span data-stu-id="b89c6-102">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>

<span data-ttu-id="b89c6-103">Язык XSD позволяет задавать ограничения применительно к элементам и атрибутам, которые он определяет.</span><span class="sxs-lookup"><span data-stu-id="b89c6-103">The XML Schema definition language (XSD) allows constraints to be specified on the elements and attributes it defines.</span></span> <span data-ttu-id="b89c6-104">При сопоставлении схемы XML с реляционной схемой в <xref:System.Data.DataSet> ограничения XML-схемы сопоставляются с соответствующими реляционными ограничениями для таблиц и столбцов в **наборе данных**.</span><span class="sxs-lookup"><span data-stu-id="b89c6-104">When mapping an XML Schema to relational schema in a <xref:System.Data.DataSet>, XML Schema constraints are mapped to appropriate relational constraints on the tables and columns within the **DataSet**.</span></span>  
  
 <span data-ttu-id="b89c6-105">В этом разделе рассматривается сопоставление следующих ограничений схемы XML:</span><span class="sxs-lookup"><span data-stu-id="b89c6-105">This section discusses the mapping of the following XML Schema constraints:</span></span>  
  
- <span data-ttu-id="b89c6-106">Ограничение уникальности, заданное с помощью **уникального** элемента.</span><span class="sxs-lookup"><span data-stu-id="b89c6-106">The uniqueness constraint specified using the **unique** element.</span></span>  
  
- <span data-ttu-id="b89c6-107">Ограничение Key, заданное с помощью элемента **Key** .</span><span class="sxs-lookup"><span data-stu-id="b89c6-107">The key constraint specified using the **key** element.</span></span>  
  
- <span data-ttu-id="b89c6-108">Ограничение keyref, заданное с помощью элемента **keyref** .</span><span class="sxs-lookup"><span data-stu-id="b89c6-108">The keyref constraint specified using the **keyref** element.</span></span>  
  
 <span data-ttu-id="b89c6-109">С помощью ограничения элемента или атрибута задаются определенные ограничения значений элемента в любом экземпляре документа.</span><span class="sxs-lookup"><span data-stu-id="b89c6-109">By using a constraint on an element or attribute, you specify certain restrictions on the values of the element in any instance of the document.</span></span> <span data-ttu-id="b89c6-110">Например, ограничение ключа для дочернего элемента **CustomerID** элемента **Customer** в схеме указывает на то, что значения дочернего элемента **CustomerID** должны быть уникальными в любом экземпляре документа, и эти значения NULL не допускаются.</span><span class="sxs-lookup"><span data-stu-id="b89c6-110">For example, a key constraint on a **CustomerID** child element of a **Customer** element in the schema indicates that the values of the **CustomerID** child element must be unique in any document instance, and that null values are not allowed.</span></span>  
  
 <span data-ttu-id="b89c6-111">Ограничения также можно указывать между элементами и атрибутами документа для установления связи внутри документа.</span><span class="sxs-lookup"><span data-stu-id="b89c6-111">Constraints can also be specified between elements and attributes in a document, in order to establish a relationship within the document.</span></span> <span data-ttu-id="b89c6-112">Ограничения key и keyref используются в схеме для указания ограничения внутри документа, что приводит к созданию связи между элементами и атрибутами документа.</span><span class="sxs-lookup"><span data-stu-id="b89c6-112">The key and keyref constraints are used in the schema to specify the constraints within the document, resulting in a relationship between document elements and attributes.</span></span>  
  
 <span data-ttu-id="b89c6-113">Процесс сопоставления преобразует эти ограничения схемы в соответствующие ограничения для таблиц, созданных в **наборе данных**.</span><span class="sxs-lookup"><span data-stu-id="b89c6-113">The mapping process converts these schema constraints into appropriate constraints on the tables created within the **DataSet**.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b89c6-114">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="b89c6-114">In This Section</span></span>  

 [<span data-ttu-id="b89c6-115">Сопоставление уникальных ограничений XML-схемы (XSD) с ограничениями набора данных</span><span class="sxs-lookup"><span data-stu-id="b89c6-115">Map unique XML Schema (XSD) Constraints to DataSet Constraints</span></span>](map-unique-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="b89c6-116">Описывает элементы XML-схемы, используемые для создания ограничений UNIQUE в **наборе данных**.</span><span class="sxs-lookup"><span data-stu-id="b89c6-116">Describes the XML Schema elements used to create unique constraints in a **DataSet**.</span></span>  
  
 [<span data-ttu-id="b89c6-117">Сопоставление ключевых ограничений XML-схемы (XSD) с ограничениями набора данных</span><span class="sxs-lookup"><span data-stu-id="b89c6-117">Map key XML Schema (XSD) Constraints to DataSet Constraints</span></span>](map-key-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="b89c6-118">Описывает элементы XML-схемы, используемые для создания ограничений ключа (ограничения UNIQUE, в которых значения NULL не допускаются) в **наборе данных**.</span><span class="sxs-lookup"><span data-stu-id="b89c6-118">Describes the XML Schema elements used to create key constraints (unique constraints where null values are not allowed) in a **DataSet**.</span></span>  
  
 [<span data-ttu-id="b89c6-119">Сопоставление ограничений XML-схемы (XSD) keyref с ограничениями набора данных</span><span class="sxs-lookup"><span data-stu-id="b89c6-119">Map keyref XML Schema (XSD) Constraints to DataSet Constraints</span></span>](map-keyref-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="b89c6-120">Описывает элементы XML-схемы, используемые для создания ограничений keyref (FOREIGN KEY) в **наборе данных**.</span><span class="sxs-lookup"><span data-stu-id="b89c6-120">Describes the XML Schema elements used to create keyref (foreign key) constraints in a **DataSet**.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b89c6-121">См. также</span><span class="sxs-lookup"><span data-stu-id="b89c6-121">Related Sections</span></span>  

 [<span data-ttu-id="b89c6-122">Наследование реляционной структуры набора данных от схемы XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="b89c6-122">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="b89c6-123">Описывает реляционную структуру или схему **набора данных** , созданного из схемы XSD.</span><span class="sxs-lookup"><span data-stu-id="b89c6-123">Describes the relational structure, or schema, of a **DataSet** that is created from XSD schema.</span></span>  
  
 [<span data-ttu-id="b89c6-124">Создание отношений наборов данных из схемы XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="b89c6-124">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)  
 <span data-ttu-id="b89c6-125">Описывает элементы XML-схемы, используемые для создания связей между столбцами таблицы в **наборе данных**.</span><span class="sxs-lookup"><span data-stu-id="b89c6-125">Describes the XML Schema elements used to create relations between table columns in a **DataSet**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b89c6-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b89c6-126">See also</span></span>

- [<span data-ttu-id="b89c6-127">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b89c6-127">ADO.NET Overview</span></span>](../ado-net-overview.md)
