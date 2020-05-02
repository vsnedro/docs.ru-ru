---
title: Расширения
ms.date: 12/13/2019
description: Сведения о том, как загружать расширения SQLite.
ms.openlocfilehash: 51c705349c25240fe42e0edda8004a3e3b013ca3
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242963"
---
# <a name="extensions"></a>Расширения

SQLite поддерживает загрузку расширений во время выполнения. Расширения включают дополнительные функции SQL, параметры сортировки, виртуальные таблицы и многое другое.

.NET Core включает дополнительную логику для поиска собственных библиотек в дополнительных местах, например в указанных пакетах NuGet. К сожалению, SQLite не может использовать эту логику. SQLite напрямую вызывает API платформы для загрузки библиотек. Поэтому может потребоваться изменить переменные среды PATH, LD_LIBRARY_PATH или DYLD_LIBRARY_PATH перед загрузкой расширений SQLite. В GitHub есть [пример](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs), демонстрирующий поиск двоичных файлов для текущей среды выполнения в указанном пакете NuGet.

Чтобы загрузить расширение, вызовите метод <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A>. Microsoft.Data.Sqlite обеспечит загрузку расширения даже при закрытии и повторном открытии соединения.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs?name=snippet_LoadExtension)]

## <a name="see-also"></a>См. также

* [Расширения, загружаемые во время выполнения](https://www.sqlite.org/loadext.html)
