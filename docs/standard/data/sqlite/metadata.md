---
title: Метаданные
ms.date: 12/13/2019
description: Сведения о том, как получать метаданные о базе данных.
ms.openlocfilehash: b2f2704a748627d9943943fa2fa7b1b7e9f3007f
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450432"
---
# <a name="metadata"></a><span data-ttu-id="9166a-103">Метаданные</span><span class="sxs-lookup"><span data-stu-id="9166a-103">Metadata</span></span>

<span data-ttu-id="9166a-104">В ADO.NET есть два интерфейса API для получения метаданных.</span><span class="sxs-lookup"><span data-stu-id="9166a-104">There are two APIs for retrieving metadata in ADO.NET.</span></span> <span data-ttu-id="9166a-105">Один из них извлекает метаданные о результатах запроса.</span><span class="sxs-lookup"><span data-stu-id="9166a-105">One retrieves metadata about query results.</span></span> <span data-ttu-id="9166a-106">Второй извлекает метаданные о схеме базы данных.</span><span class="sxs-lookup"><span data-stu-id="9166a-106">The other retrieves metadata about the database schema.</span></span>

## <a name="query-result-metadata"></a><span data-ttu-id="9166a-107">Запрос метаданных результата</span><span class="sxs-lookup"><span data-stu-id="9166a-107">Query result metadata</span></span>

<span data-ttu-id="9166a-108">Метаданные о результатах запроса можно получить с помощью метода <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> для `SqliteDataReader`.</span><span class="sxs-lookup"><span data-stu-id="9166a-108">You can retrieve metadata about the results of a query using the <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> method on `SqliteDataReader`.</span></span> <span data-ttu-id="9166a-109">В ответ возвращается <xref:System.Data.DataTable> со следующими столбцами.</span><span class="sxs-lookup"><span data-stu-id="9166a-109">The returned <xref:System.Data.DataTable> contains the following columns:</span></span>

