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
# <a name="extensions"></a><span data-ttu-id="c7756-103">Модули</span><span class="sxs-lookup"><span data-stu-id="c7756-103">Extensions</span></span>

<span data-ttu-id="c7756-104">S'Lite поддерживает наращивание погрузки во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="c7756-104">SQLite supports loading extensions at run time.</span></span> <span data-ttu-id="c7756-105">Расширения включают в себя такие вещи, как дополнительные функции S'L, коллажа, виртуальные таблицы и многое другое.</span><span class="sxs-lookup"><span data-stu-id="c7756-105">Extensions include things like additional SQL functions, collations, virtual tables, and more.</span></span>

<span data-ttu-id="c7756-106">Ядро .NET включает дополнительную логику для размещения родовых библиотек в дополнительных местах, таких как ссылки на пакеты NuGet.</span><span class="sxs-lookup"><span data-stu-id="c7756-106">.NET Core includes additional logic for locating native libraries in additional places like referenced NuGet packages.</span></span> <span data-ttu-id="c7756-107">К сожалению, S'Lite не может использовать эту логику; он вызывает API платформы сразу для загрузки библиотек.</span><span class="sxs-lookup"><span data-stu-id="c7756-107">Unfortunately, SQLite can't leverage this logic; it calls the platform API directly to load libraries.</span></span> <span data-ttu-id="c7756-108">Из-за этого может потребоваться изменить переменные PATH, LD_LIBRARY_PATH или DYLD_LIBRARY_PATH среды перед загрузкой расширений S'Lite.</span><span class="sxs-lookup"><span data-stu-id="c7756-108">Because of this, you may need to modify the PATH, LD_LIBRARY_PATH, or DYLD_LIBRARY_PATH environment variables before loading SQLite extensions.</span></span> <span data-ttu-id="c7756-109">На GitHub есть [пример,](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) демонстрирующая поиск связных данных для текущего времени выполнения внутри эталонного пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="c7756-109">There's [a sample](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) on GitHub that demonstrates finding binaries for the current runtime inside a referenced NuGet package.</span></span>

<span data-ttu-id="c7756-110">Чтобы загрузить расширение, <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> позвоните по методу.</span><span class="sxs-lookup"><span data-stu-id="c7756-110">To load an extension, call the <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> method.</span></span> <span data-ttu-id="c7756-111">Microsoft.Data.Sqlite гарантирует, что расширение остается загруженным, даже если соединение закрыто и вновь открыто.</span><span class="sxs-lookup"><span data-stu-id="c7756-111">Microsoft.Data.Sqlite will ensure that the extension remains loaded even if the connection is closed and reopened.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs?name=snippet_LoadExtension)]

## <a name="see-also"></a><span data-ttu-id="c7756-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c7756-112">See also</span></span>

* [<span data-ttu-id="c7756-113">Run-Время Загруженные расширения</span><span class="sxs-lookup"><span data-stu-id="c7756-113">Run-Time Loadable Extensions</span></span>](https://www.sqlite.org/loadext.html)
