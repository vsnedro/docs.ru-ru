---
title: Команда dotnet tool update
description: Команда dotnet tool update обновляет указанное средство .NET на вашем компьютере.
ms.date: 07/08/2020
ms.openlocfilehash: 18b153e53a6dbcb32e50ae4a7d06a1c2f53d1eb5
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634081"
---
# <a name="dotnet-tool-update"></a><span data-ttu-id="17d23-103">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="17d23-103">dotnet tool update</span></span>

<span data-ttu-id="17d23-104">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="17d23-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="17d23-105">name</span><span class="sxs-lookup"><span data-stu-id="17d23-105">Name</span></span>

<span data-ttu-id="17d23-106">`dotnet tool update` обновляет указанное [средство .NET](global-tools.md) на компьютере.</span><span class="sxs-lookup"><span data-stu-id="17d23-106">`dotnet tool update` - Updates the specified [.NET tool](global-tools.md) on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="17d23-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="17d23-107">Synopsis</span></span>

```dotnetcli
dotnet tool update <PACKAGE_ID> -g|--global
    [--add-source <SOURCE>] [--configfile <FILE>]
    [--disable-parallel] [--framework <FRAMEWORK>]
    [--ignore-failed-sources] [--interactive] [--no-cache]
    [-v|--verbosity <LEVEL>] [--version <VERSION>]

dotnet tool update <PACKAGE_ID> --tool-path <PATH>
    [--add-source <SOURCE>] [--configfile <FILE>]
    [--disable-parallel] [--framework <FRAMEWORK>]
    [--ignore-failed-sources] [--interactive] [--no-cache]
    [-v|--verbosity <LEVEL>] [--version <VERSION>]

dotnet tool update <PACKAGE_ID> --local
    [--add-source <SOURCE>] [--configfile <FILE>]
    [--disable-parallel] [--framework <FRAMEWORK>]
    [--ignore-failed-sources] [--interactive] [--no-cache]
    [--tool-manifest <PATH>]
    [-v|--verbosity <LEVEL>] [--version <VERSION>]

dotnet tool update -h|--help
```

## <a name="description"></a><span data-ttu-id="17d23-108">Описание</span><span class="sxs-lookup"><span data-stu-id="17d23-108">Description</span></span>

<span data-ttu-id="17d23-109">Команда `dotnet tool update` предоставляет способ обновления средства .NET на компьютере до последней стабильной версии пакета.</span><span class="sxs-lookup"><span data-stu-id="17d23-109">The `dotnet tool update` command provides a way for you to update .NET tools on your machine to the latest stable version of the package.</span></span> <span data-ttu-id="17d23-110">Команда удаляет и повторно устанавливает средство, эффективно обновляя его.</span><span class="sxs-lookup"><span data-stu-id="17d23-110">The command uninstalls and reinstalls a tool, effectively updating it.</span></span> <span data-ttu-id="17d23-111">Чтобы использовать команду, необходимо указать один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="17d23-111">To use the command, you specify one of the following options:</span></span>

