---
title: Наборы данных, таблицы данных и объекты DataView
description: Изучите несколько способов работы с набором данных ADO.NET, представленным в памяти представлением данных, обеспечивающим единообразную реляционную модель программирования.
ms.date: 03/30/2017
ms.assetid: 6d4c4b69-8919-4224-8a65-6cca1c61b48f
ms.openlocfilehash: 53e12f701b9be1938d62f46bbeb6e63d95c03386
ms.sourcegitcommit: e7748001b1cee80ced691d8a76ca814c0b02dd9b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2020
ms.locfileid: "86374511"
---
# <a name="datasets-datatables-and-dataviews"></a><span data-ttu-id="ebe75-103">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="ebe75-103">DataSets, DataTables, and DataViews</span></span>

<span data-ttu-id="ebe75-104">ADO.NET <xref:System.Data.DataSet> - расположенное в оперативной памяти представление данных, обеспечивающее согласованную реляционную программную модель независимо от источника данных.</span><span class="sxs-lookup"><span data-stu-id="ebe75-104">The ADO.NET <xref:System.Data.DataSet> is a memory-resident representation of data that provides a consistent relational programming model regardless of the source of the data it contains.</span></span> <span data-ttu-id="ebe75-105"><xref:System.Data.DataSet> представляет полный набор данных, включая таблицы, содержащие, упорядочивающие и ограничивающие данные, а также связи между таблицами.</span><span class="sxs-lookup"><span data-stu-id="ebe75-105">A <xref:System.Data.DataSet> represents a complete set of data including the tables that contain, order, and constrain the data, as well as the relationships between the tables.</span></span>  
  
<span data-ttu-id="ebe75-106">Существует несколько способов работы с <xref:System.Data.DataSet>, которые могут применяться отдельно или в сочетании.</span><span class="sxs-lookup"><span data-stu-id="ebe75-106">There are several ways of working with a <xref:System.Data.DataSet>, which can be applied independently or in combination.</span></span> <span data-ttu-id="ebe75-107">Вы можете:</span><span class="sxs-lookup"><span data-stu-id="ebe75-107">You can:</span></span>  
  
- <span data-ttu-id="ebe75-108">Программно создать <xref:System.Data.DataTable>, <xref:System.Data.DataRelation> и <xref:System.Data.Constraint> внутри <xref:System.Data.DataSet> и заполнить таблицы данными.</span><span class="sxs-lookup"><span data-stu-id="ebe75-108">Programmatically create a <xref:System.Data.DataTable>, <xref:System.Data.DataRelation>, and <xref:System.Data.Constraint> within a <xref:System.Data.DataSet> and populate the tables with data.</span></span>  
  
