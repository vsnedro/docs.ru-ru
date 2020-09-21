---
title: Команда dotnet nuget enable source
description: Команда dotnet nuget enable source включает существующий источник в файлах конфигурации NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: b727844dd7d7cc82476e94a3f0ec4ecc6559d5ed
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537938"
---
# <a name="dotnet-nuget-enable-source"></a>dotnet nuget enable source

**Эта статья относится к:** ✔️ пакету SDK для .NET Core 3.1.200 и более поздних версий

## <a name="name"></a>name

`dotnet nuget enable source` — включает источник NuGet.

## <a name="synopsis"></a>Краткий обзор

```dotnetcli
dotnet nuget enable source <NAME> [--configfile <FILE>]

dotnet nuget enable source -h|--help
```

## <a name="description"></a>Описание

Команда `dotnet nuget enable source` включает существующий источник в файлах конфигурации NuGet.

## <a name="arguments"></a>Аргументы

- **`NAME`**

  Имя источника.

## <a name="options"></a>Параметры

- **`--configfile <FILE>`**

  Файл конфигурации NuGet. Если этот параметр указан, будут использоваться только параметры из этого файла. Если не указано, будет использоваться иерархия файлов конфигурации из текущего каталога. Дополнительные сведения см. в статье [Распространенные конфигурации NuGet](/nuget/consume-packages/configuring-nuget-behavior).

## <a name="examples"></a>Примеры

- Включите источник с именем `mySource`:

  ```dotnetcli
  dotnet nuget enable source mySource
  ```

## <a name="see-also"></a>См. также

- [Разделы источников пакетов в файлах NuGet.config](/nuget/reference/nuget-config-file#package-source-sections)

- [Команда sources (nuget.exe)](/nuget/reference/cli-reference/cli-ref-sources)
