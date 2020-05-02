---
title: Параметры
ms.date: 12/13/2019
description: Узнайте, как используются параметры SQL.
ms.openlocfilehash: 1d2f818ad392a919faedd785394de28a9c6f56c3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401205"
---
# <a name="parameters"></a>Параметры

Параметры используются для защиты от атак путем внедрения кода SQL. Вместо сцепления вводимых пользователем данных с инструкциями SQL используйте параметры, чтобы входные данные всегда воспринимались как литеральное значение и никогда не выполнялись. В SQLite параметры обычно разрешены в везде, где допускается использование литерала в инструкциях SQL.

С параметрами можно использовать префикс `:`, `@` или `$`.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_Parameter)]

Сведения о том, как значения .NET сопоставляются со значениями SQLite, см. в разделе [Типы данных](types.md).

## <a name="truncation"></a>Усечение

Свойство <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> используется для усечения значений типа TEXT и BLOB.

```csharp
// Truncate name to 30 characters
command.Parameters.AddWithValue("$name", name).Length = 30;
```

## <a name="alternative-types"></a>Альтернативные типы

Иногда вам может потребоваться использовать альтернативный тип SQLite. Это можно сделать, установив свойство <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType>.

Можно использовать следующие сопоставления альтернативных типов. Сопоставления по умолчанию см. в разделе [Типы данных](types.md).

| Значение          | SqliteType | Примечания          |
| -------------- | ---------- | ---------------- |
| Char           | Целое число    | UTF-16           |
| DateTime       | Real       | Значение дня по юлианскому календарю |
| DateTimeOffset | Real       | Значение дня по юлианскому календарю |
| Guid           | Blob       |                  |
| TimeSpan       | Real       | В днях          |

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_SqliteType)]

## <a name="output-parameters"></a>Параметры вывода

SQLite не поддерживает выходные параметры. Вместо этого используются возвращаемые значения в результатах запроса.

## <a name="see-also"></a>См. также

* [Типы данных](types.md)
