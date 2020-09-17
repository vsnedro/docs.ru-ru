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
# <a name="custom-sqlite-versions"></a>Пользовательские версии SQLite

`Microsoft.Data.Sqlite` создается на основе `SQLitePCLRaw`. Чтобы использовать настраиваемые версии нативной библиотеки SQLite, примените пакет или настройте поставщик `SQLitePCLRaw`.

## <a name="bundles"></a>Пакеты

`SQLitePCLRaw` предоставляет пакеты, которые упрощают применение правильных зависимостей на разных платформах. Основной пакет `Microsoft.Data.Sqlite` по умолчанию добавляет `SQLitePCLRaw.bundle_e_sqlite3`. Чтобы использовать другой пакет, установите вместо него пакет `Microsoft.Data.Sqlite.Core` и нужный пакет. Пакеты автоматически инициализируются пакетом `Microsoft.Data.Sqlite`.

| Пакет | Описание |
|--|--|
| [SQLitePCLRaw.bundle_e_sqlite3](https://www.nuget.org/packages/SQLitePCLRaw.bundle_e_sqlite3) | Предоставляет согласованные версии SQLite для всех платформ. Включает расширения FTS4, FTS5, JSON1 и R*Tree. Это значение по умолчанию. |
| [SQLitePCLRaw.bundle_e_sqlcipher](https://www.nuget.org/packages/SQLitePCLRaw.bundle_e_sqlcipher) | Предоставляет неофициальную сборку `SQLCipher` с открытым кодом. |
| [SQLitePCLRaw.bundle_green](https://www.nuget.org/packages/SQLitePCLRaw.bundle_green) | Аналогично `bundle_e_sqlite3`, за исключением платформы iOS, где используется системная библиотека SQLite. |
| [SQLitePCLRaw.bundle_sqlite3](https://www.nuget.org/packages/SQLitePCLRaw.bundle_sqlite3) | Использует системную библиотеку SQLite. |
| [SQLitePCLRaw.bundle_winsqlite3](https://www.nuget.org/packages/SQLitePCLRaw.bundle_winsqlite3) | Использует `winsqlite3.dll`, то есть системную библиотеку SQLite на платформе Windows 10. |
| [SQLitePCLRaw.bundle_zetetic](https://www.nuget.org/packages/SQLitePCLRaw.bundle_zetetic) | Использует официальные сборки `SQLCipher`, предоставляемые Zetetic (не входят в пакет). |

Например, следующие команды позволяют применить неофициальную сборку `SQLCipher` с открытым кодом:

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

## <a name="sqlitepclraw-available-providers"></a>Доступные поставщики SQLitePCLRaw

Если нет желания использовать пакет, вы можете использовать доступные поставщики SQLite с основной сборкой.

| Поставщик | Описание |
|--|--|
| [SQLitePCLRaw.provider.dynamic](https://www.nuget.org/packages/SQLitePCLRaw.provider.dynamic) | Поставщик `dynamic` загружает собственную библиотеку вместо использования атрибутов <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=nameWithType>. Дополнительные сведения об использовании этого динамического поставщика см. в [этом разделе](#use-the-dynamic-provider). |
| [SQLitePCLRaw.provider.e_sqlite3](https://www.nuget.org/packages/SQLitePCLRaw.provider.e_sqlite3) | `e_sqlite3` является поставщиком по умолчанию. |
| [SQLitePCLRaw.provider.e_sqlcipher](https://www.nuget.org/packages/SQLitePCLRaw.provider.e_sqlcipher) | Поставщик `e_sqlcipher` — это неофициальная и неподдерживаемая реализация `SQLCipher`. |
| [SQLitePCLRaw.provider.sqlite3](https://www.nuget.org/packages/SQLitePCLRaw.provider.sqlite3) | Поставщик `sqlite3` — это предоставляемая системой реализация `SQLite` для iOS, macOS и Linux. |
| [SQLitePCLRaw.provider.sqlcipher](https://www.nuget.org/packages/SQLitePCLRaw.provider.sqlcipher) | Поставщик `sqlcipher` предназначен для использования официальных сборок `SQLCipher`, предоставляемых `Zetetic`. |
| [SQLitePCLRaw.provider.winsqlite3](https://www.nuget.org/packages/SQLitePCLRaw.provider.winsqlite3) | Поставщик `winsqlite3` предназначен для сред Windows 10. |

Чтобы использовать поставщик `sqlite3`, примените следующие команды:

### <a name="net-core-cli"></a>[Интерфейс командной строки .NET Core](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.core
dotnet add package SQLitePCLRaw.provider.sqlite3
```

### <a name="visual-studio"></a>[Visual Studio](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.core
Install-Package SQLitePCLRaw.provider.sqlite3
```

---

После установки пакетов настройте экземпляр `sqlite3` в качестве поставщика.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SqliteProviderSample/Program.cs)]

## <a name="use-the-dynamic-provider"></a>Использование динамического поставщика

Вы можете использовать собственную сборку SQLite, применяя пакет `SQLitePCLRaw.provider.dynamic_cdecl`. В этом случае вы обязаны самостоятельно развернуть нативную библиотеку вместе с приложением. Обратите внимание, что процедура развертывания нативных библиотек вместе с приложением будет существенно различаться на разных платформах .NET и в разных средах выполнения.

Прежде всего нужно реализовать `IGetFunctionPointer`. Ниже приведены сведения о такой реализации на .NET Core.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_NativeLibraryAdapter)]

Теперь настройте поставщик `SQLitePCLRaw`. Это нужно сделать до того, как в приложении будет использоваться `Microsoft.Data.Sqlite`. Также постарайтесь не использовать пакет `SQLitePCLRaw`, который может переопределить ваш поставщик.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_SetProvider)]
