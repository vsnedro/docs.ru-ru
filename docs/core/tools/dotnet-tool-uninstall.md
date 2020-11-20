---
title: Команда dotnet tool uninstall
description: Команда dotnet tool uninstall удаляет указанное средство .NET с компьютера.
ms.date: 02/14/2020
ms.openlocfilehash: 34dffde8f9c930327c6b42d1d89bb4f511959fb2
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634094"
---
# <a name="dotnet-tool-uninstall"></a>dotnet tool uninstall

**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий

## <a name="name"></a>name

`dotnet tool uninstall` — удаляет указанное [средство .NET](global-tools.md) с компьютера.

## <a name="synopsis"></a>Краткий обзор

```dotnetcli
dotnet tool uninstall <PACKAGE_NAME> -g|--global

dotnet tool uninstall <PACKAGE_NAME> --tool-path <PATH>

dotnet tool uninstall <PACKAGE_NAME>

dotnet tool uninstall -h|--help
```

## <a name="description"></a>Описание

Команда `dotnet tool uninstall` позволяет удалить средства .NET с компьютера. Чтобы использовать команду, необходимо указать один из следующих параметров:

* Чтобы удалить глобальное средство, установленное в расположении по умолчанию, используйте параметр `--global`.
* Чтобы удалить глобальное средство, установленное в пользовательском расположении, используйте параметр `--tool-path`.
* Чтобы удалить локальный инструмент, пропустите параметры `--global` и `--tool-path`.

**Локальные средства доступны в пакете SDK для .NET Core, начиная с версии 3.0.**

## <a name="arguments"></a>Аргументы

- **`PACKAGE_NAME`**

  Имя или идентификатор пакета NuGet, который содержит удаляемое средство .NET. Найти имя пакета можно с помощью команды [dotnet tool list](dotnet-tool-list.md).

## <a name="options"></a>Параметры

- **`-g|--global`**

  Указывает, что средство будет удалено из установки на уровне пользователя. Не может использоваться вместе с параметром `--tool-path`. Пропуск `--global` и `--tool-path` означает, что удаляемое средство является локальным.

- **`-h|--help`**

  Выводит краткую справку по команде.

- **`--tool-path <PATH>`**

  Указывает место, откуда будет удалено средство. Путь может быть абсолютным или относительным. Не может использоваться вместе с параметром `--global`. Пропуск `--global` и `--tool-path` означает, что удаляемое средство является локальным.

## <a name="examples"></a>Примеры

- **`dotnet tool uninstall -g dotnetsay`**

  Удаляет глобальное средство [dotnetsay](https://www.nuget.org/packages/dotnetsay/).

- **`dotnet tool uninstall dotnetsay --tool-path c:\global-tools`**

  Удаляет глобальное средство [dotnetsay](https://www.nuget.org/packages/dotnetsay/) из определенного каталога Windows.

- **`dotnet tool uninstall dotnetsay --tool-path ~/bin`**

  Удаляет глобальное средство [dotnetsay](https://www.nuget.org/packages/dotnetsay/) из определенного каталога Linux/macOS.

- **`dotnet tool uninstall dotnetsay`**

  Удаляет локальный инструмент [dotnetsay](https://www.nuget.org/packages/dotnetsay/) из текущего каталога.

## <a name="see-also"></a>См. также

- [Средства .NET](global-tools.md)
- [Учебник. Установка и использование глобального средства .NET с помощью интерфейса командной строки .NET](global-tools-how-to-use.md)
- [Учебник. Установка и использование локального средства .NET с помощью интерфейса командной строки .NET](local-tools-how-to-use.md)
