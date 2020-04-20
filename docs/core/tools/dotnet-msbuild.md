---
title: Команда dotnet msbuild
description: Команда dotnet msbuild обеспечивает доступ к командной строке MSBuild.
ms.date: 02/14/2020
ms.openlocfilehash: 88e85868e2d7de564b2e4c90ce6e78bde4cb350e
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463626"
---
# <a name="dotnet-msbuild"></a>dotnet msbuild

**Эта статья относится к следующему:** ✔️ пакет SDK для .NET Core 2.x и более поздних версий

## <a name="name"></a>Имя

`dotnet msbuild` — собирает проект и все его зависимости.

## <a name="synopsis"></a>Краткий обзор

```dotnetcli
dotnet msbuild <MSBUILD_ARGUMENTS>

dotnet msbuild -h
```

## <a name="description"></a>Описание:

Команда `dotnet msbuild` предоставляет доступ к полнофункциональной системе MSBuild.

Команда имеет точно такие же возможности, как и существующий клиент с интерфейсом командной строки MSBuild только для проектов в стиле SDK. Все параметры одинаковы. Дополнительные сведения о доступных параметрах см. в [справочнике по командной строке MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).

Команда [dotnet build](dotnet-build.md) эквивалентна `dotnet msbuild -restore -target:Build`. Обычно для сборки проектов используется команда [dotnet build](dotnet-build.md). Так как команда `dotnet msbuild` всегда запускает целевой объект сборки, вы можете использовать ее, если не хотите выполнять сборку проекта. Например, если вам нужно запустить конкретный целевой объект, не выполняя сборку проекта, используйте `dotnet msbuild` и укажите целевой объект.

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
  ```
