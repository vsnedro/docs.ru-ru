---
title: Команда dotnet tool update
description: Команда dotnet tool update обновляет указанное средство .NET на вашем компьютере.
ms.date: 07/08/2020
ms.openlocfilehash: 18b153e53a6dbcb32e50ae4a7d06a1c2f53d1eb5
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634081"
---
# <a name="dotnet-tool-update"></a>dotnet tool update

**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий

## <a name="name"></a>name

`dotnet tool update` обновляет указанное [средство .NET](global-tools.md) на компьютере.

## <a name="synopsis"></a>Краткий обзор

```dotnetcli
dotnet tool update <PACKAGE_ID> -g|--global
    [--add-source <SOURCE>] [--configfile <FILE>]
    [--disable-parallel] [--framework <FRAMEWORK>]
    [--ignore-failed-sources] [--interactive] [--no-cache]
    [-v|--verbosity <LEVEL>] [--version <VERSION>]

dotnet tool update <PACKAGE_ID> --tool-path <PATH>
    [--add-source <SOURCE>] [--configfile <FILE>]
    [--disable-parallel] [--framework <FRAMEWORK>]
    [--ignore-failed-sources] [--interactive] [--no-cache]
    [-v|--verbosity <LEVEL>] [--version <VERSION>]

dotnet tool update <PACKAGE_ID> --local
    [--add-source <SOURCE>] [--configfile <FILE>]
    [--disable-parallel] [--framework <FRAMEWORK>]
    [--ignore-failed-sources] [--interactive] [--no-cache]
    [--tool-manifest <PATH>]
    [-v|--verbosity <LEVEL>] [--version <VERSION>]

dotnet tool update -h|--help
```

## <a name="description"></a>Описание

Команда `dotnet tool update` предоставляет способ обновления средства .NET на компьютере до последней стабильной версии пакета. Команда удаляет и повторно устанавливает средство, эффективно обновляя его. Чтобы использовать команду, необходимо указать один из следующих параметров:

* Чтобы обновить глобальное средство, установленное в расположении по умолчанию, используйте параметр `--global`
* Чтобы обновить глобальное средство, установленное в пользовательском расположении, используйте параметр `--tool-path`.
* Чтобы обновить локальное средство, используйте параметр `--local`.

**Локальные средства доступны в пакете SDK для .NET Core, начиная с версии 3.0.**

## <a name="arguments"></a>Аргументы

- **`PACKAGE_ID`**

  Имя или идентификатор пакета NuGet, который содержит глобальное средство .NET, которое вы хотите обновить. Найти имя пакета можно с помощью команды [dotnet tool list](dotnet-tool-list.md).

## <a name="options"></a>Параметры

- **`--add-source <SOURCE>`**

  Добавляет дополнительный источник пакета NuGet для использования во время установки.

- **`--configfile <FILE>`**

  Файл конфигурации NuGet (*nuget.config*), который будет использоваться.

- **`--disable-parallel`**

  Блокирует параллельное восстановление множества проектов.

- **`--framework <FRAMEWORK>`**

  Указывает [требуемую версию .NET Framework](../../standard/frameworks.md) для обновления средства.

- **`--ignore-failed-sources`**

  Обрабатывать сбои источников пакетов как предупреждения.

- **`--interactive`**

  Позволяет остановить команду и дождаться, пока пользователь введет данные или выполнит действие (например, завершит проверку подлинности).

- **`--local`**

  Обновляет средство и манифест локального средства. Не может использоваться вместе с параметром `--global` или `--tool-path`.

- **`--no-cache`**

  Запрещает кэширование пакетов и HTTP-запросов.

- **`--tool-manifest <PATH>`**

  Путь к файлу манифеста.

- **`--tool-path <PATH>`**

  Указывает место установки глобального средства. Путь может быть абсолютным или относительным. Не может использоваться вместе с параметром `--global`. Пропуск `--global` и `--tool-path` означает, что обновляемое средство является локальным.

- **`--version <VERSION>`**

  Диапазон версий пакета средства для обновления. Нельзя использовать для перехода на более ранние версии, необходимо сначала `uninstall` новые версии.

- **`-g|--global`**

  Указывает, что обновление предназначено для средства уровня пользователя. Не может использоваться вместе с параметром `--tool-path`. Пропуск `--global` и `--tool-path` означает, что обновляемое средство является локальным.

- **`-h|--help`**

  Выводит краткую справку по команде.

- **`-v|--verbosity <LEVEL>`**

  Задает уровень детализации команды. Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.

## <a name="examples"></a>Примеры

- **`dotnet tool update -g dotnetsay`**

  Обновляет глобальное средство [dotnetsay](https://www.nuget.org/packages/dotnetsay/).

- **`dotnet tool update dotnetsay --tool-path c:\global-tools`**

  Обновляет глобальное средство [dotnetsay](https://www.nuget.org/packages/dotnetsay/), расположенное в определенном каталоге Windows.

- **`dotnet tool update dotnetsay --tool-path ~/bin`**

  Обновляет глобальное средство [dotnetsay](https://www.nuget.org/packages/dotnetsay/), расположенное в определенном каталоге Linux/macOS.

- **`dotnet tool update dotnetsay`**

  Обновляет локальное средство [dotnetsay](https://www.nuget.org/packages/dotnetsay/), установленное для текущего каталога.

- **`dotnet tool update -g dotnetsay --version 2.0.*`**

  Обновляет глобальное средство [dotnetsay](https://www.nuget.org/packages/dotnetsay/) до последней версии исправления с основным номером версии `2` и дополнительным номером версии `0`.

- **`dotnet tool update -g dotnetsay --version (2.0.*,2.1.4)`**

  Обновляет глобальное средство [dotnetsay](https://www.nuget.org/packages/dotnetsay/) до самой низкой версии в указанном диапазоне `(> 2.0.0 && < 2.1.4)`. Будет установлена версия `2.1.0`. Дополнительные сведения о семантических диапазонах версий см. в разделе [Диапазоны версий пакетов NuGet](/nuget/concepts/package-versioning#version-ranges).

## <a name="see-also"></a>См. также

- [Средства .NET](global-tools.md)
- [Семантическое управление версиями](https://semver.org)
- [Учебник. Установка и использование глобального средства .NET с помощью интерфейса командной строки .NET](global-tools-how-to-use.md)
- [Учебник. Установка и использование локального средства .NET с помощью интерфейса командной строки .NET](local-tools-how-to-use.md)
