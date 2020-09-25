---
title: DataTables
description: Сведения о ADO.NET DataTable, представляющем одну таблицу реляционных данных в памяти, локальную для. Приложение на основе NET, где оно находится.
ms.date: 03/30/2017
ms.assetid: 52ff0e32-3e5a-41de-9a3b-7b04ea52b83e
ms.openlocfilehash: d501096b4abe94653acdc5249c120abff94534d1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202309"
---
# <a name="datatables"></a><span data-ttu-id="aad4d-103">DataTables</span><span class="sxs-lookup"><span data-stu-id="aad4d-103">DataTables</span></span>

<span data-ttu-id="aad4d-104">Набор данных <xref:System.Data.DataSet> состоит из коллекции таблиц, связей и ограничений.</span><span class="sxs-lookup"><span data-stu-id="aad4d-104">A <xref:System.Data.DataSet> is made up of a collection of tables, relationships, and constraints.</span></span> <span data-ttu-id="aad4d-105">В ADO.NET <xref:System.Data.DataTable> объекты используются для представления таблиц в **наборе данных**.</span><span class="sxs-lookup"><span data-stu-id="aad4d-105">In ADO.NET, <xref:System.Data.DataTable> objects are used to represent the tables in a **DataSet**.</span></span> <span data-ttu-id="aad4d-106">Объект **DataTable** представляет одну таблицу реляционных данных в памяти; данные являются локальными для. NET-приложение, в котором оно находится, но может быть заполнено из источника данных, например Microsoft SQL Server помощью **DataAdapter** . Дополнительные сведения см. в разделе [Заполнение набора данных из DataAdapter](../populating-a-dataset-from-a-dataadapter.md).</span><span class="sxs-lookup"><span data-stu-id="aad4d-106">A **DataTable** represents one table of in-memory relational data; the data is local to the .NET-based application in which it resides, but can be populated from a data source such as Microsoft SQL Server using a **DataAdapter** For more information, see [Populating a DataSet from a DataAdapter](../populating-a-dataset-from-a-dataadapter.md).</span></span>  
  
 <span data-ttu-id="aad4d-107">Класс **DataTable** является членом пространства имен **System. Data** в библиотеке классов .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="aad4d-107">The **DataTable** class is a member of the **System.Data** namespace within the .NET Framework class library.</span></span> <span data-ttu-id="aad4d-108">Можно создавать и использовать **DataTable** независимо или как член **набора данных**, а объекты **DataTable** также можно использовать совместно с другими .NET Frameworkными объектами, включая <xref:System.Data.DataView> .</span><span class="sxs-lookup"><span data-stu-id="aad4d-108">You can create and use a **DataTable** independently or as a member of a **DataSet**, and **DataTable** objects can also be used in conjunction with other .NET Framework objects, including the <xref:System.Data.DataView>.</span></span> <span data-ttu-id="aad4d-109">Доступ к коллекции таблиц в **наборе данных** осуществляется через свойство **Tables** объекта **DataSet** .</span><span class="sxs-lookup"><span data-stu-id="aad4d-109">You access the collection of tables in a **DataSet** through the **Tables** property of the **DataSet** object.</span></span>  
  
 <span data-ttu-id="aad4d-110">Схема или структура таблицы представляется столбцами и ограничениями.</span><span class="sxs-lookup"><span data-stu-id="aad4d-110">The schema, or structure of a table is represented by columns and constraints.</span></span> <span data-ttu-id="aad4d-111">Схема **DataTable** определяется с помощью объектов, а <xref:System.Data.DataColumn> также <xref:System.Data.ForeignKeyConstraint> <xref:System.Data.UniqueConstraint> объектов и.</span><span class="sxs-lookup"><span data-stu-id="aad4d-111">You define the schema of a **DataTable** using <xref:System.Data.DataColumn> objects as well as <xref:System.Data.ForeignKeyConstraint> and <xref:System.Data.UniqueConstraint> objects.</span></span> <span data-ttu-id="aad4d-112">Столбцы таблицы могут сопоставляться со столбцами источника данных, содержать вычисляемые значения выражений, автоматически увеличивать значения или содержать значения первичного ключа.</span><span class="sxs-lookup"><span data-stu-id="aad4d-112">The columns in a table can map to columns in a data source, contain calculated values from expressions, automatically increment their values, or contain primary key values.</span></span>  
  
 <span data-ttu-id="aad4d-113">Помимо схемы, в **DataTable** также должны содержаться строки для хранения и упорядочения данных.</span><span class="sxs-lookup"><span data-stu-id="aad4d-113">In addition to a schema, a **DataTable** must also have rows to contain and order data.</span></span> <span data-ttu-id="aad4d-114">Класс <xref:System.Data.DataRow> представляет фактические данные, содержащиеся в таблице.</span><span class="sxs-lookup"><span data-stu-id="aad4d-114">The <xref:System.Data.DataRow> class represents the actual data contained in a table.</span></span> <span data-ttu-id="aad4d-115">Для получения, вычисления и обработки данных в таблице используется объект **DataRow** и его свойства и методы.</span><span class="sxs-lookup"><span data-stu-id="aad4d-115">You use the **DataRow** and its properties and methods to retrieve, evaluate, and manipulate the data in a table.</span></span> <span data-ttu-id="aad4d-116">При доступе и изменении данных в строке объект **DataRow** сохраняет как текущее, так и исходное состояние.</span><span class="sxs-lookup"><span data-stu-id="aad4d-116">As you access and change the data within a row, the **DataRow** object maintains both its current and original state.</span></span>  
  
 <span data-ttu-id="aad4d-117">С помощью одного или нескольких связанных столбцов таблицы между таблицами можно создавать связи типа «родители-потомки».</span><span class="sxs-lookup"><span data-stu-id="aad4d-117">You can create parent-child relationships between tables using one or more related columns in the tables.</span></span> <span data-ttu-id="aad4d-118">Связь между объектами **DataTable** создается с помощью <xref:System.Data.DataRelation> .</span><span class="sxs-lookup"><span data-stu-id="aad4d-118">You create a relationship between **DataTable** objects using a <xref:System.Data.DataRelation>.</span></span> <span data-ttu-id="aad4d-119">Затем объекты **DataRelation** можно использовать для возврата связанных дочерних или родительских строк определенной строки.</span><span class="sxs-lookup"><span data-stu-id="aad4d-119">**DataRelation** objects can then be used to return the related child or parent rows of a particular row.</span></span> <span data-ttu-id="aad4d-120">Дополнительные сведения см. в разделе [Добавление связей](adding-datarelations.md)данных.</span><span class="sxs-lookup"><span data-stu-id="aad4d-120">For more information, see [Adding DataRelations](adding-datarelations.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="aad4d-121">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="aad4d-121">In This Section</span></span>  

 [<span data-ttu-id="aad4d-122">Создание таблицы данных</span><span class="sxs-lookup"><span data-stu-id="aad4d-122">Creating a DataTable</span></span>](creating-a-datatable.md)  
 <span data-ttu-id="aad4d-123">Объясняет, как создать **таблицу DataTable** и добавить ее в **набор данных**.</span><span class="sxs-lookup"><span data-stu-id="aad4d-123">Explains how to create a **DataTable** and add it to a **DataSet**.</span></span>  
  
 [<span data-ttu-id="aad4d-124">Определение схемы таблицы данных</span><span class="sxs-lookup"><span data-stu-id="aad4d-124">DataTable Schema Definition</span></span>](datatable-schema-definition.md)  
 <span data-ttu-id="aad4d-125">Содержит сведения о создании и использовании объектов **DataColumn** и ограничений.</span><span class="sxs-lookup"><span data-stu-id="aad4d-125">Provides information about creating and using **DataColumn** objects and constraints.</span></span>  
  
 [<span data-ttu-id="aad4d-126">Управление данными в таблице данных</span><span class="sxs-lookup"><span data-stu-id="aad4d-126">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)  
 <span data-ttu-id="aad4d-127">Описывает, как добавлять, изменять и удалять данные таблицы.</span><span class="sxs-lookup"><span data-stu-id="aad4d-127">Explains how to add, modify, and delete data in a table.</span></span> <span data-ttu-id="aad4d-128">Объясняет, как использовать события **DataTable** для проверки изменений данных в таблице.</span><span class="sxs-lookup"><span data-stu-id="aad4d-128">Explains how to use **DataTable** events to examine changes to data in the table.</span></span>  
  
 [<span data-ttu-id="aad4d-129">Обработка событий таблиц данных</span><span class="sxs-lookup"><span data-stu-id="aad4d-129">Handling DataTable Events</span></span>](handling-datatable-events.md)  
 <span data-ttu-id="aad4d-130">Предоставляет сведения о событиях, доступных для использования с **таблицей**данных, включая события при изменении значений столбцов и добавлении или удалении строк.</span><span class="sxs-lookup"><span data-stu-id="aad4d-130">Provides information about the events available for use with a **DataTable**, including events when column values are modified and rows are added or deleted.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="aad4d-131">См. также</span><span class="sxs-lookup"><span data-stu-id="aad4d-131">Related Sections</span></span>  

 [<span data-ttu-id="aad4d-132">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="aad4d-132">ADO.NET</span></span>](../index.md)  
 <span data-ttu-id="aad4d-133">Описывает архитектуру и компоненты ADO.NET, а также их использование для получения доступа к существующим источникам данных и управления данными приложения.</span><span class="sxs-lookup"><span data-stu-id="aad4d-133">Describes the ADO.NET architecture and components, and how to use them to access existing data sources and manage application data.</span></span>  
  
 [<span data-ttu-id="aad4d-134">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="aad4d-134">DataSets, DataTables, and DataViews</span></span>](index.md)  
 <span data-ttu-id="aad4d-135">Предоставляет сведения о **наборе данных** ADO.NET, включая создание связей между таблицами.</span><span class="sxs-lookup"><span data-stu-id="aad4d-135">Provides information about the ADO.NET **DataSet** including how to create relationships between tables.</span></span>  
  
 <xref:System.Data.Constraint>  
 <span data-ttu-id="aad4d-136">Содержит справочные сведения об объекте **constraint** .</span><span class="sxs-lookup"><span data-stu-id="aad4d-136">Provides reference information about the **Constraint** object.</span></span>  
  
 <xref:System.Data.DataColumn>  
 <span data-ttu-id="aad4d-137">Содержит справочные сведения об объекте **DataColumn** .</span><span class="sxs-lookup"><span data-stu-id="aad4d-137">Provides reference information about the **DataColumn** object.</span></span>  
  
 <xref:System.Data.DataSet>  
 <span data-ttu-id="aad4d-138">Содержит справочные сведения об объекте **DataSet** .</span><span class="sxs-lookup"><span data-stu-id="aad4d-138">Provides reference information about the **DataSet** object.</span></span>  
  
 <xref:System.Data.DataTable>  
 <span data-ttu-id="aad4d-139">Содержит справочные сведения о объекте **DataTable** .</span><span class="sxs-lookup"><span data-stu-id="aad4d-139">Provides reference information about the **DataTable** object.</span></span>  
  
 [<span data-ttu-id="aad4d-140">Общие сведения о библиотеке классов</span><span class="sxs-lookup"><span data-stu-id="aad4d-140">Class Library Overview</span></span>](../../../../standard/class-library-overview.md)  
 <span data-ttu-id="aad4d-141">Содержит общие сведения о библиотеке классов .NET Framework, включая пространство имен **System** , а также его пространство имен второго уровня, **System. Data**.</span><span class="sxs-lookup"><span data-stu-id="aad4d-141">Provides an overview of the .NET Framework class library, including the **System** namespace as well as its second-level namespace, **System.Data**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aad4d-142">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="aad4d-142">See also</span></span>

- [<span data-ttu-id="aad4d-143">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="aad4d-143">ADO.NET Overview</span></span>](../ado-net-overview.md)
