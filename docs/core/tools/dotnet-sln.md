---
title: Команда dotnet sln
description: Команда dotnet-sln предоставляет удобный способ добавлять проекты в файл решений, удалять или перечислять их.
ms.date: 02/14/2020
ms.openlocfilehash: 898c53772a28b8cc3b65532dfc3d9bd6e73d467c
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634374"
---
# <a name="dotnet-sln"></a><span data-ttu-id="cbf11-103">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="cbf11-103">dotnet sln</span></span>

<span data-ttu-id="cbf11-104">**Эта статья относится к следующему:** ✔️ пакет SDK для .NET Core 2.x и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="cbf11-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="cbf11-105">name</span><span class="sxs-lookup"><span data-stu-id="cbf11-105">Name</span></span>

<span data-ttu-id="cbf11-106">`dotnet sln` — перечисляет или изменяет проекты в файле решения .NET.</span><span class="sxs-lookup"><span data-stu-id="cbf11-106">`dotnet sln` - Lists or modifies the projects in a .NET solution file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="cbf11-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="cbf11-107">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] [command]

dotnet sln [command] -h|--help
```

## <a name="description"></a><span data-ttu-id="cbf11-108">Описание</span><span class="sxs-lookup"><span data-stu-id="cbf11-108">Description</span></span>

<span data-ttu-id="cbf11-109">Команда `dotnet sln` предоставляет удобный способ перечислять и изменять проекты в файле решений.</span><span class="sxs-lookup"><span data-stu-id="cbf11-109">The `dotnet sln` command provides a convenient way to list and modify projects in a solution file.</span></span>

<span data-ttu-id="cbf11-110">Для использования команды `dotnet sln` файл решения должен уже существовать.</span><span class="sxs-lookup"><span data-stu-id="cbf11-110">To use the `dotnet sln` command, the solution file must already exist.</span></span> <span data-ttu-id="cbf11-111">Если необходимо создать его, используйте команду [dotnet new](dotnet-new.md), как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="cbf11-111">If you need to create one, use the [dotnet new](dotnet-new.md) command, as in the following example:</span></span>

```dotnetcli
dotnet new sln
```

## <a name="arguments"></a><span data-ttu-id="cbf11-112">Аргументы</span><span class="sxs-lookup"><span data-stu-id="cbf11-112">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="cbf11-113">Используемый файл решений.</span><span class="sxs-lookup"><span data-stu-id="cbf11-113">The solution file to use.</span></span> <span data-ttu-id="cbf11-114">Если этот аргумент упущен, команда ищет текущий каталог для него.</span><span class="sxs-lookup"><span data-stu-id="cbf11-114">If this argument is omitted, the command searches the current directory for one.</span></span> <span data-ttu-id="cbf11-115">Если файл решения или несколько файлов решения не найдены, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="cbf11-115">If it finds no solution file or multiple solution files, the command fails.</span></span>

## <a name="options"></a><span data-ttu-id="cbf11-116">Параметры</span><span class="sxs-lookup"><span data-stu-id="cbf11-116">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="cbf11-117">Выводит описание использования команды.</span><span class="sxs-lookup"><span data-stu-id="cbf11-117">Prints out a description of how to use the command.</span></span>

## <a name="commands"></a><span data-ttu-id="cbf11-118">Команды</span><span class="sxs-lookup"><span data-stu-id="cbf11-118">Commands</span></span>

### `list`

<span data-ttu-id="cbf11-119">Перечисляет все проекты в файле решения.</span><span class="sxs-lookup"><span data-stu-id="cbf11-119">Lists all projects in a solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="cbf11-120">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="cbf11-120">Synopsis</span></span>

```dotnetcli
dotnet sln list [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="cbf11-121">Аргументы</span><span class="sxs-lookup"><span data-stu-id="cbf11-121">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="cbf11-122">Используемый файл решений.</span><span class="sxs-lookup"><span data-stu-id="cbf11-122">The solution file to use.</span></span> <span data-ttu-id="cbf11-123">Если этот аргумент упущен, команда ищет текущий каталог для него.</span><span class="sxs-lookup"><span data-stu-id="cbf11-123">If this argument is omitted, the command searches the current directory for one.</span></span> <span data-ttu-id="cbf11-124">Если файл решения или несколько файлов решения не найдены, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="cbf11-124">If it finds no solution file or multiple solution files, the command fails.</span></span>

#### <a name="options"></a><span data-ttu-id="cbf11-125">Параметры</span><span class="sxs-lookup"><span data-stu-id="cbf11-125">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="cbf11-126">Выводит описание использования команды.</span><span class="sxs-lookup"><span data-stu-id="cbf11-126">Prints out a description of how to use the command.</span></span>
  
### `add`

<span data-ttu-id="cbf11-127">Добавление проектов в файл решения.</span><span class="sxs-lookup"><span data-stu-id="cbf11-127">Adds one or more projects to the solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="cbf11-128">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="cbf11-128">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] add [--in-root] [-s|--solution-folder <PATH>] <PROJECT_PATH> [<PROJECT_PATH>...]
dotnet sln add [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="cbf11-129">Аргументы</span><span class="sxs-lookup"><span data-stu-id="cbf11-129">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="cbf11-130">Используемый файл решений.</span><span class="sxs-lookup"><span data-stu-id="cbf11-130">The solution file to use.</span></span> <span data-ttu-id="cbf11-131">Если он не указан, команда ищет его в текущем каталоге и завершается ошибкой, если имеется несколько файлов решения.</span><span class="sxs-lookup"><span data-stu-id="cbf11-131">If it is unspecified, the command searches the current directory for one and fails if there are multiple solution files.</span></span>

- **`PROJECT_PATH`**

  <span data-ttu-id="cbf11-132">Путь к проекту или проектам, который необходимо добавить в решение.</span><span class="sxs-lookup"><span data-stu-id="cbf11-132">The path to the project or projects to add to the solution.</span></span> <span data-ttu-id="cbf11-133">Расширения [стандартной маски](https://en.wikipedia.org/wiki/Glob_(programming)) оболочки Unix/Linux правильно обрабатываются командой `dotnet sln`.</span><span class="sxs-lookup"><span data-stu-id="cbf11-133">Unix/Linux shell [globbing pattern](https://en.wikipedia.org/wiki/Glob_(programming)) expansions are processed correctly by the `dotnet sln` command.</span></span>

#### <a name="options"></a><span data-ttu-id="cbf11-134">Параметры</span><span class="sxs-lookup"><span data-stu-id="cbf11-134">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="cbf11-135">Выводит описание использования команды.</span><span class="sxs-lookup"><span data-stu-id="cbf11-135">Prints out a description of how to use the command.</span></span>

- **`--in-root`**

  <span data-ttu-id="cbf11-136">Поместите проекты в корень решения, и вам не нужно будет создавать папку решения.</span><span class="sxs-lookup"><span data-stu-id="cbf11-136">Places the projects in the root of the solution, rather than creating a solution folder.</span></span> <span data-ttu-id="cbf11-137">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="cbf11-137">Available since .NET Core 3.0 SDK.</span></span>

- **`-s|--solution-folder <PATH>`**

  <span data-ttu-id="cbf11-138">Путь к папке назначения решения, в которую будут добавлены проекты.</span><span class="sxs-lookup"><span data-stu-id="cbf11-138">The destination solution folder path to add the projects to.</span></span> <span data-ttu-id="cbf11-139">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="cbf11-139">Available since .NET Core 3.0 SDK.</span></span>

### `remove`

<span data-ttu-id="cbf11-140">Удаляет один или несколько проектов из файла решений.</span><span class="sxs-lookup"><span data-stu-id="cbf11-140">Removes a project or multiple projects from the solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="cbf11-141">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="cbf11-141">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] remove <PROJECT_PATH> [<PROJECT_PATH>...]
dotnet sln [<SOLUTION_FILE>] remove [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="cbf11-142">Аргументы</span><span class="sxs-lookup"><span data-stu-id="cbf11-142">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="cbf11-143">Используемый файл решений.</span><span class="sxs-lookup"><span data-stu-id="cbf11-143">The solution file to use.</span></span> <span data-ttu-id="cbf11-144">Если он не указан, команда ищет его в текущем каталоге и завершается ошибкой, если имеется несколько файлов решения.</span><span class="sxs-lookup"><span data-stu-id="cbf11-144">If is left unspecified, the command searches the current directory for one and fails if there are multiple solution files.</span></span>

- **`PROJECT_PATH`**

  <span data-ttu-id="cbf11-145">Путь к проекту или проектам, который необходимо добавить в решение.</span><span class="sxs-lookup"><span data-stu-id="cbf11-145">The path to the project or projects to add to the solution.</span></span> <span data-ttu-id="cbf11-146">Расширения [стандартной маски](https://en.wikipedia.org/wiki/Glob_(programming)) оболочки Unix/Linux правильно обрабатываются командой `dotnet sln`.</span><span class="sxs-lookup"><span data-stu-id="cbf11-146">Unix/Linux shell [globbing pattern](https://en.wikipedia.org/wiki/Glob_(programming)) expansions are processed correctly by the `dotnet sln` command.</span></span>

#### <a name="options"></a><span data-ttu-id="cbf11-147">Параметры</span><span class="sxs-lookup"><span data-stu-id="cbf11-147">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="cbf11-148">Выводит описание использования команды.</span><span class="sxs-lookup"><span data-stu-id="cbf11-148">Prints out a description of how to use the command.</span></span>

## <a name="examples"></a><span data-ttu-id="cbf11-149">Примеры</span><span class="sxs-lookup"><span data-stu-id="cbf11-149">Examples</span></span>

- <span data-ttu-id="cbf11-150">Перечисление проектов в решении:</span><span class="sxs-lookup"><span data-stu-id="cbf11-150">List the projects in a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln list
  ```

- <span data-ttu-id="cbf11-151">Добавление проекта C# в решение:</span><span class="sxs-lookup"><span data-stu-id="cbf11-151">Add a C# project to a solution:</span></span>

  ```dotnetcli
  dotnet sln add todo-app/todo-app.csproj
  ```

- <span data-ttu-id="cbf11-152">Удаление проекта C# из решения:</span><span class="sxs-lookup"><span data-stu-id="cbf11-152">Remove a C# project from a solution:</span></span>

  ```dotnetcli
  dotnet sln remove todo-app/todo-app.csproj
  ```

- <span data-ttu-id="cbf11-153">Добавление нескольких проектов C# в корень решения:</span><span class="sxs-lookup"><span data-stu-id="cbf11-153">Add multiple C# projects to the root of a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj --in-root
  ```

- <span data-ttu-id="cbf11-154">Добавление нескольких проектов C# в решение:</span><span class="sxs-lookup"><span data-stu-id="cbf11-154">Add multiple C# projects to a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- <span data-ttu-id="cbf11-155">Удаление нескольких проектов C# из решения:</span><span class="sxs-lookup"><span data-stu-id="cbf11-155">Remove multiple C# projects from a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- <span data-ttu-id="cbf11-156">Добавление нескольких проектов C# в решение с помощью стандартной маски (только Unix/Linux):</span><span class="sxs-lookup"><span data-stu-id="cbf11-156">Add multiple C# projects to a solution using a globbing pattern (Unix/Linux only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln add **/*.csproj
  ```

- <span data-ttu-id="cbf11-157">Добавление нескольких проектов C# в решение с помощью стандартной маски (только Windows PowerShell):</span><span class="sxs-lookup"><span data-stu-id="cbf11-157">Add multiple C# projects to a solution using a globbing pattern (Windows PowerShell only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln add (ls -r **/*.csproj)
  ```

- <span data-ttu-id="cbf11-158">Удаление нескольких проектов C# из решения с помощью стандартной маски (только Unix/Linux):</span><span class="sxs-lookup"><span data-stu-id="cbf11-158">Remove multiple C# projects from a solution using a globbing pattern (Unix/Linux only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln remove **/*.csproj
  ```

- <span data-ttu-id="cbf11-159">Удаление нескольких проектов C# из решения с помощью стандартной маски (только Windows PowerShell):</span><span class="sxs-lookup"><span data-stu-id="cbf11-159">Remove multiple C# projects from a solution using a globbing pattern (Windows PowerShell only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln remove (ls -r **/*.csproj)
  ```
