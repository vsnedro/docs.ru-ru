---
title: Пользовательские версии SQLite
ms.date: 09/04/2020
description: Сведения о том, как использовать настраиваемую версию нативной библиотеки SQLite.
ms.openlocfilehash: fbf4b4cd33e6e890ce0c0cfe0b7688487b94b4a3
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89516142"
---
# <a name="custom-sqlite-versions"></a><span data-ttu-id="785fc-103">Пользовательские версии SQLite</span><span class="sxs-lookup"><span data-stu-id="785fc-103">Custom SQLite versions</span></span>

<span data-ttu-id="785fc-104">`Microsoft.Data.Sqlite` создается на основе `SQLitePCLRaw`.</span><span class="sxs-lookup"><span data-stu-id="785fc-104">`Microsoft.Data.Sqlite` is built on top of `SQLitePCLRaw`.</span></span> <span data-ttu-id="785fc-105">Чтобы использовать настраиваемые версии нативной библиотеки SQLite, примените пакет или настройте поставщик `SQLitePCLRaw`.</span><span class="sxs-lookup"><span data-stu-id="785fc-105">You can use custom versions of the native SQLite library by using a bundle or by configuring a `SQLitePCLRaw` provider.</span></span>

## <a name="bundles"></a><span data-ttu-id="785fc-106">Пакеты</span><span class="sxs-lookup"><span data-stu-id="785fc-106">Bundles</span></span>

<span data-ttu-id="785fc-107">`SQLitePCLRaw` предоставляет пакеты, которые упрощают применение правильных зависимостей на разных платформах.</span><span class="sxs-lookup"><span data-stu-id="785fc-107">`SQLitePCLRaw` provides convenience-based bundle packages, that make it easy to bring in the right dependencies across different platforms.</span></span> <span data-ttu-id="785fc-108">Основной пакет `Microsoft.Data.Sqlite` по умолчанию добавляет `SQLitePCLRaw.bundle_e_sqlite3`.</span><span class="sxs-lookup"><span data-stu-id="785fc-108">The main `Microsoft.Data.Sqlite` package brings in `SQLitePCLRaw.bundle_e_sqlite3` by default.</span></span> <span data-ttu-id="785fc-109">Чтобы использовать другой пакет, установите вместо него пакет `Microsoft.Data.Sqlite.Core` и нужный пакет.</span><span class="sxs-lookup"><span data-stu-id="785fc-109">To use a different bundle, install the `Microsoft.Data.Sqlite.Core` package instead along with the bundle package you want to use.</span></span> <span data-ttu-id="785fc-110">Пакеты автоматически инициализируются пакетом `Microsoft.Data.Sqlite`.</span><span class="sxs-lookup"><span data-stu-id="785fc-110">Bundles are automatically initialized by `Microsoft.Data.Sqlite`.</span></span>

| <span data-ttu-id="785fc-111">Пакет</span><span class="sxs-lookup"><span data-stu-id="785fc-111">Bundle</span></span> | <span data-ttu-id="785fc-112">Описание</span><span class="sxs-lookup"><span data-stu-id="785fc-112">Description</span></span> |
|--|--|
| [<span data-ttu-id="785fc-113">SQLitePCLRaw.bundle_e_sqlite3</span><span class="sxs-lookup"><span data-stu-id="785fc-113">SQLitePCLRaw.bundle_e_sqlite3</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.bundle_e_sqlite3) | <span data-ttu-id="785fc-114">Предоставляет согласованные версии SQLite для всех платформ.</span><span class="sxs-lookup"><span data-stu-id="785fc-114">Provides a consistent version of SQLite on all platforms.</span></span> <span data-ttu-id="785fc-115">Включает расширения FTS4, FTS5, JSON1 и R\*Tree.</span><span class="sxs-lookup"><span data-stu-id="785fc-115">Includes the FTS4, FTS5, JSON1, and R\*Tree extensions.</span></span> <span data-ttu-id="785fc-116">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="785fc-116">This is the default.</span></span> |
| [<span data-ttu-id="785fc-117">SQLitePCLRaw.bundle_e_sqlcipher</span><span class="sxs-lookup"><span data-stu-id="785fc-117">SQLitePCLRaw.bundle_e_sqlcipher</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.bundle_e_sqlcipher) | <span data-ttu-id="785fc-118">Предоставляет неофициальную сборку `SQLCipher` с открытым кодом.</span><span class="sxs-lookup"><span data-stu-id="785fc-118">Provides an unofficial, open-source build of `SQLCipher`.</span></span> |
| [<span data-ttu-id="785fc-119">SQLitePCLRaw.bundle_green</span><span class="sxs-lookup"><span data-stu-id="785fc-119">SQLitePCLRaw.bundle_green</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.bundle_green) | <span data-ttu-id="785fc-120">Аналогично `bundle_e_sqlite3`, за исключением платформы iOS, где используется системная библиотека SQLite.</span><span class="sxs-lookup"><span data-stu-id="785fc-120">Same as `bundle_e_sqlite3`, except on iOS where it uses the system SQLite library.</span></span> |
| [<span data-ttu-id="785fc-121">SQLitePCLRaw.bundle_sqlite3</span><span class="sxs-lookup"><span data-stu-id="785fc-121">SQLitePCLRaw.bundle_sqlite3</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.bundle_sqlite3) | <span data-ttu-id="785fc-122">Использует системную библиотеку SQLite.</span><span class="sxs-lookup"><span data-stu-id="785fc-122">Uses the system SQLite library.</span></span> |
| [<span data-ttu-id="785fc-123">SQLitePCLRaw.bundle_winsqlite3</span><span class="sxs-lookup"><span data-stu-id="785fc-123">SQLitePCLRaw.bundle_winsqlite3</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.bundle_winsqlite3) | <span data-ttu-id="785fc-124">Использует `winsqlite3.dll`, то есть системную библиотеку SQLite на платформе Windows 10.</span><span class="sxs-lookup"><span data-stu-id="785fc-124">Uses `winsqlite3.dll`, the system SQLite library on Windows 10.</span></span> |
| [<span data-ttu-id="785fc-125">SQLitePCLRaw.bundle_zetetic</span><span class="sxs-lookup"><span data-stu-id="785fc-125">SQLitePCLRaw.bundle_zetetic</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.bundle_zetetic) | <span data-ttu-id="785fc-126">Использует официальные сборки `SQLCipher`, предоставляемые Zetetic (не входят в пакет).</span><span class="sxs-lookup"><span data-stu-id="785fc-126">Uses the official `SQLCipher` builds from Zetetic (not included).</span></span> |

