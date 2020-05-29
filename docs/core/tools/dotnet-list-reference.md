---
title: Команда dotnet list reference
description: Команду dotnet list reference удобно использовать для перечисления ссылок между проектами.
ms.date: 02/14/2020
ms.openlocfilehash: b9b34c17102c6218f3d99f6e2620e99f70140284
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83802764"
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="963e9-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="963e9-103">dotnet list reference</span></span>

<span data-ttu-id="963e9-104">**Эта статья относится к следующему:** ✔️ пакет SDK для .NET Core 2.x и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="963e9-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="963e9-105">name</span><span class="sxs-lookup"><span data-stu-id="963e9-105">Name</span></span>

<span data-ttu-id="963e9-106">`dotnet list reference` — перечисляет перекрестные ссылки между проектами.</span><span class="sxs-lookup"><span data-stu-id="963e9-106">`dotnet list reference` - Lists project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="963e9-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="963e9-107">Synopsis</span></span>

```dotnetcli
dotnet list [<PROJECT>] reference

dotnet list -h|--help
```

## <a name="description"></a><span data-ttu-id="963e9-108">Описание</span><span class="sxs-lookup"><span data-stu-id="963e9-108">Description</span></span>

<span data-ttu-id="963e9-109">Команду `dotnet list reference` удобно использовать для перечисления ссылок на проекты для заданного проекта.</span><span class="sxs-lookup"><span data-stu-id="963e9-109">The `dotnet list reference` command provides a convenient option to list project references for a given project.</span></span>

## <a name="arguments"></a><span data-ttu-id="963e9-110">Аргументы</span><span class="sxs-lookup"><span data-stu-id="963e9-110">Arguments</span></span>

* **`PROJECT`**

  <span data-ttu-id="963e9-111">Целевой файл проекта.</span><span class="sxs-lookup"><span data-stu-id="963e9-111">The project file to operate on.</span></span> <span data-ttu-id="963e9-112">Если этот файл не указан, команда будет искать текущий каталог для него.</span><span class="sxs-lookup"><span data-stu-id="963e9-112">If a file is not specified, the command will search the current directory for one.</span></span>

## <a name="options"></a><span data-ttu-id="963e9-113">Параметры</span><span class="sxs-lookup"><span data-stu-id="963e9-113">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="963e9-114">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="963e9-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="963e9-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="963e9-115">Examples</span></span>

* <span data-ttu-id="963e9-116">Перечисление ссылок на проекты для указанного проекта:</span><span class="sxs-lookup"><span data-stu-id="963e9-116">List the project references for the specified project:</span></span>

  ```dotnetcli
  dotnet list app/app.csproj reference
  ```

* <span data-ttu-id="963e9-117">Перечисление ссылок на проекты для проекта в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="963e9-117">List the project references for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet list reference
  ```
