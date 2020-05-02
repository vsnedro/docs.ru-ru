---
title: Команда dotnet remove reference
description: Команду dotnet remove reference удобно использовать для удаления ссылок между проектами.
ms.date: 02/14/2020
ms.openlocfilehash: a45153376d7d6eb764c1d2c6b473d04a273a2de1
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158337"
---
# <a name="dotnet-remove-reference"></a>dotnet remove reference

**Эта статья относится к следующему:** ✔️ пакет SDK для .NET Core 2.x и более поздних версий

## <a name="name"></a>name

`dotnet remove reference` — удаляет перекрестные ссылки между проектами (P2P).

## <a name="synopsis"></a>Краткий обзор

```dotnetcli
dotnet remove [<PROJECT>] reference [-f|--framework <FRAMEWORK>]
     <PROJECT_REFERENCES>

dotnet remove reference -h|--help
```

## <a name="description"></a>Описание

Команду `dotnet remove reference` удобно использовать для удаления ссылок на проекты из проекта.

## <a name="arguments"></a>Аргументы

`PROJECT`

Файл целевого проекта. Если он не указан, команда ищет текущий каталог для него.

`PROJECT_REFERENCES`

Удаляемые перекрестные ссылки между проектами (P2P). Вы можете указать один или несколько проектов. [Стандартные маски](https://en.wikipedia.org/wiki/Glob_(programming)) поддерживаются в терминалах на основе Unix или Linux.

## <a name="options"></a>Параметры

- **`-h|--help`**

  Выводит краткую справку по команде.

- **`-f|--framework <FRAMEWORK>`**

  Удаляет ссылку только при ориентации на конкретную [платформу](../../standard/frameworks.md) в формате TFM.

## <a name="examples"></a>Примеры

- Удаление ссылки на проект из указанного проекта:

  ```dotnetcli
  dotnet remove app/app.csproj reference lib/lib.csproj
  ```

- Удаление нескольких ссылок на проекты из проекта в текущем каталоге:

  ```dotnetcli
  dotnet remove reference lib1/lib1.csproj lib2/lib2.csproj
  ```

- Удаление нескольких ссылок на проект с помощью стандартной маски в Unix или Linux:

  ```dotnetcli
  dotnet remove app/app.csproj reference **/*.csproj`
  ```
