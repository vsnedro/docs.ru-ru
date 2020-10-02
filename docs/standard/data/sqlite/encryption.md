---
title: Шифрование
ms.date: 09/08/2020
description: Узнайте, как зашифровать файл базы данных.
ms.openlocfilehash: 1b33e1510a269aba87caba2cd39faab33791aa55
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203414"
---
# <a name="encryption"></a><span data-ttu-id="4be6a-103">Шифрование</span><span class="sxs-lookup"><span data-stu-id="4be6a-103">Encryption</span></span>

<span data-ttu-id="4be6a-104">По умолчанию SQLite не поддерживает шифрование файлов базы данных.</span><span class="sxs-lookup"><span data-stu-id="4be6a-104">SQLite doesn't support encrypting database files by default.</span></span> <span data-ttu-id="4be6a-105">Вместо этого используйте измененную версию SQLite, например [SEE](https://www.hwaci.com/sw/sqlite/see.html), [SQLCipher](https://www.zetetic.net/sqlcipher/), [SQLiteCrypt](http://www.sqlite-crypt.com/) или [wxSQLite3](https://utelle.github.io/wxsqlite3).</span><span class="sxs-lookup"><span data-stu-id="4be6a-105">Instead, you need to use a modified version of SQLite like [SEE](https://www.hwaci.com/sw/sqlite/see.html), [SQLCipher](https://www.zetetic.net/sqlcipher/), [SQLiteCrypt](http://www.sqlite-crypt.com/), or [wxSQLite3](https://utelle.github.io/wxsqlite3).</span></span> <span data-ttu-id="4be6a-106">Хотя в этой статье показано, как использовать неподдерживаемую сборку SQLCipher с открытым кодом, этот подход в целом применим и к другим решениям.</span><span class="sxs-lookup"><span data-stu-id="4be6a-106">This article demonstrates using an unsupported, open-source build of SQLCipher, but the information also applies to other solutions since they generally follow the same pattern.</span></span>

## <a name="installation"></a><span data-ttu-id="4be6a-107">Установка</span><span class="sxs-lookup"><span data-stu-id="4be6a-107">Installation</span></span>

### <a name="net-core-cli"></a>[<span data-ttu-id="4be6a-108">Интерфейс командной строки .NET Core</span><span class="sxs-lookup"><span data-stu-id="4be6a-108">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet remove package Microsoft.Data.Sqlite
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studio"></a>[<span data-ttu-id="4be6a-109">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4be6a-109">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Remove-Package Microsoft.Data.Sqlite
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

<span data-ttu-id="4be6a-110">См. сведения об использовании другой собственной библиотеки для шифрования в руководстве по [настраиваемым версиям SQLite](custom-versions.md).</span><span class="sxs-lookup"><span data-stu-id="4be6a-110">For more information about using a different native library for encryption, see [Custom SQLite versions](custom-versions.md).</span></span>

## <a name="specify-the-key"></a><span data-ttu-id="4be6a-111">Выбор ключа</span><span class="sxs-lookup"><span data-stu-id="4be6a-111">Specify the key</span></span>

<span data-ttu-id="4be6a-112">Чтобы включить шифрование в новой базе данных, укажите ключ с помощью ключевого слова строки подключения `Password`.</span><span class="sxs-lookup"><span data-stu-id="4be6a-112">To enable encryption on a new database, specify the key using the `Password` connection string keyword.</span></span> <span data-ttu-id="4be6a-113">Используйте <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder>, чтобы добавить или обновить значение из входных данных пользователя и избежать атак путем внедрения строки подключения.</span><span class="sxs-lookup"><span data-stu-id="4be6a-113">Use <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> to add or update the value from user input and avoid connection string injection attacks.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

> [!TIP]
> <span data-ttu-id="4be6a-114">Метод шифрования и расшифровки существующих баз данных зависит от используемого решения.</span><span class="sxs-lookup"><span data-stu-id="4be6a-114">The method for encrypting and decrypting existing databases varies depending on which solution you're using.</span></span> <span data-ttu-id="4be6a-115">Например, предположим, что вам нужно использовать функцию `sqlcipher_export()` в SQLCipher.</span><span class="sxs-lookup"><span data-stu-id="4be6a-115">For example, you need to use the `sqlcipher_export()` function on SQLCipher.</span></span> <span data-ttu-id="4be6a-116">Дополнительные сведения см. в документации по решению.</span><span class="sxs-lookup"><span data-stu-id="4be6a-116">Check your solution's documentation for details.</span></span>

## <a name="rekeying-the-database"></a><span data-ttu-id="4be6a-117">Смена ключей базы данных</span><span class="sxs-lookup"><span data-stu-id="4be6a-117">Rekeying the database</span></span>

<span data-ttu-id="4be6a-118">Если вам нужно изменить ключ зашифрованной базы данных, выдайте инструкцию `PRAGMA rekey`.</span><span class="sxs-lookup"><span data-stu-id="4be6a-118">If you want to change the key of an encrypted database, issue a `PRAGMA rekey` statement.</span></span>

<span data-ttu-id="4be6a-119">К сожалению, SQLite не поддерживает параметры в инструкциях `PRAGMA`.</span><span class="sxs-lookup"><span data-stu-id="4be6a-119">Unfortunately, SQLite doesn't support parameters in `PRAGMA` statements.</span></span> <span data-ttu-id="4be6a-120">Вместо этого используйте функцию `quote()`, чтобы предотвратить внедрение кода SQL.</span><span class="sxs-lookup"><span data-stu-id="4be6a-120">Instead, use the `quote()` function to prevent SQL injection.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_Rekey)]
