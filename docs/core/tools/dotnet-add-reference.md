---
title: Команда dotnet add reference
description: Команду dotnet add reference удобно использовать для добавления ссылок между проектами.
ms.date: 02/14/2020
ms.openlocfilehash: b261e24ed6a9d5bd489d317d2663b1420b5c34ff
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158324"
---
# <a name="dotnet-add-reference"></a><span data-ttu-id="2b8ee-103">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="2b8ee-103">dotnet add reference</span></span>

<span data-ttu-id="2b8ee-104">**Эта статья относится к следующему:** ✔️ пакет SDK для .NET Core 2.x и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="2b8ee-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="2b8ee-105">name</span><span class="sxs-lookup"><span data-stu-id="2b8ee-105">Name</span></span>

<span data-ttu-id="2b8ee-106">`dotnet add reference` — добавляет перекрестные ссылки между проектами (P2P).</span><span class="sxs-lookup"><span data-stu-id="2b8ee-106">`dotnet add reference` - Adds project-to-project (P2P) references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="2b8ee-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="2b8ee-107">Synopsis</span></span>

```dotnetcli
dotnet add [<PROJECT>] reference [-f|--framework <FRAMEWORK>]
     [--interactive] <PROJECT_REFERENCES>

dotnet add reference -h|--help
```

## <a name="description"></a><span data-ttu-id="2b8ee-108">Описание</span><span class="sxs-lookup"><span data-stu-id="2b8ee-108">Description</span></span>

<span data-ttu-id="2b8ee-109">Команду `dotnet add reference` удобно использовать для добавления ссылок на проекты в проект.</span><span class="sxs-lookup"><span data-stu-id="2b8ee-109">The `dotnet add reference` command provides a convenient option to add project references to a project.</span></span> <span data-ttu-id="2b8ee-110">После запуска этой команды в файл проекта добавляются элементы `<ProjectReference>`.</span><span class="sxs-lookup"><span data-stu-id="2b8ee-110">After running the command, the `<ProjectReference>` elements are added to the project file.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a><span data-ttu-id="2b8ee-111">Аргументы</span><span class="sxs-lookup"><span data-stu-id="2b8ee-111">Arguments</span></span>

- **`PROJECT`**

  <span data-ttu-id="2b8ee-112">Указывает файл проекта.</span><span class="sxs-lookup"><span data-stu-id="2b8ee-112">Specifies the project file.</span></span> <span data-ttu-id="2b8ee-113">Если он не указан, команда ищет текущий каталог для него.</span><span class="sxs-lookup"><span data-stu-id="2b8ee-113">If not specified, the command searches the current directory for one.</span></span>

- **`PROJECT_REFERENCES`**

  <span data-ttu-id="2b8ee-114">Добавляемые перекрестные ссылки между проектами (P2P).</span><span class="sxs-lookup"><span data-stu-id="2b8ee-114">Project-to-project (P2P) references to add.</span></span> <span data-ttu-id="2b8ee-115">Укажите один или несколько проектов.</span><span class="sxs-lookup"><span data-stu-id="2b8ee-115">Specify one or more projects.</span></span> <span data-ttu-id="2b8ee-116">[Стандартные маски](https://en.wikipedia.org/wiki/Glob_(programming)) поддерживаются в системах на основе Unix или Linux.</span><span class="sxs-lookup"><span data-stu-id="2b8ee-116">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux-based systems.</span></span>

## <a name="options"></a><span data-ttu-id="2b8ee-117">Параметры</span><span class="sxs-lookup"><span data-stu-id="2b8ee-117">Options</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="2b8ee-118">Добавляет ссылки на проект только при ориентации на конкретную [платформу](../../standard/frameworks.md) в формате TFM.</span><span class="sxs-lookup"><span data-stu-id="2b8ee-118">Adds project references only when targeting a specific [framework](../../standard/frameworks.md) using the TFM format.</span></span>

- **`-h|--help`**

  <span data-ttu-id="2b8ee-119">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="2b8ee-119">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="2b8ee-120">Позволяет остановить команду и дождаться, пока пользователь введет данные или выполнит действие (как правило, для завершения проверки подлинности).</span><span class="sxs-lookup"><span data-stu-id="2b8ee-120">Allows the command to stop and wait for user input or action (typically used to complete authentication).</span></span> <span data-ttu-id="2b8ee-121">Доступно, начиная с пакета SDK для .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="2b8ee-121">Available since .NET Core 3.0 SDK.</span></span>

## <a name="examples"></a><span data-ttu-id="2b8ee-122">Примеры</span><span class="sxs-lookup"><span data-stu-id="2b8ee-122">Examples</span></span>

- <span data-ttu-id="2b8ee-123">Добавление ссылки на проект:</span><span class="sxs-lookup"><span data-stu-id="2b8ee-123">Add a project reference:</span></span>

  ```dotnetcli
  dotnet add app/app.csproj reference lib/lib.csproj
  ```

- <span data-ttu-id="2b8ee-124">Добавление нескольких ссылок на проекты в проект в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="2b8ee-124">Add multiple project references to the project in the current directory:</span></span>

  ```dotnetcli
  dotnet add reference lib1/lib1.csproj lib2/lib2.csproj
  ```

- <span data-ttu-id="2b8ee-125">Добавление нескольких ссылок на проект с помощью стандартной маски в Linux/Unix:</span><span class="sxs-lookup"><span data-stu-id="2b8ee-125">Add multiple project references using a globbing pattern on Linux/Unix:</span></span>

  ```dotnetcli
  dotnet add app/app.csproj reference **/*.csproj
  ```
