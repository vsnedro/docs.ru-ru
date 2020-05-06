---
title: Ошибки базы данных
ms.date: 12/13/2019
description: В этой статье описывается то, как библиотека обрабатывает ошибки базы данных и повторные попытки.
ms.openlocfilehash: 9a613b6f94a89dc40e627c14f46836be77080035
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450492"
---
# <a name="database-errors"></a>Ошибки базы данных

<xref:Microsoft.Data.Sqlite.SqliteException> вызывается при обнаружении ошибки SQLite. Сообщение предоставляется SQLite. Свойства `SqliteErrorCode` и `SqliteExtendedErrorCode` содержат [код результата](https://www.sqlite.org/rescode.html) SQLite ошибки.

Ошибки могут возникать при каждом взаимодействии Microsoft.Data.SQLite со встроенной библиотекой SQLite. В следующем списке приведены распространенные сценарии, в которых могут возникать ошибки:

* открытие соединения;
* запуск транзакции;
* выполнение команды;
* Вызов <xref:Microsoft.Data.Sqlite.SqliteDataReader.NextResult%2A>.

Тщательно продумайте, как ваше приложение будет обрабатывать эти ошибки.

## <a name="locking-retries-and-timeouts"></a>Блокировка, повторные попытки и время ожидания

SQLite применяет строгие правила при блокировке таблиц и файлов базы данных. Если в приложении используется любой вариант параллельного доступа к базе данных, то вы, скорее всего, столкнетесь с ошибками занятости и блокировки. Вы можете исключить многие ошибки, используя [общий кэш](connection-strings.md#cache) и [упреждающее ведение журнала](async.md).

Каждый раз, когда поставщик Microsoft.Data.SQLite обнаруживает ошибку занятости или блокировки, он автоматически выполняет повторные попытки до тех пор, пока команда не будет выполнена успешно или не будет достигнуто время ожидания команды.

Время ожидания команды можно увеличить, установив параметр <xref:Microsoft.Data.Sqlite.SqliteCommand.CommandTimeout%2A>. По умолчанию время ожидания составляет 30 секунд. При указании значения `0` время ожидания не ограничено.

```csharp
// Retry for 60 seconds while locked
command.CommandTimeout = 60;
```

Иногда поставщику Microsoft.Data.Sqlite необходимо создать неявный объект команды. Например, во время запуска транзакции (BeginTransaction). Чтобы задать время ожидания для этих команд, используйте <xref:Microsoft.Data.Sqlite.SqliteConnection.DefaultTimeout%2A>.

```csharp
// Set the default timeout of all commands on this connection
connection.DefaultTimeout = 60;
```

## <a name="see-also"></a>См. также

* [Коды ошибок SQLite](https://www.sqlite.org/rescode.html)
* [Блокировка файлов в SQLite](https://www.sqlite.org/lockingv3.html)
* [Режим общего кэша](https://www.sqlite.org/sharedcache.html)
* [Упреждающее ведение журнала](https://www.sqlite.org/wal.html)
