---
title: Команда dotnet tool run
description: Команда dotnet tool run вызывает локальное средство.
ms.date: 02/14/2020
ms.openlocfilehash: 116ecb61748a0ca70ed385b279b11b939748f4a8
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634159"
---
# <a name="dotnet-tool-run"></a>dotnet tool run

**Эта статья относится к следующему.** ✔️ SDK для .NET Core 3.0 и более поздних версий

## <a name="name"></a>name

`dotnet tool run` — вызов локального средства.

## <a name="synopsis"></a>Краткий обзор

```dotnetcli
dotnet tool run <COMMAND NAME>

dotnet tool run -h|--help
```

## <a name="description"></a>Описание

Команда `dotnet tool run` позволяет выполнить поиск по файлам манифеста средства, которые входят в область текущего каталога. При нахождении ссылки на указанное средство оно запускается. См. дополнительные сведения о [запуске локального средства](global-tools.md#invoke-a-local-tool).

## <a name="arguments"></a>Аргументы

- **`COMMAND_NAME`**

  Имя выполняемой команды в средстве.

## <a name="options"></a>Параметры

- **`-h|--help`**

  Выводит краткую справку по команде.

## <a name="example"></a>Пример

- **`dotnet tool run dotnetsay`**

  Запуск локального средства `dotnetsay`.

## <a name="see-also"></a>См. также

- [Средства .NET](global-tools.md)
- [Учебник. Установка и использование локального средства .NET с помощью интерфейса командной строки .NET](local-tools-how-to-use.md)
