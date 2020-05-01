---
title: Пользовательские версии SQLite
ms.date: 12/13/2019
description: Сведения о том, как использовать настраиваемую версию нативной библиотеки SQLite.
ms.openlocfilehash: dd27278c1dbe17b12e5067d04d19043bf259b1e8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746991"
---
# <a name="custom-sqlite-versions"></a><span data-ttu-id="745a4-103">Пользовательские версии SQLite</span><span class="sxs-lookup"><span data-stu-id="745a4-103">Custom SQLite versions</span></span>

<span data-ttu-id="745a4-104">Microsoft.Data.Sqlite создана на основе SQLitePCLRaw.</span><span class="sxs-lookup"><span data-stu-id="745a4-104">Microsoft.Data.Sqlite is built on top of SQLitePCLRaw.</span></span> <span data-ttu-id="745a4-105">Чтобы использовать настраиваемые версии нативной библиотеки SQLite, примените пакет или настройте поставщик SQLitePCLRaw.</span><span class="sxs-lookup"><span data-stu-id="745a4-105">You can use custom versions of the native SQLite library by using a bundle or by configuring a SQLitePCLRaw provider.</span></span>

## <a name="bundles"></a><span data-ttu-id="745a4-106">Пакеты</span><span class="sxs-lookup"><span data-stu-id="745a4-106">Bundles</span></span>

<span data-ttu-id="745a4-107">SQLitePCLRaw предоставляет пакеты, которые упрощают применение правильных зависимостей на разных платформах.</span><span class="sxs-lookup"><span data-stu-id="745a4-107">SQLitePCLRaw provides bundle packages that make it easy to bring in the right dependencies across different platforms.</span></span>

<span data-ttu-id="745a4-108">Основной пакет Microsoft.Data.Sqlite применяет по умолчанию SQLitePCLRaw.bundle_e_sqlite3.</span><span class="sxs-lookup"><span data-stu-id="745a4-108">The main Microsoft.Data.Sqlite package brings in SQLitePCLRaw.bundle_e_sqlite3 by default.</span></span>

<span data-ttu-id="745a4-109">Чтобы использовать другой пакет, установите вместо него пакет `Microsoft.Data.Sqlite.Core` и нужный пакет.</span><span class="sxs-lookup"><span data-stu-id="745a4-109">To use a different bundle, install the `Microsoft.Data.Sqlite.Core` package instead along with the bundle package you want to use.</span></span> <span data-ttu-id="745a4-110">Пакеты автоматически инициализируются пакетом Microsoft.Data.Sqlite.</span><span class="sxs-lookup"><span data-stu-id="745a4-110">Bundles are automatically initialized by Microsoft.Data.Sqlite.</span></span>

| <span data-ttu-id="745a4-111">Пакет</span><span class="sxs-lookup"><span data-stu-id="745a4-111">Bundle</span></span> | <span data-ttu-id="745a4-112">Описание</span><span class="sxs-lookup"><span data-stu-id="745a4-112">Description</span></span> |
| --- | --- |
| <span data-ttu-id="745a4-113">SQLitePCLRaw.bundle_e_sqlite3</span><span class="sxs-lookup"><span data-stu-id="745a4-113">SQLitePCLRaw.bundle_e_sqlite3</span></span> | <span data-ttu-id="745a4-114">Предоставляет согласованные версии SQLite для всех платформ.</span><span class="sxs-lookup"><span data-stu-id="745a4-114">Provides a consistent version of SQLite on all platforms.</span></span> <span data-ttu-id="745a4-115">Включает расширения FTS4, FTS5, JSON1 и R\*Tree.</span><span class="sxs-lookup"><span data-stu-id="745a4-115">Includes the FTS4, FTS5, JSON1, and R\*Tree extensions.</span></span> <span data-ttu-id="745a4-116">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="745a4-116">This is the default.</span></span> |
| <span data-ttu-id="745a4-117">SQLitePCLRaw.bundle_green</span><span class="sxs-lookup"><span data-stu-id="745a4-117">SQLitePCLRaw.bundle_green</span></span> | <span data-ttu-id="745a4-118">Аналогично bundle_e_sqlite3, за исключением платформы iOS, где используется системная библиотека SQLite.</span><span class="sxs-lookup"><span data-stu-id="745a4-118">Same as bundle_e_sqlite3, except on iOS where it uses the system SQLite library.</span></span> |
| <span data-ttu-id="745a4-119">SQLitePCLRaw.bundle_zetetic</span><span class="sxs-lookup"><span data-stu-id="745a4-119">SQLitePCLRaw.bundle_zetetic</span></span> | <span data-ttu-id="745a4-120">Использует официальные сборки SQLCipher, предоставляемые Zetetic (не входят в пакет).</span><span class="sxs-lookup"><span data-stu-id="745a4-120">Uses the official SQLCipher builds from Zetetic (not included).</span></span> |
| <span data-ttu-id="745a4-121">SQLitePCLRaw.bundle_winsqlite3</span><span class="sxs-lookup"><span data-stu-id="745a4-121">SQLitePCLRaw.bundle_winsqlite3</span></span> | <span data-ttu-id="745a4-122">Использует winsqlite3.dll, которая является системной библиотекой SQLite на платформе Windows 10.</span><span class="sxs-lookup"><span data-stu-id="745a4-122">Uses winsqlite3.dll, the system SQLite library on Windows 10.</span></span> |
| <span data-ttu-id="745a4-123">SQLitePCLRaw.bundle_e_sqlcipher</span><span class="sxs-lookup"><span data-stu-id="745a4-123">SQLitePCLRaw.bundle_e_sqlcipher</span></span> | <span data-ttu-id="745a4-124">Предоставляет неофициальную сборку SQLCipher с открытым кодом.</span><span class="sxs-lookup"><span data-stu-id="745a4-124">Provides an unofficial, open-source build of SQLCipher.</span></span> |

