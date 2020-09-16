---
title: XML-документы и данные
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: e695047f-3c0f-4045-8708-5baea91cc380
ms.openlocfilehash: 6d2a52567a1fc8bdbbb1d039ac583c889d77d4af
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540138"
---
# <a name="xml-documents-and-data"></a><span data-ttu-id="8f46a-102">XML-документы и данные</span><span class="sxs-lookup"><span data-stu-id="8f46a-102">XML Documents and Data</span></span>

<span data-ttu-id="8f46a-103">Платформа .NET Framework имеет всеобъемлющий и интегрированный набор классов, с помощью которых можно легко создавать приложения, использующие XML.</span><span class="sxs-lookup"><span data-stu-id="8f46a-103">The .NET Framework provides a comprehensive and integrated set of classes that enable you to build XML-aware apps easily.</span></span> <span data-ttu-id="8f46a-104">Классы из следующих пространств имен поддерживают синтаксический анализ и запись XML-кода, изменение XML-данных в памяти, проверку данных и преобразование XSLT.</span><span class="sxs-lookup"><span data-stu-id="8f46a-104">The classes in the following namespaces support parsing and writing XML, editing XML data in memory, data validation, and XSLT transformation.</span></span>

- <xref:System.Xml>

- <xref:System.Xml.XPath>

- <xref:System.Xml.Xsl>

- <xref:System.Xml.Schema>

- <xref:System.Xml.Linq>

<span data-ttu-id="8f46a-105">Чтобы получить полный список, выполните поиск System.Xml в [браузере API .NET](../../../../api/index.md?term=system.xml).</span><span class="sxs-lookup"><span data-stu-id="8f46a-105">For a full list, search for "System.Xml" on the [.NET API browser](../../../../api/index.md?term=system.xml).</span></span>

<span data-ttu-id="8f46a-106">Классы из этих пространств имен поддерживают рекомендации W3C.</span><span class="sxs-lookup"><span data-stu-id="8f46a-106">The classes in these namespaces support World Wide Web Consortium (W3C) recommendations.</span></span> <span data-ttu-id="8f46a-107">Пример:</span><span class="sxs-lookup"><span data-stu-id="8f46a-107">For example:</span></span>

