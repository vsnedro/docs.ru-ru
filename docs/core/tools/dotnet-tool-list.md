---
title: Команда dotnet tool list
description: Команда dotnet tool list выводит список средств .NET, установленных на компьютере.
ms.date: 02/14/2020
ms.openlocfilehash: d884f2c41834dd9704de3a8ca15417ba368fde4b
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634289"
---
# <a name="dotnet-tool-list"></a><span data-ttu-id="8e5fa-103">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="8e5fa-103">dotnet tool list</span></span>

<span data-ttu-id="8e5fa-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="8e5fa-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="8e5fa-105">name</span><span class="sxs-lookup"><span data-stu-id="8e5fa-105">Name</span></span>

<span data-ttu-id="8e5fa-106">`dotnet tool list` — выводит все [средства .NET](global-tools.md) указанного типа, установленных на компьютере в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-106">`dotnet tool list` - Lists all [.NET tools](global-tools.md) of the specified type currently installed on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="8e5fa-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="8e5fa-107">Synopsis</span></span>

```dotnetcli
dotnet tool list -g|--global

dotnet tool list --tool-path <PATH>

dotnet tool list --local

dotnet tool list

dotnet tool list -h|--help
```

## <a name="description"></a><span data-ttu-id="8e5fa-108">Описание</span><span class="sxs-lookup"><span data-stu-id="8e5fa-108">Description</span></span>

<span data-ttu-id="8e5fa-109">Команда `dotnet tool list` позволяет получить список всех установленных на компьютере глобальных, установочных и локальных средств .NET.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-109">The `dotnet tool list` command provides a way for you to list all .NET global, tool-path, or local tools installed on your machine.</span></span> <span data-ttu-id="8e5fa-110">Эта команда выводит имя пакета, установленную версию и команду средства.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-110">The command lists the package name, version installed, and the tool command.</span></span>  <span data-ttu-id="8e5fa-111">Чтобы использовать эту команду, необходимо указать один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="8e5fa-111">To use the command, you specify one of the following:</span></span>

* <span data-ttu-id="8e5fa-112">Чтобы получить список глобальных средств, установленных в расположении по умолчанию, используйте параметр `--global`.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-112">To list global tools installed in the default location, use the `--global` option</span></span>
* <span data-ttu-id="8e5fa-113">Чтобы получить список глобальных средств, установленных в настраиваемом расположении, используйте параметр `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-113">To list global tools installed in a custom location, use the `--tool-path` option.</span></span>
* <span data-ttu-id="8e5fa-114">Чтобы получить список локальных средств, используйте параметр `--local` или опустите параметры `--global`, `--tool-path` и `--local`.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-114">To list local tools, use the `--local` option or omit the `--global`, `--tool-path`, and `--local` options.</span></span>

<span data-ttu-id="8e5fa-115">**Локальные средства доступны в пакете SDK для .NET Core, начиная с версии 3.0.**</span><span class="sxs-lookup"><span data-stu-id="8e5fa-115">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

## <a name="options"></a><span data-ttu-id="8e5fa-116">Параметры</span><span class="sxs-lookup"><span data-stu-id="8e5fa-116">Options</span></span>

- **`-g|--global`**

  <span data-ttu-id="8e5fa-117">Выводит глобальные средства на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-117">Lists user-wide global tools.</span></span> <span data-ttu-id="8e5fa-118">Не может использоваться вместе с параметром `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-118">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="8e5fa-119">Пропуск `--global` и `--tool-path` выводит локальные инструменты.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-119">Omitting both `--global` and `--tool-path` lists local tools.</span></span>

- **`-h|--help`**

  <span data-ttu-id="8e5fa-120">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-120">Prints out a short help for the command.</span></span>

- **`--local`**

  <span data-ttu-id="8e5fa-121">Выдает список локальных средств для текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-121">Lists local tools for the current directory.</span></span> <span data-ttu-id="8e5fa-122">Не сочетается с параметрами `--global` и `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-122">Can't be combined with the `--global` or `--tool-path` options.</span></span> <span data-ttu-id="8e5fa-123">Если не указывать `--global` и `--tool-path`, выдает список локальных средств, даже если `--local` не заданы.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-123">Omitting both `--global` and `--tool-path` lists local tools even if `--local` is not specified.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="8e5fa-124">Задает пользовательское расположение для глобальных средств.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-124">Specifies a custom location where to find global tools.</span></span> <span data-ttu-id="8e5fa-125">Путь может быть абсолютным или относительным.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-125">PATH can be absolute or relative.</span></span> <span data-ttu-id="8e5fa-126">Не может использоваться вместе с параметром `--global`.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-126">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="8e5fa-127">Пропуск `--global` и `--tool-path` выводит локальные инструменты.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-127">Omitting both `--global` and `--tool-path` lists local tools.</span></span>

## <a name="examples"></a><span data-ttu-id="8e5fa-128">Примеры</span><span class="sxs-lookup"><span data-stu-id="8e5fa-128">Examples</span></span>

- **`dotnet tool list -g`**

  <span data-ttu-id="8e5fa-129">Выводит все глобальные средства, установленные на уровне пользователя на вашем компьютере (для текущего профиля пользователя).</span><span class="sxs-lookup"><span data-stu-id="8e5fa-129">Lists all global tools installed user-wide on your machine (current user profile).</span></span>

- **`dotnet tool list --tool-path c:\global-tools`**

  <span data-ttu-id="8e5fa-130">Выводит глобальные средства в определенном каталоге Windows.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-130">Lists the global tools from a specific Windows directory.</span></span>

- **`dotnet tool list --tool-path ~/bin`**

  <span data-ttu-id="8e5fa-131">Выводит глобальные средства в определенном каталоге Linux/macOS.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-131">Lists the global tools from a specific Linux/macOS directory.</span></span>

- <span data-ttu-id="8e5fa-132">**`dotnet tool list`** или **`dotnet tool list --local`**</span><span class="sxs-lookup"><span data-stu-id="8e5fa-132">**`dotnet tool list`** or **`dotnet tool list --local`**</span></span>

  <span data-ttu-id="8e5fa-133">Выводит все локальные средства, доступные в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-133">Lists all local tools available in the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="8e5fa-134">См. также</span><span class="sxs-lookup"><span data-stu-id="8e5fa-134">See also</span></span>

- [<span data-ttu-id="8e5fa-135">Средства .NET</span><span class="sxs-lookup"><span data-stu-id="8e5fa-135">.NET tools</span></span>](global-tools.md)
- [<span data-ttu-id="8e5fa-136">Учебник. Установка и использование глобального средства .NET с помощью интерфейса командной строки .NET</span><span class="sxs-lookup"><span data-stu-id="8e5fa-136">Tutorial: Install and use a .NET global tool using the .NET CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="8e5fa-137">Учебник. Установка и использование локального средства .NET с помощью интерфейса командной строки .NET</span><span class="sxs-lookup"><span data-stu-id="8e5fa-137">Tutorial: Install and use a .NET local tool using the .NET CLI</span></span>](local-tools-how-to-use.md)
