---
title: Наборы данных, таблицы данных и объекты DataView
description: Изучите несколько способов работы с набором данных ADO.NET, представленным в памяти представлением данных, обеспечивающим единообразную реляционную модель программирования.
ms.date: 03/30/2017
ms.assetid: 6d4c4b69-8919-4224-8a65-6cca1c61b48f
ms.openlocfilehash: f6562452261cbc1f7ee36fb264b858646a42e4f5
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286899"
---
# <a name="datasets-datatables-and-dataviews"></a><span data-ttu-id="f7fb0-103">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="f7fb0-103">DataSets, DataTables, and DataViews</span></span>
<span data-ttu-id="f7fb0-104">ADO.NET <xref:System.Data.DataSet> - расположенное в оперативной памяти представление данных, обеспечивающее согласованную реляционную программную модель независимо от источника данных.</span><span class="sxs-lookup"><span data-stu-id="f7fb0-104">The ADO.NET <xref:System.Data.DataSet> is a memory-resident representation of data that provides a consistent relational programming model regardless of the source of the data it contains.</span></span> <span data-ttu-id="f7fb0-105"><xref:System.Data.DataSet> представляет полный набор данных, включая таблицы, содержащие, упорядочивающие и ограничивающие данные, а также связи между таблицами.</span><span class="sxs-lookup"><span data-stu-id="f7fb0-105">A <xref:System.Data.DataSet> represents a complete set of data including the tables that contain, order, and constrain the data, as well as the relationships between the tables.</span></span>  
  
 <span data-ttu-id="f7fb0-106">Существует несколько способов работы с <xref:System.Data.DataSet>, которые могут применяться отдельно или в сочетании.</span><span class="sxs-lookup"><span data-stu-id="f7fb0-106">There are several ways of working with a <xref:System.Data.DataSet>, which can be applied independently or in combination.</span></span> <span data-ttu-id="f7fb0-107">Вы можете выбрать один из следующих вариантов.</span><span class="sxs-lookup"><span data-stu-id="f7fb0-107">You can:</span></span>  
  
- <span data-ttu-id="f7fb0-108">Программно создать <xref:System.Data.DataTable>, <xref:System.Data.DataRelation> и <xref:System.Data.Constraint> внутри <xref:System.Data.DataSet> и заполнить таблицы данными.</span><span class="sxs-lookup"><span data-stu-id="f7fb0-108">Programmatically create a <xref:System.Data.DataTable>, <xref:System.Data.DataRelation>, and <xref:System.Data.Constraint> within a <xref:System.Data.DataSet> and populate the tables with data.</span></span>  
  
