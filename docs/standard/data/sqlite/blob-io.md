---
title: Ввод-вывод больших двоичных объектов
ms.date: 12/13/2019
description: Узнайте, как использовать функцию ввода-вывода большого двоичного объекта в SQLite.
ms.openlocfilehash: 0c133deacdc19684eca3a6724fb398dc01fda558
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450306"
---
# <a name="blob-io"></a>Ввод-вывод больших двоичных объектов

Вы можете уменьшить использование памяти при выполнении операций чтения и записи больших двоичных объектов путем потоковой передачи данных в базу данных и из нее. Это может быть особенно удобно при анализе или преобразовании данных.

Сначала вставьте строку, как обычно. С помощью функции SQL `zeroblob()` выделите пространство в базе данных для хранения большого объекта. С помощью функции `last_insert_rowid()` можно легко получить идентификатор строки ROWID.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Insert)]

После вставки строки откройте поток для записи большого объекта с помощью <xref:Microsoft.Data.Sqlite.SqliteBlob>.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Write)]

Чтобы выполнить потоковую передачу большого объекта из базы данных, помимо столбца большого объекта необходимо выбрать ROWID или один из его псевдонимов, как показано здесь. Если не выбрать ROWID, весь объект будет загружен в память. Если все сделано правильно, то объект, возвращаемый `GetStream()`, будет объектом `SqliteBlob`.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Read)]