| <span data-ttu-id="9166a-110">Столбец</span><span class="sxs-lookup"><span data-stu-id="9166a-110">Column</span></span>             | <span data-ttu-id="9166a-111">Type</span><span class="sxs-lookup"><span data-stu-id="9166a-111">Type</span></span>    | <span data-ttu-id="9166a-112">Описание</span><span class="sxs-lookup"><span data-stu-id="9166a-112">Description</span></span>                                                               |
| ------------------ | ------- | ------------------------------------------------------------------------- |
| `AllowDBNull`      | <span data-ttu-id="9166a-113">логический</span><span class="sxs-lookup"><span data-stu-id="9166a-113">Boolean</span></span> | <span data-ttu-id="9166a-114">True, если исходный столбец принимает значения NULL.</span><span class="sxs-lookup"><span data-stu-id="9166a-114">True if the origin column may be NULL.</span></span>                                    |
| `BaseCatalogName`  | <span data-ttu-id="9166a-115">Строка</span><span class="sxs-lookup"><span data-stu-id="9166a-115">String</span></span>  | <span data-ttu-id="9166a-116">Имя базы данных для исходного столбца.</span><span class="sxs-lookup"><span data-stu-id="9166a-116">The name of the origin column's database.</span></span> <span data-ttu-id="9166a-117">Всегда имеет значение NULL для выражений.</span><span class="sxs-lookup"><span data-stu-id="9166a-117">Always NULL for expressions.</span></span>    |
| `BaseColumnName`   | <span data-ttu-id="9166a-118">Строка</span><span class="sxs-lookup"><span data-stu-id="9166a-118">String</span></span>  | <span data-ttu-id="9166a-119">Имя исходного столбца без псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="9166a-119">The unaliased name of the origin column.</span></span> <span data-ttu-id="9166a-120">Всегда имеет значение NULL для выражений.</span><span class="sxs-lookup"><span data-stu-id="9166a-120">Always NULL for expressions.</span></span>    |
| `BaseSchemaName`   | <span data-ttu-id="9166a-121">Строка</span><span class="sxs-lookup"><span data-stu-id="9166a-121">String</span></span>  | <span data-ttu-id="9166a-122">Всегда имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="9166a-122">Always NULL.</span></span> <span data-ttu-id="9166a-123">SQLite не поддерживает схемы.</span><span class="sxs-lookup"><span data-stu-id="9166a-123">SQLite doesn't support schemas.</span></span>                              |
| `BaseServerName`   | <span data-ttu-id="9166a-124">Строка</span><span class="sxs-lookup"><span data-stu-id="9166a-124">String</span></span>  | <span data-ttu-id="9166a-125">Путь к файлу базы данных, указанный в строке подключения.</span><span class="sxs-lookup"><span data-stu-id="9166a-125">The path to the database file specified in the connection string.</span></span>         |
| `BaseTableName`    | <span data-ttu-id="9166a-126">Строка</span><span class="sxs-lookup"><span data-stu-id="9166a-126">String</span></span>  | <span data-ttu-id="9166a-127">Имя таблицы для исходного столбца.</span><span class="sxs-lookup"><span data-stu-id="9166a-127">The name of the origin column's table.</span></span> <span data-ttu-id="9166a-128">Всегда имеет значение NULL для выражений.</span><span class="sxs-lookup"><span data-stu-id="9166a-128">Always NULL for expressions.</span></span>       |
| `ColumnName`       | <span data-ttu-id="9166a-129">Строка</span><span class="sxs-lookup"><span data-stu-id="9166a-129">String</span></span>  | <span data-ttu-id="9166a-130">Имя или псевдоним столбца в наборе результатов.</span><span class="sxs-lookup"><span data-stu-id="9166a-130">The name or alias of the column in the result set.</span></span>                        |
| `ColumnOrdinal`    | <span data-ttu-id="9166a-131">Int32</span><span class="sxs-lookup"><span data-stu-id="9166a-131">Int32</span></span>   | <span data-ttu-id="9166a-132">Порядковый номер столбца в наборе результатов.</span><span class="sxs-lookup"><span data-stu-id="9166a-132">The ordinal of the column in the result set.</span></span>                              |
| `ColumnSize`       | <span data-ttu-id="9166a-133">Int32</span><span class="sxs-lookup"><span data-stu-id="9166a-133">Int32</span></span>   | <span data-ttu-id="9166a-134">Всегда имеет значение -1.</span><span class="sxs-lookup"><span data-stu-id="9166a-134">Always -1.</span></span> <span data-ttu-id="9166a-135">В будущих версиях `Microsoft.Data.Sqlite` это значение может измениться.</span><span class="sxs-lookup"><span data-stu-id="9166a-135">This may change in future versions of `Microsoft.Data.Sqlite`.</span></span>   |
| `DataType`         | <span data-ttu-id="9166a-136">Type</span><span class="sxs-lookup"><span data-stu-id="9166a-136">Type</span></span>    | <span data-ttu-id="9166a-137">Тип данных .NET по умолчанию для этого столбца.</span><span class="sxs-lookup"><span data-stu-id="9166a-137">The default .NET data type of the column.</span></span>                                 |
| `DataTypeName`     | <span data-ttu-id="9166a-138">Строка</span><span class="sxs-lookup"><span data-stu-id="9166a-138">String</span></span>  | <span data-ttu-id="9166a-139">Тип данных SQLite для этого столбца.</span><span class="sxs-lookup"><span data-stu-id="9166a-139">The SQLite data type of the column.</span></span>                                       |
| `IsAliased`        | <span data-ttu-id="9166a-140">логический</span><span class="sxs-lookup"><span data-stu-id="9166a-140">Boolean</span></span> | <span data-ttu-id="9166a-141">True, если имя столбца в наборе результатов обозначено псевдонимом.</span><span class="sxs-lookup"><span data-stu-id="9166a-141">True if the column name is aliased in the result set.</span></span>                     |
| `IsAutoIncrement`  | <span data-ttu-id="9166a-142">логический</span><span class="sxs-lookup"><span data-stu-id="9166a-142">Boolean</span></span> | <span data-ttu-id="9166a-143">True, если исходный столбец был создан с применением ключевого слова AUTOINCREMENT.</span><span class="sxs-lookup"><span data-stu-id="9166a-143">True if the origin column was created with the AUTOINCREMENT keyword.</span></span>     |
| `IsExpression`     | <span data-ttu-id="9166a-144">логический</span><span class="sxs-lookup"><span data-stu-id="9166a-144">Boolean</span></span> | <span data-ttu-id="9166a-145">True, если столбец создавался из выражения в запросе.</span><span class="sxs-lookup"><span data-stu-id="9166a-145">True if the column originates from an expression in the query.</span></span>            |
| `IsKey`            | <span data-ttu-id="9166a-146">логический</span><span class="sxs-lookup"><span data-stu-id="9166a-146">Boolean</span></span> | <span data-ttu-id="9166a-147">True, если исходный столбец входит в PRIMARY KEY.</span><span class="sxs-lookup"><span data-stu-id="9166a-147">True if the origin column is part of the PRIMARY KEY.</span></span>                     |
| `IsUnique`         | <span data-ttu-id="9166a-148">логический</span><span class="sxs-lookup"><span data-stu-id="9166a-148">Boolean</span></span> | <span data-ttu-id="9166a-149">True, если исходный столбец имеет атрибут UNIQUE.</span><span class="sxs-lookup"><span data-stu-id="9166a-149">True if the origin column is UNIQUE.</span></span>                                      |
| `NumericPrecision` | <span data-ttu-id="9166a-150">Int16</span><span class="sxs-lookup"><span data-stu-id="9166a-150">Int16</span></span>   | <span data-ttu-id="9166a-151">Всегда имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="9166a-151">Always NULL.</span></span> <span data-ttu-id="9166a-152">В будущих версиях `Microsoft.Data.Sqlite` это значение может измениться.</span><span class="sxs-lookup"><span data-stu-id="9166a-152">This may change in future versions of `Microsoft.Data.Sqlite`.</span></span> |
| `NumericScale`     | <span data-ttu-id="9166a-153">Int16</span><span class="sxs-lookup"><span data-stu-id="9166a-153">Int16</span></span>   | <span data-ttu-id="9166a-154">Всегда имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="9166a-154">Always NULL.</span></span> <span data-ttu-id="9166a-155">В будущих версиях `Microsoft.Data.Sqlite` это значение может измениться.</span><span class="sxs-lookup"><span data-stu-id="9166a-155">This may change in future versions of `Microsoft.Data.Sqlite`.</span></span> |