- <span data-ttu-id="f7fb0-109">Заполнить <xref:System.Data.DataSet> таблицами данных из существующего реляционного источника данных с помощью `DataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="f7fb0-109">Populate the <xref:System.Data.DataSet> with tables of data from an existing relational data source using a `DataAdapter`.</span></span>  
  
- <span data-ttu-id="f7fb0-110">Загрузить и сохранить содержимое <xref:System.Data.DataSet> с помощью XML-кода.</span><span class="sxs-lookup"><span data-stu-id="f7fb0-110">Load and persist the <xref:System.Data.DataSet> contents using XML.</span></span> <span data-ttu-id="f7fb0-111">Дополнительные сведения см. в статье [Использование XML в наборах данных](using-xml-in-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="f7fb0-111">For more information, see [Using XML in a DataSet](using-xml-in-a-dataset.md).</span></span>  
  
 <span data-ttu-id="f7fb0-112">Строго типизированный <xref:System.Data.DataSet> также можно передавать с помощью веб-службы с поддержкой XML-кода.</span><span class="sxs-lookup"><span data-stu-id="f7fb0-112">A strongly typed <xref:System.Data.DataSet> can also be transported using an XML Web service.</span></span> <span data-ttu-id="f7fb0-113">Конструкция <xref:System.Data.DataSet> делает его идеальным для передачи данных с помощью веб-служб с поддержкой XML-кода.</span><span class="sxs-lookup"><span data-stu-id="f7fb0-113">The design of the <xref:System.Data.DataSet> makes it ideal for transporting data using XML Web services.</span></span> <span data-ttu-id="f7fb0-114">Общие сведения об XML-веб-службах см. в разделе [Общие сведения об XML-веб-службах](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w9fdtx28(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="f7fb0-114">For an overview of XML Web services, see [XML Web Services Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w9fdtx28(v=vs.100)).</span></span> <span data-ttu-id="f7fb0-115">Пример использования <xref:System.Data.DataSet> из XML-веб-службы см. в разделе [Потребление набора данных из веб-службы XML](consuming-a-dataset-from-an-xml-web-service.md).</span><span class="sxs-lookup"><span data-stu-id="f7fb0-115">For an example of consuming a <xref:System.Data.DataSet> from an XML Web service, see [Consuming a DataSet from an XML Web Service](consuming-a-dataset-from-an-xml-web-service.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f7fb0-116">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="f7fb0-116">In This Section</span></span>  
 [<span data-ttu-id="f7fb0-117">Создание набора данных</span><span class="sxs-lookup"><span data-stu-id="f7fb0-117">Creating a DataSet</span></span>](creating-a-dataset.md)  
 <span data-ttu-id="f7fb0-118">Описывает синтаксис, необходимый для создания экземпляра <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="f7fb0-118">Describes the syntax for creating an instance of a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="f7fb0-119">Добавление новой таблицы данных в набор данных</span><span class="sxs-lookup"><span data-stu-id="f7fb0-119">Adding a DataTable to a DataSet</span></span>](adding-a-datatable-to-a-dataset.md)  
 <span data-ttu-id="f7fb0-120">Описывает создание и добавление таблиц и столбцов в <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="f7fb0-120">Describes how to create and add tables and columns to a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="f7fb0-121">Добавление отношений DataRelation</span><span class="sxs-lookup"><span data-stu-id="f7fb0-121">Adding DataRelations</span></span>](adding-datarelations.md)  
 <span data-ttu-id="f7fb0-122">Описывает создание связей между таблицами <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="f7fb0-122">Describes how to create relations between tables in a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="f7fb0-123">Навигация по отношениям DataRelation</span><span class="sxs-lookup"><span data-stu-id="f7fb0-123">Navigating DataRelations</span></span>](navigating-datarelations.md)  
 <span data-ttu-id="f7fb0-124">Описывает использование связей между таблицами <xref:System.Data.DataSet> для возвращения дочерних или родительских строк связи типа «родитель-потомок».</span><span class="sxs-lookup"><span data-stu-id="f7fb0-124">Describes how to use the relations between tables in a <xref:System.Data.DataSet> to return the child or parent rows of a parent-child relationship.</span></span>  
  
 [<span data-ttu-id="f7fb0-125">Слияние содержимого набора данных</span><span class="sxs-lookup"><span data-stu-id="f7fb0-125">Merging DataSet Contents</span></span>](merging-dataset-contents.md)  
 <span data-ttu-id="f7fb0-126">Описывает процесс слияния содержимого одного <xref:System.Data.DataSet>, <xref:System.Data.DataTable> или массива <xref:System.Data.DataRow> с <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="f7fb0-126">Describes how to merge the contents of one <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, or <xref:System.Data.DataRow> array into another <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="f7fb0-127">Копирование содержимого набора данных</span><span class="sxs-lookup"><span data-stu-id="f7fb0-127">Copying DataSet Contents</span></span>](copying-dataset-contents.md)  
 <span data-ttu-id="f7fb0-128">Описывает создание копии <xref:System.Data.DataSet>, которая может содержать схему, а также указанные данные.</span><span class="sxs-lookup"><span data-stu-id="f7fb0-128">Describes how to create a copy of a <xref:System.Data.DataSet> that can contain schema as well as specified data.</span></span>  
  
 [<span data-ttu-id="f7fb0-129">Обработка событий наборов данных</span><span class="sxs-lookup"><span data-stu-id="f7fb0-129">Handling DataSet Events</span></span>](handling-dataset-events.md)  
 <span data-ttu-id="f7fb0-130">Описывает события <xref:System.Data.DataSet> и их использование.</span><span class="sxs-lookup"><span data-stu-id="f7fb0-130">Describes the events of a <xref:System.Data.DataSet> and how to use them.</span></span>  
  
 [<span data-ttu-id="f7fb0-131">Типизированные наборы данных</span><span class="sxs-lookup"><span data-stu-id="f7fb0-131">Typed DataSets</span></span>](typed-datasets.md)  
 <span data-ttu-id="f7fb0-132">Обсуждается, что такое типизированный <xref:System.Data.DataSet> и как его создавать и использовать.</span><span class="sxs-lookup"><span data-stu-id="f7fb0-132">Discusses what a typed <xref:System.Data.DataSet> is and how to create and use it.</span></span>  
  
 [<span data-ttu-id="f7fb0-133">DataTables</span><span class="sxs-lookup"><span data-stu-id="f7fb0-133">DataTables</span></span>](datatables.md)  
 <span data-ttu-id="f7fb0-134">Описывает создание <xref:System.Data.DataTable>, определение схемы и управление данными.</span><span class="sxs-lookup"><span data-stu-id="f7fb0-134">Describes how to create a <xref:System.Data.DataTable>, define the schema, and manipulate data.</span></span>  
  
 [<span data-ttu-id="f7fb0-135">Объекты DataTableReader</span><span class="sxs-lookup"><span data-stu-id="f7fb0-135">DataTableReaders</span></span>](datatablereaders.md)  
 <span data-ttu-id="f7fb0-136">Описывает создание и использование <xref:System.Data.DataTableReader>.</span><span class="sxs-lookup"><span data-stu-id="f7fb0-136">Describes how to create and use a <xref:System.Data.DataTableReader>.</span></span>  
  
 [<span data-ttu-id="f7fb0-137">Объекты DataView</span><span class="sxs-lookup"><span data-stu-id="f7fb0-137">DataViews</span></span>](dataviews.md)  
 <span data-ttu-id="f7fb0-138">Описывает создание `DataViews` и работу с ними, а также работу с событиями <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="f7fb0-138">Describes how to create and work with `DataViews` and work with <xref:System.Data.DataView> events.</span></span>  
  
 [<span data-ttu-id="f7fb0-139">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="f7fb0-139">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)  
 <span data-ttu-id="f7fb0-140">Описывает взаимодействие <xref:System.Data.DataSet> с XML-данными в качестве источника данных, включая загрузку и сохранение содержимого <xref:System.Data.DataSet> в виде XML-данных.</span><span class="sxs-lookup"><span data-stu-id="f7fb0-140">Describes how the <xref:System.Data.DataSet> interacts with XML as a data source, including loading and persisting the contents of a <xref:System.Data.DataSet> as XML data.</span></span>  
  
 [<span data-ttu-id="f7fb0-141">Потребление набора данных из веб-службы XML</span><span class="sxs-lookup"><span data-stu-id="f7fb0-141">Consuming a DataSet from an XML Web Service</span></span>](consuming-a-dataset-from-an-xml-web-service.md)  
 <span data-ttu-id="f7fb0-142">Описывает создание веб-службы с поддержкой XML, использующей <xref:System.Data.DataSet> для передачи данных.</span><span class="sxs-lookup"><span data-stu-id="f7fb0-142">Describes how to create an XML Web service that uses a <xref:System.Data.DataSet> to transport data.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f7fb0-143">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="f7fb0-143">Related Sections</span></span>  
 [<span data-ttu-id="f7fb0-144">Новые возможности в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f7fb0-144">What's New in ADO.NET</span></span>](../whats-new.md)  
 <span data-ttu-id="f7fb0-145">Представляет новые возможности ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="f7fb0-145">Introduces features that are new in ADO.NET.</span></span>  
  
 [<span data-ttu-id="f7fb0-146">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f7fb0-146">ADO.NET Overview</span></span>](../ado-net-overview.md)  
 <span data-ttu-id="f7fb0-147">Содержит введение в структуру и компоненты ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="f7fb0-147">Provides an introduction to the design and components of ADO.NET.</span></span>  
  
 [<span data-ttu-id="f7fb0-148">Заполнение набора данных с помощью адаптера данных DataAdapter</span><span class="sxs-lookup"><span data-stu-id="f7fb0-148">Populating a DataSet from a DataAdapter</span></span>](../populating-a-dataset-from-a-dataadapter.md)  
 <span data-ttu-id="f7fb0-149">Описывается загрузка **DataSet** данными из источника данных.</span><span class="sxs-lookup"><span data-stu-id="f7fb0-149">Describes how to load a **DataSet** with data from a data source.</span></span>  
  
 [<span data-ttu-id="f7fb0-150">Обновление источников данных с объектами DataAdapter</span><span class="sxs-lookup"><span data-stu-id="f7fb0-150">Updating Data Sources with DataAdapters</span></span>](../updating-data-sources-with-dataadapters.md)  
 <span data-ttu-id="f7fb0-151">Описывается решение по внесению измененных в **DataSet** данных обратно в источник данных.</span><span class="sxs-lookup"><span data-stu-id="f7fb0-151">Describes how to resolve changes to the data in a **DataSet** back to the data source.</span></span>  
  
 [<span data-ttu-id="f7fb0-152">Добавление существующих ограничений к набору данных</span><span class="sxs-lookup"><span data-stu-id="f7fb0-152">Adding Existing Constraints to a DataSet</span></span>](../adding-existing-constraints-to-a-dataset.md)  
 <span data-ttu-id="f7fb0-153">Описывает заполнение **DataSet** сведениями о первичном ключе из источника данных.</span><span class="sxs-lookup"><span data-stu-id="f7fb0-153">Describes how to populate a **DataSet** with primary key information from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7fb0-154">См. также</span><span class="sxs-lookup"><span data-stu-id="f7fb0-154">See also</span></span>

- [<span data-ttu-id="f7fb0-155">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f7fb0-155">ADO.NET</span></span>](../index.md)
- [<span data-ttu-id="f7fb0-156">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f7fb0-156">ADO.NET Overview</span></span>](../ado-net-overview.md)
