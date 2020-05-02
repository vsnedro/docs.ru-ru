---
title: Ограничения ADO.NET
ms.date: 12/13/2019
description: Описание некоторых ограничений ADO.NET, которые могут возникнуть.
ms.openlocfilehash: 8664b73071fc859ed30080f549b05e7d6ed020f4
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901255"
---
# <a name="adonet-limitations"></a><span data-ttu-id="55455-103">Ограничения ADO.NET</span><span class="sxs-lookup"><span data-stu-id="55455-103">ADO.NET limitations</span></span>

<span data-ttu-id="55455-104">Microsoft. Data. SQLite предоставляет реализации многих абстракций ADO.NET, но с некоторыми ограничениями.</span><span class="sxs-lookup"><span data-stu-id="55455-104">Microsoft.Data.Sqlite provides implementations of many of the ADO.NET abstractions, but there are some limitations.</span></span>

## <a name="database-schema-information"></a><span data-ttu-id="55455-105">Сведения о схеме базы данных</span><span class="sxs-lookup"><span data-stu-id="55455-105">Database schema information</span></span>

<span data-ttu-id="55455-106">Метаданные о результатах запросов доступны с помощью метода <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A>.</span><span class="sxs-lookup"><span data-stu-id="55455-106">Metadata about query results is available using the <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> method.</span></span>

<span data-ttu-id="55455-107">Реализация `DbConnection.GetSchema()` отсутствует.</span><span class="sxs-lookup"><span data-stu-id="55455-107">`DbConnection.GetSchema()` isn't implemented.</span></span> <span data-ttu-id="55455-108">Этот API не определен правильно, поэтому мы рекомендуем получать метаданные базы данных непосредственно с помощью стандартных API-интерфейсов SQLite, таких как таблица [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) и прагма [table_info](https://www.sqlite.org/pragma.html#pragma_table_info).</span><span class="sxs-lookup"><span data-stu-id="55455-108">This API isn't well-defined, so we recommend retrieving database metadata directly using standard SQLite APIs like the [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) table and the [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) PRAGMA.</span></span>

<span data-ttu-id="55455-109">Дополнительные сведения см. в разделе [Метаданные](metadata.md).</span><span class="sxs-lookup"><span data-stu-id="55455-109">For more information, see [Metadata](metadata.md).</span></span>

## <a name="systemtransactions"></a><span data-ttu-id="55455-110">System.Transactions</span><span class="sxs-lookup"><span data-stu-id="55455-110">System.Transactions</span></span>

<span data-ttu-id="55455-111">Microsoft.Data.Sqlite пока не поддерживает System.Transactions.</span><span class="sxs-lookup"><span data-stu-id="55455-111">Microsoft.Data.Sqlite doesn't yet support System.Transactions.</span></span> <span data-ttu-id="55455-112">Вместо этого используйте транзакции ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="55455-112">Use ADO.NET transactions instead.</span></span> <span data-ttu-id="55455-113">Дополнительные сведения см. в статье о [транзакциях](transactions.md).</span><span class="sxs-lookup"><span data-stu-id="55455-113">For more information, see [Transactions](transactions.md).</span></span>

<span data-ttu-id="55455-114">Предоставьте отзыв об отсутствии поддержки System.Transactions в проблеме [#13825](https://github.com/dotnet/efcore/issues/13825).</span><span class="sxs-lookup"><span data-stu-id="55455-114">Provide feedback about the lack of support for System.Transactions on issue [#13825](https://github.com/dotnet/efcore/issues/13825).</span></span>

## <a name="data-adapters"></a><span data-ttu-id="55455-115">Адаптеры данных</span><span class="sxs-lookup"><span data-stu-id="55455-115">Data adapters</span></span>

<span data-ttu-id="55455-116">`DbDataAdapter` еще не реализован в Microsoft.Data.Sqlite.</span><span class="sxs-lookup"><span data-stu-id="55455-116">`DbDataAdapter` isn't yet implemented by Microsoft.Data.Sqlite.</span></span> <span data-ttu-id="55455-117">Это означает, что `DataSet` и `DataTable` ADO.NET можно использовать только для загрузки данных, но не их обновления.</span><span class="sxs-lookup"><span data-stu-id="55455-117">This means you can only use ADO.NET `DataSet` and `DataTable` to load data and not update it.</span></span>

<span data-ttu-id="55455-118">Используйте проблему [#13838](https://github.com/dotnet/efcore/issues/13838), чтобы отправить отзыв о реализации `DbDataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="55455-118">Use issue [#13838](https://github.com/dotnet/efcore/issues/13838) to provide feedback about implementing `DbDataAdapter`.</span></span>

## <a name="output-parameters"></a><span data-ttu-id="55455-119">Параметры вывода</span><span class="sxs-lookup"><span data-stu-id="55455-119">Output parameters</span></span>

<span data-ttu-id="55455-120">SQLite не поддерживает выходные параметры.</span><span class="sxs-lookup"><span data-stu-id="55455-120">SQLite doesn't support output parameters.</span></span>

## <a name="positional-parameters"></a><span data-ttu-id="55455-121">Позиционные параметры</span><span class="sxs-lookup"><span data-stu-id="55455-121">Positional parameters</span></span>

<span data-ttu-id="55455-122">Microsoft.Data.Sqlite поддерживает только именованные [параметры](parameters.md).</span><span class="sxs-lookup"><span data-stu-id="55455-122">Microsoft.Data.Sqlite only supports named [parameters](parameters.md).</span></span> <span data-ttu-id="55455-123">Позиционные параметры не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="55455-123">Positional parameters aren't supported.</span></span>

## <a name="stored-procedures"></a><span data-ttu-id="55455-124">Хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="55455-124">Stored procedures</span></span>

<span data-ttu-id="55455-125">SQLite не поддерживает хранимые процедуры.</span><span class="sxs-lookup"><span data-stu-id="55455-125">SQLite doesn't support stored procedures.</span></span>

## <a name="isolation-levels"></a><span data-ttu-id="55455-126">Уровни изоляции</span><span class="sxs-lookup"><span data-stu-id="55455-126">Isolation levels</span></span>

<span data-ttu-id="55455-127">Уровни изоляции `Chaos` и `Snapshot` не поддерживаются в транзакциях SQLite.</span><span class="sxs-lookup"><span data-stu-id="55455-127">The `Chaos` and `Snapshot` isolation levels aren't supported in SQLite transactions.</span></span>

## <a name="see-also"></a><span data-ttu-id="55455-128">См. также</span><span class="sxs-lookup"><span data-stu-id="55455-128">See also</span></span>

* [<span data-ttu-id="55455-129">Ограничения асинхронного режима</span><span class="sxs-lookup"><span data-stu-id="55455-129">Async limitations</span></span>](async.md)
* [<span data-ttu-id="55455-130">Типы данных</span><span class="sxs-lookup"><span data-stu-id="55455-130">Data types</span></span>](types.md)
* [<span data-ttu-id="55455-131">Транзакции</span><span class="sxs-lookup"><span data-stu-id="55455-131">Transactions</span></span>](transactions.md)