<span data-ttu-id="785fc-127">Например, следующие команды позволяют применить неофициальную сборку `SQLCipher` с открытым кодом:</span><span class="sxs-lookup"><span data-stu-id="785fc-127">For example, to use the unofficial, open-source build of `SQLCipher` use the following commands.</span></span>

### <a name="net-core-cli"></a>[<span data-ttu-id="785fc-128">Интерфейс командной строки .NET Core</span><span class="sxs-lookup"><span data-stu-id="785fc-128">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studio"></a>[<span data-ttu-id="785fc-129">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="785fc-129">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

## <a name="sqlitepclraw-available-providers"></a><span data-ttu-id="785fc-130">Доступные поставщики SQLitePCLRaw</span><span class="sxs-lookup"><span data-stu-id="785fc-130">SQLitePCLRaw available providers</span></span>

<span data-ttu-id="785fc-131">Если нет желания использовать пакет, вы можете использовать доступные поставщики SQLite с основной сборкой.</span><span class="sxs-lookup"><span data-stu-id="785fc-131">When not relying on a bundle, you can use the available providers of SQLite with the core assembly.</span></span>

| <span data-ttu-id="785fc-132">Поставщик</span><span class="sxs-lookup"><span data-stu-id="785fc-132">Provider</span></span> | <span data-ttu-id="785fc-133">Описание</span><span class="sxs-lookup"><span data-stu-id="785fc-133">Description</span></span> |
|--|--|
| [<span data-ttu-id="785fc-134">SQLitePCLRaw.provider.dynamic</span><span class="sxs-lookup"><span data-stu-id="785fc-134">SQLitePCLRaw.provider.dynamic</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.provider.dynamic) | <span data-ttu-id="785fc-135">Поставщик `dynamic` загружает собственную библиотеку вместо использования атрибутов <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="785fc-135">The `dynamic` provider loads the native library instead of using <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=nameWithType> attributes.</span></span> <span data-ttu-id="785fc-136">Дополнительные сведения об использовании этого динамического поставщика см. в [этом разделе](#use-the-dynamic-provider).</span><span class="sxs-lookup"><span data-stu-id="785fc-136">For more information on using this provider, see [use the dynamic provider](#use-the-dynamic-provider).</span></span> |
| [<span data-ttu-id="785fc-137">SQLitePCLRaw.provider.e_sqlite3</span><span class="sxs-lookup"><span data-stu-id="785fc-137">SQLitePCLRaw.provider.e_sqlite3</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.provider.e_sqlite3) | <span data-ttu-id="785fc-138">`e_sqlite3` является поставщиком по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="785fc-138">The `e_sqlite3` is the default provider.</span></span> |
| [<span data-ttu-id="785fc-139">SQLitePCLRaw.provider.e_sqlcipher</span><span class="sxs-lookup"><span data-stu-id="785fc-139">SQLitePCLRaw.provider.e_sqlcipher</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.provider.e_sqlcipher) | <span data-ttu-id="785fc-140">Поставщик `e_sqlcipher` — это неофициальная и неподдерживаемая реализация `SQLCipher`.</span><span class="sxs-lookup"><span data-stu-id="785fc-140">The `e_sqlcipher` provider is the unofficial and unsupported `SQLCipher`.</span></span> |
| [<span data-ttu-id="785fc-141">SQLitePCLRaw.provider.sqlite3</span><span class="sxs-lookup"><span data-stu-id="785fc-141">SQLitePCLRaw.provider.sqlite3</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.provider.sqlite3) | <span data-ttu-id="785fc-142">Поставщик `sqlite3` — это предоставляемая системой реализация `SQLite` для iOS, macOS и Linux.</span><span class="sxs-lookup"><span data-stu-id="785fc-142">The `sqlite3` provider is a system-provided `SQLite` for iOS, macOS, and Linux.</span></span> |
| [<span data-ttu-id="785fc-143">SQLitePCLRaw.provider.sqlcipher</span><span class="sxs-lookup"><span data-stu-id="785fc-143">SQLitePCLRaw.provider.sqlcipher</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.provider.sqlcipher) | <span data-ttu-id="785fc-144">Поставщик `sqlcipher` предназначен для использования официальных сборок `SQLCipher`, предоставляемых `Zetetic`.</span><span class="sxs-lookup"><span data-stu-id="785fc-144">The `sqlcipher` provider is for official `SQLCipher` builds from `Zetetic`.</span></span> |
| [<span data-ttu-id="785fc-145">SQLitePCLRaw.provider.winsqlite3</span><span class="sxs-lookup"><span data-stu-id="785fc-145">SQLitePCLRaw.provider.winsqlite3</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.provider.winsqlite3) | <span data-ttu-id="785fc-146">Поставщик `winsqlite3` предназначен для сред Windows 10.</span><span class="sxs-lookup"><span data-stu-id="785fc-146">The `winsqlite3` provider is for Windows 10 environments.</span></span> |

<span data-ttu-id="785fc-147">Чтобы использовать поставщик `sqlite3`, примените следующие команды:</span><span class="sxs-lookup"><span data-stu-id="785fc-147">To use the `sqlite3` provider use the following commands:</span></span>

### <a name="net-core-cli"></a>[<span data-ttu-id="785fc-148">Интерфейс командной строки .NET Core</span><span class="sxs-lookup"><span data-stu-id="785fc-148">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.core
dotnet add package SQLitePCLRaw.provider.sqlite3
```

### <a name="visual-studio"></a>[<span data-ttu-id="785fc-149">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="785fc-149">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.core
Install-Package SQLitePCLRaw.provider.sqlite3
```

---

<span data-ttu-id="785fc-150">После установки пакетов настройте экземпляр `sqlite3` в качестве поставщика.</span><span class="sxs-lookup"><span data-stu-id="785fc-150">With the packages installed, you then set the provider to the `sqlite3` instance.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SqliteProviderSample/Program.cs)]

