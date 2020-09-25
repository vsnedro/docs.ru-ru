---
title: Указание отношений между элементами без вложенности
ms.date: 03/30/2017
ms.assetid: e31325da-7691-4d33-acf4-99fccca67006
ms.openlocfilehash: 6684e992242d5c695f3c237f70de61b4dae1c48f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183407"
---
# <a name="specify-relations-between-elements-with-no-nesting"></a><span data-ttu-id="dbed0-102">Указание отношений между элементами без вложенности</span><span class="sxs-lookup"><span data-stu-id="dbed0-102">Specify Relations Between Elements with No Nesting</span></span>

<span data-ttu-id="dbed0-103">Если элементы не вложены, какие-либо неявные связи не создаются.</span><span class="sxs-lookup"><span data-stu-id="dbed0-103">When elements are not nested, no implicit relations are created.</span></span> <span data-ttu-id="dbed0-104">Однако можно явно указать связи между элементами, которые не вложены с помощью аннотации **msdata: relationship** .</span><span class="sxs-lookup"><span data-stu-id="dbed0-104">You can, however, explicitly specify relations between elements that are not nested by using the **msdata:Relationship** annotation.</span></span>  
  
 <span data-ttu-id="dbed0-105">В следующем примере показана схема XML, в которой заметка **msdata: relationship** задается между элементами **Order** и **OrderDetail** , которые не являются вложенными.</span><span class="sxs-lookup"><span data-stu-id="dbed0-105">The following example shows an XML Schema in which the **msdata:Relationship** annotation is specified between the **Order** and **OrderDetail** elements, which are not nested.</span></span> <span data-ttu-id="dbed0-106">Аннотация **msdata: relationship** указывается как дочерний элемент элемента **Schema** .</span><span class="sxs-lookup"><span data-stu-id="dbed0-106">The **msdata:Relationship** annotation is specified as the child element of the **Schema** element.</span></span>  
  
```xml  
<xs:schema id="MyDataSet" xmlns=""
             xmlns:xs="http://www.w3.org/2001/XMLSchema"
             xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element name="OrderDetail">  
       <xs:complexType>  
         <xs:sequence>  
           <xs:element name="OrderNo" type="xs:string" />  
           <xs:element name="ItemNo" type="xs:string" />  
         </xs:sequence>  
       </xs:complexType>  
      </xs:element>  
      <xs:element name="Order">  
       <xs:complexType>  
         <xs:sequence>  
           <xs:element name="OrderNumber" type="xs:string" />  
           <xs:element name="EmpNumber" type="xs:string" />  
         </xs:sequence>  
       </xs:complexType>  
      </xs:element>  
    </xs:choice>  
  </xs:complexType>  
  
  </xs:element>  
   <xs:annotation>  
     <xs:appinfo>  
       <msdata:Relationship name="OrdOrderDetailRelation"  
                            msdata:parent="Order"
                            msdata:child="OrderDetail"
                            msdata:parentkey="OrderNumber"
                            msdata:childkey="OrderNo"/>  
     </xs:appinfo>  
  </xs:annotation>  
</xs:schema>  
```  
  
 <span data-ttu-id="dbed0-107">В процессе сопоставления схемы языка определения схемы XML (XSD) создаются <xref:System.Data.DataSet> таблицы **Order** и **OrderDetail** и связь, указанная между этими двумя таблицами, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="dbed0-107">The XML Schema definition language (XSD) schema mapping process creates a <xref:System.Data.DataSet> with **Order** and **OrderDetail** tables and a relationship specified between these two tables, as shown below.</span></span>  
  
```text  
RelationName: OrdOrderDetailRelation  
ParentTable: Order  
ParentColumns: OrderNumber
ChildTable: OrderDetail  
ChildColumns: OrderNo
Nested: False  
```  
  
## <a name="see-also"></a><span data-ttu-id="dbed0-108">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="dbed0-108">See also</span></span>

- [<span data-ttu-id="dbed0-109">Создание отношений наборов данных из схемы XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="dbed0-109">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="dbed0-110">Сопоставление ограничений XML-схемы (XSD) с ограничениями набора данных</span><span class="sxs-lookup"><span data-stu-id="dbed0-110">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="dbed0-111">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="dbed0-111">ADO.NET Overview</span></span>](../ado-net-overview.md)
