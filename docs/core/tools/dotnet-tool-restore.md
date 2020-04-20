---
title: Команда dotnet tool restore
description: Команда dotnet tool restore устанавливает на компьютере локальные средства .NET Core, которые доступны для текущего каталога.
ms.date: 02/14/2020
ms.openlocfilehash: a518c2d45bbe9522bddfed4bbef61b30f1ad634b
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463333"
---
# <a name="dotnet-tool-restore"></a><span data-ttu-id="db4b5-103">dotnet tool restore</span><span class="sxs-lookup"><span data-stu-id="db4b5-103">dotnet tool restore</span></span>

<span data-ttu-id="db4b5-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 3.0 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="db4b5-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="db4b5-105">name</span><span class="sxs-lookup"><span data-stu-id="db4b5-105">Name</span></span>

<span data-ttu-id="db4b5-106">`dotnet tool restore` — устанавливает на компьютере локальные средства .NET Core, которые доступны для текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="db4b5-106">`dotnet tool restore` - Installs on your machine the .NET Core local tools that are in scope for the current directory.</span></span>

## <a name="synopsis"></a><span data-ttu-id="db4b5-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="db4b5-107">Synopsis</span></span>

```dotnetcli
dotnet tool restore <PACKAGE_NAME>
    [--configfile <FILE>] [--add-source <SOURCE>]
    [tool-manifest <PATH_TO_MANIFEST_FILE>] [--disable-parallel]
    [--ignore-failed-sources] [--no-cache] [--interactive]
    [-v|--verbosity <LEVEL>]

dotnet tool restore -h|--help
```

## <a name="description"></a><span data-ttu-id="db4b5-108">Описание</span><span class="sxs-lookup"><span data-stu-id="db4b5-108">Description</span></span>

<span data-ttu-id="db4b5-109">Команда `dotnet tool restore` находит файл манифеста средства, который доступен для текущего каталога, и устанавливает перечисленные в нем средства.</span><span class="sxs-lookup"><span data-stu-id="db4b5-109">The `dotnet tool restore` command finds the tool manifest file that is in scope for the current directory and installs the tools that are listed in it.</span></span> <span data-ttu-id="db4b5-110">Сведения о файлах манифеста см. в разделе [Установка локального средства](global-tools.md#install-a-local-tool) и [Вызов локального средства](global-tools.md#invoke-a-local-tool).</span><span class="sxs-lookup"><span data-stu-id="db4b5-110">For information about manifest files, see [Install a local tool](global-tools.md#install-a-local-tool) and [Invoke a local tool](global-tools.md#invoke-a-local-tool).</span></span>

## <a name="arguments"></a><span data-ttu-id="db4b5-111">Аргументы</span><span class="sxs-lookup"><span data-stu-id="db4b5-111">Arguments</span></span>

- **`PACKAGE_NAME`**

<span data-ttu-id="db4b5-112">Имя или идентификатор пакета NuGet, который содержит устанавливаемое средство .NET Core.</span><span class="sxs-lookup"><span data-stu-id="db4b5-112">Name/ID of the NuGet package that contains the .NET Core tool to install.</span></span>

## <a name="options"></a><span data-ttu-id="db4b5-113">Параметры</span><span class="sxs-lookup"><span data-stu-id="db4b5-113">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="db4b5-114">Файл конфигурации NuGet (*nuget.config*), который будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="db4b5-114">The NuGet configuration (*nuget.config*) file to use.</span></span>

- **`--add-source <SOURCE>`**

  <span data-ttu-id="db4b5-115">Добавляет дополнительный источник пакета NuGet для использования во время установки.</span><span class="sxs-lookup"><span data-stu-id="db4b5-115">Adds an additional NuGet package source to use during installation.</span></span>

- **`--tool-manifest <PATH>`**

  <span data-ttu-id="db4b5-116">Путь к файлу манифеста.</span><span class="sxs-lookup"><span data-stu-id="db4b5-116">Path to the manifest file.</span></span>

- **`--disable-parallel`**

  <span data-ttu-id="db4b5-117">Блокирует параллельное восстановление множества проектов.</span><span class="sxs-lookup"><span data-stu-id="db4b5-117">Prevent restoring multiple projects in parallel.</span></span>

- **`--ignore-failed-sources`**

  <span data-ttu-id="db4b5-118">Обрабатывать сбои источников пакетов как предупреждения.</span><span class="sxs-lookup"><span data-stu-id="db4b5-118">Treat package source failures as warnings.</span></span>

- **`--no-cache`**

  <span data-ttu-id="db4b5-119">Не кэшировать пакеты и HTTP-запросы.</span><span class="sxs-lookup"><span data-stu-id="db4b5-119">Do not cache packages and http requests.</span></span>

- **`--interactive`**

  <span data-ttu-id="db4b5-120">Позволяет остановить команду и дождаться, пока пользователь введет данные или выполнит действие (например, завершит проверку подлинности).</span><span class="sxs-lookup"><span data-stu-id="db4b5-120">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span>

- **`-h|--help`**

  <span data-ttu-id="db4b5-121">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="db4b5-121">Prints out a short help for the command.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="db4b5-122">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="db4b5-122">Sets the verbosity level of the command.</span></span> <span data-ttu-id="db4b5-123">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="db4b5-123">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="example"></a><span data-ttu-id="db4b5-124">Пример</span><span class="sxs-lookup"><span data-stu-id="db4b5-124">Example</span></span>

- **`dotnet tool restore`**

  <span data-ttu-id="db4b5-125">Восстанавливает локальные средства для текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="db4b5-125">Restores local tools for the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="db4b5-126">См. также</span><span class="sxs-lookup"><span data-stu-id="db4b5-126">See also</span></span>

- [<span data-ttu-id="db4b5-127">Средства .NET Core</span><span class="sxs-lookup"><span data-stu-id="db4b5-127">.NET Core tools</span></span>](global-tools.md)
- [<span data-ttu-id="db4b5-128">Учебник. Установка и использование локального средства .NET Core с помощью интерфейса командной строки .NET Core</span><span class="sxs-lookup"><span data-stu-id="db4b5-128">Tutorial: Install and use a .NET Core local tool using the .NET Core CLI</span></span>](local-tools-how-to-use.md)
