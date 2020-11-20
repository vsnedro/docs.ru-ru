---
title: Команда dotnet tool search
description: Команда dotnet tool search выполняет поиск инструментов .NET, опубликованных в NuGet.org.
ms.date: 11/11/2020
ms.openlocfilehash: e0289e651ec4a439c791c8c948bef2d85d9c3794
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634146"
---
# <a name="dotnet-tool-search"></a>dotnet tool search

**Эта статья относится к:** ✔️ пакету SDK для .NET 5.0 и более поздних версий

## <a name="name"></a>Название

`dotnet tool search` — поиск всех [инструментов .NET](global-tools.md), опубликованных в NuGet.

## <a name="synopsis"></a>Краткий обзор

```dotnetcli
dotnet tool search [--detail]  [--prerelease]
    [--skip <NUMBER>] [--take <NUMBER>] <SEARCH TERM>

dotnet tool search -h|--help
```

## <a name="description"></a>Описание

Команда `dotnet tool search` предоставляет возможность поиска в NuGet средств, которые можно использовать в качестве глобальных средств, средств пути к средству и локальных средств. Эта команда выполняет поиск в именах инструментов и метаданных, таких как заголовки, описания и теги.

Команда использует [API поиска NuGet](/nuget/api/search-query-service-resource#search-for-packages). Она применяет фильтр по ключу `packageType=dotnettool`, чтобы выбрать только пакеты инструментов .NET.

## <a name="options"></a>Параметры

- **`--detail`**

  Отображение подробных результатов запроса.

- **`--prerelease`**

  Включение пакетов предварительных версий.

- **`--skip <NUMBER>`**

  Задать число пропускаемых результатов запроса. Используется для разбиения на страницы.

- **`--take <NUMBER>`**

  Задать число отображаемых результатов запроса. Используется для разбиения на страницы.

- **`-h|--help`**

  Отображение справки в командной строке.

## <a name="examples"></a>Примеры

- Поиск на сайте NuGet.org инструментов .NET, имеющих в имени или описании пакета строку "format":

  ```dotnetcli
  dotnet tool search format
  ```

  Выходные данные выглядят примерно так, как в следующем примере:

  ```output
  Package ID                              Latest Version      Authors                                                                     Downloads      Verified
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------
  dotnet-format                           4.1.131201          Microsoft                                                                   496746
  bsoa.generator                          1.0.0               Microsoft                                                                   533
  ```

- Поиск на сайте NuGet.org инструментов .NET, имеющих в имени или метаданных пакета строку "format", отображение только первого результата и вывод подробного представления:

  ```dotnetcli
  dotnet tool search format --take 1 --detail
  ```

  Выходные данные выглядят примерно так, как в следующем примере:

  ```output
  ----------------
  dotnet-format
  Latest Version: 4.1.131201
  Authors: Microsoft
  Tags:
  Downloads: 496746
  Verified: False
  Description: Command line tool for formatting C# and Visual Basic code files based on .editorconfig settings.
  Versions:
          3.0.2 Downloads: 1973
          3.0.4 Downloads: 9064
          3.1.37601 Downloads: 114730
          3.2.107702 Downloads: 13423
          3.3.111304 Downloads: 131195
          4.0.130203 Downloads: 78610
          4.1.131201 Downloads: 145927
  ```

## <a name="see-also"></a>См. также раздел

- [Средства .NET](global-tools.md)
- [Учебник. Установка и использование глобального средства .NET с помощью интерфейса командной строки .NET](global-tools-how-to-use.md)
- [Учебник. Установка и использование локального средства .NET с помощью интерфейса командной строки .NET](local-tools-how-to-use.md)
