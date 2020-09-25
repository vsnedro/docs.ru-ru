---
title: Запись сведений о схеме набора данных как XSD
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4e530831-695e-49ff-8f0b-e5b0c526b8eb
ms.openlocfilehash: 7634dfc8415b6f73fc60f2ebe59c92a0c31f83a2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173735"
---
# <a name="writing-dataset-schema-information-as-xsd"></a><span data-ttu-id="bbe96-102">Запись сведений о схеме набора данных как XSD</span><span class="sxs-lookup"><span data-stu-id="bbe96-102">Writing DataSet Schema Information as XSD</span></span>

<span data-ttu-id="bbe96-103">Можно записать схему набора данных <xref:System.Data.DataSet> в виде схемы на языке XSD, чтобы можно было передать ее в XML-документ с взаимосвязанными данными или без них.</span><span class="sxs-lookup"><span data-stu-id="bbe96-103">You can write the schema of a <xref:System.Data.DataSet> as XML Schema definition language (XSD) schema, so that you can transport it, with or without related data, in an XML document.</span></span> <span data-ttu-id="bbe96-104">XML-схема может быть записана в файл, в поток, в <xref:System.Xml.XmlWriter> или строку; она полезна для создания строго типизированного **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="bbe96-104">XML Schema can be written to a file, a stream, an <xref:System.Xml.XmlWriter>, or a string; it is useful for generating a strongly typed **DataSet**.</span></span> <span data-ttu-id="bbe96-105">Дополнительные сведения о строго типизированных объектах DataSet см. в разделе [типизированные наборы](typed-datasets.md) **данных** .</span><span class="sxs-lookup"><span data-stu-id="bbe96-105">For more information about strongly typed **DataSet** objects, see [Typed DataSets](typed-datasets.md).</span></span>  
  
 <span data-ttu-id="bbe96-106">Можно указать способ представления столбца таблицы в XML-схеме с помощью свойства **ColumnMapping** <xref:System.Data.DataColumn> объекта.</span><span class="sxs-lookup"><span data-stu-id="bbe96-106">You can specify how a column of a table is represented in XML Schema using the **ColumnMapping** property of the <xref:System.Data.DataColumn> object.</span></span> <span data-ttu-id="bbe96-107">Дополнительные сведения см. в разделе «Сопоставление столбцов с XML-элементами, атрибутами и текстом» [статьи запись содержимого набора данных в виде XML-данных](writing-dataset-contents-as-xml-data.md).</span><span class="sxs-lookup"><span data-stu-id="bbe96-107">For more information, see "Mapping Columns to XML Elements, Attributes, and Text" in [Writing DataSet Contents as XML Data](writing-dataset-contents-as-xml-data.md).</span></span>  
  
 <span data-ttu-id="bbe96-108">Для записи схемы **набора данных** в виде XML-схемы в файл, поток или **XmlWriter**используйте метод **вритексмлсчема** **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="bbe96-108">To write the schema of a **DataSet** as XML Schema, to a file, stream, or **XmlWriter**, use the **WriteXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="bbe96-109">**Вритексмлсчема** принимает один параметр, который задает назначение результирующей схемы XML.</span><span class="sxs-lookup"><span data-stu-id="bbe96-109">**WriteXmlSchema** takes one parameter that specifies the destination of the resulting XML Schema.</span></span> <span data-ttu-id="bbe96-110">В следующих примерах кода показано, как записать XML-схему **набора данных** в файл, передав строку, содержащую имя файла и <xref:System.IO.StreamWriter> объект.</span><span class="sxs-lookup"><span data-stu-id="bbe96-110">The following code examples demonstrate how to write the XML Schema of a **DataSet** to a file by passing a string containing a file name and a <xref:System.IO.StreamWriter> object.</span></span>  
  
```vb  
dataSet.WriteXmlSchema("Customers.xsd")  
```  
  
```csharp  
dataSet.WriteXmlSchema("Customers.xsd");  
```  
  
```vb  
Dim writer As System.IO.StreamWriter = New System.IO.StreamWriter("Customers.xsd")  
dataSet.WriteXmlSchema(writer)  
writer.Close()  
```  
  
```csharp  
System.IO.StreamWriter writer = new System.IO.StreamWriter("Customers.xsd");  
dataSet.WriteXmlSchema(writer);  
writer.Close();  
```  
  
 <span data-ttu-id="bbe96-111">Чтобы получить схему **набора данных** и записать ее в виде строки XML-схемы, **используйте метод GetString** , как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="bbe96-111">To obtain the schema of a **DataSet** and write it as an XML Schema string, use the **GetXmlSchema** method, as shown in the following example.</span></span>  
  
```vb  
Dim schemaString As String = dataSet.GetXmlSchema()  
```  
  
```csharp  
string schemaString = dataSet.GetXmlSchema();  
```  
  
## <a name="see-also"></a><span data-ttu-id="bbe96-112">См. также</span><span class="sxs-lookup"><span data-stu-id="bbe96-112">See also</span></span>

- [<span data-ttu-id="bbe96-113">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="bbe96-113">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="bbe96-114">Запись содержимого набора как данных XML</span><span class="sxs-lookup"><span data-stu-id="bbe96-114">Writing DataSet Contents as XML Data</span></span>](writing-dataset-contents-as-xml-data.md)
- [<span data-ttu-id="bbe96-115">Типизированные наборы данных</span><span class="sxs-lookup"><span data-stu-id="bbe96-115">Typed DataSets</span></span>](typed-datasets.md)
- [<span data-ttu-id="bbe96-116">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="bbe96-116">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="bbe96-117">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="bbe96-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
