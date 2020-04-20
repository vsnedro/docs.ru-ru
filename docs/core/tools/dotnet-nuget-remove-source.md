---
title: Команда dotnet nuget remove source
description: Команда dotnet nuget remove source удаляет существующий источник из файлов конфигурации NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: b259873e1885644b272136fa31414410bdfd9f27
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463495"
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

  Файл конфигурации NuGet. Если этот параметр указан, будут использоваться только параметры из этого файла. Если не указано, будет использоваться иерархия файлов конфигурации из текущего каталога. Дополнительные сведения см. в статье [Распространенные конфигурации NuGet](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).

## <a name="examples"></a>Примеры

- Удалите источник с именем `mySource`:

  ```dotnetcli
  dotnet nuget remove source mySource
  ```

## <a name="see-also"></a>См. также

- [Разделы источников пакетов в файлах NuGet.config](/nuget/reference/nuget-config-file#package-source-sections)

- [Команда sources (nuget.exe)](/nuget/reference/cli-reference/cli-ref-sources)