- <span data-ttu-id="ebe75-109">Заполнить <xref:System.Data.DataSet> таблицами данных из существующего реляционного источника данных с помощью `DataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="ebe75-109">Populate the <xref:System.Data.DataSet> with tables of data from an existing relational data source using a `DataAdapter`.</span></span>  
  
- <span data-ttu-id="ebe75-110">Загрузить и сохранить содержимое <xref:System.Data.DataSet> с помощью XML-кода.</span><span class="sxs-lookup"><span data-stu-id="ebe75-110">Load and persist the <xref:System.Data.DataSet> contents using XML.</span></span> <span data-ttu-id="ebe75-111">Дополнительные сведения см. в статье [Использование XML в наборах данных](using-xml-in-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="ebe75-111">For more information, see [Using XML in a DataSet](using-xml-in-a-dataset.md).</span></span>  
  
<span data-ttu-id="ebe75-112">Строго типизированный <xref:System.Data.DataSet> также можно передавать с помощью веб-службы с поддержкой XML-кода.</span><span class="sxs-lookup"><span data-stu-id="ebe75-112">A strongly typed <xref:System.Data.DataSet> can also be transported using an XML Web service.</span></span> <span data-ttu-id="ebe75-113">Конструкция <xref:System.Data.DataSet> делает его идеальным для передачи данных с помощью веб-служб с поддержкой XML-кода.</span><span class="sxs-lookup"><span data-stu-id="ebe75-113">The design of the <xref:System.Data.DataSet> makes it ideal for transporting data using XML Web services.</span></span> <span data-ttu-id="ebe75-114">Общие сведения об XML-веб-службах см. в разделе [Общие сведения об XML-веб-службах](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w9fdtx28(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="ebe75-114">For an overview of XML Web services, see [XML Web Services Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w9fdtx28(v=vs.100)).</span></span> <span data-ttu-id="ebe75-115">Пример использования <xref:System.Data.DataSet> из XML-веб-службы см. в разделе [Потребление набора данных из веб-службы XML](consuming-a-dataset-from-an-xml-web-service.md).</span><span class="sxs-lookup"><span data-stu-id="ebe75-115">For an example of consuming a <xref:System.Data.DataSet> from an XML Web service, see [Consuming a DataSet from an XML Web Service](consuming-a-dataset-from-an-xml-web-service.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ebe75-116">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="ebe75-116">In this section</span></span>

 [<span data-ttu-id="ebe75-117">Руководство по безопасности</span><span class="sxs-lookup"><span data-stu-id="ebe75-117">Security guidance</span></span>](security-guidance.md)  
 <span data-ttu-id="ebe75-118">Предоставляет руководство по безопасности для <xref:System.Data.DataSet> и <xref:System.Data.DataTable> .</span><span class="sxs-lookup"><span data-stu-id="ebe75-118">Provides security guidance for <xref:System.Data.DataSet> and <xref:System.Data.DataTable>.</span></span>

 [<span data-ttu-id="ebe75-119">Создание набора данных</span><span class="sxs-lookup"><span data-stu-id="ebe75-119">Creating a DataSet</span></span>](creating-a-dataset.md)  
 <span data-ttu-id="ebe75-120">Описывает синтаксис, необходимый для создания экземпляра <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="ebe75-120">Describes the syntax for creating an instance of a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="ebe75-121">Добавление новой таблицы данных в набор данных</span><span class="sxs-lookup"><span data-stu-id="ebe75-121">Adding a DataTable to a DataSet</span></span>](adding-a-datatable-to-a-dataset.md)  
 <span data-ttu-id="ebe75-122">Описывает создание и добавление таблиц и столбцов в <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="ebe75-122">Describes how to create and add tables and columns to a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="ebe75-123">Добавление отношений DataRelation</span><span class="sxs-lookup"><span data-stu-id="ebe75-123">Adding DataRelations</span></span>](adding-datarelations.md)  
 <span data-ttu-id="ebe75-124">Описывает создание связей между таблицами <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="ebe75-124">Describes how to create relations between tables in a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="ebe75-125">Навигация по отношениям DataRelation</span><span class="sxs-lookup"><span data-stu-id="ebe75-125">Navigating DataRelations</span></span>](navigating-datarelations.md)  
 <span data-ttu-id="ebe75-126">Описывает использование связей между таблицами <xref:System.Data.DataSet> для возвращения дочерних или родительских строк связи типа «родитель-потомок».</span><span class="sxs-lookup"><span data-stu-id="ebe75-126">Describes how to use the relations between tables in a <xref:System.Data.DataSet> to return the child or parent rows of a parent-child relationship.</span></span>  
  
 [<span data-ttu-id="ebe75-127">Слияние содержимого набора данных</span><span class="sxs-lookup"><span data-stu-id="ebe75-127">Merging DataSet Contents</span></span>](merging-dataset-contents.md)  
 <span data-ttu-id="ebe75-128">Описывает процесс слияния содержимого одного <xref:System.Data.DataSet>, <xref:System.Data.DataTable> или массива <xref:System.Data.DataRow> с <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="ebe75-128">Describes how to merge the contents of one <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, or <xref:System.Data.DataRow> array into another <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="ebe75-129">Копирование содержимого набора данных</span><span class="sxs-lookup"><span data-stu-id="ebe75-129">Copying DataSet Contents</span></span>](copying-dataset-contents.md)  
 <span data-ttu-id="ebe75-130">Описывает создание копии <xref:System.Data.DataSet>, которая может содержать схему, а также указанные данные.</span><span class="sxs-lookup"><span data-stu-id="ebe75-130">Describes how to create a copy of a <xref:System.Data.DataSet> that can contain schema as well as specified data.</span></span>  
  
 [<span data-ttu-id="ebe75-131">Обработка событий наборов данных</span><span class="sxs-lookup"><span data-stu-id="ebe75-131">Handling DataSet Events</span></span>](handling-dataset-events.md)  
 <span data-ttu-id="ebe75-132">Описывает события <xref:System.Data.DataSet> и их использование.</span><span class="sxs-lookup"><span data-stu-id="ebe75-132">Describes the events of a <xref:System.Data.DataSet> and how to use them.</span></span>  
  
 [<span data-ttu-id="ebe75-133">Типизированные наборы данных</span><span class="sxs-lookup"><span data-stu-id="ebe75-133">Typed DataSets</span></span>](typed-datasets.md)  
 <span data-ttu-id="ebe75-134">Обсуждается, что такое типизированный <xref:System.Data.DataSet> и как его создавать и использовать.</span><span class="sxs-lookup"><span data-stu-id="ebe75-134">Discusses what a typed <xref:System.Data.DataSet> is and how to create and use it.</span></span>  
  
 [<span data-ttu-id="ebe75-135">DataTables</span><span class="sxs-lookup"><span data-stu-id="ebe75-135">DataTables</span></span>](datatables.md)  
 <span data-ttu-id="ebe75-136">Описывает создание <xref:System.Data.DataTable>, определение схемы и управление данными.</span><span class="sxs-lookup"><span data-stu-id="ebe75-136">Describes how to create a <xref:System.Data.DataTable>, define the schema, and manipulate data.</span></span>  
  
 [<span data-ttu-id="ebe75-137">Объекты DataTableReader</span><span class="sxs-lookup"><span data-stu-id="ebe75-137">DataTableReaders</span></span>](datatablereaders.md)  
 <span data-ttu-id="ebe75-138">Описывает создание и использование <xref:System.Data.DataTableReader>.</span><span class="sxs-lookup"><span data-stu-id="ebe75-138">Describes how to create and use a <xref:System.Data.DataTableReader>.</span></span>  
  
 [<span data-ttu-id="ebe75-139">Объекты DataView</span><span class="sxs-lookup"><span data-stu-id="ebe75-139">DataViews</span></span>](dataviews.md)  
 <span data-ttu-id="ebe75-140">Описывает создание `DataViews` и работу с ними, а также работу с событиями <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="ebe75-140">Describes how to create and work with `DataViews` and work with <xref:System.Data.DataView> events.</span></span>  
  
 [<span data-ttu-id="ebe75-141">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="ebe75-141">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)  
 <span data-ttu-id="ebe75-142">Описывает взаимодействие <xref:System.Data.DataSet> с XML-данными в качестве источника данных, включая загрузку и сохранение содержимого <xref:System.Data.DataSet> в виде XML-данных.</span><span class="sxs-lookup"><span data-stu-id="ebe75-142">Describes how the <xref:System.Data.DataSet> interacts with XML as a data source, including loading and persisting the contents of a <xref:System.Data.DataSet> as XML data.</span></span>  
  
 [<span data-ttu-id="ebe75-143">Потребление набора данных из веб-службы XML</span><span class="sxs-lookup"><span data-stu-id="ebe75-143">Consuming a DataSet from an XML Web Service</span></span>](consuming-a-dataset-from-an-xml-web-service.md)  
 <span data-ttu-id="ebe75-144">Описывает создание веб-службы с поддержкой XML, использующей <xref:System.Data.DataSet> для передачи данных.</span><span class="sxs-lookup"><span data-stu-id="ebe75-144">Describes how to create an XML Web service that uses a <xref:System.Data.DataSet> to transport data.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ebe75-145">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="ebe75-145">Related sections</span></span>

 [<span data-ttu-id="ebe75-146">Новые возможности в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ebe75-146">What's New in ADO.NET</span></span>](../whats-new.md)  
 <span data-ttu-id="ebe75-147">Представляет новые возможности ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="ebe75-147">Introduces features that are new in ADO.NET.</span></span>  
  
 [<span data-ttu-id="ebe75-148">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ebe75-148">ADO.NET Overview</span></span>](../ado-net-overview.md)  
 <span data-ttu-id="ebe75-149">Содержит введение в структуру и компоненты ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="ebe75-149">Provides an introduction to the design and components of ADO.NET.</span></span>  
  
 [<span data-ttu-id="ebe75-150">Заполнение набора данных с помощью адаптера данных DataAdapter</span><span class="sxs-lookup"><span data-stu-id="ebe75-150">Populating a DataSet from a DataAdapter</span></span>](../populating-a-dataset-from-a-dataadapter.md)  
 <span data-ttu-id="ebe75-151">Описывается загрузка **DataSet** данными из источника данных.</span><span class="sxs-lookup"><span data-stu-id="ebe75-151">Describes how to load a **DataSet** with data from a data source.</span></span>  
  
 [<span data-ttu-id="ebe75-152">Обновление источников данных с объектами DataAdapter</span><span class="sxs-lookup"><span data-stu-id="ebe75-152">Updating Data Sources with DataAdapters</span></span>](../updating-data-sources-with-dataadapters.md)  
 <span data-ttu-id="ebe75-153">Описывается решение по внесению измененных в **DataSet** данных обратно в источник данных.</span><span class="sxs-lookup"><span data-stu-id="ebe75-153">Describes how to resolve changes to the data in a **DataSet** back to the data source.</span></span>  
  
 [<span data-ttu-id="ebe75-154">Добавление существующих ограничений к набору данных</span><span class="sxs-lookup"><span data-stu-id="ebe75-154">Adding Existing Constraints to a DataSet</span></span>](../adding-existing-constraints-to-a-dataset.md)  
 <span data-ttu-id="ebe75-155">Описывает заполнение **DataSet** сведениями о первичном ключе из источника данных.</span><span class="sxs-lookup"><span data-stu-id="ebe75-155">Describes how to populate a **DataSet** with primary key information from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebe75-156">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ebe75-156">See also</span></span>

- [<span data-ttu-id="ebe75-157">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ebe75-157">ADO.NET</span></span>](../index.md)
- [<span data-ttu-id="ebe75-158">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ebe75-158">ADO.NET Overview</span></span>](../ado-net-overview.md)
