---
title: Типы данных
ms.date: 12/13/2019
description: Описание поддерживаемых типов данных и некоторых связанных с ними ограничений.
ms.openlocfilehash: a11ff382f80cd979506d6195c299c8234c3eb8ea
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389043"
---
# <a name="data-types"></a>Типы данных

SQLite имеет всего четыре примитивных типа данных: INTEGER, REAL, TEXT и BLOB. API, возвращающие значения базы данных в виде `object`, возвращают только один из этих четырех типов. Microsoft.Data.Sqlite поддерживает дополнительные типы .NET, но значения в конечном итоге приводятся между этими типами и одним из четырех примитивных типов.

| .NET           | SQLite  | Примечания                                                       |
| -------------- | ------- | ------------------------------------------------------------- |
| логический        | INTEGER | `0` или `1`                                                    |
| Byte           | INTEGER |                                                               |
| Byte[]         | BLOB    |                                                               |
| Char           | TEXT    | UTF-8                                                         |
| DateTime       | TEXT    | гггг-ММ-дд ЧЧ:мм:сс.FFFFFFF                                   |
| DateTimeOffset | TEXT    | гггг-ММ-дд ЧЧ:мм:сс.FFFFFFFzzz                                |
| Decimal        | TEXT    | Формат `0.0###########################`. Значение REAL будет с потерями. |
| Double         | real    |                                                               |
| Guid           | TEXT    | 00000000-0000-0000-0000-000000000000                          |
| Int16          | INTEGER |                                                               |
| Int32          | INTEGER |                                                               |
| Int64          | INTEGER |                                                               |
| SByte          | INTEGER |                                                               |
| Single         | real    |                                                               |
| Строка         | TEXT    | UTF-8                                                         |
| TimeSpan       | TEXT    | д.чч:мм:сс.fffffff                                            |
| UInt16         | INTEGER |                                                               |
| UInt32         | INTEGER |                                                               |
| UInt64         | INTEGER | Переполнение больших значений                                         |

## <a name="alternative-types"></a>Альтернативные типы

Некоторые типы .NET можно считывать из альтернативных типов SQLite. Параметры также можно настроить для использования этих альтернативных типов. Дополнительные сведения см. в разделе [Параметры](parameters.md#alternative-types).

| .NET           | SQLite  | Примечания          |
| -------------- | ------- | ---------------- |
| Char           | INTEGER | UTF-16           |
| DateTime       | real    | Значение дня по юлианскому календарю |
| DateTimeOffset | real    | Значение дня по юлианскому календарю |
| Guid           | BLOB    |                  |
| TimeSpan       | real    | В днях          |

Например, следующий запрос считывает значение TimeSpan из столбца REAL в результирующем наборе.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_AlternativeType)]

## <a name="column-types"></a>Типы столбцов

SQLite использует систему динамических типов, где тип значения связан с самим значением, а не со столбцом, где оно хранится. Вы можете свободно использовать любое нужное имя столбца типов. Microsoft.Data.Sqlite не применяет дополнительную семантику к этим именам.

Имя типа столбца влияет на [сходство типа](https://www.sqlite.org/datatype3.html#type_affinity). Одна из распространенных проблем заключается в том, что при использовании типа столбца STRING предпринимается попытка преобразовать значения в тип INTEGER или REAL, что может привести к непредвиденным результатам. Рекомендуется использовать только имена четырех примитивных типов SQLite: INTEGER, REAL, TEXT и BLOB.

SQLite позволяет задавать аспекты типа, такие как длина, точность и число знаков после запятой, но они не применяются ядром СУБД. За их применение отвечает приложение.

## <a name="see-also"></a>См. также

- [Типы данных в SQLite](https://www.sqlite.org/datatype3.html)
