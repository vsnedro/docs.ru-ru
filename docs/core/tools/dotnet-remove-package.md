---
title: Команда dotnet remove package
description: Команду dotnet remove package удобно использовать для удаления ссылки на пакет NuGet в проекте.
ms.date: 02/14/2020
ms.openlocfilehash: fc74ac1364a0ed027b83dab270d382f238dc00e5
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463459"
---
# <a name="dotnet-remove-package"></a><span data-ttu-id="0032c-103">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="0032c-103">dotnet remove package</span></span>

<span data-ttu-id="0032c-104">**Эта статья относится к следующему:** ✔️ пакет SDK для .NET Core 2.x и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="0032c-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="0032c-105">Имя</span><span class="sxs-lookup"><span data-stu-id="0032c-105">Name</span></span>

<span data-ttu-id="0032c-106">`dotnet remove package` — удаляет ссылку на пакет из файла проекта.</span><span class="sxs-lookup"><span data-stu-id="0032c-106">`dotnet remove package` - Removes package reference from a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="0032c-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="0032c-107">Synopsis</span></span>

```dotnetcli
dotnet remove [<PROJECT>] package <PACKAGE_NAME>

dotnet remove package -h|--help
```

## <a name="description"></a><span data-ttu-id="0032c-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="0032c-108">Description</span></span>

<span data-ttu-id="0032c-109">Команду `dotnet remove package` удобно использовать для удаления ссылки на пакет NuGet из проекта.</span><span class="sxs-lookup"><span data-stu-id="0032c-109">The `dotnet remove package` command provides a convenient option to remove a NuGet package reference from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="0032c-110">Аргументы</span><span class="sxs-lookup"><span data-stu-id="0032c-110">Arguments</span></span>

`PROJECT`

<span data-ttu-id="0032c-111">Указывает файл проекта.</span><span class="sxs-lookup"><span data-stu-id="0032c-111">Specifies the project file.</span></span> <span data-ttu-id="0032c-112">Если он не указан, команда ищет текущий каталог для него.</span><span class="sxs-lookup"><span data-stu-id="0032c-112">If not specified, the command searches the current directory for one.</span></span>

`PACKAGE_NAME`

<span data-ttu-id="0032c-113">Удаляемая ссылка на пакет.</span><span class="sxs-lookup"><span data-stu-id="0032c-113">The package reference to remove.</span></span>

## <a name="options"></a><span data-ttu-id="0032c-114">Параметры</span><span class="sxs-lookup"><span data-stu-id="0032c-114">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="0032c-115">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="0032c-115">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="0032c-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="0032c-116">Examples</span></span>

- <span data-ttu-id="0032c-117">Удалите пакет NuGet `Newtonsoft.Json` из проекта в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="0032c-117">Remove `Newtonsoft.Json` NuGet package from a project in the current directory:</span></span>

  ```dotnetcli
  dotnet remove package Newtonsoft.Json
  ```
