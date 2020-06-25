---
title: Команда dotnet msbuild
description: Команда dotnet msbuild обеспечивает доступ к командной строке MSBuild.
ms.date: 02/14/2020
ms.openlocfilehash: 9739fe782e17db3955db087ca1781ad4280cd491
ms.sourcegitcommit: 1eae045421d9ea2bfc82aaccfa5b1ff1b8c9e0e4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "84803172"
---
# <a name="dotnet-msbuild"></a><span data-ttu-id="52b00-103">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="52b00-103">dotnet msbuild</span></span>

<span data-ttu-id="52b00-104">**Эта статья относится к следующему:** ✔️ пакет SDK для .NET Core 2.x и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="52b00-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="52b00-105">name</span><span class="sxs-lookup"><span data-stu-id="52b00-105">Name</span></span>

<span data-ttu-id="52b00-106">`dotnet msbuild` — собирает проект и все его зависимости.</span><span class="sxs-lookup"><span data-stu-id="52b00-106">`dotnet msbuild` - Builds a project and all of its dependencies.</span></span> <span data-ttu-id="52b00-107">Примечание. При наличии нескольких файлов может потребоваться указать решение или файл проекта.</span><span class="sxs-lookup"><span data-stu-id="52b00-107">Note: A solution or project file may need to be specified if there are multiple.</span></span>

## <a name="synopsis"></a><span data-ttu-id="52b00-108">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="52b00-108">Synopsis</span></span>

```dotnetcli
dotnet msbuild <MSBUILD_ARGUMENTS>

dotnet msbuild -h
```

## <a name="description"></a><span data-ttu-id="52b00-109">Описание</span><span class="sxs-lookup"><span data-stu-id="52b00-109">Description</span></span>

<span data-ttu-id="52b00-110">Команда `dotnet msbuild` предоставляет доступ к полнофункциональной системе MSBuild.</span><span class="sxs-lookup"><span data-stu-id="52b00-110">The `dotnet msbuild` command allows access to a fully functional MSBuild.</span></span>

<span data-ttu-id="52b00-111">Команда имеет точно такие же возможности, как и существующий клиент с интерфейсом командной строки MSBuild только для проектов в стиле SDK.</span><span class="sxs-lookup"><span data-stu-id="52b00-111">The command has the exact same capabilities as the existing MSBuild command-line client for SDK-style projects only.</span></span> <span data-ttu-id="52b00-112">Все параметры одинаковы.</span><span class="sxs-lookup"><span data-stu-id="52b00-112">The options are all the same.</span></span> <span data-ttu-id="52b00-113">Дополнительные сведения о доступных параметрах см. в [справочнике по командной строке MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="52b00-113">For more information about the available options, see the [MSBuild command-line reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

<span data-ttu-id="52b00-114">Команда [dotnet build](dotnet-build.md) эквивалентна `dotnet msbuild -restore`.</span><span class="sxs-lookup"><span data-stu-id="52b00-114">The [dotnet build](dotnet-build.md) command is equivalent to `dotnet msbuild -restore`.</span></span> <span data-ttu-id="52b00-115">Если вы не хотите выполнять сборку проекта и у вас есть определенный целевой объект, используйте `dotnet build` или `dotnet msbuild` и укажите целевой объект.</span><span class="sxs-lookup"><span data-stu-id="52b00-115">When you don't want to build the project and you have a specific target you want to run, use `dotnet build` or `dotnet msbuild` and specify the target.</span></span>

## <a name="examples"></a><span data-ttu-id="52b00-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="52b00-116">Examples</span></span>

- <span data-ttu-id="52b00-117">Сборка проекта и его зависимостей:</span><span class="sxs-lookup"><span data-stu-id="52b00-117">Build a project and its dependencies:</span></span>

  ```dotnetcli
  dotnet msbuild
  ```

- <span data-ttu-id="52b00-118">Сборка проекта и его зависимостей с помощью конфигурации Release:</span><span class="sxs-lookup"><span data-stu-id="52b00-118">Build a project and its dependencies using Release configuration:</span></span>

  ```dotnetcli
  dotnet msbuild -property:Configuration=Release
  ```

- <span data-ttu-id="52b00-119">Запустите цель публикации и публикацию для RID `osx.10.11-x64`:</span><span class="sxs-lookup"><span data-stu-id="52b00-119">Run the publish target and publish for the `osx.10.11-x64` RID:</span></span>

  ```dotnetcli
  dotnet msbuild -target:Publish -property:RuntimeIdentifiers=osx.10.11-x64
  ```

- <span data-ttu-id="52b00-120">Весь проект со всеми целевыми объектами, включенными в пакет SDK:</span><span class="sxs-lookup"><span data-stu-id="52b00-120">See the whole project with all targets included by the SDK:</span></span>

  ```dotnetcli
  dotnet msbuild -preprocess
  dotnet msbuild -preprocess:<fileName>.xml
  ```
