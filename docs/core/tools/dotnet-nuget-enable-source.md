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
# <a name="dotnet-nuget-enable-source"></a><span data-ttu-id="7b150-103">dotnet nuget enable source</span><span class="sxs-lookup"><span data-stu-id="7b150-103">dotnet nuget enable source</span></span>

<span data-ttu-id="7b150-104">**Эта статья относится к:** ✔️ пакету SDK для .NET Core 3.1.200 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="7b150-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="7b150-105">name</span><span class="sxs-lookup"><span data-stu-id="7b150-105">Name</span></span>

<span data-ttu-id="7b150-106">`dotnet nuget enable source` — включает источник NuGet.</span><span class="sxs-lookup"><span data-stu-id="7b150-106">`dotnet nuget enable source` - Enable a NuGet source.</span></span>

## <a name="synopsis"></a><span data-ttu-id="7b150-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="7b150-107">Synopsis</span></span>

```dotnetcli
dotnet nuget enable source <NAME> [--configfile <FILE>]

dotnet nuget enable source -h|--help
```

## <a name="description"></a><span data-ttu-id="7b150-108">Описание</span><span class="sxs-lookup"><span data-stu-id="7b150-108">Description</span></span>

<span data-ttu-id="7b150-109">Команда `dotnet nuget enable source` включает существующий источник в файлах конфигурации NuGet.</span><span class="sxs-lookup"><span data-stu-id="7b150-109">The `dotnet nuget enable source` command enables an existing source in your NuGet configuration files.</span></span>

## <a name="arguments"></a><span data-ttu-id="7b150-110">Аргументы</span><span class="sxs-lookup"><span data-stu-id="7b150-110">Arguments</span></span>

- **`NAME`**

  <span data-ttu-id="7b150-111">Имя источника.</span><span class="sxs-lookup"><span data-stu-id="7b150-111">Name of the source.</span></span>

## <a name="options"></a><span data-ttu-id="7b150-112">Параметры</span><span class="sxs-lookup"><span data-stu-id="7b150-112">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="7b150-113">Файл конфигурации NuGet.</span><span class="sxs-lookup"><span data-stu-id="7b150-113">The NuGet configuration file.</span></span> <span data-ttu-id="7b150-114">Если этот параметр указан, будут использоваться только параметры из этого файла.</span><span class="sxs-lookup"><span data-stu-id="7b150-114">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="7b150-115">Если не указано, будет использоваться иерархия файлов конфигурации из текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="7b150-115">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="7b150-116">Дополнительные сведения см. в статье [Распространенные конфигурации NuGet](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span><span class="sxs-lookup"><span data-stu-id="7b150-116">For more information, see [Common NuGet Configurations](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span></span>

## <a name="examples"></a><span data-ttu-id="7b150-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="7b150-117">Examples</span></span>

- <span data-ttu-id="7b150-118">Включите источник с именем `mySource`:</span><span class="sxs-lookup"><span data-stu-id="7b150-118">Enable a source with name of `mySource`:</span></span>

  ```dotnetcli
  dotnet nuget enable source mySource
  ```

## <a name="see-also"></a><span data-ttu-id="7b150-119">См. также</span><span class="sxs-lookup"><span data-stu-id="7b150-119">See also</span></span>

- [<span data-ttu-id="7b150-120">Разделы источников пакетов в файлах NuGet.config</span><span class="sxs-lookup"><span data-stu-id="7b150-120">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="7b150-121">Команда sources (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="7b150-121">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
