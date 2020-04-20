---
title: Команда dotnet nuget enable source
description: Команда dotnet nuget enable source включает существующий источник в файлах конфигурации NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: 38fb5917361bd7952fef9c31ed897fb81f005155
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463562"
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

  Файл конфигурации NuGet. Если этот параметр указан, будут использоваться только параметры из этого файла. Если не указано, будет использоваться иерархия файлов конфигурации из текущего каталога. Дополнительные сведения см. в статье [Распространенные конфигурации NuGet](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).

## <a name="examples"></a>Примеры

- Включите источник с именем `mySource`:

  ```dotnetcli
  dotnet nuget enable source mySource
  ```

## <a name="see-also"></a>См. также

- [Разделы источников пакетов в файлах NuGet.config](/nuget/reference/nuget-config-file#package-source-sections)

- [Команда sources (nuget.exe)](/nuget/reference/cli-reference/cli-ref-sources)
