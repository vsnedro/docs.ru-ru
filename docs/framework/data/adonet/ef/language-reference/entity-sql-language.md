---
title: Язык Entity SQL
ms.date: 03/30/2017
ms.assetid: 9e7d8837-28c5-429d-a824-7bafb59724cf
ms.openlocfilehash: 2600b7626ebc5196c702f2d1e3159fd9549227f7
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553386"
---
# <a name="entity-sql-language"></a><span data-ttu-id="f90e6-102">Язык Entity SQL</span><span class="sxs-lookup"><span data-stu-id="f90e6-102">Entity SQL Language</span></span>
<span data-ttu-id="f90e6-103">Entity SQL представляет собой независимый от хранилища язык запросов, аналогичный языку SQL.</span><span class="sxs-lookup"><span data-stu-id="f90e6-103">Entity SQL is a storage-independent query language that is similar to SQL.</span></span> <span data-ttu-id="f90e6-104">Entity SQL позволяет выполнять запросы к данным сущности, представленным либо в виде объектов, либо в табличной форме.</span><span class="sxs-lookup"><span data-stu-id="f90e6-104">Entity SQL allows you to query entity data, either as objects or in a tabular form.</span></span> <span data-ttu-id="f90e6-105">Возможность использования Entity SQL необходимо рассматривать в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="f90e6-105">You should consider using Entity SQL in the following cases:</span></span>  
  
- <span data-ttu-id="f90e6-106">Если запрос должен создаваться динамически во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="f90e6-106">When a query must be dynamically constructed at runtime.</span></span> <span data-ttu-id="f90e6-107">В этом случае следует также рассмотреть возможность использования методов построителя запросов <xref:System.Data.Objects.ObjectQuery%601> вместо создания строки запроса Entity SQL во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="f90e6-107">In this case, you should also consider using the query builder methods of <xref:System.Data.Objects.ObjectQuery%601> instead of constructing an Entity SQL query string at runtime.</span></span>  
  