## <a name="use-the-dynamic-provider"></a><span data-ttu-id="785fc-151">Использование динамического поставщика</span><span class="sxs-lookup"><span data-stu-id="785fc-151">Use the dynamic provider</span></span>

<span data-ttu-id="785fc-152">Вы можете использовать собственную сборку SQLite, применяя пакет `SQLitePCLRaw.provider.dynamic_cdecl`.</span><span class="sxs-lookup"><span data-stu-id="785fc-152">You can use your own build of SQLite by leveraging the `SQLitePCLRaw.provider.dynamic_cdecl` package.</span></span> <span data-ttu-id="785fc-153">В этом случае вы обязаны самостоятельно развернуть нативную библиотеку вместе с приложением.</span><span class="sxs-lookup"><span data-stu-id="785fc-153">In this case, you're responsible for deploying the native library with your app.</span></span> <span data-ttu-id="785fc-154">Обратите внимание, что процедура развертывания нативных библиотек вместе с приложением будет существенно различаться на разных платформах .NET и в разных средах выполнения.</span><span class="sxs-lookup"><span data-stu-id="785fc-154">Note, the details of deploying native libraries with your app vary considerably depending on which .NET platform and runtime you're using.</span></span>

<span data-ttu-id="785fc-155">Прежде всего нужно реализовать `IGetFunctionPointer`.</span><span class="sxs-lookup"><span data-stu-id="785fc-155">First, you'll need to implement `IGetFunctionPointer`.</span></span> <span data-ttu-id="785fc-156">Ниже приведены сведения о такой реализации на .NET Core.</span><span class="sxs-lookup"><span data-stu-id="785fc-156">The implementation on .NET Core is as follows:</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_NativeLibraryAdapter)]

<span data-ttu-id="785fc-157">Теперь настройте поставщик `SQLitePCLRaw`.</span><span class="sxs-lookup"><span data-stu-id="785fc-157">Next, configure the `SQLitePCLRaw` provider.</span></span> <span data-ttu-id="785fc-158">Это нужно сделать до того, как в приложении будет использоваться `Microsoft.Data.Sqlite`.</span><span class="sxs-lookup"><span data-stu-id="785fc-158">Ensure this is done before `Microsoft.Data.Sqlite` is used in your app.</span></span> <span data-ttu-id="785fc-159">Также постарайтесь не использовать пакет `SQLitePCLRaw`, который может переопределить ваш поставщик.</span><span class="sxs-lookup"><span data-stu-id="785fc-159">Also, avoid using a `SQLitePCLRaw` bundle package which might override your provider.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_SetProvider)]
