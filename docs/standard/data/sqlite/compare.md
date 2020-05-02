---
title: Сравнение с System.Data.SQLite
ms.date: 12/13/2019
description: Описание некоторых различий между библиотеками Microsoft.Data.SQLite и System.Data.SQLite.
ms.openlocfilehash: 076bbc6f746cf9296c96ec73047397a21a3b2558
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900714"
---
# <a name="comparison-to-systemdatasqlite"></a>Сравнение с System.Data.SQLite

В 2005 году Роберт Симпсон создал System.Data.SQLite, поставщик SQLite для ADO.NET 2.0. В 2010 году сопровождение и развитие этого проекта взяла на себя команда SQLite. Стоит также упомянуть, что команда Mono в 2007 году создала ответвление этого кода Mono.Data.Sqlite. System.Data.SQLite имеет долгую историю, и теперь это стабильный и полнофункциональный поставщик ADO.NET, оснащенный инструментарием Visual Studio. В новых выпусках продолжают поставляться сборки, совместимые с каждой версией платформы .NET Framework, вплоть до старой версии 2.0 и даже .NET Compact Framework 3.5.

Первая версия .NET Core (выпущенная в 2016 году) была единой, облегченной, современной и кроссплатформенной реализацией .NET. Устаревшие API и API с более современными альтернативными вариантами были намеренно удалены. В ADO.NET не было никаких API DataSet (в том числе DataTable и DataAdapter).

Команда Entity Framework была в некоторой степени знакома с базой кода System.Data.SQLite. Брайс Ламбсон, участник команды EF, ранее помог команде SQLite добавить поддержку Entity Framework версий 5 и 6. Брайс также экспериментировал со своей собственной реализацией поставщика SQLite ADO.NET примерно в то же время, когда планировался .NET Core. После долгого обсуждения команда Entity Framework решила создавать Microsoft.Data.Sqlite на основе прототипа Брайса. Это позволило бы им создать новую облегченную и современную реализацию, которая соответствовала бы целям .NET Core.

В качестве примера того, что мы понимаем под более современной реализацией, посмотрите код создания [пользовательской функции](user-defined-functions.md) в System.Data.SQLite и в Microsoft.Data.Sqlite.

```csharp
// System.Data.SQLite
connection.BindFunction(
    new SQLiteFunctionAttribute("ceiling", 1, FunctionType.Scalar),
    (Func<object[], object>)((object[] args) => Math.Ceiling((double)((object[])args[1])[0])),
    null);

// Microsoft.Data.Sqlite
connection.CreateFunction(
    "ceiling",
    (double arg) => Math.Ceiling(arg));
```

В 2017 году произошло изменение стратегии .NET Core 2.0. Было решено, что совместимость с .NET Framework жизненно важна для успеха .NET Core. Многие из удаленных API, включая API DataSet, были добавлены обратно. Помимо других интересных вещей, это разблокировало проект System.Data.SQLite и позволило также перенести его в .NET Core. Однако первоначальная цель создания облегченной и современной библиотеки Microsoft.Data.Sqlite осталась прежней. Подробные сведения об API ADO.NET, которые не реализованы в Microsoft.Data.Sqlite, см. в статье об [ограничениях ADO.NET](adonet-limitations.md).

Когда в Microsoft.Data.Sqlite добавляются новые функции, всегда принимается во внимание проект System.Data.SQLite. Мы стараемся, когда это возможно, сводить к минимуму их различия, чтобы облегчить переход между ними.

## <a name="data-types"></a>Типы данных

Самая большая разница между Microsoft.Data.Sqlite и System.Data.SQLite заключается в способах обработки типов данных. Как описано в статье [Типы данных](types.md), Microsoft.Data.Sqlite не пытается маскировать базовую странность SQLite — любая произвольная строка может быть указана в качестве типа столбца, и имеется только четыре примитивных типа: INTEGER, REAL, TEXT и BLOB.

System.Data.SQLite применяет к типам столбцов дополнительную семантику, сопоставляя их непосредственно с типами .NET. Это придает поставщику ощущение более строгой типизации, но остаются некоторые шероховатости. Например, им пришлось ввести новую инструкцию SQL (TYPES) для указания типов столбцов выражений в инструкциях SELECT.

## <a name="connection-strings"></a>Строки подключения

В Microsoft.Data.Sqlite [строка подключения](connection-strings.md) имеет гораздо меньше ключевых слов. В следующей таблице показаны альтернативные варианты, которые можно использовать в качестве замены.

| Ключевое слово          | Альтернатива                                         |
| ---------------- | --------------------------------------------------- |
| Cache Size       | Отправьте `PRAGMA cache_size = <pages>`                  |
| Default Timeout (Время ожидания по умолчанию)  | Используйте свойство DefaultTimeout в SqliteConnection |
| FailIfMissing    | Используйте `Mode=ReadWrite`.                                |
| FullUri          | Используйте ключевое слово Data Source                         |
| Journal Mode     | Отправьте `PRAGMA journal_mode = <mode>`                 |
| Legacy Format    | Отправьте `PRAGMA legacy_file_format = 1`                |
| Max Page Count   | Отправьте `PRAGMA max_page_count = <pages>`              |
| Page Size        | Отправьте `PRAGMA page_size = <bytes>`                   |
| Только для чтения        | Используйте `Mode=ReadOnly`.                                 |
| Синхронная      | Отправьте `PRAGMA synchronous = <mode>`                  |
| URI              | Используйте ключевое слово Data Source                         |
| UseUTF16Encoding | Отправьте `PRAGMA encoding = 'UTF-16'`                   |

## <a name="authorization"></a>Авторизация

В Microsoft.Data.SQLite нет API, соответствующего обратному вызову авторизации SQLite. Используйте вопрос [#13835](https://github.com/dotnet/efcore/issues/13835), чтобы отправить отзыв об этой функции.

## <a name="data-change-notifications"></a>Уведомления об изменениях данных

В Microsoft.Data.SQLite нет API, соответствующего уведомлениям об изменениях данных SQLite. Используйте вопрос [#13827](https://github.com/dotnet/efcore/issues/13827), чтобы отправить отзыв об этой функции.

## <a name="virtual-table-modules"></a>Модули виртуальных таблиц

В Microsoft.Data.SQLite нет API для создания модулей виртуальных таблиц. Используйте вопрос [#13823](https://github.com/dotnet/efcore/issues/13823), чтобы отправить отзыв об этой функции.

## <a name="see-also"></a>См. также

* [Типы данных](types.md)
* [Строки подключения](connection-strings.md)
* [Шифрование](encryption.md)
* [Ограничения ADO.NET](adonet-limitations.md)
* [Ограничения Dapper](dapper-limitations.md)