- <span data-ttu-id="f90e6-108">Если требуется определить запрос как часть определения модели.</span><span class="sxs-lookup"><span data-stu-id="f90e6-108">When you want to define a query as part of the model definition.</span></span> <span data-ttu-id="f90e6-109">В модели данных поддерживается только Entity SQL.</span><span class="sxs-lookup"><span data-stu-id="f90e6-109">Only Entity SQL is supported in a data model.</span></span> <span data-ttu-id="f90e6-110">Дополнительные сведения см. в разделе [QueryView Element (MSL)](/ef/ef6/modeling/designer/advanced/edmx/msl-spec#queryview-element-msl) .</span><span class="sxs-lookup"><span data-stu-id="f90e6-110">For more information, see [QueryView Element (MSL)](/ef/ef6/modeling/designer/advanced/edmx/msl-spec#queryview-element-msl)</span></span>  
  
- <span data-ttu-id="f90e6-111">Если EntityClient применяется для возврата допускающих только для чтения данных сущности в виде наборов строк с использованием <xref:System.Data.EntityClient.EntityDataReader>.</span><span class="sxs-lookup"><span data-stu-id="f90e6-111">When using EntityClient to return read-only entity data as rowsets using a <xref:System.Data.EntityClient.EntityDataReader>.</span></span> <span data-ttu-id="f90e6-112">Дополнительные сведения см. [в разделе Поставщик EntityClient для Entity Framework](../entityclient-provider-for-the-entity-framework.md).</span><span class="sxs-lookup"><span data-stu-id="f90e6-112">For more information, see [EntityClient Provider for the Entity Framework](../entityclient-provider-for-the-entity-framework.md).</span></span>  
  
- <span data-ttu-id="f90e6-113">Для специалиста по языкам запросов на основе SQL язык Entity SQL может оказаться самым естественным выбором.</span><span class="sxs-lookup"><span data-stu-id="f90e6-113">If you are already an expert in SQL-based query languages, Entity SQL may seem the most natural to you.</span></span>  
  
## <a name="using-entity-sql-with-the-entityclient-provider"></a><span data-ttu-id="f90e6-114">Использование Entity SQL с поставщиком EntityClient</span><span class="sxs-lookup"><span data-stu-id="f90e6-114">Using Entity SQL with the EntityClient provider</span></span>  
 <span data-ttu-id="f90e6-115">Если требуется использовать Entity SQL с поставщиком EntityClient, см. дополнительные сведения в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="f90e6-115">If you want to use Entity SQL with the EntityClient provider, see the following topics for more information:</span></span>  
  
 [<span data-ttu-id="f90e6-116">Поставщик EntityClient для Entity Framework</span><span class="sxs-lookup"><span data-stu-id="f90e6-116">EntityClient Provider for the Entity Framework</span></span>](../entityclient-provider-for-the-entity-framework.md)  
  
 [<span data-ttu-id="f90e6-117">Практическое руководство. Сборка строки соединения EntityConnection</span><span class="sxs-lookup"><span data-stu-id="f90e6-117">How to: Build an EntityConnection Connection String</span></span>](../how-to-build-an-entityconnection-connection-string.md)  
  
 [<span data-ttu-id="f90e6-118">Практическое руководство. Выполнение запроса, возвращающего типы-примитивы</span><span class="sxs-lookup"><span data-stu-id="f90e6-118">How to: Execute a Query that Returns PrimitiveType Results</span></span>](../how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [<span data-ttu-id="f90e6-119">Практическое руководство. Выполнение запроса, возвращающего результаты типа StructuralType</span><span class="sxs-lookup"><span data-stu-id="f90e6-119">How to: Execute a Query that Returns StructuralType Results</span></span>](../how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [<span data-ttu-id="f90e6-120">Практическое руководство. Выполнение запроса, возвращающего результаты RefType</span><span class="sxs-lookup"><span data-stu-id="f90e6-120">How to: Execute a Query that Returns RefType Results</span></span>](../how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [<span data-ttu-id="f90e6-121">Практическое руководство. Выполнение запроса, возвращающего сложные типы</span><span class="sxs-lookup"><span data-stu-id="f90e6-121">How to: Execute a Query that Returns Complex Types</span></span>](../how-to-execute-a-query-that-returns-complex-types.md)  
  
 [<span data-ttu-id="f90e6-122">Практическое руководство. Выполнение запроса, возвращающего вложенные коллекции</span><span class="sxs-lookup"><span data-stu-id="f90e6-122">How to: Execute a Query that Returns Nested Collections</span></span>](../how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [<span data-ttu-id="f90e6-123">Практическое руководство. Выполнение SQL-запроса к параметрическому объекту с использованием EntityCommand</span><span class="sxs-lookup"><span data-stu-id="f90e6-123">How to: Execute a Parameterized Entity SQL Query Using EntityCommand</span></span>](../how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [<span data-ttu-id="f90e6-124">Практическое руководство. Выполнение параметризованной хранимой процедуры с использованием EntityCommand</span><span class="sxs-lookup"><span data-stu-id="f90e6-124">How to: Execute a Parameterized Stored Procedure Using EntityCommand</span></span>](../how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [<span data-ttu-id="f90e6-125">Практическое руководство. Выполнение полиморфного запроса</span><span class="sxs-lookup"><span data-stu-id="f90e6-125">How to: Execute a Polymorphic Query</span></span>](../how-to-execute-a-polymorphic-query.md)  
  
 [<span data-ttu-id="f90e6-126">Практическое руководство. Переход по отношениям с помощью оператора Navigate</span><span class="sxs-lookup"><span data-stu-id="f90e6-126">How to: Navigate Relationships with the Navigate Operator</span></span>](../how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="using-entity-sql-with-object-queries"></a><span data-ttu-id="f90e6-127">Использование Entity SQL с запросами объектов</span><span class="sxs-lookup"><span data-stu-id="f90e6-127">Using Entity SQL with object queries</span></span>  
 <span data-ttu-id="f90e6-128">Если требуется использовать Entity SQL с запросами объектов, см. дополнительные сведения в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="f90e6-128">If you want to use Entity SQL with object queries, see the following topics for more information:</span></span>  
  
 <span data-ttu-id="f90e6-129">[Практическое руководство. Выполнение запроса, возвращающего объекты типа сущностей](/previous-versions/dotnet/netframework-4.0/bb738694(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f90e6-129">[How to: Execute a Query that Returns Entity Type Objects](/previous-versions/dotnet/netframework-4.0/bb738694(v=vs.100))</span></span>  
  
 <span data-ttu-id="f90e6-130">[Практическое руководство. Выполнение параметризованного запроса](/previous-versions/dotnet/netframework-4.0/bb738521(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f90e6-130">[How to: Execute a Parameterized Query](/previous-versions/dotnet/netframework-4.0/bb738521(v=vs.100))</span></span>  
  
 <span data-ttu-id="f90e6-131">[Практическое руководство. Навигация по отношениям с помощью свойств навигации](/previous-versions/dotnet/netframework-4.0/bb896321(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f90e6-131">[How to: Navigate Relationships Using Navigation Properties](/previous-versions/dotnet/netframework-4.0/bb896321(v=vs.100))</span></span>  
  
 <span data-ttu-id="f90e6-132">[Практическое руководство. Вызов пользовательских функций](/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f90e6-132">[How to: Call a User-Defined Function](/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))</span></span>  
  
 <span data-ttu-id="f90e6-133">[Практическое руководство. Фильтрация данных](/previous-versions/dotnet/netframework-4.0/cc716755(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f90e6-133">[How to: Filter Data](/previous-versions/dotnet/netframework-4.0/cc716755(v=vs.100))</span></span>  
  
 <span data-ttu-id="f90e6-134">[Практическое руководство. Сортировка данных](/previous-versions/dotnet/netframework-4.0/cc716784(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f90e6-134">[How to: Sort Data](/previous-versions/dotnet/netframework-4.0/cc716784(v=vs.100))</span></span>  
  
 <span data-ttu-id="f90e6-135">[Практическое руководство. Группировка данных](/previous-versions/dotnet/netframework-4.0/bb896341(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f90e6-135">[How to: Group Data](/previous-versions/dotnet/netframework-4.0/bb896341(v=vs.100))</span></span>  
  
 <span data-ttu-id="f90e6-136">[Практическое руководство. Агрегирование данных](/previous-versions/dotnet/netframework-4.0/cc716738(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f90e6-136">[How to: Aggregate Data](/previous-versions/dotnet/netframework-4.0/cc716738(v=vs.100))</span></span>  
  
 <span data-ttu-id="f90e6-137">[Практическое руководство. Выполнение запроса, возвращающего объекты анонимного типа](/previous-versions/dotnet/netframework-4.0/bb738512(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f90e6-137">[How to: Execute a Query that Returns Anonymous Type Objects](/previous-versions/dotnet/netframework-4.0/bb738512(v=vs.100))</span></span>  
  
 <span data-ttu-id="f90e6-138">[Практическое руководство. Выполнение запроса, возвращающего коллекцию примитивных типов](/previous-versions/dotnet/netframework-4.0/bb738451(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f90e6-138">[How to: Execute a Query that Returns a Collection of Primitive Types](/previous-versions/dotnet/netframework-4.0/bb738451(v=vs.100))</span></span>  
  
 <span data-ttu-id="f90e6-139">[Практическое руководство. Запросы связанных объектов в EntityCollection](/previous-versions/dotnet/netframework-4.0/cc716708(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f90e6-139">[How to: Query Related Objects in an EntityCollection](/previous-versions/dotnet/netframework-4.0/cc716708(v=vs.100))</span></span>  
  
 <span data-ttu-id="f90e6-140">[Практическое руководство. Порядок объединения двух запросов](/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f90e6-140">[How to: Order the Union of Two Queries](/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100))</span></span>  
  
 <span data-ttu-id="f90e6-141">[Практическое руководство. Разбивка на страницы результатов запроса](/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f90e6-141">[How to: Page Through Query Results](/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f90e6-142">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="f90e6-142">In This Section</span></span>  
 [<span data-ttu-id="f90e6-143">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="f90e6-143">Entity SQL Overview</span></span>](entity-sql-overview.md)  
  
 [<span data-ttu-id="f90e6-144">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="f90e6-144">Entity SQL Reference</span></span>](entity-sql-reference.md)  
  
## <a name="see-also"></a><span data-ttu-id="f90e6-145">См. также</span><span class="sxs-lookup"><span data-stu-id="f90e6-145">See also</span></span>

- [<span data-ttu-id="f90e6-146">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="f90e6-146">ADO.NET Entity Framework</span></span>](../index.md)
- [<span data-ttu-id="f90e6-147">Справочник по языку</span><span class="sxs-lookup"><span data-stu-id="f90e6-147">Language Reference</span></span>](index.md)
