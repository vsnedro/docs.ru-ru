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
# <a name="dotnet-tool-search"></a><span data-ttu-id="8108b-103">dotnet tool search</span><span class="sxs-lookup"><span data-stu-id="8108b-103">dotnet tool search</span></span>

<span data-ttu-id="8108b-104">**Эта статья относится к:** ✔️ пакету SDK для .NET 5.0 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="8108b-104">**This article applies to:** ✔️ .NET 5.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="8108b-105">Название</span><span class="sxs-lookup"><span data-stu-id="8108b-105">Name</span></span>

<span data-ttu-id="8108b-106">`dotnet tool search` — поиск всех [инструментов .NET](global-tools.md), опубликованных в NuGet.</span><span class="sxs-lookup"><span data-stu-id="8108b-106">`dotnet tool search` - Searches all [.NET tools](global-tools.md) that are published to NuGet.</span></span>

## <a name="synopsis"></a><span data-ttu-id="8108b-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="8108b-107">Synopsis</span></span>

```dotnetcli
dotnet tool search [--detail]  [--prerelease]
    [--skip <NUMBER>] [--take <NUMBER>] <SEARCH TERM>

dotnet tool search -h|--help
```

## <a name="description"></a><span data-ttu-id="8108b-108">Описание</span><span class="sxs-lookup"><span data-stu-id="8108b-108">Description</span></span>

<span data-ttu-id="8108b-109">Команда `dotnet tool search` предоставляет возможность поиска в NuGet средств, которые можно использовать в качестве глобальных средств, средств пути к средству и локальных средств.</span><span class="sxs-lookup"><span data-stu-id="8108b-109">The `dotnet tool search` command provides a way for you to search NuGet for tools that can be used as .NET global, tool-path, or local tools.</span></span> <span data-ttu-id="8108b-110">Эта команда выполняет поиск в именах инструментов и метаданных, таких как заголовки, описания и теги.</span><span class="sxs-lookup"><span data-stu-id="8108b-110">The command searches the tool names and metadata such as titles, descriptions, and tags.</span></span>

<span data-ttu-id="8108b-111">Команда использует [API поиска NuGet](/nuget/api/search-query-service-resource#search-for-packages).</span><span class="sxs-lookup"><span data-stu-id="8108b-111">The command uses the [NuGet Search API](/nuget/api/search-query-service-resource#search-for-packages).</span></span> <span data-ttu-id="8108b-112">Она применяет фильтр по ключу `packageType=dotnettool`, чтобы выбрать только пакеты инструментов .NET.</span><span class="sxs-lookup"><span data-stu-id="8108b-112">It filters on `packageType=dotnettool` to select only .NET tool packages.</span></span>

## <a name="options"></a><span data-ttu-id="8108b-113">Параметры</span><span class="sxs-lookup"><span data-stu-id="8108b-113">Options</span></span>

- **`--detail`**

  <span data-ttu-id="8108b-114">Отображение подробных результатов запроса.</span><span class="sxs-lookup"><span data-stu-id="8108b-114">Shows detailed results from the query.</span></span>

- **`--prerelease`**

  <span data-ttu-id="8108b-115">Включение пакетов предварительных версий.</span><span class="sxs-lookup"><span data-stu-id="8108b-115">Includes pre-release packages.</span></span>

- **`--skip <NUMBER>`**

  <span data-ttu-id="8108b-116">Задать число пропускаемых результатов запроса.</span><span class="sxs-lookup"><span data-stu-id="8108b-116">Specifies the number of query results to skip.</span></span> <span data-ttu-id="8108b-117">Используется для разбиения на страницы.</span><span class="sxs-lookup"><span data-stu-id="8108b-117">Used for pagination.</span></span>

- **`--take <NUMBER>`**

  <span data-ttu-id="8108b-118">Задать число отображаемых результатов запроса.</span><span class="sxs-lookup"><span data-stu-id="8108b-118">Specifies the number of query results to show.</span></span> <span data-ttu-id="8108b-119">Используется для разбиения на страницы.</span><span class="sxs-lookup"><span data-stu-id="8108b-119">Used for pagination.</span></span>

- **`-h|--help`**

  <span data-ttu-id="8108b-120">Отображение справки в командной строке.</span><span class="sxs-lookup"><span data-stu-id="8108b-120">Shows command-line help.</span></span>

## <a name="examples"></a><span data-ttu-id="8108b-121">Примеры</span><span class="sxs-lookup"><span data-stu-id="8108b-121">Examples</span></span>

- <span data-ttu-id="8108b-122">Поиск на сайте NuGet.org инструментов .NET, имеющих в имени или описании пакета строку "format":</span><span class="sxs-lookup"><span data-stu-id="8108b-122">Search NuGet.org for .NET tools that have "format" in their package name or description:</span></span>

  ```dotnetcli
  dotnet tool search format
  ```

  <span data-ttu-id="8108b-123">Выходные данные выглядят примерно так, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8108b-123">The output looks like the following example:</span></span>

  ```output
  Package ID                              Latest Version      Authors                                                                     Downloads      Verified
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------
  dotnet-format                           4.1.131201          Microsoft                                                                   496746
  bsoa.generator                          1.0.0               Microsoft                                                                   533
  ```

- <span data-ttu-id="8108b-124">Поиск на сайте NuGet.org инструментов .NET, имеющих в имени или метаданных пакета строку "format", отображение только первого результата и вывод подробного представления:</span><span class="sxs-lookup"><span data-stu-id="8108b-124">Search NuGet.org for .NET tools that have "format" in their package name or metadata, show only the first result, and show a detailed view.</span></span>

  ```dotnetcli
  dotnet tool search format --take 1 --detail
  ```

  <span data-ttu-id="8108b-125">Выходные данные выглядят примерно так, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8108b-125">The output looks like the following example:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="8108b-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8108b-126">See also</span></span>

- [<span data-ttu-id="8108b-127">Средства .NET</span><span class="sxs-lookup"><span data-stu-id="8108b-127">.NET tools</span></span>](global-tools.md)
- [<span data-ttu-id="8108b-128">Учебник. Установка и использование глобального средства .NET с помощью интерфейса командной строки .NET</span><span class="sxs-lookup"><span data-stu-id="8108b-128">Tutorial: Install and use a .NET global tool using the .NET CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="8108b-129">Учебник. Установка и использование локального средства .NET с помощью интерфейса командной строки .NET</span><span class="sxs-lookup"><span data-stu-id="8108b-129">Tutorial: Install and use a .NET local tool using the .NET CLI</span></span>](local-tools-how-to-use.md)
