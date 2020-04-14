---
title: Модули
ms.date: 12/13/2019
description: Узнайте, как загрузить расширения S'Lite.
ms.openlocfilehash: 51c705349c25240fe42e0edda8004a3e3b013ca3
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242963"
---
# <a name="extensions"></a>Модули

S'Lite поддерживает наращивание погрузки во время выполнения. Расширения включают в себя такие вещи, как дополнительные функции S'L, коллажа, виртуальные таблицы и многое другое.

Ядро .NET включает дополнительную логику для размещения родовых библиотек в дополнительных местах, таких как ссылки на пакеты NuGet. К сожалению, S'Lite не может использовать эту логику; он вызывает API платформы сразу для загрузки библиотек. Из-за этого может потребоваться изменить переменные PATH, LD_LIBRARY_PATH или DYLD_LIBRARY_PATH среды перед загрузкой расширений S'Lite. На GitHub есть [пример,](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) демонстрирующая поиск связных данных для текущего времени выполнения внутри эталонного пакета NuGet.

Чтобы загрузить расширение, <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> позвоните по методу. Microsoft.Data.Sqlite гарантирует, что расширение остается загруженным, даже если соединение закрыто и вновь открыто.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs?name=snippet_LoadExtension)]

## <a name="see-also"></a>См. также раздел

* [Run-Время Загруженные расширения](https://www.sqlite.org/loadext.html)
