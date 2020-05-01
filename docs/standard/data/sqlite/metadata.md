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
# <a name="metadata"></a>Метаданные

В ADO.NET есть два интерфейса API для получения метаданных. Один из них извлекает метаданные о результатах запроса. Второй извлекает метаданные о схеме базы данных.

## <a name="query-result-metadata"></a>Запрос метаданных результата

Метаданные о результатах запроса можно получить с помощью метода <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> для `SqliteDataReader`. В ответ возвращается <xref:System.Data.DataTable> со следующими столбцами.

| Столбец             | Type    | Описание                                                               |
| ------------------ | ------- | ------------------------------------------------------------------------- |
| `AllowDBNull`      | логический | True, если исходный столбец принимает значения NULL.                                    |
| `BaseCatalogName`  | Строка  | Имя базы данных для исходного столбца. Всегда имеет значение NULL для выражений.    |
| `BaseColumnName`   | Строка  | Имя исходного столбца без псевдонимов. Всегда имеет значение NULL для выражений.    |
| `BaseSchemaName`   | Строка  | Всегда имеет значение NULL. SQLite не поддерживает схемы.                              |
| `BaseServerName`   | Строка  | Путь к файлу базы данных, указанный в строке подключения.         |
| `BaseTableName`    | Строка  | Имя таблицы для исходного столбца. Всегда имеет значение NULL для выражений.       |
| `ColumnName`       | Строка  | Имя или псевдоним столбца в наборе результатов.                        |
| `ColumnOrdinal`    | Int32   | Порядковый номер столбца в наборе результатов.                              |
| `ColumnSize`       | Int32   | Всегда имеет значение -1. В будущих версиях `Microsoft.Data.Sqlite` это значение может измениться.   |
| `DataType`         | Type    | Тип данных .NET по умолчанию для этого столбца.                                 |
| `DataTypeName`     | Строка  | Тип данных SQLite для этого столбца.                                       |
| `IsAliased`        | логический | True, если имя столбца в наборе результатов обозначено псевдонимом.                     |
| `IsAutoIncrement`  | логический | True, если исходный столбец был создан с применением ключевого слова AUTOINCREMENT.     |
| `IsExpression`     | логический | True, если столбец создавался из выражения в запросе.            |
| `IsKey`            | логический | True, если исходный столбец входит в PRIMARY KEY.                     |
| `IsUnique`         | логический | True, если исходный столбец имеет атрибут UNIQUE.                                      |
| `NumericPrecision` | Int16   | Всегда имеет значение NULL. В будущих версиях `Microsoft.Data.Sqlite` это значение может измениться. |
| `NumericScale`     | Int16   | Всегда имеет значение NULL. В будущих версиях `Microsoft.Data.Sqlite` это значение может измениться. |

В следующем примере кода показано, как использовать инструкцию `GetSchemaTable` для создания строки отладки для вывода метаданных о результате.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ResultMetadataSample/Program.cs?name=snippet_ResultMetadata)]

Например, такой запрос создает следующую строку отладки:

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

## <a name="schema-metadata"></a>Метаданные схемы

Microsoft.Data.Sqlite не реализует метод GetSchema для DbConnection. Но вы можете напрямую запросить сведения о схеме, используя таблицу [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) и такие инструкции PRAGMA, как [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) и [foreign_key_list](https://www.sqlite.org/pragma.html#pragma_foreign_key_list).

Например, такой запрос извлекает метаданные обо всех столбцах таблицы.

```sql
SELECT t.name AS tbl_name, c.name, c.type, c.notnull, c.dflt_value, c.pk
FROM sqlite_master AS t,
     pragma_table_info(t.name) AS c
WHERE t.type = 'table';
```

## <a name="see-also"></a>См. также

* [Хранение схемы базы данных SQL](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema)
* [Инструкции PRAGMA](https://www.sqlite.org/pragma.html)
* [Типы данных](types.md)
