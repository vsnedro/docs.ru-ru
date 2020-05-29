---
title: Команда dotnet list reference
description: Команду dotnet list reference удобно использовать для перечисления ссылок между проектами.
ms.date: 02/14/2020
ms.openlocfilehash: b9b34c17102c6218f3d99f6e2620e99f70140284
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83802764"
---
# <a name="dotnet-list-reference"></a>dotnet list reference

**Эта статья относится к следующему:** ✔️ пакет SDK для .NET Core 2.x и более поздних версий

## <a name="name"></a>name

`dotnet list reference` — перечисляет перекрестные ссылки между проектами.

## <a name="synopsis"></a>Краткий обзор

```dotnetcli
dotnet list [<PROJECT>] reference

dotnet list -h|--help
```

## <a name="description"></a>Описание

Команду `dotnet list reference` удобно использовать для перечисления ссылок на проекты для заданного проекта.

## <a name="arguments"></a>Аргументы

* **`PROJECT`**

  Целевой файл проекта. Если этот файл не указан, команда будет искать текущий каталог для него.

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
