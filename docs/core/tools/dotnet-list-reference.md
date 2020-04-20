---
title: Команда dotnet list reference
description: Команду dotnet list reference удобно использовать для перечисления ссылок между проектами.
ms.date: 02/14/2020
ms.openlocfilehash: c0ea46298123e69ae527870e50d204d8fcf5cc85
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463649"
---
# <a name="dotnet-list-reference"></a>dotnet list reference

**Эта статья относится к следующему:** ✔️ пакет SDK для .NET Core 2.x и более поздних версий

## <a name="name"></a>Имя

`dotnet list reference` — перечисляет перекрестные ссылки между проектами.

## <a name="synopsis"></a>Краткий обзор

```dotnetcli
dotnet list [<PROJECT>|<SOLUTION>] reference

dotnet list -h|--help
```

## <a name="description"></a>Описание:

Команду `dotnet list reference` удобно использовать для перечисления ссылок на проекты для заданного проекта или решения.

## <a name="arguments"></a>Аргументы

* **`PROJECT | SOLUTION`**

  Указывает файл проекта или решения, используемый для перечисления ссылок. Если он не указан, команда ищет текущий каталог для него.

## <a name="options"></a>Параметры

* **`-h|--help`**

  Выводит краткую справку по команде.

## <a name="examples"></a>Примеры

* Перечисление ссылок на проекты для указанного проекта:

  ```dotnetcli
  dotnet list app/app.csproj reference
  ```

* Перечисление ссылок на проекты для проекта в текущем каталоге:

  ```dotnetcli
  dotnet list reference
  ```
