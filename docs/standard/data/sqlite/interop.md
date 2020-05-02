---
title: Взаимодействие
ms.date: 12/13/2019
description: Узнайте, как взаимодействовать с библиотеками SQLite.
ms.openlocfilehash: 486e2a8e00999b8ebe9c85a5fcc1539c514676d3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450462"
---
# <a name="interoperability"></a>Взаимодействие

Microsoft.Data.Sqlite использует SQLitePCLRaw для взаимодействия с собственной библиотекой SQLite. SQLitePCLRaw предоставляет тонкий API .NET через собственный API SQLite. SqliteConnection и SqliteDataReader предоставляют доступ к базовым объектам SQLitePCLRaw, что позволяет вам напрямую вызывать эти API.

В следующем примере показано, как вызвать `sqlite3_trace` для записи выполненных инструкций SQL на консоль:

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/InteropSample/Program.cs?name=snippet_Trace)]

А в следующем примере показан вызов `sqlite3_stmt_status`, чтобы увидеть, сколько шагов виртуальной машины SQLite скомпилировано в инструкции SQL:

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/InteropSample/Program.cs?name=snippet_StatementStatus)]

Объекты SQLitePCLRaw даже предоставляют указатель на собственные объекты, что позволяет вам выполнять P/Invoke для дополнительных собственных API SQLite.
