---
title: Параметры сортировки
ms.date: 12/13/2019
description: Узнайте, как создать пользовательскую последовательность сопоставления.
ms.openlocfilehash: 9879846cc191a62c4cb47a0fbaa47c59153ba61c
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242976"
---
# <a name="collation"></a>Параметры сортировки

Коллаизирование последовательностей используется S'Lite при сравнении значений TEXT для определения порядка и равенства. Можно указать, какой коллаж использовать при создании столбцов или на операцию в запросах S'L. По умолчанию S'Lite включает в себя три последовательности коллажа.

| Параметры сортировки | Описание                               |
| --------- | ----------------------------------------- |
| RTRIM     | Игнорирует задняя белая область               |
| НОКЕЙС    | Нечувствительные к делу для символов ASCII А-Я |
| BINARY    | Дело чувствительное. Сравнивает байты напрямую   |

## <a name="custom-collation"></a>Пользовательский коллаж

Вы также можете определить свои собственные последовательности сопоставления <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>или переопределить встроенные с помощью. Ниже приводится следующий пример, переопределяемый коллаж NOCASE для поддержки символов Unicode. [Полный пример кода](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/CollationSample/Program.cs) доступен на GitHub.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/CollationSample/Program.cs?name=snippet_Collation)]

## <a name="like-operator"></a>Like - оператор

Оператор LIKE в S'Lite не соблюдает коллажа. Реализация по умолчанию имеет ту же семантику, что и коллаж NOCASE. Это только случай бесчувственным для ASCII символов а через Я.

Вы можете легко сделать оператора LIKE чувствительным, используя следующее заявление прагмы:

```sql
PRAGMA case_sensitive_like = 1
```

Подробнее о выполнении оператора LIKE читайте в материале [«Функции,](user-defined-functions.md) определяемые пользователями».

## <a name="see-also"></a>См. также раздел

* [Определяемые пользователем функции](user-defined-functions.md)
* [Синтаксис СЗЛ](https://www.sqlite.org/lang.html)
