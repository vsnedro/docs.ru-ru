---
title: Ограничения Dapper
ms.date: 12/13/2019
description: Описание некоторых ограничений, которые будут возникать при использовании Dapper.
ms.openlocfilehash: 396507f25f591a9ab5c3bb07c0af6fd8d175e4ea
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901201"
---
# <a name="dapper-limitations"></a>Ограничения Dapper

При использовании Microsoft.Data.SQLite с [Dapper](https://stackexchange.github.io/Dapper/) необходимо учитывать ряд ограничений.

## <a name="parameters"></a>Параметры

В именах параметров SQLite учитывается регистр букв. Убедитесь, что имена параметров, используемые в SQL, соответствуют регистру свойств анонимного объекта. Обратите внимание на проблему [#18861](https://github.com/dotnet/efcore/issues/18861), чтобы упростить себе работу.

Dapper также ожидает от параметров использования префикса `@`. Другие префиксы работать не будут.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_Parameter)]

## <a name="data-types"></a>Типы данных

Dapper считывает значения с помощью индексатора SqliteDataReader. Тип возвращаемого значения этого индексатора — object, то есть он будет возвращать только значения long, double, string или byte[]. Дополнительные сведения см. в разделе [Типы данных](types.md). Dapper обрабатывает большинство преобразований между этими и прочими примитивными типами. К сожалению, он не может обрабатывать `DateTimeOffset`, `Guid`или `TimeSpan`. Создавайте обработчики типов, если эти типы нужно включать в результаты.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_TypeHandlers)]

Не забудьте добавить обработчики типов перед выполнением запроса.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_AddTypeHandlers)]

## <a name="see-also"></a>См. также

* [Типы данных](types.md)
* [Ограничения асинхронного режима](async.md)
