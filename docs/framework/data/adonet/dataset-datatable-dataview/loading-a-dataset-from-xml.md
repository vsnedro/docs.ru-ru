---
title: Загрузка набора данных из XML
description: Узнайте, как добавить содержимое в набор данных ADO.NET из XML. .NET Framework обеспечивает гибкость для загрузки и структуры набора данных.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49c083b7-a5ed-41cf-aabc-5aaba96f00e6
ms.openlocfilehash: 77715913c24423c1dc95478977f4e3821e4c247b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90545315"
---
# <a name="loading-a-dataset-from-xml"></a><span data-ttu-id="515e0-104">Загрузка набора данных из XML</span><span class="sxs-lookup"><span data-stu-id="515e0-104">Loading a DataSet from XML</span></span>
<span data-ttu-id="515e0-105">Содержимое объекта <xref:System.Data.DataSet> технологии ADO.NET может быть создано на основе XML-потока или XML-документа.</span><span class="sxs-lookup"><span data-stu-id="515e0-105">The contents of an ADO.NET <xref:System.Data.DataSet> can be created from an XML stream or document.</span></span> <span data-ttu-id="515e0-106">Кроме того, использование .NET Framework обеспечивает большую гибкость при выборе сведений, загружаемых из XML, а также способа создания схемы или реляционной структуры <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="515e0-106">In addition, with the .NET Framework you have great flexibility over what information is loaded from XML, and how the schema or relational structure of the <xref:System.Data.DataSet> is created.</span></span>  
  
 <span data-ttu-id="515e0-107">Для заполнения <xref:System.Data.DataSet> данными из XML используйте метод **ReadXml** <xref:System.Data.DataSet> объекта.</span><span class="sxs-lookup"><span data-stu-id="515e0-107">To fill a <xref:System.Data.DataSet> with data from XML, use the **ReadXml** method of the <xref:System.Data.DataSet> object.</span></span> <span data-ttu-id="515e0-108">Метод **ReadXml** считывает данные из файла, потока или **XmlReader**и принимает в качестве аргументов источник XML и необязательный аргумент **XmlReadMode** .</span><span class="sxs-lookup"><span data-stu-id="515e0-108">The **ReadXml** method reads from a file, a stream, or an **XmlReader**, and takes as arguments the source of the XML plus an optional **XmlReadMode** argument.</span></span> <span data-ttu-id="515e0-109">Дополнительные сведения о **XmlReader**см. в разделе [чтение XML-данных с помощью XmlTextReader](/previous-versions/dotnet/netframework-4.0/tfz3cz6w(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="515e0-109">For more information about the **XmlReader**, see [Reading XML Data with XmlTextReader](/previous-versions/dotnet/netframework-4.0/tfz3cz6w(v=vs.100)).</span></span> <span data-ttu-id="515e0-110">Метод **ReadXml** считывает содержимое XML-потока или документа и загружает <xref:System.Data.DataSet> с данными.</span><span class="sxs-lookup"><span data-stu-id="515e0-110">The **ReadXml** method reads the contents of the XML stream or document and loads the <xref:System.Data.DataSet> with data.</span></span> <span data-ttu-id="515e0-111">Также будет создана реляционная схема в <xref:System.Data.DataSet> зависимости от указанного параметра **XmlReadMode** и наличия уже существующей реляционной схемы.</span><span class="sxs-lookup"><span data-stu-id="515e0-111">It will also create the relational schema of the <xref:System.Data.DataSet> depending on the **XmlReadMode** specified and whether or not a relational schema already exists.</span></span>  
  
 <span data-ttu-id="515e0-112">В следующей таблице описаны параметры для аргумента **XmlReadMode** .</span><span class="sxs-lookup"><span data-stu-id="515e0-112">The following table describes the options for the **XmlReadMode** argument.</span></span>  
  
|<span data-ttu-id="515e0-113">Параметр</span><span class="sxs-lookup"><span data-stu-id="515e0-113">Option</span></span>|<span data-ttu-id="515e0-114">Описание</span><span class="sxs-lookup"><span data-stu-id="515e0-114">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="515e0-115">**Автоматически**</span><span class="sxs-lookup"><span data-stu-id="515e0-115">**Auto**</span></span>|<span data-ttu-id="515e0-116">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="515e0-116">This is the default.</span></span> <span data-ttu-id="515e0-117">Анализирует XML и выбирает наиболее подходящий параметр в следующем порядке.</span><span class="sxs-lookup"><span data-stu-id="515e0-117">Examines the XML and chooses the most appropriate option in the following order:</span></span><br /><br /> <span data-ttu-id="515e0-118">— Если XML является DiffGram, используется **DiffGram** .</span><span class="sxs-lookup"><span data-stu-id="515e0-118">-   If the XML is a DiffGram, **DiffGram** is used.</span></span><br /><span data-ttu-id="515e0-119">— Если <xref:System.Data.DataSet> содержит схему или XML содержит встроенную схему, используется **реадсчема** .</span><span class="sxs-lookup"><span data-stu-id="515e0-119">-   If the <xref:System.Data.DataSet> contains a schema or the XML contains an inline schema, **ReadSchema** is used.</span></span><br /><span data-ttu-id="515e0-120">— Если объект не <xref:System.Data.DataSet> содержит схему и XML не содержит встроенную схему, используется **инферсчема** .</span><span class="sxs-lookup"><span data-stu-id="515e0-120">-   If the <xref:System.Data.DataSet> does not contain a schema and the XML does not contain an inline schema, **InferSchema** is used.</span></span><br /><br /> <span data-ttu-id="515e0-121">Если вы знакомы с форматом считываемых данных XML, рекомендуется установить явное значение **XmlReadMode**, а не **принимать значение по умолчанию** .</span><span class="sxs-lookup"><span data-stu-id="515e0-121">If you know the format of the XML being read, for best performance it is recommended that you set an explicit **XmlReadMode**, rather than accept the **Auto** default.</span></span>|  
|<span data-ttu-id="515e0-122">**ReadSchema**</span><span class="sxs-lookup"><span data-stu-id="515e0-122">**ReadSchema**</span></span>|<span data-ttu-id="515e0-123">Считывает любую встроенную схему и загружает данные и схему.</span><span class="sxs-lookup"><span data-stu-id="515e0-123">Reads any inline schema and loads the data and schema.</span></span><br /><br /> <span data-ttu-id="515e0-124">Если набор данных <xref:System.Data.DataSet> уже содержит схему, новые таблицы добавляются из встроенной схемы в существующую в наборе данных <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="515e0-124">If the <xref:System.Data.DataSet> already contains a schema, new tables are added from the inline schema to the existing schema in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="515e0-125">Если любая таблица встроенной схемы уже существует в наборе данных <xref:System.Data.DataSet>, возникает исключение.</span><span class="sxs-lookup"><span data-stu-id="515e0-125">If any tables in the inline schema already exist in the <xref:System.Data.DataSet>, an exception is thrown.</span></span> <span data-ttu-id="515e0-126">Вы не сможете изменить схему существующей таблицы с помощью параметра **XmlReadMode. реадсчема**.</span><span class="sxs-lookup"><span data-stu-id="515e0-126">You will not be able to modify the schema of an existing table using **XmlReadMode.ReadSchema**.</span></span><br /><br /> <span data-ttu-id="515e0-127">Если набор данных <xref:System.Data.DataSet> не содержит схему, а также отсутствует встроенная схема, то данные не считываются.</span><span class="sxs-lookup"><span data-stu-id="515e0-127">If the <xref:System.Data.DataSet> does not contain a schema, and there is no inline schema, no data is read.</span></span><br /><br /> <span data-ttu-id="515e0-128">Встроенная схема может быть определена с помощью схемы на языке XSD.</span><span class="sxs-lookup"><span data-stu-id="515e0-128">Inline schema can be defined using XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="515e0-129">Дополнительные сведения о создании встроенной схемы в виде схемы XML см. [в разделе Наследование реляционной структуры набора данных из схемы XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span><span class="sxs-lookup"><span data-stu-id="515e0-129">For details about writing inline schema as XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>|  
|<span data-ttu-id="515e0-130">**IgnoreSchema**</span><span class="sxs-lookup"><span data-stu-id="515e0-130">**IgnoreSchema**</span></span>|<span data-ttu-id="515e0-131">Не учитывает любую встроенную схему и загружает данные в существующую схему <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="515e0-131">Ignores any inline schema and loads the data into the existing <xref:System.Data.DataSet> schema.</span></span> <span data-ttu-id="515e0-132">Любые данные, не совпадающие с существующей схемой, удаляются.</span><span class="sxs-lookup"><span data-stu-id="515e0-132">Any data that does not match the existing schema is discarded.</span></span> <span data-ttu-id="515e0-133">Если схема не существует в наборе данных <xref:System.Data.DataSet>, данные не загружаются.</span><span class="sxs-lookup"><span data-stu-id="515e0-133">If no schema exists in the <xref:System.Data.DataSet>, no data is loaded.</span></span><br /><br /> <span data-ttu-id="515e0-134">Если данные являются DiffGram, **игноресчема** имеет те же функциональные возможности, что и **DiffGram** *.*</span><span class="sxs-lookup"><span data-stu-id="515e0-134">If the data is a DiffGram, **IgnoreSchema** has the same functionality as **DiffGram** *.*</span></span>|  
|<span data-ttu-id="515e0-135">**InferSchema**</span><span class="sxs-lookup"><span data-stu-id="515e0-135">**InferSchema**</span></span>|<span data-ttu-id="515e0-136">Не учитывает любую встроенную схему и формирует по одной схеме в расчете на каждую структуру XML-данных, а затем загружает данные.</span><span class="sxs-lookup"><span data-stu-id="515e0-136">Ignores any inline schema and infers the schema per the structure of the XML data, then loads the data.</span></span><br /><br /> <span data-ttu-id="515e0-137">Если набор данных <xref:System.Data.DataSet> уже содержит схему, текущая схема расширяется путем добавления столбцов в существующие таблицы.</span><span class="sxs-lookup"><span data-stu-id="515e0-137">If the <xref:System.Data.DataSet> already contains a schema, the current schema is extended by adding columns to existing tables.</span></span> <span data-ttu-id="515e0-138">Дополнительные таблицы не будут добавлены, если отсутствуют существующие таблицы.</span><span class="sxs-lookup"><span data-stu-id="515e0-138">Extra tables will not be added if there are not existing tables.</span></span> <span data-ttu-id="515e0-139">Если уже существует формируемая таблица с другим пространством имен или любой из формируемых столбцов конфликтует с существующими столбцами, то возникает исключение.</span><span class="sxs-lookup"><span data-stu-id="515e0-139">An exception is thrown if an inferred table already exists with a different namespace, or if any inferred columns conflict with existing columns.</span></span><br /><br /> <span data-ttu-id="515e0-140">Дополнительные сведения о том, как **ReadXmlSchema** выводит схему из XML-документа, см. в разделе вывод [реляционной структуры набора данных из XML](inferring-dataset-relational-structure-from-xml.md).</span><span class="sxs-lookup"><span data-stu-id="515e0-140">For details about how **ReadXmlSchema** infers a schema from an XML document, see [Inferring DataSet Relational Structure from XML](inferring-dataset-relational-structure-from-xml.md).</span></span>|  
|<span data-ttu-id="515e0-141">**DiffGram**</span><span class="sxs-lookup"><span data-stu-id="515e0-141">**DiffGram**</span></span>|<span data-ttu-id="515e0-142">Считывает данные DiffGram и добавляет их в текущую схему.</span><span class="sxs-lookup"><span data-stu-id="515e0-142">Reads a DiffGram and adds the data to the current schema.</span></span> <span data-ttu-id="515e0-143">**DiffGram** объединяет новые строки с существующими строками, в которых уникальные значения идентификаторов совпадают.</span><span class="sxs-lookup"><span data-stu-id="515e0-143">**DiffGram** merges new rows with existing rows where the unique identifier values match.</span></span> <span data-ttu-id="515e0-144">См. подраздел «Слияние данных из XML» в конце данного раздела.</span><span class="sxs-lookup"><span data-stu-id="515e0-144">See "Merging Data from XML" at the end of this topic.</span></span> <span data-ttu-id="515e0-145">Дополнительные сведения о дельтами см. в разделе [дельтами](diffgrams.md).</span><span class="sxs-lookup"><span data-stu-id="515e0-145">For more information about DiffGrams, see [DiffGrams](diffgrams.md).</span></span>|  
|<span data-ttu-id="515e0-146">**Fragment**</span><span class="sxs-lookup"><span data-stu-id="515e0-146">**Fragment**</span></span>|<span data-ttu-id="515e0-147">Продолжает считывание нескольких XML-фрагментов до достижения конца потока.</span><span class="sxs-lookup"><span data-stu-id="515e0-147">Continues reading multiple XML fragments until the end of the stream is reached.</span></span> <span data-ttu-id="515e0-148">Фрагменты, совпадающие со схемой <xref:System.Data.DataSet>, добавляются в соответствующие таблицы.</span><span class="sxs-lookup"><span data-stu-id="515e0-148">Fragments that match the <xref:System.Data.DataSet> schema are appended to the appropriate tables.</span></span> <span data-ttu-id="515e0-149">Фрагменты, не совпадающие со схемой <xref:System.Data.DataSet>, удаляются.</span><span class="sxs-lookup"><span data-stu-id="515e0-149">Fragments that do not match the <xref:System.Data.DataSet> schema are discarded.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="515e0-150">Если вы передали **XmlReader** в метод **ReadXml** , который располагает частью пути в XML-документ, то метод **ReadXml** прочитает его в следующий узел Element и будет считать его корневым элементом, считывая его только до конца узла Element.</span><span class="sxs-lookup"><span data-stu-id="515e0-150">If you pass an **XmlReader** to **ReadXml** that is positioned part of the way into an XML document, **ReadXml** will read to the next element node and will treat that as the root element, reading until the end of the element node only.</span></span> <span data-ttu-id="515e0-151">Это не применяется при указании **XmlReadMode. Fragment**.</span><span class="sxs-lookup"><span data-stu-id="515e0-151">This does not apply if you specify **XmlReadMode.Fragment**.</span></span>  
  
## <a name="dtd-entities"></a><span data-ttu-id="515e0-152">Сущности DTD</span><span class="sxs-lookup"><span data-stu-id="515e0-152">DTD Entities</span></span>  
 <span data-ttu-id="515e0-153">Если XML содержит сущности, определенные в схеме определения типа документа (DTD), при попытке загрузить объект <xref:System.Data.DataSet> путем передачи имени файла, потока или непроверяющего **XmlReader** в метод **ReadXml**будет создано исключение.</span><span class="sxs-lookup"><span data-stu-id="515e0-153">If your XML contains entities defined in a document type definition (DTD) schema, an exception will be thrown if you attempt to load a <xref:System.Data.DataSet> by passing a file name, stream, or non-validating **XmlReader** to **ReadXml**.</span></span> <span data-ttu-id="515e0-154">Вместо этого необходимо создать **XmlValidatingReader**, указав для **EntityHandling** значение **EntityHandling. ExpandEntities**и передав **XmlValidatingReader** в **ReadXml**.</span><span class="sxs-lookup"><span data-stu-id="515e0-154">Instead, you must create an **XmlValidatingReader**, with **EntityHandling** set to **EntityHandling.ExpandEntities**, and pass your **XmlValidatingReader** to **ReadXml**.</span></span> <span data-ttu-id="515e0-155">**XmlValidatingReader** развернет сущности перед считыванием <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="515e0-155">The **XmlValidatingReader** will expand the entities prior to being read by the <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="515e0-156">В следующих примерах кода показаны способы загрузки набора данных <xref:System.Data.DataSet> из XML-потока.</span><span class="sxs-lookup"><span data-stu-id="515e0-156">The following code examples show how to load a <xref:System.Data.DataSet> from an XML stream.</span></span> <span data-ttu-id="515e0-157">В первом примере показано имя файла, передаваемое методу **ReadXml** .</span><span class="sxs-lookup"><span data-stu-id="515e0-157">The first example shows a file name being passed to the **ReadXml** method.</span></span> <span data-ttu-id="515e0-158">Во втором примере показана загрузка строки, содержащей XML-код, с помощью объекта <xref:System.IO.StringReader>.</span><span class="sxs-lookup"><span data-stu-id="515e0-158">The second example shows a string that contains XML being loaded using a <xref:System.IO.StringReader>.</span></span>  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXml("input.xml", XmlReadMode.ReadSchema)  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.ReadXml("input.xml", XmlReadMode.ReadSchema);  
```  
  
```vb  
Dim dataSet As DataSet = New DataSet  
Dim dataTable As DataTable = New DataTable("table1")  
dataTable.Columns.Add("col1", Type.GetType("System.String"))  
dataSet.Tables.Add(dataTable)  
  
Dim xmlData As String = "<XmlDS><table1><col1>Value1</col1></table1><table1><col1>Value2</col1></table1></XmlDS>"  
  
Dim xmlSR As System.IO.StringReader = New System.IO.StringReader(xmlData)  
  
dataSet.ReadXml(xmlSR, XmlReadMode.IgnoreSchema)  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
DataTable dataTable = new DataTable("table1");  
dataTable.Columns.Add("col1", typeof(string));  
dataSet.Tables.Add(dataTable);  
  
string xmlData = "<XmlDS><table1><col1>Value1</col1></table1><table1><col1>Value2</col1></table1></XmlDS>";  
  
System.IO.StringReader xmlSR = new System.IO.StringReader(xmlData);  
  
dataSet.ReadXml(xmlSR, XmlReadMode.IgnoreSchema);  
```  
  
> [!NOTE]
> <span data-ttu-id="515e0-159">При вызове метода **ReadXml** для загрузки очень большого файла может возникнуть снижение производительности.</span><span class="sxs-lookup"><span data-stu-id="515e0-159">If you call **ReadXml** to load a very large file, you may encounter slow performance.</span></span> <span data-ttu-id="515e0-160">Чтобы обеспечить наилучшую производительность для метода **ReadXml**, в большом файле вызовите <xref:System.Data.DataTable.BeginLoadData%2A> метод для каждой таблицы в <xref:System.Data.DataSet> , а затем вызовите метода **ReadXml**.</span><span class="sxs-lookup"><span data-stu-id="515e0-160">To ensure best performance for **ReadXml**, on a large file, call the <xref:System.Data.DataTable.BeginLoadData%2A> method for each table in the <xref:System.Data.DataSet>, and then call **ReadXml**.</span></span> <span data-ttu-id="515e0-161">Наконец, вызывайте метод <xref:System.Data.DataTable.EndLoadData%2A> для каждой таблицы в наборе данных <xref:System.Data.DataSet>, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="515e0-161">Finally, call <xref:System.Data.DataTable.EndLoadData%2A> for each table in the <xref:System.Data.DataSet>, as shown in the following example.</span></span>  
  
```vb  
Dim dataTable As DataTable  
  
For Each dataTable In dataSet.Tables  
   dataTable.BeginLoadData()  
Next  
  
dataSet.ReadXml("file.xml")  
  
For Each dataTable in dataSet.Tables  
   dataTable.EndLoadData()  
Next  
```  
  
```csharp  
foreach (DataTable dataTable in dataSet.Tables)  
   dataTable.BeginLoadData();  
  
dataSet.ReadXml("file.xml");
  
foreach (DataTable dataTable in dataSet.Tables)  
   dataTable.EndLoadData();  
```  
  
> [!NOTE]
> <span data-ttu-id="515e0-162">Если схема XSD для <xref:System.Data.DataSet> включает в себя **targetNamespace**, данные могут быть не считаны, и при вызове метода **ReadXml** могут возникнуть исключения, если для загрузки <xref:System.Data.DataSet> с XML, содержащим элементы с неквалифицированным пространством имен, возникает исключение.</span><span class="sxs-lookup"><span data-stu-id="515e0-162">If the XSD schema for your <xref:System.Data.DataSet> includes a **targetNamespace**, data may not be read, and you may encounter exceptions, when calling **ReadXml** to load the <xref:System.Data.DataSet> with XML that contains elements with no qualifying namespace.</span></span> <span data-ttu-id="515e0-163">Для чтения неквалифицированных элементов в этом случае задайте **elementFormDefault** равным "квалифицированный" в схеме XSD.</span><span class="sxs-lookup"><span data-stu-id="515e0-163">To read unqualified elements in this case, set **elementFormDefault** equal to "qualified" in your XSD schema.</span></span> <span data-ttu-id="515e0-164">Пример:</span><span class="sxs-lookup"><span data-stu-id="515e0-164">For example:</span></span>  
  
```xml  
<xsd:schema id="customDataSet"
  elementFormDefault="qualified"  
  targetNamespace="http://www.tempuri.org/customDataSet.xsd"
  xmlns="http://www.tempuri.org/customDataSet.xsd"
  xmlns:xsd="http://www.w3.org/2001/XMLSchema"
  xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
</xsd:schema>  
```  
  
## <a name="merging-data-from-xml"></a><span data-ttu-id="515e0-165">Слияние данных из XML</span><span class="sxs-lookup"><span data-stu-id="515e0-165">Merging Data from XML</span></span>  
 <span data-ttu-id="515e0-166">Если набор данных <xref:System.Data.DataSet> уже содержит данные, новые данные из XML-кода добавляются к данным, находящимся в наборе данных <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="515e0-166">If the <xref:System.Data.DataSet> already contains data, the new data from the XML is added to the data already present in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="515e0-167">**ReadXml** не выполняет слияние из XML-кода с <xref:System.Data.DataSet> любыми строками с совпадающими первичными ключами.</span><span class="sxs-lookup"><span data-stu-id="515e0-167">**ReadXml** does not merge from the XML into the <xref:System.Data.DataSet> any row information with matching primary keys.</span></span> <span data-ttu-id="515e0-168">Чтобы перезаписать существующие сведения о строке новыми данными из XML, используйте **ReadXml** , чтобы создать новый объект <xref:System.Data.DataSet> , а затем <xref:System.Data.DataSet.Merge%2A> новый <xref:System.Data.DataSet> в существующем <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="515e0-168">To overwrite existing row information with new information from XML, use **ReadXml** to create a new <xref:System.Data.DataSet>, and then <xref:System.Data.DataSet.Merge%2A> the new <xref:System.Data.DataSet> into the existing <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="515e0-169">Обратите внимание, что при загрузке DiffGram с помощью метода **ReadXml** с параметром **XmlReadMode** для **DiffGram** будут объединены строки с одинаковым уникальным идентификатором.</span><span class="sxs-lookup"><span data-stu-id="515e0-169">Note that loading a DiffGram using **ReadXML** with an **XmlReadMode** of **DiffGram** will merge rows that have the same unique identifier.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="515e0-170">См. также</span><span class="sxs-lookup"><span data-stu-id="515e0-170">See also</span></span>

- <xref:System.Data.DataSet.Merge%2A?displayProperty=nameWithType>
- [<span data-ttu-id="515e0-171">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="515e0-171">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="515e0-172">DiffGrams</span><span class="sxs-lookup"><span data-stu-id="515e0-172">DiffGrams</span></span>](diffgrams.md)
- [<span data-ttu-id="515e0-173">Наследование реляционной структуры набора данных от схемы XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="515e0-173">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [<span data-ttu-id="515e0-174">Определение реляционной структуры набора данных из XML</span><span class="sxs-lookup"><span data-stu-id="515e0-174">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="515e0-175">Загрузка сведений о схеме набора данных из XML</span><span class="sxs-lookup"><span data-stu-id="515e0-175">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="515e0-176">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="515e0-176">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="515e0-177">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="515e0-177">ADO.NET Overview</span></span>](../ado-net-overview.md)
