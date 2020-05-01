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
# <a name="custom-sqlite-versions"></a>Пользовательские версии SQLite

Microsoft.Data.Sqlite создана на основе SQLitePCLRaw. Чтобы использовать настраиваемые версии нативной библиотеки SQLite, примените пакет или настройте поставщик SQLitePCLRaw.

## <a name="bundles"></a>Пакеты

SQLitePCLRaw предоставляет пакеты, которые упрощают применение правильных зависимостей на разных платформах.

Основной пакет Microsoft.Data.Sqlite применяет по умолчанию SQLitePCLRaw.bundle_e_sqlite3.

Чтобы использовать другой пакет, установите вместо него пакет `Microsoft.Data.Sqlite.Core` и нужный пакет. Пакеты автоматически инициализируются пакетом Microsoft.Data.Sqlite.

| Пакет | Описание |
| --- | --- |
| SQLitePCLRaw.bundle_e_sqlite3 | Предоставляет согласованные версии SQLite для всех платформ. Включает расширения FTS4, FTS5, JSON1 и R*Tree. Это значение по умолчанию. |
| SQLitePCLRaw.bundle_green | Аналогично bundle_e_sqlite3, за исключением платформы iOS, где используется системная библиотека SQLite. |
| SQLitePCLRaw.bundle_zetetic | Использует официальные сборки SQLCipher, предоставляемые Zetetic (не входят в пакет). |
| SQLitePCLRaw.bundle_winsqlite3 | Использует winsqlite3.dll, которая является системной библиотекой SQLite на платформе Windows 10. |
| SQLitePCLRaw.bundle_e_sqlcipher | Предоставляет неофициальную сборку SQLCipher с открытым кодом. |

Например, следующие команды позволяют применять неофициальную сборку SQLCipher с открытым кодом.

### <a name="net-core-cli"></a>[Интерфейс командной строки .NET Core](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studio"></a>[Visual Studio](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

## <a name="sqlitepclraw-providers"></a>Поставщики SQLitePCLRaw

Вы можете использовать собственную сборку SQLite, применяя пакет `SQLitePCLRaw.provider.dynamic_cdecl`. В этом случае вы обязаны самостоятельно развернуть нативную библиотеку вместе с приложением. Обратите внимание, что процедура развертывания нативных библиотек вместе с приложением будет существенно различаться на разных платформах .NET и в разных средах выполнения.

Прежде всего нужно реализовать IGetFunctionPointer. Эта реализация создается на .NET Core достаточно просто.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_NativeLibraryAdapter)]

После этого настройте поставщик SQLitePCLRaw. Это нужно выполнить до момента применения Microsoft.Data.Sqlite в приложении. Также старайтесь не использовать пакет SQLitePCLRaw, который может переопределить ваш поставщик.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_SetProvider)]
