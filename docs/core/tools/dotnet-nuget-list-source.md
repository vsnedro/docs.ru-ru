---
title: Команда dotnet nuget list source
description: Команда dotnet nuget list source выводит список всех существующих источников в файлах конфигурации NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: 8b14413949bd60ddeed977d19eec9bb99982da70
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463541"
---
# <a name="dotnet-nuget-list-source"></a>dotnet nuget list source

**Эта статья относится к:** ✔️ пакету SDK для .NET Core 3.1.200 и более поздних версий

## <a name="name"></a>name

`dotnet nuget list source` — перечисляет все настроенные источники NuGet.

## <a name="synopsis"></a>Краткий обзор

```dotnetcli
dotnet nuget list source [--format [Detailed|Short]] [--configfile <FILE>]

dotnet nuget list source -h|--help
```

## <a name="description"></a>Описание

Команда `dotnet nuget list source` перечисляет все существующие источники из файлов конфигурации NuGet.

## <a name="options"></a>Параметры

- **`--configfile <FILE>`**

  Файл конфигурации NuGet. Если этот параметр указан, будут использоваться только параметры из этого файла. Если не указано, будет использоваться иерархия файлов конфигурации из текущего каталога. Дополнительные сведения см. в статье [Распространенные конфигурации NuGet](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).

- **`--format [Detailed|Short]`**

  Формат выходных данных команды list: `Detailed` (по умолчанию) и `Short`.

## <a name="examples"></a>Примеры

- Список настроенных источников из текущего каталога:

  ```dotnetcli
  dotnet nuget list source
  ```

## <a name="see-also"></a>См. также

- [Разделы источников пакетов в файлах NuGet.config](/nuget/reference/nuget-config-file#package-source-sections)

- [Команда sources (nuget.exe)](/nuget/reference/cli-reference/cli-ref-sources)
