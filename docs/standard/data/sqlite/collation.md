---
title: Параметры сортировки
ms.date: 12/13/2019
description: Узнайте, как создать пользовательскую последовательность сортировки.
ms.openlocfilehash: 9879846cc191a62c4cb47a0fbaa47c59153ba61c
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242976"
---
# <a name="collation"></a>Параметры сортировки

При сравнении текстовых значений для определения порядка и равенства в SQLite используются последовательности сортировки. Вы можете указать используемые параметры сортировки при создании столбцов или для отдельных операций в SQL-запросах. По умолчанию в SQLite предоставляется три последовательности сортировки.

| Параметры сортировки | Описание                               |
| --------- | ----------------------------------------- |
| RTRIM     | Игнорирует конечные пробелы               |
| NOCASE    | Без учета регистра для символов A–Z в кодировке ASCII |
| BINARY    | С учетом регистра. Сравнивает байты напрямую   |

## <a name="custom-collation"></a>Настраиваемые параметры сортировки

Вы можете определить собственные последовательности сортировки или переопределить встроенные, используя <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>. В следующем примере демонстрируется переопределение параметров сортировки NOCASE для поддержки символов Юникода. [Полный пример кода](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/CollationSample/Program.cs) можно найти на сайте GitHub.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/CollationSample/Program.cs?name=snippet_Collation)]

## <a name="like-operator"></a>Оператор LIKE

Оператор LIKE в SQLite не учитывает параметры сортировки. Реализация по умолчанию использует семантику, аналогичную параметрам сортировки NOCASE. Регистр не учитывается для символов A–Z в кодировке ASCII.

Вы можете легко настроить учет регистра для оператора LIKE с помощью следующей инструкции pragma:

```sql
PRAGMA case_sensitive_like = 1
```

Дополнительные сведения о переопределении реализации оператора LIKE см. в описании [определяемых пользователем функций](user-defined-functions.md).

## <a name="see-also"></a>См. также

* [Определяемые пользователем функции](user-defined-functions.md)
* [Синтаксис SQL](https://www.sqlite.org/lang.html)