<span data-ttu-id="745a4-125">Например, следующие команды позволяют применять неофициальную сборку SQLCipher с открытым кодом.</span><span class="sxs-lookup"><span data-stu-id="745a4-125">For example, to use the unofficial, open-source build of SQLCipher use the following commands.</span></span>

### <a name="net-core-cli"></a>[<span data-ttu-id="745a4-126">Интерфейс командной строки .NET Core</span><span class="sxs-lookup"><span data-stu-id="745a4-126">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studio"></a>[<span data-ttu-id="745a4-127">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="745a4-127">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

## <a name="sqlitepclraw-providers"></a><span data-ttu-id="745a4-128">Поставщики SQLitePCLRaw</span><span class="sxs-lookup"><span data-stu-id="745a4-128">SQLitePCLRaw providers</span></span>

<span data-ttu-id="745a4-129">Вы можете использовать собственную сборку SQLite, применяя пакет `SQLitePCLRaw.provider.dynamic_cdecl`.</span><span class="sxs-lookup"><span data-stu-id="745a4-129">You can use your own build of SQLite by leveraging the `SQLitePCLRaw.provider.dynamic_cdecl` package.</span></span> <span data-ttu-id="745a4-130">В этом случае вы обязаны самостоятельно развернуть нативную библиотеку вместе с приложением.</span><span class="sxs-lookup"><span data-stu-id="745a4-130">In this case, you're responsible for deploying the native library with your app.</span></span> <span data-ttu-id="745a4-131">Обратите внимание, что процедура развертывания нативных библиотек вместе с приложением будет существенно различаться на разных платформах .NET и в разных средах выполнения.</span><span class="sxs-lookup"><span data-stu-id="745a4-131">Note, the details of deploying native libraries with your app vary considerably depending on which .NET platform and runtime you're using.</span></span>

<span data-ttu-id="745a4-132">Прежде всего нужно реализовать IGetFunctionPointer.</span><span class="sxs-lookup"><span data-stu-id="745a4-132">First, you'll need to implement IGetFunctionPointer.</span></span> <span data-ttu-id="745a4-133">Эта реализация создается на .NET Core достаточно просто.</span><span class="sxs-lookup"><span data-stu-id="745a4-133">The implementation is fairly trivial on .NET Core.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_NativeLibraryAdapter)]

<span data-ttu-id="745a4-134">После этого настройте поставщик SQLitePCLRaw.</span><span class="sxs-lookup"><span data-stu-id="745a4-134">Next, configure the SQLitePCLRaw provider.</span></span> <span data-ttu-id="745a4-135">Это нужно выполнить до момента применения Microsoft.Data.Sqlite в приложении.</span><span class="sxs-lookup"><span data-stu-id="745a4-135">Ensure this is done before Microsoft.Data.Sqlite is used in your app.</span></span> <span data-ttu-id="745a4-136">Также старайтесь не использовать пакет SQLitePCLRaw, который может переопределить ваш поставщик.</span><span class="sxs-lookup"><span data-stu-id="745a4-136">Also, avoid using a SQLitePCLRaw bundle package which might override your provider.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_SetProvider)]
