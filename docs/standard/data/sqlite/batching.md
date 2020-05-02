---
title: Пакетная обработка
ms.date: 12/13/2019
description: Сведения о том, как выполнить пакет инструкций SQL в одной команде.
ms.openlocfilehash: 0799784471520bb279db6a4b5879ad30945bdebb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450312"
---
# <a name="batching"></a>Пакетная обработка

В SQLite нет собственной поддержки пакетной обработки инструкций SQL в одной команде. Но так как сеть не используется, это не окажет никакого положительного влияния на производительность. Однако Microsoft.Data.Sqlite для удобства реализует пакетную обработку инструкций в качестве удобства, чтобы его поведение было больше похоже на другие поставщики ADO.NET.

При вызове <xref:System.Data.Common.DbCommand.ExecuteReader%2A?displayProperty=nameWithType> инструкции выполняются вплоть до первой инструкции, возвращающей результаты. При вызове <xref:System.Data.Common.DbDataReader.NextResult%2A?displayProperty=nameWithType> выполнение инструкций продолжается до следующей инструкции, возвращающей результаты, или до конца пакета. При вызове <xref:System.Data.Common.DbDataReader.Dispose%2A?displayProperty=nameWithType> или <xref:System.Data.Common.DbDataReader.Close%2A> выполняются все оставшиеся инструкции, которые не были использованы `NextResult()`. Если не очистить модуль чтения данных, метод завершения пытается выполнить оставшиеся инструкции, но все возникающие ошибки игнорируются. Поэтому при использовании пакетов важно очищать объекты `DbDataReader`.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BatchingSample/Program.cs?name=snippet_Batching)]

## <a name="see-also"></a>См. также

* [Массовая вставка](bulk-insert.md)
