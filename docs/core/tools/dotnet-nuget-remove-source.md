---
title: Команда dotnet nuget remove source
description: Команда dotnet nuget remove source удаляет существующий источник из файлов конфигурации NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: b5575c31c0008d6e3e5a2e52906a076614217dd0
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537898"
---
# <a name="dotnet-nuget-remove-source"></a>dotnet nuget remove source

**Эта статья относится к:** ✔️ пакету SDK для .NET Core 3.1.200 и более поздних версий

## <a name="name"></a>name

`dotnet nuget remove source` — удаление источника NuGet.

## <a name="synopsis"></a>Краткий обзор

```dotnetcli
dotnet nuget remove source <NAME> [--configfile <FILE>]

dotnet nuget remove source -h|--help
```

## <a name="description"></a>Описание

Команда `dotnet nuget remove source` удаляет существующий источник из файлов конфигурации NuGet.

## <a name="arguments"></a>Аргументы

- **`NAME`**

  Имя источника.

## <a name="options"></a>Параметры

- **`--configfile`**

  Файл конфигурации NuGet. Если этот параметр указан, будут использоваться только параметры из этого файла. Если не указано, будет использоваться иерархия файлов конфигурации из текущего каталога. Дополнительные сведения см. в статье [Распространенные конфигурации NuGet](/nuget/consume-packages/configuring-nuget-behavior).

## <a name="examples"></a>Примеры

- Удалите источник с именем `mySource`:

  ```dotnetcli
  dotnet nuget remove source mySource
  ```

## <a name="see-also"></a>См. также

- [Разделы источников пакетов в файлах NuGet.config](/nuget/reference/nuget-config-file#package-source-sections)

- [Команда sources (nuget.exe)](/nuget/reference/cli-reference/cli-ref-sources)