- <span data-ttu-id="8f46a-108">Класс <xref:System.Xml.XmlDocument?displayProperty=nameWithType> реализует рекомендации модели W3C [DOM базового уровня 1](https://www.w3.org/TR/REC-DOM-Level-1/) и [DOM базового уровня 2](https://www.w3.org/TR/DOM-Level-2-Core/).</span><span class="sxs-lookup"><span data-stu-id="8f46a-108">The <xref:System.Xml.XmlDocument?displayProperty=nameWithType> class implements the [W3C Document Object Model (DOM) Level 1 Core](https://www.w3.org/TR/REC-DOM-Level-1/) and [DOM Level 2 Core](https://www.w3.org/TR/DOM-Level-2-Core/) recommendations.</span></span>

- <span data-ttu-id="8f46a-109">Классы <xref:System.Xml.XmlReader?displayProperty=nameWithType> и <xref:System.Xml.XmlWriter?displayProperty=nameWithType> поддерживают рекомендации [W3C XML 1.0](https://www.w3.org/TR/2006/REC-xml-20060816/) и [Пространства имен в XML](https://www.w3.org/TR/REC-xml-names/).</span><span class="sxs-lookup"><span data-stu-id="8f46a-109">The <xref:System.Xml.XmlReader?displayProperty=nameWithType> and <xref:System.Xml.XmlWriter?displayProperty=nameWithType> classes support the [W3C XML 1.0](https://www.w3.org/TR/2006/REC-xml-20060816/) and the [Namespaces in XML](https://www.w3.org/TR/REC-xml-names/) recommendations.</span></span>

- <span data-ttu-id="8f46a-110">Схемы в классе <xref:System.Xml.Schema.XmlSchemaSet?displayProperty=nameWithType> поддерживают рекомендации в разделах [Схема XML W3C, часть 1. Структуры](https://www.w3.org/TR/xmlschema-1/) и [Схема XML, часть 2. Типы данных](https://www.w3.org/TR/xmlschema-2/).</span><span class="sxs-lookup"><span data-stu-id="8f46a-110">Schemas in the <xref:System.Xml.Schema.XmlSchemaSet?displayProperty=nameWithType> class support the [W3C XML Schema Part 1: Structures](https://www.w3.org/TR/xmlschema-1/) and [XML Schema Part 2: Datatypes](https://www.w3.org/TR/xmlschema-2/) recommendations.</span></span>

- <span data-ttu-id="8f46a-111">Классы в пространстве имен <xref:System.Xml.Xsl?displayProperty=nameWithType> поддерживают преобразования XSLT, соответствующие рекомендациям [W3C XSLT 1.0](https://www.w3.org/TR/xslt).</span><span class="sxs-lookup"><span data-stu-id="8f46a-111">Classes in the <xref:System.Xml.Xsl?displayProperty=nameWithType> namespace support XSLT transformations that conform to the [W3C XSLT 1.0](https://www.w3.org/TR/xslt) recommendation.</span></span>

<span data-ttu-id="8f46a-112">Классы XML в платформе .NET Framework предоставляют следующие преимущества.</span><span class="sxs-lookup"><span data-stu-id="8f46a-112">The XML classes in the .NET Framework provide these benefits:</span></span>

- <span data-ttu-id="8f46a-113">**Производительность**</span><span class="sxs-lookup"><span data-stu-id="8f46a-113">**Productivity.**</span></span> <span data-ttu-id="8f46a-114">[LINQ to XML (C#)](../../linq/linq-xml-overview.md) и [LINQ to XML (Visual Basic)](../../linq/linq-xml-overview.md) упрощает программирование с использованием XML и обеспечивает работу с запросами, похожую на работу в SQL.</span><span class="sxs-lookup"><span data-stu-id="8f46a-114">[LINQ to XML (C#)](../../linq/linq-xml-overview.md) and [LINQ to XML (Visual Basic)](../../linq/linq-xml-overview.md) makes it easier to program with XML and provides a query experience that is similar to SQL.</span></span>

- <span data-ttu-id="8f46a-115">**Расширяемость**</span><span class="sxs-lookup"><span data-stu-id="8f46a-115">**Extensibility.**</span></span> <span data-ttu-id="8f46a-116">XML-классы в .NET Framework являются расширяемыми, что было достигнуто за счет использования абстрактных базовых классов и виртуальных методов.</span><span class="sxs-lookup"><span data-stu-id="8f46a-116">The XML classes in the .NET Framework are extensible through the use of abstract base classes and virtual methods.</span></span> <span data-ttu-id="8f46a-117">Например, можно создать класс, производный от класса <xref:System.Xml.XmlUrlResolver>, который будет сохранять поток кэширования на локальном диске.</span><span class="sxs-lookup"><span data-stu-id="8f46a-117">For example, you can create a derived class of the <xref:System.Xml.XmlUrlResolver> class that stores the cache stream to the local disk.</span></span>

- <span data-ttu-id="8f46a-118">**Модульная архитектура**</span><span class="sxs-lookup"><span data-stu-id="8f46a-118">**Pluggable architecture.**</span></span> <span data-ttu-id="8f46a-119">Платформа .NET Framework обеспечивает архитектуру, в которой компоненты могут использовать друг друга, а данные можно передавать в потоках между компонентами.</span><span class="sxs-lookup"><span data-stu-id="8f46a-119">The .NET Framework provides an architecture in which components can utilize one another, and data can be streamed between components.</span></span> <span data-ttu-id="8f46a-120">Например, хранилище данных, такое как объект <xref:System.Xml.XPath.XPathDocument> или <xref:System.Xml.XmlDocument>, можно преобразовать с помощью класса <xref:System.Xml.Xsl.XslCompiledTransform>, а выходные данные затем могут быть переданы в виде потока в другое хранилище или возвращены в виде потока из веб-службы XML.</span><span class="sxs-lookup"><span data-stu-id="8f46a-120">For example, a data store, such as an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object, can be transformed with the <xref:System.Xml.Xsl.XslCompiledTransform> class, and the output can then be streamed either into another store or returned as a stream from a web service.</span></span>

- <span data-ttu-id="8f46a-121">**Производительность.**</span><span class="sxs-lookup"><span data-stu-id="8f46a-121">**Performance.**</span></span> <span data-ttu-id="8f46a-122">С целью повышения быстродействия приложений некоторые XML-классы в .NET Framework поддерживают модель на основе потоковой передачи со следующими характеристиками.</span><span class="sxs-lookup"><span data-stu-id="8f46a-122">For better app performance, some of the XML classes in the .NET Framework support a streaming-based model with the following characteristics:</span></span>

  - <span data-ttu-id="8f46a-123">Минимальное кэширование для анализа по запросу в однопроходном режиме (<xref:System.Xml.XmlReader>).</span><span class="sxs-lookup"><span data-stu-id="8f46a-123">Minimal caching for forward-only, pull-model parsing (<xref:System.Xml.XmlReader>).</span></span>

  - <span data-ttu-id="8f46a-124">Проверка в однопроходном режиме (<xref:System.Xml.XmlReader>).</span><span class="sxs-lookup"><span data-stu-id="8f46a-124">Forward-only validation (<xref:System.Xml.XmlReader>).</span></span>

  - <span data-ttu-id="8f46a-125">Навигация, аналогичная курсорам, которая сводит создание узлов к минимуму (до одного виртуального узла) и обеспечивает произвольный доступ к документу (<xref:System.Xml.XPath.XPathNavigator>).</span><span class="sxs-lookup"><span data-stu-id="8f46a-125">Cursor style navigation that minimizes node creation to a single virtual node while providing random access to the document (<xref:System.Xml.XPath.XPathNavigator>).</span></span>

  <span data-ttu-id="8f46a-126">В случае если требуется обработка XSLT, для повышения производительности можно использовать класс <xref:System.Xml.XPath.XPathDocument>, который является оптимизированным хранилищем «только для чтения» для запросов XPath, обеспечивающих эффективное взаимодействие с классом <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="8f46a-126">For better performance whenever XSLT processing is required, you can use the <xref:System.Xml.XPath.XPathDocument> class, which is an optimized, read-only store for XPath queries designed to work efficiently with the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>

- <span data-ttu-id="8f46a-127">**Интеграция с ADO.NET**</span><span class="sxs-lookup"><span data-stu-id="8f46a-127">**Integration with ADO.NET.**</span></span> <span data-ttu-id="8f46a-128">Классы XML и [ADO.NET](../../../framework/data/adonet/index.md) тесно интегрированы для сведения воедино реляционных данных и XML.</span><span class="sxs-lookup"><span data-stu-id="8f46a-128">The XML classes and [ADO.NET](../../../framework/data/adonet/index.md) are tightly integrated to bring together relational data and XML.</span></span> <span data-ttu-id="8f46a-129">Класс <xref:System.Data.DataSet> представляет собой кэш «в памяти» для данных, полученных из базы данных.</span><span class="sxs-lookup"><span data-stu-id="8f46a-129">The <xref:System.Data.DataSet> class is an in-memory cache of data retrieved from a database.</span></span> <span data-ttu-id="8f46a-130">Класс <xref:System.Data.DataSet> позволяет считывать и записывать код XML с помощью классов <xref:System.Xml.XmlReader> и <xref:System.Xml.XmlWriter>, сохранять внутреннюю реляционную структуру в виде схем XML (XSD) и логически выводить структуру схем XML-документов.</span><span class="sxs-lookup"><span data-stu-id="8f46a-130">The <xref:System.Data.DataSet> class has the ability to read and write XML by using the <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter> classes, to persist its internal relational schema structure as XML schemas (XSD), and to infer the schema structure of an XML document.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="8f46a-131">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="8f46a-131">In This Section</span></span>

<span data-ttu-id="8f46a-132">[Варианты обработки XML-данных](xml-processing-options.md) Обсуждаются параметры обработки XML-данных.</span><span class="sxs-lookup"><span data-stu-id="8f46a-132">[XML Processing Options](xml-processing-options.md) Discusses options for processing XML data.</span></span>

<span data-ttu-id="8f46a-133">[Обработка XML-данных в памяти](processing-xml-data-in-memory.md) Содержит обсуждение трех моделей обработки XML-данных в памяти: [LINQ to XML (C#)](../../linq/linq-xml-overview.md) и [LINQ to XML (Visual Basic)](../../linq/linq-xml-overview.md), класс <xref:System.Xml.XmlDocument> (основанный на модели W3C DOM) и класс <xref:System.Xml.XPath.XPathDocument> (основанный на модели данных XPath).</span><span class="sxs-lookup"><span data-stu-id="8f46a-133">[Processing XML Data In-Memory](processing-xml-data-in-memory.md) Discusses the three models for processing XML data in-memory: [LINQ to XML (C#)](../../linq/linq-xml-overview.md) and [LINQ to XML (Visual Basic)](../../linq/linq-xml-overview.md), the <xref:System.Xml.XmlDocument> class (based on the W3C Document Object Model), and the <xref:System.Xml.XPath.XPathDocument> class (based on the XPath data model).</span></span>

<span data-ttu-id="8f46a-134">[Преобразования XSLT](xslt-transformations.md)</span><span class="sxs-lookup"><span data-stu-id="8f46a-134">[XSLT Transformations](xslt-transformations.md)</span></span>\
<span data-ttu-id="8f46a-135">Описывается, как использовать обработчик XSLT.</span><span class="sxs-lookup"><span data-stu-id="8f46a-135">Describes how to use the XSLT processor.</span></span>

<span data-ttu-id="8f46a-136">[Модель объектов схемы XML (SOM)](xml-schema-object-model-som.md)</span><span class="sxs-lookup"><span data-stu-id="8f46a-136">[XML Schema Object Model (SOM)](xml-schema-object-model-som.md)</span></span>\
<span data-ttu-id="8f46a-137">Описываются классы, используемые для построения схем XML (XSD-файлов) и работы с ними, используя класс <xref:System.Xml.Schema.XmlSchema> для загрузки и изменения схемы.</span><span class="sxs-lookup"><span data-stu-id="8f46a-137">Describes the classes used for building and manipulating XML Schemas (XSD) by providing an <xref:System.Xml.Schema.XmlSchema> class to load and edit a schema.</span></span>

<span data-ttu-id="8f46a-138">[Интеграция XML с реляционными данными и ADO.NET](xml-integration-with-relational-data-and-adonet.md)</span><span class="sxs-lookup"><span data-stu-id="8f46a-138">[XML Integration with Relational Data and ADO.NET](xml-integration-with-relational-data-and-adonet.md)</span></span>\
<span data-ttu-id="8f46a-139">Описывается, как платформа .NET Framework реализует синхронный доступ в режиме реального времени к данным в реляционном и иерархическом представлении с помощью объектов <xref:System.Data.DataSet> и <xref:System.Xml.XmlDataDocument>.</span><span class="sxs-lookup"><span data-stu-id="8f46a-139">Describes how the .NET Framework enables real-time, synchronous access to both the relational and hierarchical representations of data through the <xref:System.Data.DataSet> object and the <xref:System.Xml.XmlDataDocument> object.</span></span>

<span data-ttu-id="8f46a-140">[Управление пространствами имен в XML-документе](managing-namespaces-in-an-xml-document.md)</span><span class="sxs-lookup"><span data-stu-id="8f46a-140">[Managing Namespaces in an XML Document](managing-namespaces-in-an-xml-document.md)</span></span>\
<span data-ttu-id="8f46a-141">Описывает использование класса <xref:System.Xml.XmlNamespaceManager> для хранения и ведения информации о пространствах имен.</span><span class="sxs-lookup"><span data-stu-id="8f46a-141">Describes how the <xref:System.Xml.XmlNamespaceManager> class is used to store and maintain namespace information.</span></span>

<span data-ttu-id="8f46a-142">[Поддержка типов в классах System.Xml](type-support-in-the-system-xml-classes.md)</span><span class="sxs-lookup"><span data-stu-id="8f46a-142">[Type Support in the System.Xml Classes](type-support-in-the-system-xml-classes.md)</span></span>\
<span data-ttu-id="8f46a-143">Описывает сопоставление типов данных XML с типами CLR, преобразование типов данных XML и другие возможности по работе с типами, которые есть в классах <xref:System.Xml>.</span><span class="sxs-lookup"><span data-stu-id="8f46a-143">Describes how XML data types map to CLR types, how to convert XML data types, and other type support features in the <xref:System.Xml> classes.</span></span>

## <a name="related-sections"></a><span data-ttu-id="8f46a-144">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="8f46a-144">Related Sections</span></span>

<span data-ttu-id="8f46a-145">[ADO.NET](../../../framework/data/adonet/index.md)</span><span class="sxs-lookup"><span data-stu-id="8f46a-145">[ADO.NET](../../../framework/data/adonet/index.md)</span></span>\
<span data-ttu-id="8f46a-146">Приводятся сведения о доступе к данным с помощью ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="8f46a-146">Provides information on how to access data using ADO.NET.</span></span>

<span data-ttu-id="8f46a-147">[Безопасность](../../security/index.md)</span><span class="sxs-lookup"><span data-stu-id="8f46a-147">[Security](../../security/index.md)</span></span>\
<span data-ttu-id="8f46a-148">Приводятся общие сведения о системе безопасности в платформе .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8f46a-148">Provides an overview of the .NET Framework security system.</span></span>
