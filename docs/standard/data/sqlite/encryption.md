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
# <a name="encryption"></a>Шифрование

По умолчанию SQLite не поддерживает шифрование файлов базы данных. Вместо этого используйте измененную версию SQLite, например [SEE](https://www.hwaci.com/sw/sqlite/see.html), [SQLCipher](https://www.zetetic.net/sqlcipher/), [SQLiteCrypt](http://www.sqlite-crypt.com/) или [wxSQLite3](https://utelle.github.io/wxsqlite3). Хотя в этой статье показано, как использовать неподдерживаемую сборку SQLCipher с открытым кодом, этот подход в целом применим и к другим решениям.

## <a name="installation"></a>Установка

### <a name="net-core-cli"></a>[Интерфейс командной строки .NET Core](#tab/netcore-cli)

```dotnetcli
dotnet remove package Microsoft.Data.Sqlite
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studio"></a>[Visual Studio](#tab/visual-studio)

``` PowerShell
Remove-Package Microsoft.Data.Sqlite
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

См. сведения об использовании другой собственной библиотеки для шифрования в руководстве по [настраиваемым версиям SQLite](custom-versions.md).

## <a name="specify-the-key"></a>Выбор ключа

Чтобы включить шифрование в новой базе данных, укажите ключ с помощью ключевого слова строки подключения `Password`. Используйте <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder>, чтобы добавить или обновить значение из входных данных пользователя и избежать атак путем внедрения строки подключения.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

> [!TIP]
> Метод шифрования и расшифровки существующих баз данных зависит от используемого решения. Например, предположим, что вам нужно использовать функцию `sqlcipher_export()` в SQLCipher. Дополнительные сведения см. в документации по решению.

## <a name="rekeying-the-database"></a>Смена ключей базы данных

Если вам нужно изменить ключ зашифрованной базы данных, выдайте инструкцию `PRAGMA rekey`.

К сожалению, SQLite не поддерживает параметры в инструкциях `PRAGMA`. Вместо этого используйте функцию `quote()`, чтобы предотвратить внедрение кода SQL.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_Rekey)]