* <span data-ttu-id="17d23-112">Чтобы обновить глобальное средство, установленное в расположении по умолчанию, используйте параметр `--global`</span><span class="sxs-lookup"><span data-stu-id="17d23-112">To update a global tool that was installed in the default location, use the `--global` option</span></span>
* <span data-ttu-id="17d23-113">Чтобы обновить глобальное средство, установленное в пользовательском расположении, используйте параметр `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="17d23-113">To update a global tool that was installed in a custom location, use the `--tool-path` option.</span></span>
* <span data-ttu-id="17d23-114">Чтобы обновить локальное средство, используйте параметр `--local`.</span><span class="sxs-lookup"><span data-stu-id="17d23-114">To update a local tool, use the `--local` option.</span></span>

<span data-ttu-id="17d23-115">**Локальные средства доступны в пакете SDK для .NET Core, начиная с версии 3.0.**</span><span class="sxs-lookup"><span data-stu-id="17d23-115">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

## <a name="arguments"></a><span data-ttu-id="17d23-116">Аргументы</span><span class="sxs-lookup"><span data-stu-id="17d23-116">Arguments</span></span>

- **`PACKAGE_ID`**

  <span data-ttu-id="17d23-117">Имя или идентификатор пакета NuGet, который содержит глобальное средство .NET, которое вы хотите обновить.</span><span class="sxs-lookup"><span data-stu-id="17d23-117">Name/ID of the NuGet package that contains the .NET global tool to update.</span></span> <span data-ttu-id="17d23-118">Найти имя пакета можно с помощью команды [dotnet tool list](dotnet-tool-list.md).</span><span class="sxs-lookup"><span data-stu-id="17d23-118">You can find the package name using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

## <a name="options"></a><span data-ttu-id="17d23-119">Параметры</span><span class="sxs-lookup"><span data-stu-id="17d23-119">Options</span></span>

- **`--add-source <SOURCE>`**

  <span data-ttu-id="17d23-120">Добавляет дополнительный источник пакета NuGet для использования во время установки.</span><span class="sxs-lookup"><span data-stu-id="17d23-120">Adds an additional NuGet package source to use during installation.</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="17d23-121">Файл конфигурации NuGet (*nuget.config*), который будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="17d23-121">The NuGet configuration (*nuget.config*) file to use.</span></span>

- **`--disable-parallel`**

  <span data-ttu-id="17d23-122">Блокирует параллельное восстановление множества проектов.</span><span class="sxs-lookup"><span data-stu-id="17d23-122">Prevent restoring multiple projects in parallel.</span></span>

- **`--framework <FRAMEWORK>`**

  <span data-ttu-id="17d23-123">Указывает [требуемую версию .NET Framework](../../standard/frameworks.md) для обновления средства.</span><span class="sxs-lookup"><span data-stu-id="17d23-123">Specifies the [target framework](../../standard/frameworks.md) to update the tool for.</span></span>

- **`--ignore-failed-sources`**

  <span data-ttu-id="17d23-124">Обрабатывать сбои источников пакетов как предупреждения.</span><span class="sxs-lookup"><span data-stu-id="17d23-124">Treat package source failures as warnings.</span></span>

- **`--interactive`**

  <span data-ttu-id="17d23-125">Позволяет остановить команду и дождаться, пока пользователь введет данные или выполнит действие (например, завершит проверку подлинности).</span><span class="sxs-lookup"><span data-stu-id="17d23-125">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span>

- **`--local`**

  <span data-ttu-id="17d23-126">Обновляет средство и манифест локального средства.</span><span class="sxs-lookup"><span data-stu-id="17d23-126">Update the tool and the local tool manifest.</span></span> <span data-ttu-id="17d23-127">Не может использоваться вместе с параметром `--global` или `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="17d23-127">Can't be combined with the `--global` option or the `--tool-path` option.</span></span>

- **`--no-cache`**

  <span data-ttu-id="17d23-128">Запрещает кэширование пакетов и HTTP-запросов.</span><span class="sxs-lookup"><span data-stu-id="17d23-128">Do not cache packages and HTTP requests.</span></span>

- **`--tool-manifest <PATH>`**

  <span data-ttu-id="17d23-129">Путь к файлу манифеста.</span><span class="sxs-lookup"><span data-stu-id="17d23-129">Path to the manifest file.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="17d23-130">Указывает место установки глобального средства.</span><span class="sxs-lookup"><span data-stu-id="17d23-130">Specifies the location where the global tool is installed.</span></span> <span data-ttu-id="17d23-131">Путь может быть абсолютным или относительным.</span><span class="sxs-lookup"><span data-stu-id="17d23-131">PATH can be absolute or relative.</span></span> <span data-ttu-id="17d23-132">Не может использоваться вместе с параметром `--global`.</span><span class="sxs-lookup"><span data-stu-id="17d23-132">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="17d23-133">Пропуск `--global` и `--tool-path` означает, что обновляемое средство является локальным.</span><span class="sxs-lookup"><span data-stu-id="17d23-133">Omitting both `--global` and `--tool-path` specifies that the tool to be updated is a local tool.</span></span>

- **`--version <VERSION>`**

  <span data-ttu-id="17d23-134">Диапазон версий пакета средства для обновления.</span><span class="sxs-lookup"><span data-stu-id="17d23-134">The version range of the tool package to update to.</span></span> <span data-ttu-id="17d23-135">Нельзя использовать для перехода на более ранние версии, необходимо сначала `uninstall` новые версии.</span><span class="sxs-lookup"><span data-stu-id="17d23-135">This cannot be used to downgrade versions, you must `uninstall` newer versions first.</span></span>

