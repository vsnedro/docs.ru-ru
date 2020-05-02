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
# <a name="extensions"></a><span data-ttu-id="28f68-103">Расширения</span><span class="sxs-lookup"><span data-stu-id="28f68-103">Extensions</span></span>

<span data-ttu-id="28f68-104">SQLite поддерживает загрузку расширений во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="28f68-104">SQLite supports loading extensions at run time.</span></span> <span data-ttu-id="28f68-105">Расширения включают дополнительные функции SQL, параметры сортировки, виртуальные таблицы и многое другое.</span><span class="sxs-lookup"><span data-stu-id="28f68-105">Extensions include things like additional SQL functions, collations, virtual tables, and more.</span></span>

<span data-ttu-id="28f68-106">.NET Core включает дополнительную логику для поиска собственных библиотек в дополнительных местах, например в указанных пакетах NuGet.</span><span class="sxs-lookup"><span data-stu-id="28f68-106">.NET Core includes additional logic for locating native libraries in additional places like referenced NuGet packages.</span></span> <span data-ttu-id="28f68-107">К сожалению, SQLite не может использовать эту логику. SQLite напрямую вызывает API платформы для загрузки библиотек.</span><span class="sxs-lookup"><span data-stu-id="28f68-107">Unfortunately, SQLite can't leverage this logic; it calls the platform API directly to load libraries.</span></span> <span data-ttu-id="28f68-108">Поэтому может потребоваться изменить переменные среды PATH, LD_LIBRARY_PATH или DYLD_LIBRARY_PATH перед загрузкой расширений SQLite.</span><span class="sxs-lookup"><span data-stu-id="28f68-108">Because of this, you may need to modify the PATH, LD_LIBRARY_PATH, or DYLD_LIBRARY_PATH environment variables before loading SQLite extensions.</span></span> <span data-ttu-id="28f68-109">В GitHub есть [пример](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs), демонстрирующий поиск двоичных файлов для текущей среды выполнения в указанном пакете NuGet.</span><span class="sxs-lookup"><span data-stu-id="28f68-109">There's [a sample](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) on GitHub that demonstrates finding binaries for the current runtime inside a referenced NuGet package.</span></span>

<span data-ttu-id="28f68-110">Чтобы загрузить расширение, вызовите метод <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A>.</span><span class="sxs-lookup"><span data-stu-id="28f68-110">To load an extension, call the <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> method.</span></span> <span data-ttu-id="28f68-111">Microsoft.Data.Sqlite обеспечит загрузку расширения даже при закрытии и повторном открытии соединения.</span><span class="sxs-lookup"><span data-stu-id="28f68-111">Microsoft.Data.Sqlite will ensure that the extension remains loaded even if the connection is closed and reopened.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs?name=snippet_LoadExtension)]

## <a name="see-also"></a><span data-ttu-id="28f68-112">См. также</span><span class="sxs-lookup"><span data-stu-id="28f68-112">See also</span></span>

* [<span data-ttu-id="28f68-113">Расширения, загружаемые во время выполнения</span><span class="sxs-lookup"><span data-stu-id="28f68-113">Run-Time Loadable Extensions</span></span>](https://www.sqlite.org/loadext.html)
