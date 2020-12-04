---
title: Команда dotnet pack
description: Команда dotnet pack создает пакеты NuGet для проекта .NET.
ms.date: 04/28/2020
ms.openlocfilehash: 3ca7947b4ed9902b163f09a7b57696f304610cce
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674805"
---
# <a name="dotnet-pack"></a>dotnet pack

**Эта статья относится к следующему:** ✔️ пакет SDK для .NET Core 2.x и более поздних версий

## <a name="name"></a>name

`dotnet pack` — упаковывает код в пакет NuGet.

## <a name="synopsis"></a>Краткий обзор

```dotnetcli
dotnet pack [<PROJECT>|<SOLUTION>] [-c|--configuration <CONFIGURATION>]
    [--force] [--include-source] [--include-symbols] [--interactive]
    [--no-build] [--no-dependencies] [--no-restore] [--nologo]
    [-o|--output <OUTPUT_DIRECTORY>] [--runtime <RUNTIME_IDENTIFIER>]
    [-s|--serviceable] [-v|--verbosity <LEVEL>]
    [--version-suffix <VERSION_SUFFIX>]

dotnet pack -h|--help
```

## <a name="description"></a>Описание

Команда `dotnet pack` выполняет сборку проекта и создает пакеты NuGet. Результат выполнения команды — пакет NuGet (то есть файл *NUPKG*).

Если вы хотите создать пакет, содержащий отладочные символы, доступны два варианта:

- `--include-symbols` — создает пакет символов.
- `--include-source` — создает пакет символов с папкой `src`, содержащей исходные файлы.

Зависимости NuGet упакованного проекта добавляются в файл *NUSPEC*, чтобы их можно было разрешить при установке пакета. Межпроектные ссылки не упаковываются в проекте. Сейчас при наличии межпроектных зависимостей требуется один пакет на каждый проект.

`dotnet pack` по умолчанию сначала выполняет сборку проекта. Чтобы избежать этого, передайте параметр `--no-build`. Этот вариант часто бывает полезен, например в сценариях сборки с непрерывной интеграцией (CI), когда вы знаете, что код был собран недавно.

> [!NOTE]
> В некоторых случаях выполнить неявную сборку невозможно. Это может произойти, если задано свойство `GeneratePackageOnBuild`, позволяющее избежать циклической зависимости между целевыми объектами сборки и упаковки. Кроме того, сборка может завершиться ошибкой при наличии заблокированного файла или другой проблемы.

