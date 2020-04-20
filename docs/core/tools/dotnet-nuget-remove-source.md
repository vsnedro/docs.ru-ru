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
# <a name="dotnet-nuget-remove-source"></a><span data-ttu-id="04a94-103">dotnet nuget remove source</span><span class="sxs-lookup"><span data-stu-id="04a94-103">dotnet nuget remove source</span></span>

<span data-ttu-id="04a94-104">**Эта статья относится к:** ✔️ пакету SDK для .NET Core 3.1.200 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="04a94-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="04a94-105">name</span><span class="sxs-lookup"><span data-stu-id="04a94-105">Name</span></span>

<span data-ttu-id="04a94-106">`dotnet nuget remove source` — удаление источника NuGet.</span><span class="sxs-lookup"><span data-stu-id="04a94-106">`dotnet nuget remove source` - Remove a NuGet source.</span></span>

## <a name="synopsis"></a><span data-ttu-id="04a94-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="04a94-107">Synopsis</span></span>

```dotnetcli
dotnet nuget remove source <NAME> [--configfile <FILE>]

dotnet nuget remove source -h|--help
```

## <a name="description"></a><span data-ttu-id="04a94-108">Описание</span><span class="sxs-lookup"><span data-stu-id="04a94-108">Description</span></span>

<span data-ttu-id="04a94-109">Команда `dotnet nuget remove source` удаляет существующий источник из файлов конфигурации NuGet.</span><span class="sxs-lookup"><span data-stu-id="04a94-109">The `dotnet nuget remove source` command removes an existing source from your NuGet configuration files.</span></span>

## <a name="arguments"></a><span data-ttu-id="04a94-110">Аргументы</span><span class="sxs-lookup"><span data-stu-id="04a94-110">Arguments</span></span>

- **`NAME`**

  <span data-ttu-id="04a94-111">Имя источника.</span><span class="sxs-lookup"><span data-stu-id="04a94-111">Name of the source.</span></span>

## <a name="options"></a><span data-ttu-id="04a94-112">Параметры</span><span class="sxs-lookup"><span data-stu-id="04a94-112">Options</span></span>

- **`--configfile`**

  <span data-ttu-id="04a94-113">Файл конфигурации NuGet.</span><span class="sxs-lookup"><span data-stu-id="04a94-113">The NuGet configuration file.</span></span> <span data-ttu-id="04a94-114">Если этот параметр указан, будут использоваться только параметры из этого файла.</span><span class="sxs-lookup"><span data-stu-id="04a94-114">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="04a94-115">Если не указано, будет использоваться иерархия файлов конфигурации из текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="04a94-115">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="04a94-116">Дополнительные сведения см. в статье [Распространенные конфигурации NuGet](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span><span class="sxs-lookup"><span data-stu-id="04a94-116">For more information, see [Common NuGet Configurations](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span></span>

## <a name="examples"></a><span data-ttu-id="04a94-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="04a94-117">Examples</span></span>

- <span data-ttu-id="04a94-118">Удалите источник с именем `mySource`:</span><span class="sxs-lookup"><span data-stu-id="04a94-118">Remove a source with name of `mySource`:</span></span>

  ```dotnetcli
  dotnet nuget remove source mySource
  ```

## <a name="see-also"></a><span data-ttu-id="04a94-119">См. также</span><span class="sxs-lookup"><span data-stu-id="04a94-119">See also</span></span>

- [<span data-ttu-id="04a94-120">Разделы источников пакетов в файлах NuGet.config</span><span class="sxs-lookup"><span data-stu-id="04a94-120">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="04a94-121">Команда sources (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="04a94-121">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
