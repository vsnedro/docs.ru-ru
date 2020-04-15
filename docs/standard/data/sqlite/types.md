---
title: Типы данных
ms.date: 12/13/2019
description: Описывает поддерживаемые типы данных и некоторые ограничения вокруг них.
ms.openlocfilehash: a11ff382f80cd979506d6195c299c8234c3eb8ea
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389043"
---
# <a name="data-types"></a>Типы данных

СА-Лит имеет только четыре примитивных типа данных: INTEGER, REAL, TEXT и BLOB. AAP, возвращающие значения `object` базы данных как будут возвращать только один из этих четырех типов. Дополнительные типы .NET поддерживаются Microsoft.Data.Sqlite, но значения в конечном счете принудятся между этими типами и одним из четырех примитивных типов.

| .NET           | SQLite  | Remarks                                                       |
| -------------- | ------- | ------------------------------------------------------------- |
| Логическое        | INTEGER | `0` или `1`                                                    |
| Byte           | INTEGER |                                                               |
| Byte[]         | BLOB    |                                                               |
| CHAR           | TEXT    | UTF-8                                                         |
| Дата и время       | TEXT    | yyyy-MM-dd HH:mm:ss. ФФКФФ                                   |
| DateTimeOffset | TEXT    | yyyy-MM-dd HH:mm:ss. FFFFFfzzz                                |
| Decimal        | TEXT    | `0.0###########################`Формат. REAL было бы убыточным. |
| Double         | real    |                                                               |
| Guid           | TEXT    | 00000000-0000-0000-0000-000000000000                          |
| Int16          | INTEGER |                                                               |
| Int32          | INTEGER |                                                               |
| Int64          | INTEGER |                                                               |
| SByte          | INTEGER |                                                               |
| Один         | real    |                                                               |
| Строка         | TEXT    | UTF-8                                                         |
| TimeSpan       | TEXT    | d.hh:mm:ss.fffff                                            |
| UInt16         | INTEGER |                                                               |
| UInt32         | INTEGER |                                                               |
| UInt64         | INTEGER | Большой переполниние значений                                         |

## <a name="alternative-types"></a>Альтернативные типы

Некоторые типы .NET можно прочитать из альтернативных типов S'Lite. Параметры также могут быть настроены для использования этих альтернативных типов. Дополнительные сведения см. в разделе [Параметры](parameters.md#alternative-types).

| .NET           | SQLite  | Remarks          |
| -------------- | ------- | ---------------- |
| CHAR           | INTEGER | UTF-16           |
| Дата и время       | real    | Джулиан день значение |
| DateTimeOffset | real    | Джулиан день значение |
| Guid           | BLOB    |                  |
| TimeSpan       | real    | В дни          |

Например, следующий запрос считывает значение TimeSpan из реального столбца в наборе результатов.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_AlternativeType)]

## <a name="column-types"></a>Типы столбцов

Система динамического типа, в которой тип значения связан с самим значением, а не с столбецом, в котором оно хранится. Вы можете использовать любое имя типа столбца, которое вы хотите. Microsoft.Data.Sqlite не будет применять дополнительные семантики к этим именам.

Имя типа столбца влияет на [сродство типа.](https://www.sqlite.org/datatype3.html#type_affinity) Один распространенный gotcha является то, что с помощью столбца типа STRING будет пытаться преобразовать значения в INTEGER или REAL, что может привести к неожиданным результатам. Мы рекомендуем использовать только четыре примитивных типа S'Lite: INTEGER, REAL, TEXT и BLOB.

S'Lite позволяет указывать такие аспекты типа, как длина, точность и масштаб, но они не применяются движком базы данных. Ваше приложение отвечает за их соблюдение.

## <a name="see-also"></a>См. также

- [Типы данных в S'Lite](https://www.sqlite.org/datatype3.html)