- **`-g|--global`**

  <span data-ttu-id="17d23-136">Указывает, что обновление предназначено для средства уровня пользователя.</span><span class="sxs-lookup"><span data-stu-id="17d23-136">Specifies that the update is for a user-wide tool.</span></span> <span data-ttu-id="17d23-137">Не может использоваться вместе с параметром `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="17d23-137">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="17d23-138">Пропуск `--global` и `--tool-path` означает, что обновляемое средство является локальным.</span><span class="sxs-lookup"><span data-stu-id="17d23-138">Omitting both `--global` and `--tool-path` specifies that the tool to be updated is a local tool.</span></span>

- **`-h|--help`**

  <span data-ttu-id="17d23-139">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="17d23-139">Prints out a short help for the command.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="17d23-140">Задает уровень детализации команды.</span><span class="sxs-lookup"><span data-stu-id="17d23-140">Sets the verbosity level of the command.</span></span> <span data-ttu-id="17d23-141">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="17d23-141">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="17d23-142">Примеры</span><span class="sxs-lookup"><span data-stu-id="17d23-142">Examples</span></span>

- **`dotnet tool update -g dotnetsay`**

  <span data-ttu-id="17d23-143">Обновляет глобальное средство [dotnetsay](https://www.nuget.org/packages/dotnetsay/).</span><span class="sxs-lookup"><span data-stu-id="17d23-143">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool.</span></span>

- **`dotnet tool update dotnetsay --tool-path c:\global-tools`**

  <span data-ttu-id="17d23-144">Обновляет глобальное средство [dotnetsay](https://www.nuget.org/packages/dotnetsay/), расположенное в определенном каталоге Windows.</span><span class="sxs-lookup"><span data-stu-id="17d23-144">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool located in a specific Windows directory.</span></span>

- **`dotnet tool update dotnetsay --tool-path ~/bin`**

  <span data-ttu-id="17d23-145">Обновляет глобальное средство [dotnetsay](https://www.nuget.org/packages/dotnetsay/), расположенное в определенном каталоге Linux/macOS.</span><span class="sxs-lookup"><span data-stu-id="17d23-145">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool located in a specific Linux/macOS directory.</span></span>

- **`dotnet tool update dotnetsay`**

  <span data-ttu-id="17d23-146">Обновляет локальное средство [dotnetsay](https://www.nuget.org/packages/dotnetsay/), установленное для текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="17d23-146">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) local tool installed for the current directory.</span></span>

- **`dotnet tool update -g dotnetsay --version 2.0.*`**

  <span data-ttu-id="17d23-147">Обновляет глобальное средство [dotnetsay](https://www.nuget.org/packages/dotnetsay/) до последней версии исправления с основным номером версии `2` и дополнительным номером версии `0`.</span><span class="sxs-lookup"><span data-stu-id="17d23-147">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool to the latest patch version, with a major version of `2`, and a minor version of `0`.</span></span>

- **`dotnet tool update -g dotnetsay --version (2.0.*,2.1.4)`**

  <span data-ttu-id="17d23-148">Обновляет глобальное средство [dotnetsay](https://www.nuget.org/packages/dotnetsay/) до самой низкой версии в указанном диапазоне `(> 2.0.0 && < 2.1.4)`. Будет установлена версия `2.1.0`.</span><span class="sxs-lookup"><span data-stu-id="17d23-148">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool to the lowest version within the specified range `(> 2.0.0 && < 2.1.4)`, version `2.1.0` would be installed.</span></span> <span data-ttu-id="17d23-149">Дополнительные сведения о семантических диапазонах версий см. в разделе [Диапазоны версий пакетов NuGet](/nuget/concepts/package-versioning#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="17d23-149">For more information on semantic versioning ranges, see [NuGet packaging version ranges](/nuget/concepts/package-versioning#version-ranges).</span></span>

## <a name="see-also"></a><span data-ttu-id="17d23-150">См. также</span><span class="sxs-lookup"><span data-stu-id="17d23-150">See also</span></span>

- [<span data-ttu-id="17d23-151">Средства .NET</span><span class="sxs-lookup"><span data-stu-id="17d23-151">.NET tools</span></span>](global-tools.md)
- [<span data-ttu-id="17d23-152">Семантическое управление версиями</span><span class="sxs-lookup"><span data-stu-id="17d23-152">Semantic versioning</span></span>](https://semver.org)
- [<span data-ttu-id="17d23-153">Учебник. Установка и использование глобального средства .NET с помощью интерфейса командной строки .NET</span><span class="sxs-lookup"><span data-stu-id="17d23-153">Tutorial: Install and use a .NET global tool using the .NET CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="17d23-154">Учебник. Установка и использование локального средства .NET с помощью интерфейса командной строки .NET</span><span class="sxs-lookup"><span data-stu-id="17d23-154">Tutorial: Install and use a .NET local tool using the .NET CLI</span></span>](local-tools-how-to-use.md)
