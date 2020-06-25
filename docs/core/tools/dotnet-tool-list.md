---
title: Команда dotnet tool list
description: Команда dotnet tool list выводит список средств .NET Core, установленных на компьютере.
ms.date: 02/14/2020
ms.openlocfilehash: 7ca894ab0f5daf0118ff92fb39e0118b952b3d83
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768278"
---
# <a name="dotnet-tool-list"></a><span data-ttu-id="f9d4e-103">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="f9d4e-103">dotnet tool list</span></span>

<span data-ttu-id="f9d4e-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="f9d4e-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="f9d4e-105">name</span><span class="sxs-lookup"><span data-stu-id="f9d4e-105">Name</span></span>

<span data-ttu-id="f9d4e-106">`dotnet tool list` — выводит все [средства .NET Core](global-tools.md) указанного типа, установленных на компьютере в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="f9d4e-106">`dotnet tool list` - Lists all [.NET Core tools](global-tools.md) of the specified type currently installed on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="f9d4e-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="f9d4e-107">Synopsis</span></span>

```dotnetcli
dotnet tool list -g|--global

dotnet tool list --tool-path <PATH>

dotnet tool list --local

dotnet tool list

dotnet tool list -h|--help
```

## <a name="description"></a><span data-ttu-id="f9d4e-108">Описание</span><span class="sxs-lookup"><span data-stu-id="f9d4e-108">Description</span></span>

<span data-ttu-id="f9d4e-109">Команда `dotnet tool list` позволяет получить список всех установленных на компьютере глобальных, установочных и локальных средств .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f9d4e-109">The `dotnet tool list` command provides a way for you to list all .NET Core global, tool-path, or local tools installed on your machine.</span></span> <span data-ttu-id="f9d4e-110">Эта команда выводит имя пакета, установленную версию и команду средства.</span><span class="sxs-lookup"><span data-stu-id="f9d4e-110">The command lists the package name, version installed, and the tool command.</span></span>  <span data-ttu-id="f9d4e-111">Чтобы использовать эту команду, необходимо указать один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="f9d4e-111">To use the command, you specify one of the following:</span></span>

* <span data-ttu-id="f9d4e-112">Чтобы получить список глобальных средств, установленных в расположении по умолчанию, используйте параметр `--global`.</span><span class="sxs-lookup"><span data-stu-id="f9d4e-112">To list global tools installed in the default location, use the `--global` option</span></span>
* <span data-ttu-id="f9d4e-113">Чтобы получить список глобальных средств, установленных в настраиваемом расположении, используйте параметр `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="f9d4e-113">To list global tools installed in a custom location, use the `--tool-path` option.</span></span>
* <span data-ttu-id="f9d4e-114">Для перечисления локальных средств — локальное средство.</span><span class="sxs-lookup"><span data-stu-id="f9d4e-114">To list local tools, A local tool.</span></span> <span data-ttu-id="f9d4e-115">Используйте параметр `--local` или опустите параметры `--global`, `--tool-path` и `--local`.</span><span class="sxs-lookup"><span data-stu-id="f9d4e-115">use the `--local` option or omit the `--global`, `--tool-path`, and `--local` options.</span></span>

<span data-ttu-id="f9d4e-116">**Локальные средства доступны в пакете SDK для .NET Core, начиная с версии 3.0.**</span><span class="sxs-lookup"><span data-stu-id="f9d4e-116">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

## <a name="options"></a><span data-ttu-id="f9d4e-117">Параметры</span><span class="sxs-lookup"><span data-stu-id="f9d4e-117">Options</span></span>

- **`-g|--global`**

  <span data-ttu-id="f9d4e-118">Выводит глобальные средства на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="f9d4e-118">Lists user-wide global tools.</span></span> <span data-ttu-id="f9d4e-119">Не может использоваться вместе с параметром `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="f9d4e-119">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="f9d4e-120">Пропуск `--global` и `--tool-path` выводит локальные инструменты.</span><span class="sxs-lookup"><span data-stu-id="f9d4e-120">Omitting both `--global` and `--tool-path` lists local tools.</span></span>

