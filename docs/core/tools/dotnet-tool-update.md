---
title: Команда dotnet tool update
description: Команда dotnet tool update обновляет указанное средство .NET Core на вашем компьютере.
ms.date: 02/14/2020
ms.openlocfilehash: 6176846dbe8e2a91d9c6959dede15718d8f983b2
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463303"
---
# <a name="dotnet-tool-update"></a>dotnet tool update

**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий

## <a name="name"></a>name

`dotnet tool update` обновляет указанное [средство .NET Core](global-tools.md) на компьютер.

## <a name="synopsis"></a>Краткий обзор

```dotnetcli
dotnet tool update <PACKAGE_NAME> -g|--global
    [--configfile <FILE>] [--framework <FRAMEWORK>]
    [-v|--verbosity <LEVEL>] [--add-source <SOURCE>]

dotnet tool update <PACKAGE_NAME> --tool-path <PATH>
    [--configfile <FILE>] [--framework <FRAMEWORK>]
    [-v|--verbosity <LEVEL>] [--add-source <SOURCE>]

dotnet tool update <PACKAGE_NAME>
    [--configfile <FILE>] [--framework <FRAMEWORK>]
    [-v|--verbosity <LEVEL>] [--add-source <SOURCE>]

dotnet tool update -h|--help
```

## <a name="description"></a>Описание

Команда `dotnet tool update` предоставляет способ обновления средства .NET Core на компьютере до последней стабильной версии пакета. Команда удаляет и повторно устанавливает средство, эффективно обновляя его. Чтобы использовать команду, необходимо указать один из следующих параметров:

* Чтобы обновить глобальное средство, установленное в расположении по умолчанию, используйте параметр `--global`
* Чтобы обновить глобальное средство, установленное в пользовательском расположении, используйте параметр `--tool-path`.
* Чтобы обновить локальный инструмент, пропустите параметры `--global` и `--tool-path`.

**Локальные средства доступны в пакете SDK для .NET Core, начиная с версии 3.0.**

## <a name="arguments"></a>Аргументы

- **`PACKAGE_NAME`**

  Имя или идентификатор пакета NuGet, который содержит глобальное средство .NET Core, которое вы хотите обновить. Найти имя пакета можно с помощью команды [dotnet tool list](dotnet-tool-list.md).

## <a name="options"></a>Параметры

- **`--add-source <SOURCE>`**

  Добавляет дополнительный источник пакета NuGet для использования во время установки.

- **`--configfile <FILE>`**

  Файл конфигурации NuGet (*nuget.config*), который будет использоваться.

- **`--framework <FRAMEWORK>`**

  Указывает [требуемую версию .NET Framework](../../standard/frameworks.md) для обновления средства.

- **`-g|--global`**

  Указывает, что обновление предназначено для средства уровня пользователя. Не может использоваться вместе с параметром `--tool-path`. Пропуск `--global` и `--tool-path` означает, что обновляемое средство является локальным.

- **`-h|--help`**

  Выводит краткую справку по команде.

- **`--tool-path <PATH>`**

  Указывает место установки глобального средства. Путь может быть абсолютным или относительным. Не может использоваться вместе с параметром `--global`. Пропуск `--global` и `--tool-path` означает, что обновляемое средство является локальным.

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

## <a name="see-also"></a>См. также

- [Средства .NET Core](global-tools.md)
- [Учебник. Установка и использование глобального средства .NET Core с помощью интерфейса командной строки .NET Core](global-tools-how-to-use.md)
- [Учебник. Установка и использование локального средства .NET Core с помощью интерфейса командной строки .NET Core](local-tools-how-to-use.md)
