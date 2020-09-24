---
title: Наследование реляционной структуры набора данных от схемы XML (XSD)
ms.date: 03/30/2017
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
ms.openlocfilehash: 878e39af575328fb0abba096c327d36203a52231
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164809"
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a><span data-ttu-id="2a9de-102">Наследование реляционной структуры набора данных от схемы XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="2a9de-102">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>

<span data-ttu-id="2a9de-103">В этом разделе приведены общие сведения о построении реляционной схемы `DataSet` на основе документа схемы на языке XSD.</span><span class="sxs-lookup"><span data-stu-id="2a9de-103">This section provides an overview of how the relational schema of a `DataSet` is built from an XML Schema definition language (XSD) schema document.</span></span> <span data-ttu-id="2a9de-104">Как правило, для каждого `complexType` дочернего элемента в элементе Schema создается таблица в `DataSet` .</span><span class="sxs-lookup"><span data-stu-id="2a9de-104">In general, for each `complexType` child element of a schema element, a table is generated in the `DataSet`.</span></span> <span data-ttu-id="2a9de-105">Структура таблицы задается определением сложного типа.</span><span class="sxs-lookup"><span data-stu-id="2a9de-105">The table structure is determined by the definition of the complex type.</span></span> <span data-ttu-id="2a9de-106">Таблицы создаются в `DataSet` для элементов верхнего уровня схемы.</span><span class="sxs-lookup"><span data-stu-id="2a9de-106">Tables are created in the `DataSet` for top-level elements in the schema.</span></span> <span data-ttu-id="2a9de-107">Однако таблица создается только для элемента верхнего уровня `complexType` `complexType` , если элемент вложен в другой `complexType` элемент. в этом случае вложенный `complexType` элемент сопоставляется с элементом в `DataTable` `DataSet` .</span><span class="sxs-lookup"><span data-stu-id="2a9de-107">However, a table is only created for a top-level `complexType` element when the `complexType` element is nested inside another `complexType` element, in which case the nested `complexType` element is mapped to a `DataTable` within the `DataSet`.</span></span>  
  
 <span data-ttu-id="2a9de-108">Дополнительные сведения о XSD см. в разделе консорциум W3C (W3C) [XML-схема, часть 0: рекомендации по основам](https://www.w3.org/TR/xmlschema-0/), [рекомендации по схеме XML Part 1:](https://www.w3.org/TR/xmlschema-1/)Structures и [XML Schema, часть 2: рекомендации по типам](https://www.w3.org/TR/xmlschema-2/)данных.</span><span class="sxs-lookup"><span data-stu-id="2a9de-108">For more information about the XSD, see the World Wide Web Consortium (W3C) [XML Schema Part 0: Primer Recommendation](https://www.w3.org/TR/xmlschema-0/), the [XML Schema Part 1: Structures Recommendation](https://www.w3.org/TR/xmlschema-1/), and the [XML Schema Part 2: Datatypes Recommendation](https://www.w3.org/TR/xmlschema-2/).</span></span>  
  
 <span data-ttu-id="2a9de-109">В следующем примере показана схема XML `customers` , где — это дочерний элемент `MyDataSet` элемента DataSet, который является элементом **набора данных** .</span><span class="sxs-lookup"><span data-stu-id="2a9de-109">The following example demonstrates an XML Schema where `customers` is the child element of the `MyDataSet` element, which is a **DataSet** element.</span></span>  
  
```xml  
<xs:schema id="SomeID"
            xmlns=""
            xmlns:xs="http://www.w3.org/2001/XMLSchema"
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:element name="MyDataSet" msdata:IsDataSet="true">  
     <xs:complexType>  
       <xs:choice maxOccurs="unbounded">  
         <xs:element name="customers" >
           <xs:complexType >  
             <xs:sequence>  
               <xs:element name="CustomerID" type="xs:integer"
                            minOccurs="0" />  
               <xs:element name="CompanyName" type="xs:string"
                            minOccurs="0" />  
               <xs:element name="Phone" type="xs:string" />  
             </xs:sequence>  
           </xs:complexType>  
          </xs:element>  
       </xs:choice>  
     </xs:complexType>  
   </xs:element>  
 </xs:schema>  
```  
  
 <span data-ttu-id="2a9de-110">В предыдущем примере элемент `customers` является элементом сложного типа.</span><span class="sxs-lookup"><span data-stu-id="2a9de-110">In the preceding example, the element `customers` is a complex type element.</span></span> <span data-ttu-id="2a9de-111">Поэтому проводится синтаксический анализ определения сложного типа, а процесс сопоставления создает следующую таблицу.</span><span class="sxs-lookup"><span data-stu-id="2a9de-111">Therefore, the complex type definition is parsed, and the mapping process creates the following table.</span></span>  
  
```text  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="2a9de-112">Тип данных каждого столбца в таблице получается из типа схемы XML соответствующего элемента или указанного атрибута.</span><span class="sxs-lookup"><span data-stu-id="2a9de-112">The data type of each column in the table is derived from the XML Schema type of the corresponding element or attribute specified.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2a9de-113">Если элемент `customers` имеет простой тип данных схемы XML, такой как **Integer**, таблица не создается.</span><span class="sxs-lookup"><span data-stu-id="2a9de-113">If the element `customers` is of a simple XML Schema data type such as **integer**, no table is generated.</span></span> <span data-ttu-id="2a9de-114">Таблицы создаются только для элементов верхнего уровня, которые являются сложными типами.</span><span class="sxs-lookup"><span data-stu-id="2a9de-114">Tables are only created for the top-level elements that are complex types.</span></span>  
  
 <span data-ttu-id="2a9de-115">В следующей схеме XML элемент **Schema** имеет два дочерних элемента, `InStateCustomers` и `OutOfStateCustomers` .</span><span class="sxs-lookup"><span data-stu-id="2a9de-115">In the following XML Schema, the **Schema** element has two element children, `InStateCustomers` and `OutOfStateCustomers`.</span></span>  
  
```xml  
<xs:schema id="SomeID"
            xmlns=""
            xmlns:xs="http://www.w3.org/2001/XMLSchema"
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:element name="InStateCustomers" type="customerType" />  
   <xs:element name="OutOfStateCustomers" type="customerType" />  
    <xs:complexType name="customerType" >  
  
     </xs:complexType>  
  
   <xs:element name="MyDataSet" msdata:IsDataSet="true">  
     <xs:complexType>  
       <xs:choice maxOccurs="unbounded">  
         <xs:element ref="customers" />  
       </xs:choice>  
     </xs:complexType>  
   </xs:element>  
 </xs:schema>  
```  
  
 <span data-ttu-id="2a9de-116">Дочерние элементы `InStateCustomers` и `OutOfStateCustomers` являются элементами сложного типа (`customerType`).</span><span class="sxs-lookup"><span data-stu-id="2a9de-116">Both the `InStateCustomers` and the `OutOfStateCustomers` child elements are complex type elements (`customerType`).</span></span> <span data-ttu-id="2a9de-117">Таким образом, процесс сопоставления создает следующие две идентичные таблицы в `DataSet` .</span><span class="sxs-lookup"><span data-stu-id="2a9de-117">Therefore, the mapping process generates the following two identical tables in the `DataSet`.</span></span>  
  
```text  
InStateCustomers (CustomerID, CompanyName, Phone)  
OutOfStateCustomers (CustomerID, CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="2a9de-118">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="2a9de-118">In This Section</span></span>  

 [<span data-ttu-id="2a9de-119">Сопоставление ограничений XML-схемы (XSD) с ограничениями набора данных</span><span class="sxs-lookup"><span data-stu-id="2a9de-119">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="2a9de-120">Описывает элементы XML-схемы, используемые для создания ограничений UNIQUE и FOREIGN KEY в `DataSet` .</span><span class="sxs-lookup"><span data-stu-id="2a9de-120">Describes the XML Schema elements used to create unique and foreign key constraints in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="2a9de-121">Создание отношений наборов данных из схемы XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="2a9de-121">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)  
 <span data-ttu-id="2a9de-122">Описывает элементы XML-схемы, используемые для создания связей между столбцами таблицы в `DataSet` .</span><span class="sxs-lookup"><span data-stu-id="2a9de-122">Describes the XML Schema elements used to create relations between table columns in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="2a9de-123">Ограничения и отношения схемы XML</span><span class="sxs-lookup"><span data-stu-id="2a9de-123">XML Schema Constraints and Relationships</span></span>](xml-schema-constraints-and-relationships.md)  
 <span data-ttu-id="2a9de-124">Описывает, как неявным образом создаются связи при использовании элементов схемы XML для создания ограничений в `DataSet` .</span><span class="sxs-lookup"><span data-stu-id="2a9de-124">Describes how relations are created implicitly when using XML Schema elements to create constraints in a `DataSet`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2a9de-125">См. также</span><span class="sxs-lookup"><span data-stu-id="2a9de-125">Related Sections</span></span>  

 [<span data-ttu-id="2a9de-126">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="2a9de-126">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)  
 <span data-ttu-id="2a9de-127">Описывает загрузку и сохранение реляционной структуры и данных в `DataSet` виде XML-данных.</span><span class="sxs-lookup"><span data-stu-id="2a9de-127">Describes how to load and persist the relational structure and data in a `DataSet` as XML data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a9de-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2a9de-128">See also</span></span>

- [<span data-ttu-id="2a9de-129">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2a9de-129">ADO.NET Overview</span></span>](../ado-net-overview.md)
