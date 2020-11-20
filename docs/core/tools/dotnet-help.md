---
title: Команда dotnet help
description: Команда dotnet help выводит более подробную документацию из Интернета для указанной команды.
ms.date: 02/14/2020
ms.openlocfilehash: d583142edabb24df972bdf9a06dbfe04688f9d97
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634472"
---
# <a name="dotnet-help-reference"></a>Справочник по команде dotnet help

**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.0 и более поздних версий

## <a name="name"></a>Имя

`dotnet help` — выводит более подробную документацию из Интернета для указанной команды.

## <a name="synopsis"></a>Краткий обзор

```dotnetcli
dotnet help <COMMAND_NAME> [-h|--help]
```

## <a name="description"></a>Описание:

Команда `dotnet help` открывает страницу сайта docs.microsoft.com с подробной справочной информацией об указанной команде.

## <a name="arguments"></a>Аргументы

- **`COMMAND_NAME`**

  Имя команды интерфейса командной строки .NET. Список допустимых команд интерфейса командной строки см. в разделе [Команды CLI](index.md#cli-commands).

## <a name="options"></a>Параметры

- **`-h|--help`**

  Выводит краткую справку по команде.

## <a name="examples"></a>Примеры

- Открывает страницу документации по команде[dotnet new](dotnet-new.md):

  ```dotnetcli
  dotnet help new
  ```
