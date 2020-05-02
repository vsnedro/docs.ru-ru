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
# <a name="adonet-limitations"></a>Ограничения ADO.NET

Microsoft. Data. SQLite предоставляет реализации многих абстракций ADO.NET, но с некоторыми ограничениями.

## <a name="database-schema-information"></a>Сведения о схеме базы данных

Метаданные о результатах запросов доступны с помощью метода <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A>.

Реализация `DbConnection.GetSchema()` отсутствует. Этот API не определен правильно, поэтому мы рекомендуем получать метаданные базы данных непосредственно с помощью стандартных API-интерфейсов SQLite, таких как таблица [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) и прагма [table_info](https://www.sqlite.org/pragma.html#pragma_table_info).

Дополнительные сведения см. в разделе [Метаданные](metadata.md).

## <a name="systemtransactions"></a>System.Transactions

Microsoft.Data.Sqlite пока не поддерживает System.Transactions. Вместо этого используйте транзакции ADO.NET. Дополнительные сведения см. в статье о [транзакциях](transactions.md).

Предоставьте отзыв об отсутствии поддержки System.Transactions в проблеме [#13825](https://github.com/dotnet/efcore/issues/13825).

## <a name="data-adapters"></a>Адаптеры данных

`DbDataAdapter` еще не реализован в Microsoft.Data.Sqlite. Это означает, что `DataSet` и `DataTable` ADO.NET можно использовать только для загрузки данных, но не их обновления.

Используйте проблему [#13838](https://github.com/dotnet/efcore/issues/13838), чтобы отправить отзыв о реализации `DbDataAdapter`.

## <a name="output-parameters"></a>Параметры вывода

SQLite не поддерживает выходные параметры.

## <a name="positional-parameters"></a>Позиционные параметры

Microsoft.Data.Sqlite поддерживает только именованные [параметры](parameters.md). Позиционные параметры не поддерживаются.

## <a name="stored-procedures"></a>Хранимые процедуры

SQLite не поддерживает хранимые процедуры.

## <a name="isolation-levels"></a>Уровни изоляции

Уровни изоляции `Chaos` и `Snapshot` не поддерживаются в транзакциях SQLite.

## <a name="see-also"></a>См. также

* [Ограничения асинхронного режима](async.md)
* [Типы данных](types.md)
* [Транзакции](transactions.md)
