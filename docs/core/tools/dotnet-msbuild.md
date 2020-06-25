---
title: Команда dotnet msbuild
description: Команда dotnet msbuild обеспечивает доступ к командной строке MSBuild.
ms.date: 02/14/2020
ms.openlocfilehash: 9739fe782e17db3955db087ca1781ad4280cd491
ms.sourcegitcommit: 1eae045421d9ea2bfc82aaccfa5b1ff1b8c9e0e4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "84803172"
---
# <a name="dotnet-msbuild"></a>dotnet msbuild

**Эта статья относится к следующему:** ✔️ пакет SDK для .NET Core 2.x и более поздних версий

## <a name="name"></a>name

`dotnet msbuild` — собирает проект и все его зависимости. Примечание. При наличии нескольких файлов может потребоваться указать решение или файл проекта.

## <a name="synopsis"></a>Краткий обзор

```dotnetcli
dotnet msbuild <MSBUILD_ARGUMENTS>

dotnet msbuild -h
```

## <a name="description"></a>Описание

Команда `dotnet msbuild` предоставляет доступ к полнофункциональной системе MSBuild.

Команда имеет точно такие же возможности, как и существующий клиент с интерфейсом командной строки MSBuild только для проектов в стиле SDK. Все параметры одинаковы. Дополнительные сведения о доступных параметрах см. в [справочнике по командной строке MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).

Команда [dotnet build](dotnet-build.md) эквивалентна `dotnet msbuild -restore`. Если вы не хотите выполнять сборку проекта и у вас есть определенный целевой объект, используйте `dotnet build` или `dotnet msbuild` и укажите целевой объект.

## <a name="examples"></a>Примеры

- Сборка проекта и его зависимостей:

  ```dotnetcli
  dotnet msbuild
  ```

- Сборка проекта и его зависимостей с помощью конфигурации Release:

  ```dotnetcli
  dotnet msbuild -property:Configuration=Release
  ```

- Запустите цель публикации и публикацию для RID `osx.10.11-x64`:

  ```dotnetcli
  dotnet msbuild -target:Publish -property:RuntimeIdentifiers=osx.10.11-x64
  ```

- Весь проект со всеми целевыми объектами, включенными в пакет SDK:

  ```dotnetcli
  dotnet msbuild -preprocess
  dotnet msbuild -preprocess:<fileName>.xml
  ```