Может предоставлять свойства MSBuild команде `dotnet pack` для процесса упаковки. Дополнительные сведения см. в разделах [Свойства метаданных NuGet](csproj.md#nuget-metadata-properties) и [Справочник по командной строке MSBuild](/visualstudio/msbuild/msbuild-command-line-reference). В разделе [Примеры](#examples) показано, как использовать параметр -p MSBuild в различных сценариях.

Веб-проекты по умолчанию не упаковываются. Чтобы переопределить такое поведение по умолчанию, добавьте следующее свойство в файл с расширением *.csproj*:

```xml
<PropertyGroup>
   <IsPackable>true</IsPackable>
</PropertyGroup>
```

### <a name="implicit-restore"></a>Неявное восстановление

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a>Аргументы

`PROJECT | SOLUTION`

  Проект или решение для упаковки. Это путь к файлу [.csproj](csproj.md), .vbproj или .fsproj либо файлу решения или каталогу. Если он не указан, команда ищет текущий каталог для файла решения или проекта.

## <a name="options"></a>Параметры

- **`-c|--configuration <CONFIGURATION>`**

  Определяет конфигурацию сборки. По умолчанию для большинства проектов используется `Debug`, но можно переопределить параметры конфигурации сборки в проекте.

- **`--force`**

  Принудительное разрешение всех зависимостей, даже если последнее восстановление прошло успешно. Указание этого флага дает тот же результат, что удаление файла *project.assets.json*.

- **`-h|--help`**

  Выводит краткую справку по команде.

- **`--include-source`**

  Включает пакеты NuGet отладочных символов в дополнение к обычным пакетам NuGet в выходном каталоге. Исходные файлы включены в папку `src` пакета символов.

- **`--include-symbols`**

  Включает пакеты NuGet отладочных символов в дополнение к обычным пакетам NuGet в выходном каталоге.

- **`--interactive`**

  Позволяет остановить команду и дождаться, пока пользователь введет данные или выполнит действие (например, завершит проверку подлинности). Доступно, начиная с пакета SDK для .NET Core 3.0.

- **`--no-build`**

  Не выполняет сборку проекта перед упаковкой. Он также неявно задает флаг `--no-restore`.

- **`--no-dependencies`**

  Межпроектные ссылки игнорируются, и восстанавливается только корневой проект.

- **`--no-restore`**

  Не выполняет неявное восстановление при выполнении команды.

- **`--nologo`**

  Скрывает загрузочный баннер или сообщение об авторских правах. Доступно, начиная с пакета SDK для .NET Core 3.0.

- **`-o|--output <OUTPUT_DIRECTORY>`**

  Собранные пакеты помещаются в указанный каталог.

- **`--runtime <RUNTIME_IDENTIFIER>`**

  Задает целевую среду выполнения для восстановления пакетов. Список идентификаторов сред выполнения (RID) см. в [каталоге RID](../rid-catalog.md).

- **`-s|--serviceable`**

  Задает флаг "подлежит обслуживанию" в пакете. Дополнительные сведения см. в записи блога о том, что [.NET Framework 4.5.1 поддерживает обновления системы безопасности Майкрософт для библиотек .NET NuGet](https://aka.ms/nupkgservicing).

- **`--version-suffix <VERSION_SUFFIX>`**

  Определяет значение для свойства `$(VersionSuffix)` MSBuild в проекте.

- **`-v|--verbosity <LEVEL>`**

  Задает уровень детализации команды. Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.

## <a name="examples"></a>Примеры

- Упаковка проекта в текущем каталоге:

  ```dotnetcli
  dotnet pack
  ```

- Упаковка проекта `app1`:

  ```dotnetcli
  dotnet pack ~/projects/app1/project.csproj
  ```

- Упаковка проекта в текущем каталоге; полученные пакеты помещаются в папку `nupkgs`:

  ```dotnetcli
  dotnet pack --output nupkgs
  ```

- Упаковка проекта в текущем каталоге в папку `nupkgs` и пропуск этапа сборки:

  ```dotnetcli
  dotnet pack --no-build --output nupkgs
  ```

- Если суффикс версии пакета в файле *CSPROJ* настроен как `<VersionSuffix>$(VersionSuffix)</VersionSuffix>`, упаковка текущего проекта и обновление версии полученных пакетов с использованием указанного суффикса:

  ```dotnetcli
  dotnet pack --version-suffix "ci-1234"
  ```

- Устанавливает версию пакета в `2.1.0` с использованием свойства MSBuild `PackageVersion`:

  ```dotnetcli
  dotnet pack -p:PackageVersion=2.1.0
  ```

- Упакуйте проект для [требуемой версии .NET Framework](../../standard/frameworks.md):

  ```dotnetcli
  dotnet pack -p:TargetFrameworks=net45
  ```

- Упакуйте проект и используйте определенную среду выполнения (Windows 10) для операции восстановления:

  ```dotnetcli
  dotnet pack --runtime win10-x64
  ```

- Упакуйте проект с помощью *NUSPEC-файла*:

  ```dotnetcli
  dotnet pack ~/projects/app1/project.csproj -p:NuspecFile=~/projects/app1/project.nuspec -p:NuspecBasePath=~/projects/app1/nuget
  ```

  Дополнительные сведения об использовании `NuspecFile`, `NuspecBasePath` и `NuspecProperties` см. в следующих документах:

  - [Упаковка с помощью NUSPEC](/nuget/reference/msbuild-targets#packing-using-a-nuspec)
  - [Улучшенные точки расширения для создания настраиваемого пакета](/nuget/reference/msbuild-targets#advanced-extension-points-to-create-customized-package)
  - [Глобальные свойства](/visualstudio/msbuild/msbuild-properties#global-properties)
