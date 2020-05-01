---
title: Шифрование
ms.date: 12/13/2019
description: Узнайте, как зашифровать файл базы данных.
ms.openlocfilehash: ccdd4b6b8642b3cde1c2667c9ca432a9b0ef21f2
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450486"
---
# <a name="encryption"></a><span data-ttu-id="9d3d4-103">Шифрование</span><span class="sxs-lookup"><span data-stu-id="9d3d4-103">Encryption</span></span>

<span data-ttu-id="9d3d4-104">По умолчанию SQLite не поддерживает шифрование файлов базы данных.</span><span class="sxs-lookup"><span data-stu-id="9d3d4-104">SQLite doesn't support encrypting database files by default.</span></span> <span data-ttu-id="9d3d4-105">Вместо этого используйте измененную версию SQLite, например [SEE](https://www.hwaci.com/sw/sqlite/see.html), [SQLCipher](https://www.zetetic.net/sqlcipher/), [SQLiteCrypt](http://www.sqlite-crypt.com/) или [wxSQLite3](https://utelle.github.io/wxsqlite3).</span><span class="sxs-lookup"><span data-stu-id="9d3d4-105">Instead, you need to use a modified version of SQLite like [SEE](https://www.hwaci.com/sw/sqlite/see.html), [SQLCipher](https://www.zetetic.net/sqlcipher/), [SQLiteCrypt](http://www.sqlite-crypt.com/), or [wxSQLite3](https://utelle.github.io/wxsqlite3).</span></span> <span data-ttu-id="9d3d4-106">Хотя в этой статье показано, как использовать неподдерживаемую сборку SQLCipher с открытым кодом, этот подход в целом применим и к другим решениям.</span><span class="sxs-lookup"><span data-stu-id="9d3d4-106">This article demonstrates using an unsupported, open-source build of SQLCipher, but the information also applies to other solutions since they generally follow the same pattern.</span></span>

## <a name="installation"></a><span data-ttu-id="9d3d4-107">Установка</span><span class="sxs-lookup"><span data-stu-id="9d3d4-107">Installation</span></span>

### <a name="net-core-cli"></a>[<span data-ttu-id="9d3d4-108">Интерфейс командной строки .NET Core</span><span class="sxs-lookup"><span data-stu-id="9d3d4-108">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet remove package Microsoft.Data.Sqlite
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studio"></a>[<span data-ttu-id="9d3d4-109">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9d3d4-109">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Remove-Package Microsoft.Data.Sqlite
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

<span data-ttu-id="9d3d4-110">См. сведения об использовании другой собственной библиотеки для шифрования в руководстве по [настраиваемым версиям SQLite](custom-versions.md).</span><span class="sxs-lookup"><span data-stu-id="9d3d4-110">For more information about using a different native library for encryption, see [Custom SQLite versions](custom-versions.md).</span></span>

## <a name="specify-the-key"></a><span data-ttu-id="9d3d4-111">Выбор ключа</span><span class="sxs-lookup"><span data-stu-id="9d3d4-111">Specify the key</span></span>

<span data-ttu-id="9d3d4-112">Чтобы включить шифрование, укажите ключ с помощью ключевого слова строки подключения `Password`.</span><span class="sxs-lookup"><span data-stu-id="9d3d4-112">To enable encryption, specify the key using the `Password` connection string keyword.</span></span> <span data-ttu-id="9d3d4-113">Используйте <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder>, чтобы добавить или обновить значение из входных данных пользователя и избежать атак путем внедрения строки подключения.</span><span class="sxs-lookup"><span data-stu-id="9d3d4-113">Use <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> to add or update the value from user input and avoid connection string injection attacks.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="rekeying-the-database"></a><span data-ttu-id="9d3d4-114">Смена ключей базы данных</span><span class="sxs-lookup"><span data-stu-id="9d3d4-114">Rekeying the database</span></span>

<span data-ttu-id="9d3d4-115">Если вам нужно изменить ключ шифрования базы данных, выдайте инструкцию `PRAGMA rekey`.</span><span class="sxs-lookup"><span data-stu-id="9d3d4-115">If you want to change the encryption key of a database, issue a `PRAGMA rekey` statement.</span></span> <span data-ttu-id="9d3d4-116">Чтобы расшифровать базу данных, укажите `NULL`.</span><span class="sxs-lookup"><span data-stu-id="9d3d4-116">To decrypt the database, specify `NULL`.</span></span>

<span data-ttu-id="9d3d4-117">К сожалению, SQLite не поддерживает параметры в инструкциях `PRAGMA`.</span><span class="sxs-lookup"><span data-stu-id="9d3d4-117">Unfortunately, SQLite doesn't support parameters in `PRAGMA` statements.</span></span> <span data-ttu-id="9d3d4-118">Вместо этого используйте функцию `quote()`, чтобы предотвратить внедрение кода SQL.</span><span class="sxs-lookup"><span data-stu-id="9d3d4-118">Instead, use the `quote()` function to prevent SQL injection.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_Rekey)]