<span data-ttu-id="9166a-156">В следующем примере кода показано, как использовать инструкцию `GetSchemaTable` для создания строки отладки для вывода метаданных о результате.</span><span class="sxs-lookup"><span data-stu-id="9166a-156">The following example shows how to use `GetSchemaTable` to create a debug string that shows metadata about a result:</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ResultMetadataSample/Program.cs?name=snippet_ResultMetadata)]

<span data-ttu-id="9166a-157">Например, такой запрос создает следующую строку отладки:</span><span class="sxs-lookup"><span data-stu-id="9166a-157">For example, this query would produce the following debug string:</span></span>

```sql
SELECT id AS post_id,
       title,
       body,
       random() AS random
FROM post
```

```output
post.id AS post_id INTEGER PRIMARY KEY AUTOINCREMENT
post.title TEXT NOT NULL UNIQUE
post.body TEXT
(expression) AS random BLOB
```

## <a name="schema-metadata"></a><span data-ttu-id="9166a-158">Метаданные схемы</span><span class="sxs-lookup"><span data-stu-id="9166a-158">Schema metadata</span></span>

<span data-ttu-id="9166a-159">Microsoft.Data.Sqlite не реализует метод GetSchema для DbConnection.</span><span class="sxs-lookup"><span data-stu-id="9166a-159">Microsoft.Data.Sqlite doesn't implement the GetSchema method on DbConnection.</span></span> <span data-ttu-id="9166a-160">Но вы можете напрямую запросить сведения о схеме, используя таблицу [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) и такие инструкции PRAGMA, как [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) и [foreign_key_list](https://www.sqlite.org/pragma.html#pragma_foreign_key_list).</span><span class="sxs-lookup"><span data-stu-id="9166a-160">Instead, you can query directly for schema information using the [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) table and PRAGMA statements like [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) and [foreign_key_list](https://www.sqlite.org/pragma.html#pragma_foreign_key_list).</span></span>

<span data-ttu-id="9166a-161">Например, такой запрос извлекает метаданные обо всех столбцах таблицы.</span><span class="sxs-lookup"><span data-stu-id="9166a-161">For example, this query will retrieve metadata about all the columns in the database.</span></span>

```sql
SELECT t.name AS tbl_name, c.name, c.type, c.notnull, c.dflt_value, c.pk
FROM sqlite_master AS t,
     pragma_table_info(t.name) AS c
WHERE t.type = 'table';
```

## <a name="see-also"></a><span data-ttu-id="9166a-162">См. также</span><span class="sxs-lookup"><span data-stu-id="9166a-162">See also</span></span>

* [<span data-ttu-id="9166a-163">Хранение схемы базы данных SQL</span><span class="sxs-lookup"><span data-stu-id="9166a-163">Storage of the SQL Database Schema</span></span>](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema)
* [<span data-ttu-id="9166a-164">Инструкции PRAGMA</span><span class="sxs-lookup"><span data-stu-id="9166a-164">PRAGMA Statements</span></span>](https://www.sqlite.org/pragma.html)
* [<span data-ttu-id="9166a-165">Типы данных</span><span class="sxs-lookup"><span data-stu-id="9166a-165">Data types</span></span>](types.md)