- **`-h|--help`**

  <span data-ttu-id="f9d4e-121">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="f9d4e-121">Prints out a short help for the command.</span></span>

- **`--local`**

  <span data-ttu-id="f9d4e-122">Выдает список локальных средств для текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="f9d4e-122">Lists local tools for the current directory.</span></span> <span data-ttu-id="f9d4e-123">Не сочетается с параметрами `--global` и `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="f9d4e-123">Can't be combined with the `--global` or `--tool-path` options.</span></span> <span data-ttu-id="f9d4e-124">Если не указывать `--global` и `--tool-path`, выдает список локальных средств, даже если `--local` не заданы.</span><span class="sxs-lookup"><span data-stu-id="f9d4e-124">Omitting both `--global` and `--tool-path` lists local tools even if `--local` is not specified.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="f9d4e-125">Задает пользовательское расположение для глобальных средств.</span><span class="sxs-lookup"><span data-stu-id="f9d4e-125">Specifies a custom location where to find global tools.</span></span> <span data-ttu-id="f9d4e-126">Путь может быть абсолютным или относительным.</span><span class="sxs-lookup"><span data-stu-id="f9d4e-126">PATH can be absolute or relative.</span></span> <span data-ttu-id="f9d4e-127">Не может использоваться вместе с параметром `--global`.</span><span class="sxs-lookup"><span data-stu-id="f9d4e-127">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="f9d4e-128">Пропуск `--global` и `--tool-path` выводит локальные инструменты.</span><span class="sxs-lookup"><span data-stu-id="f9d4e-128">Omitting both `--global` and `--tool-path` lists local tools.</span></span>

## <a name="examples"></a><span data-ttu-id="f9d4e-129">Примеры</span><span class="sxs-lookup"><span data-stu-id="f9d4e-129">Examples</span></span>

- **`dotnet tool list -g`**

  <span data-ttu-id="f9d4e-130">Выводит все глобальные средства, установленные на уровне пользователя на вашем компьютере (для текущего профиля пользователя).</span><span class="sxs-lookup"><span data-stu-id="f9d4e-130">Lists all global tools installed user-wide on your machine (current user profile).</span></span>

- **`dotnet tool list --tool-path c:\global-tools`**

  <span data-ttu-id="f9d4e-131">Выводит глобальные средства в определенном каталоге Windows.</span><span class="sxs-lookup"><span data-stu-id="f9d4e-131">Lists the global tools from a specific Windows directory.</span></span>

- **`dotnet tool list --tool-path ~/bin`**

  <span data-ttu-id="f9d4e-132">Выводит глобальные средства в определенном каталоге Linux/macOS.</span><span class="sxs-lookup"><span data-stu-id="f9d4e-132">Lists the global tools from a specific Linux/macOS directory.</span></span>

- <span data-ttu-id="f9d4e-133">**`dotnet tool list`** или **`dotnet tool list --local`**</span><span class="sxs-lookup"><span data-stu-id="f9d4e-133">**`dotnet tool list`** or **`dotnet tool list --local`**</span></span>

  <span data-ttu-id="f9d4e-134">Выводит все локальные средства, доступные в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="f9d4e-134">Lists all local tools available in the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="f9d4e-135">См. также</span><span class="sxs-lookup"><span data-stu-id="f9d4e-135">See also</span></span>

- [<span data-ttu-id="f9d4e-136">Средства .NET Core</span><span class="sxs-lookup"><span data-stu-id="f9d4e-136">.NET Core tools</span></span>](global-tools.md)
- [<span data-ttu-id="f9d4e-137">Учебник. Установка и использование глобального средства .NET Core с помощью интерфейса командной строки .NET Core</span><span class="sxs-lookup"><span data-stu-id="f9d4e-137">Tutorial: Install and use a .NET Core global tool using the .NET Core CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="f9d4e-138">Учебник. Установка и использование локального средства .NET Core с помощью интерфейса командной строки .NET Core</span><span class="sxs-lookup"><span data-stu-id="f9d4e-138">Tutorial: Install and use a .NET Core local tool using the .NET Core CLI</span></span>](local-tools-how-to-use.md)
