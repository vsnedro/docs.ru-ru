---
title: Средство удаления
description: Обзор средства удаления .NET Core — интерактивного средства, позволяющего управлять очисткой пакетов SDK и сред выполнения .NET Core.
author: sfoslund
ms.date: 05/27/2020
ms.openlocfilehash: 4e70fd3438b582bd5a0d6a52d7e58ed5e07f8811
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2020
ms.locfileid: "84446910"
---
# <a name="net-core-uninstall-tool"></a><span data-ttu-id="3fda4-103">Средство удаления .NET Core</span><span class="sxs-lookup"><span data-stu-id="3fda4-103">.NET Core Uninstall Tool</span></span>

<span data-ttu-id="3fda4-104">[Средство удаления .NET Core](https://aka.ms/dotnet-core-uninstall-tool) (`dotnet-core-uninstall`) позволяет удалять пакеты SDK и среды выполнения .NET Core из системы.</span><span class="sxs-lookup"><span data-stu-id="3fda4-104">The [.NET Core Uninstall Tool](https://aka.ms/dotnet-core-uninstall-tool) (`dotnet-core-uninstall`) lets you remove .NET Core SDKs and Runtimes from a system.</span></span> <span data-ttu-id="3fda4-105">Указать версии, которые нужно удалить, можно с помощью ряда параметров.</span><span class="sxs-lookup"><span data-stu-id="3fda4-105">A collection of options is available to specify which versions you want to uninstall.</span></span>

<span data-ttu-id="3fda4-106">Это средство поддерживают ОС Windows и macOS.</span><span class="sxs-lookup"><span data-stu-id="3fda4-106">The tool supports Windows and macOS.</span></span> <span data-ttu-id="3fda4-107">ОС Linux сейчас не поддерживает это средство.</span><span class="sxs-lookup"><span data-stu-id="3fda4-107">Linux is currently not supported.</span></span>

<span data-ttu-id="3fda4-108">В ОС Windows средство может удалять только пакеты SDK и среды выполнения, установленные с помощью одного из следующих установщиков:</span><span class="sxs-lookup"><span data-stu-id="3fda4-108">On Windows, the tool can only uninstall SDKs and Runtimes that were installed using one of the following installers:</span></span>

- <span data-ttu-id="3fda4-109">установщик сред выполнения и пакетов SDK для .NET Core;</span><span class="sxs-lookup"><span data-stu-id="3fda4-109">The .NET Core SDK and runtime installer.</span></span>
- <span data-ttu-id="3fda4-110">установщик Visual Studio более ранних версий, чем Visual Studio 2019 версии 16.3.</span><span class="sxs-lookup"><span data-stu-id="3fda4-110">The Visual Studio installer in versions earlier than Visual Studio 2019 version 16.3.</span></span>

<span data-ttu-id="3fda4-111">В macOS средство может удалять только пакеты SDK и среды выполнения, расположенные в папке */usr/local/share/dotnet*.</span><span class="sxs-lookup"><span data-stu-id="3fda4-111">On macOS, the tool can only uninstall SDKs and runtimes located in the */usr/local/share/dotnet* folder.</span></span>

<span data-ttu-id="3fda4-112">Из-за этих ограничений средство не сможет удалить все пакеты SDK и среды выполнения .NET Core на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3fda4-112">Because of these limitations, the tool may not be able to uninstall all of the .NET Core SDKs and runtimes on your machine.</span></span> <span data-ttu-id="3fda4-113">Вы можете использовать команду `dotnet --info`, чтобы найти все установленные пакеты SDK и среды выполнения .NET Core, в том числе те, которые не удается удалить с помощью этого средства.</span><span class="sxs-lookup"><span data-stu-id="3fda4-113">You can use the `dotnet --info` command to find all of the .NET Core SDKs and runtimes installed, including those SDKs and runtimes that this tool can't remove.</span></span> <span data-ttu-id="3fda4-114">Команда `dotnet-core-uninstall list` позволяет просмотреть, какие пакеты SDK можно удалить с помощью средства.</span><span class="sxs-lookup"><span data-stu-id="3fda4-114">The `dotnet-core-uninstall list` command displays which SDKs can be uninstalled with the tool.</span></span>

## <a name="install-the-tool"></a><span data-ttu-id="3fda4-115">Установка средства</span><span class="sxs-lookup"><span data-stu-id="3fda4-115">Install the tool</span></span>

<span data-ttu-id="3fda4-116">Средство удаления .NET Core можно скачать по [этой ссылке](https://aka.ms/dotnet-core-uninstall-tool), а его исходный код доступен в репозитории GitHub [dotnet/cli-lab](https://github.com/dotnet/cli-lab).</span><span class="sxs-lookup"><span data-stu-id="3fda4-116">You can download the .NET Core Uninstall Tool from [here](https://aka.ms/dotnet-core-uninstall-tool) and find the source code at the [dotnet/cli-lab](https://github.com/dotnet/cli-lab) GitHub repository.</span></span>

> [!NOTE]
> <span data-ttu-id="3fda4-117">Для удаления пакетов SDK и сред выполнения .NET Core средству требуются повышенные права.</span><span class="sxs-lookup"><span data-stu-id="3fda4-117">The tool requires elevation to uninstall .NET Core SDKs and runtimes.</span></span> <span data-ttu-id="3fda4-118">Следовательно, его нужно устанавливать в защищенном от записи каталоге, например *C:\Program Files* в ОС Windows или */usr/local/bin* в macOS.</span><span class="sxs-lookup"><span data-stu-id="3fda4-118">Therefore, it should be installed in a write-protected directory such as *C:\Program Files* on Windows or */usr/local/bin* on macOS.</span></span> <span data-ttu-id="3fda4-119">Ознакомьтесь также со статьей [Повышенные права доступа для команд dotnet](../tools/elevated-access.md).</span><span class="sxs-lookup"><span data-stu-id="3fda4-119">See also [Elevated access for dotnet commands](../tools/elevated-access.md).</span></span> <span data-ttu-id="3fda4-120">Дополнительные сведения см. в [подробных инструкциях по установке](https://aka.ms/dotnet-core-uninstall-tool).</span><span class="sxs-lookup"><span data-stu-id="3fda4-120">For more information, see the [detailed installation instructions](https://aka.ms/dotnet-core-uninstall-tool).</span></span>

## <a name="run-the-tool"></a><span data-ttu-id="3fda4-121">Запуск программы</span><span class="sxs-lookup"><span data-stu-id="3fda4-121">Run the tool</span></span>

<span data-ttu-id="3fda4-122">Шаги ниже демонстрируют рекомендуемый подход к работе со средством удаления.</span><span class="sxs-lookup"><span data-stu-id="3fda4-122">The following steps show the recommended approach for running the uninstall tool:</span></span>

- [<span data-ttu-id="3fda4-123">Шаг 1. Отображение установленных пакетов SDK и сред выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="3fda4-123">Step 1 - Display installed .NET Core SDKs and runtimes</span></span>](#step-1---display-installed-net-core-sdks-and-runtimes)
- [<span data-ttu-id="3fda4-124">Шаг 2. Пробный запуск</span><span class="sxs-lookup"><span data-stu-id="3fda4-124">Step 2 - Do a dry run</span></span>](#step-2---do-a-dry-run)
- [<span data-ttu-id="3fda4-125">Шаг 3. Удаление пакетов SDK и сред выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="3fda4-125">Step 3 - Uninstall .NET Core SDKs and Runtimes</span></span>](#step-3---uninstall-net-core-sdks-and-runtimes)
- [<span data-ttu-id="3fda4-126">Шаг 4. Удаление резервной папки NuGet (необязательный)</span><span class="sxs-lookup"><span data-stu-id="3fda4-126">Step 4 - Delete the NuGet fallback folder (optional)</span></span>](#step-4---delete-the-nuget-fallback-folder-optional)

### <a name="step-1---display-installed-net-core-sdks-and-runtimes"></a><span data-ttu-id="3fda4-127">Шаг 1. Отображение установленных пакетов SDK и сред выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="3fda4-127">Step 1 - Display installed .NET Core SDKs and runtimes</span></span>

<span data-ttu-id="3fda4-128">Команда `dotnet-core-uninstall list` перечисляет установленные пакеты SDK и среды выполнения .NET Core, которые можно удалить с помощью этого средства.</span><span class="sxs-lookup"><span data-stu-id="3fda4-128">The `dotnet-core-uninstall list` command lists the installed .NET Core SDKs and runtimes that can be removed with this tool.</span></span> <span data-ttu-id="3fda4-129">Некоторые пакеты SDK и среды выполнения могут требоваться для работы Visual Studio, и они отображаются с предупреждением о том, почему их не рекомендуется удалять.</span><span class="sxs-lookup"><span data-stu-id="3fda4-129">Some SDKs and runtimes may be required by Visual Studio and they're displayed with a note of why it isn't recommended to uninstall them.</span></span>

> [!NOTE]
> <span data-ttu-id="3fda4-130">В большинстве случаев выходные данные команды `dotnet-core-uninstall list` не будут соответствовать списку установленных версий в выходных данных `dotnet --info`.</span><span class="sxs-lookup"><span data-stu-id="3fda4-130">The output of the `dotnet-core-uninstall list` command will not match the list of installed versions in the output of `dotnet --info` in most cases.</span></span> <span data-ttu-id="3fda4-131">В частности, это средство не будет отображать версии, установленные ZIP-файлами или управляемые Visual Studio (любая версия, установленная с Visual Studio 2019 версии 16.3 или более поздней версии).</span><span class="sxs-lookup"><span data-stu-id="3fda4-131">Specifically, this tool will not display versions installed by zip files or managed by Visual Studio (any version installed with Visual Studio 2019 16.3 or later).</span></span> <span data-ttu-id="3fda4-132">Один из способов проверить, находится ли версия под управлением Visual Studio, — просмотреть ее в `Add or Remove Programs`, в которой управляемые версии Visual Studio помечены в отображаемых именах.</span><span class="sxs-lookup"><span data-stu-id="3fda4-132">One way to check if a version is managed by Visual Studio is to view it in `Add or Remove Programs`, where Visual Studio managed versions are marked as such in their display names.</span></span>

<span data-ttu-id="3fda4-133">**dotnet-core-uninstall list**</span><span class="sxs-lookup"><span data-stu-id="3fda4-133">**dotnet-core-uninstall list**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="3fda4-134">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="3fda4-134">Synopsis</span></span>

```console
dotnet-core-uninstall list [options]
```

#### <a name="options"></a><span data-ttu-id="3fda4-135">Параметры</span><span class="sxs-lookup"><span data-stu-id="3fda4-135">Options</span></span>

## <a name="windows"></a>[<span data-ttu-id="3fda4-136">Windows</span><span class="sxs-lookup"><span data-stu-id="3fda4-136">Windows</span></span>](#tab/windows)

* **`--aspnet-runtime`**

  <span data-ttu-id="3fda4-137">Перечисляет все среды выполнения ASP.NET Core, которые можно удалить с помощью этого средства.</span><span class="sxs-lookup"><span data-stu-id="3fda4-137">Lists all the ASP.NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="3fda4-138">Перечисляет все пакеты размещения .NET Core, которые можно удалить с помощью этого средства.</span><span class="sxs-lookup"><span data-stu-id="3fda4-138">Lists all the .NET Core hosting bundles that can be uninstalled with this tool.</span></span>

* **`--runtime`**

  <span data-ttu-id="3fda4-139">Перечисляет все среды выполнения .NET Core, которые можно удалить с помощью этого средства.</span><span class="sxs-lookup"><span data-stu-id="3fda4-139">Lists all .NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--sdk`**

  <span data-ttu-id="3fda4-140">Перечисляет все пакеты SDK для .NET Core, которые можно удалить с помощью этого средства.</span><span class="sxs-lookup"><span data-stu-id="3fda4-140">Lists all .NET Core SDKs that can be uninstalled with this tool.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="3fda4-141">Устанавливает уровень детализации.</span><span class="sxs-lookup"><span data-stu-id="3fda4-141">Sets the verbosity level.</span></span> <span data-ttu-id="3fda4-142">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="3fda4-142">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="3fda4-143">Значение по умолчанию — `normal`.</span><span class="sxs-lookup"><span data-stu-id="3fda4-143">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="3fda4-144">Перечисляет все пакеты SDK и среды выполнения .NET Core x64, которые можно удалить с помощью этого средства.</span><span class="sxs-lookup"><span data-stu-id="3fda4-144">Lists all x64 .NET Core SDKs and runtimes that can be uninstalled with this tool.</span></span>

* **`--x86`**

  <span data-ttu-id="3fda4-145">Перечисляет все пакеты SDK и среды выполнения .NET Core x86, которые можно удалить с помощью этого средства.</span><span class="sxs-lookup"><span data-stu-id="3fda4-145">Lists all x86 .NET Core SDKs and runtimes that can be uninstalled with this tool.</span></span>

## <a name="macos"></a>[<span data-ttu-id="3fda4-146">macOS</span><span class="sxs-lookup"><span data-stu-id="3fda4-146">macOS</span></span>](#tab/macos)

* **`--runtime`**

  <span data-ttu-id="3fda4-147">Перечисляет все среды выполнения .NET Core, которые можно удалить с помощью этого средства.</span><span class="sxs-lookup"><span data-stu-id="3fda4-147">Lists all .NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--sdk`**

  <span data-ttu-id="3fda4-148">Перечисляет все пакеты SDK для .NET Core, которые можно удалить с помощью этого средства.</span><span class="sxs-lookup"><span data-stu-id="3fda4-148">Lists all .NET Core SDKs that can be uninstalled with this tool.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="3fda4-149">Устанавливает уровень детализации.</span><span class="sxs-lookup"><span data-stu-id="3fda4-149">Sets the verbosity level.</span></span> <span data-ttu-id="3fda4-150">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="3fda4-150">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="3fda4-151">Значение по умолчанию — `normal`.</span><span class="sxs-lookup"><span data-stu-id="3fda4-151">The default value is `normal`.</span></span>
  
---

#### <a name="examples"></a><span data-ttu-id="3fda4-152">Примеры</span><span class="sxs-lookup"><span data-stu-id="3fda4-152">Examples</span></span>

* <span data-ttu-id="3fda4-153">Перечисление всех пакетов SDK и сред выполнения .NET Core, которые можно удалить с помощью этого средства:</span><span class="sxs-lookup"><span data-stu-id="3fda4-153">List all .NET Core SDKs and runtimes that can be removed with this tool:</span></span>

  ```console
  dotnet-core-uninstall list
  ```

* <span data-ttu-id="3fda4-154">Перечисление всех пакетов SDK и сред выполнения .NET Core x64:</span><span class="sxs-lookup"><span data-stu-id="3fda4-154">List all x64 .NET Core SDKs and runtimes:</span></span>

  ```console
  dotnet-core-uninstall list --x64
  ```

* <span data-ttu-id="3fda4-155">Перечисление всех пакетов SDK для .NET Core x86:</span><span class="sxs-lookup"><span data-stu-id="3fda4-155">List all x86 .NET Core SDKs:</span></span>

  ```console
  dotnet-core-uninstall list --sdk --x86
  ```

### <a name="step-2---do-a-dry-run"></a><span data-ttu-id="3fda4-156">Шаг 2. Пробный запуск</span><span class="sxs-lookup"><span data-stu-id="3fda4-156">Step 2 - Do a dry run</span></span>

<span data-ttu-id="3fda4-157">Команды `dotnet-core-uninstall dry-run` и `dotnet-core-uninstall whatif` позволяют просмотреть пакеты SDK и среды выполнения .NET Core, которые будут удалены, на основе указанных параметров без выполнения удаления.</span><span class="sxs-lookup"><span data-stu-id="3fda4-157">The `dotnet-core-uninstall dry-run` and `dotnet-core-uninstall whatif` commands display the .NET Core SDKs and runtimes that will be removed based on the options provided without performing the uninstall.</span></span> <span data-ttu-id="3fda4-158">Эти синонимичные команды.</span><span class="sxs-lookup"><span data-stu-id="3fda4-158">These commands are synonyms.</span></span>

<span data-ttu-id="3fda4-159">**dotnet-core-uninstall dry-run and dotnet-core-uninstall whatif**</span><span class="sxs-lookup"><span data-stu-id="3fda4-159">**dotnet-core-uninstall dry-run and dotnet-core-uninstall whatif**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="3fda4-160">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="3fda4-160">Synopsis</span></span>

```console
dotnet-core-uninstall dry-run [options] [<VERSION>...]

dotnet-core-uninstall whatif [options] [<VERSION>...]
```

#### <a name="arguments"></a><span data-ttu-id="3fda4-161">Аргументы</span><span class="sxs-lookup"><span data-stu-id="3fda4-161">Arguments</span></span>

* **`VERSION`**

  <span data-ttu-id="3fda4-162">Указанная версия для удаления.</span><span class="sxs-lookup"><span data-stu-id="3fda4-162">The specified version to uninstall.</span></span> <span data-ttu-id="3fda4-163">Вы можете перечислить несколько версий одну за другой, разделяя их пробелами.</span><span class="sxs-lookup"><span data-stu-id="3fda4-163">You may list several versions one after the other, separated by spaces.</span></span> <span data-ttu-id="3fda4-164">Поддерживаются также файлы ответов.</span><span class="sxs-lookup"><span data-stu-id="3fda4-164">Response files are also supported.</span></span>

  > [!TIP]
  > <span data-ttu-id="3fda4-165">Файлы ответов можно использовать вместо того, чтобы указывать все версии в командной строке.</span><span class="sxs-lookup"><span data-stu-id="3fda4-165">Response files are an alternative to placing all the versions on the command line.</span></span>
  > <span data-ttu-id="3fda4-166">Это текстовые файлы, обычно с расширением \*.rsp. Каждая версия указывается в отдельной строке.</span><span class="sxs-lookup"><span data-stu-id="3fda4-166">They're text files, typically with a \*.rsp extension, and each version is listed on a separate line.</span></span>
  > <span data-ttu-id="3fda4-167">Чтобы указать файл ответов для аргумента `VERSION`, используйте символ \@ сразу после имени файла ответа.</span><span class="sxs-lookup"><span data-stu-id="3fda4-167">To specify a response file for the `VERSION` argument, use the \@ character immediately followed by the response file name.</span></span>

#### <a name="options"></a><span data-ttu-id="3fda4-168">Параметры</span><span class="sxs-lookup"><span data-stu-id="3fda4-168">Options</span></span>

## <a name="windows"></a>[<span data-ttu-id="3fda4-169">Windows</span><span class="sxs-lookup"><span data-stu-id="3fda4-169">Windows</span></span>](#tab/windows)

* **`--all`**

  <span data-ttu-id="3fda4-170">Удаляет все пакеты SDK и среды выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3fda4-170">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>[ <VERSION>...]`**

  <span data-ttu-id="3fda4-171">Удаляет только пакеты SDK и среды .NET Core, версия которых вышла раньше, чем указанная.</span><span class="sxs-lookup"><span data-stu-id="3fda4-171">Removes only the .NET Core SDKs and runtimes with a version smaller than the specified version.</span></span> <span data-ttu-id="3fda4-172">Указанная версия не удаляется.</span><span class="sxs-lookup"><span data-stu-id="3fda4-172">The specified version remains installed.</span></span>

* **`--all-but <VERSIONS>[ <VERSION>...]`**

  <span data-ttu-id="3fda4-173">Удаляет все пакеты SDK и среды выполнения .NET Core, за исключением указанных версий.</span><span class="sxs-lookup"><span data-stu-id="3fda4-173">Removes all .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="3fda4-174">Удаляет пакеты SDK и среды выполнения .NET Core, за исключением самых поздних версий.</span><span class="sxs-lookup"><span data-stu-id="3fda4-174">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="3fda4-175">Удаляет пакеты SDK и среды выполнения .NET Core, замененные более поздними исправлениями.</span><span class="sxs-lookup"><span data-stu-id="3fda4-175">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="3fda4-176">Этот параметр обеспечивает защиту файла global.json.</span><span class="sxs-lookup"><span data-stu-id="3fda4-176">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="3fda4-177">Удаляет пакеты SDK и среды выполнения .NET Core, помеченные как предварительные версии.</span><span class="sxs-lookup"><span data-stu-id="3fda4-177">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="3fda4-178">Удаляет пакеты SDK и среды выполнения .NET Core, помеченные как предварительные версии, за исключением самых поздних.</span><span class="sxs-lookup"><span data-stu-id="3fda4-178">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--aspnet-runtime`**

  <span data-ttu-id="3fda4-179">Удаляет только среды выполнения ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="3fda4-179">Removes ASP.NET Core runtimes only.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="3fda4-180">Удаляет только среду выполнения и пакеты размещения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3fda4-180">Removes .NET Core runtime and hosting bundles only.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="3fda4-181">Удаляет пакеты SDK и среды выполнения .NET Core, соответствующие указанной версии `major.minor`.</span><span class="sxs-lookup"><span data-stu-id="3fda4-181">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="3fda4-182">Удаляет только среды выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3fda4-182">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="3fda4-183">Удаляет только пакеты SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3fda4-183">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="3fda4-184">Устанавливает уровень детализации.</span><span class="sxs-lookup"><span data-stu-id="3fda4-184">Sets the verbosity level.</span></span> <span data-ttu-id="3fda4-185">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="3fda4-185">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="3fda4-186">Значение по умолчанию — `normal`.</span><span class="sxs-lookup"><span data-stu-id="3fda4-186">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="3fda4-187">Необходимо использовать с `--sdk`, `--runtime` и `--aspnet-runtime` для удаления пакетов SDK или сред выполнения x64.</span><span class="sxs-lookup"><span data-stu-id="3fda4-187">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x64 SDKs or runtimes.</span></span>

* **`--x86`**

  <span data-ttu-id="3fda4-188">Необходимо использовать с `--sdk`, `--runtime` и `--aspnet-runtime` для удаления пакетов SDK или сред выполнения x86.</span><span class="sxs-lookup"><span data-stu-id="3fda4-188">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x86 SDKs or runtimes.</span></span>

* <span data-ttu-id="3fda4-189">**`--force`** Принудительно удаляет версии, которые могут использоваться в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3fda4-189">**`--force`** Forces removal of versions that might be used by Visual Studio.</span></span>

<span data-ttu-id="3fda4-190">Примечания.</span><span class="sxs-lookup"><span data-stu-id="3fda4-190">Notes:</span></span>

1. <span data-ttu-id="3fda4-191">Требуется только один из параметров `--sdk`, `--runtime`, `--aspnet-runtime` или `--hosting-bundle`.</span><span class="sxs-lookup"><span data-stu-id="3fda4-191">Exactly one of `--sdk`, `--runtime`, `--aspnet-runtime`, and `--hosting-bundle` is required.</span></span>
2. <span data-ttu-id="3fda4-192">Параметры `--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` и `[<VERSION>...]` служат для исключения.</span><span class="sxs-lookup"><span data-stu-id="3fda4-192">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>
3. <span data-ttu-id="3fda4-193">Если `--x64` или `--x86` не указаны, будут удалены обе версии.</span><span class="sxs-lookup"><span data-stu-id="3fda4-193">If `--x64` or `--x86` aren't specified, then both x64 and x86 will be removed.</span></span>

## <a name="macos"></a>[<span data-ttu-id="3fda4-194">macOS</span><span class="sxs-lookup"><span data-stu-id="3fda4-194">macOS</span></span>](#tab/macos)

* **`--all`**

  <span data-ttu-id="3fda4-195">Удаляет все пакеты SDK и среды выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3fda4-195">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>[ <VERSION>...]`**

  <span data-ttu-id="3fda4-196">Удаляет пакеты SDK и среды выполнения .NET Core, версия которых вышла ранее, чем указанная.</span><span class="sxs-lookup"><span data-stu-id="3fda4-196">Removes .NET Core SDKs and runtimes below the specified version.</span></span> <span data-ttu-id="3fda4-197">Указанная версия не будет удалена.</span><span class="sxs-lookup"><span data-stu-id="3fda4-197">The specified version will remain.</span></span>

* **`--all-but <VERSIONS>[ <VERSION>...]`**

  <span data-ttu-id="3fda4-198">Удаляет пакеты SDK и среды выполнения .NET Core, за исключением указанных версий.</span><span class="sxs-lookup"><span data-stu-id="3fda4-198">Removes .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="3fda4-199">Удаляет пакеты SDK и среды выполнения .NET Core, за исключением самых поздних версий.</span><span class="sxs-lookup"><span data-stu-id="3fda4-199">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="3fda4-200">Удаляет пакеты SDK и среды выполнения .NET Core, замененные более поздними исправлениями.</span><span class="sxs-lookup"><span data-stu-id="3fda4-200">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="3fda4-201">Этот параметр обеспечивает защиту файла global.json.</span><span class="sxs-lookup"><span data-stu-id="3fda4-201">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="3fda4-202">Удаляет пакеты SDK и среды выполнения .NET Core, помеченные как предварительные версии.</span><span class="sxs-lookup"><span data-stu-id="3fda4-202">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="3fda4-203">Удаляет пакеты SDK и среды выполнения .NET Core, помеченные как предварительные версии, за исключением самых поздних.</span><span class="sxs-lookup"><span data-stu-id="3fda4-203">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="3fda4-204">Удаляет пакеты SDK и среды выполнения .NET Core, соответствующие указанной версии `major.minor`.</span><span class="sxs-lookup"><span data-stu-id="3fda4-204">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="3fda4-205">Удаляет только среды выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3fda4-205">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="3fda4-206">Удаляет только пакеты SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3fda4-206">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="3fda4-207">Устанавливает уровень детализации.</span><span class="sxs-lookup"><span data-stu-id="3fda4-207">Sets the verbosity level.</span></span> <span data-ttu-id="3fda4-208">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="3fda4-208">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="3fda4-209">Значение по умолчанию — `normal`.</span><span class="sxs-lookup"><span data-stu-id="3fda4-209">The default value is `normal`.</span></span>
  
* <span data-ttu-id="3fda4-210">**`--force`** Принудительно удаляет версии, которые могут использоваться Visual Studio или пакетами SDK.</span><span class="sxs-lookup"><span data-stu-id="3fda4-210">**`--force`** Forces removal of versions that might be used by Visual Studio or SDKs.</span></span>

<span data-ttu-id="3fda4-211">Примечания.</span><span class="sxs-lookup"><span data-stu-id="3fda4-211">Notes:</span></span>

1. <span data-ttu-id="3fda4-212">Требуется указать только один параметр: `--sdk` или `--runtime`.</span><span class="sxs-lookup"><span data-stu-id="3fda4-212">Exactly one of `--sdk` and `--runtime` is required.</span></span>
2. <span data-ttu-id="3fda4-213">Параметры `--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` и `[<VERSION>...]` служат для исключения.</span><span class="sxs-lookup"><span data-stu-id="3fda4-213">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>

---

#### <a name="examples"></a><span data-ttu-id="3fda4-214">Примеры</span><span class="sxs-lookup"><span data-stu-id="3fda4-214">Examples</span></span>

> [!NOTE]
> <span data-ttu-id="3fda4-215">По умолчанию пакеты SDK и среды выполнения .NET Core, которые могут требоваться для работы Visual Studio или других пакетов SDK, не включаются в выходные данные `dotnet-core-uninstall dry-run`.</span><span class="sxs-lookup"><span data-stu-id="3fda4-215">By default, .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs are not included in `dotnet-core-uninstall dry-run` output.</span></span> <span data-ttu-id="3fda4-216">В примерах ниже некоторые указанные пакеты SDK и среды выполнения могут быть исключены из выходных данных в зависимости от состояния компьютера.</span><span class="sxs-lookup"><span data-stu-id="3fda4-216">In the following examples, some of the specified SDKs and runtimes may not be included in the output, depending on the state of the machine.</span></span> <span data-ttu-id="3fda4-217">Чтобы включить все пакеты SDK и среды выполнения, укажите их явно в качестве аргументов или используйте параметр `--force`.</span><span class="sxs-lookup"><span data-stu-id="3fda4-217">To include all SDKs and runtimes, list them explicitly as arguments or use the `--force` option.</span></span>

* <span data-ttu-id="3fda4-218">Пробный запуск удаления всех сред выполнения .NET Core, замененных более поздними версиями:</span><span class="sxs-lookup"><span data-stu-id="3fda4-218">Dry run of removing all .NET Core runtimes that have been superseded by higher patches:</span></span>

  ```console
  dotnet-core-uninstall dry-run --all-lower-patches --runtime
  ```

* <span data-ttu-id="3fda4-219">Пробный запуск удаления всех пакетов SDK для .NET Core, версия которых вышла раньше `2.2.301`:</span><span class="sxs-lookup"><span data-stu-id="3fda4-219">Dry run of removing all .NET Core SDKs below the version `2.2.301`:</span></span>

  ```console
  dotnet-core-uninstall whatif --all-below 2.2.301 --sdk
  ```

### <a name="step-3---uninstall-net-core-sdks-and-runtimes"></a><span data-ttu-id="3fda4-220">Шаг 3. Удаление пакетов SDK и сред выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="3fda4-220">Step 3 - Uninstall .NET Core SDKs and Runtimes</span></span>

<span data-ttu-id="3fda4-221">Команда `dotnet-core-uninstall remove` удаляет пакеты SDK и среды выполнения .NET Core, указанные с использованием коллекции параметров.</span><span class="sxs-lookup"><span data-stu-id="3fda4-221">`dotnet-core-uninstall remove` uninstalls .NET Core SDKs and Runtimes that are specified by a collection of options.</span></span> <span data-ttu-id="3fda4-222">Средство нельзя использовать для удаления пакетов SDK и сред выполнения с версией 5.0 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="3fda4-222">The tool can't be used to uninstall SDKs and Runtimes with version 5.0 or above.</span></span>

<span data-ttu-id="3fda4-223">У средства разрушающее поведение, поэтому **настоятельно** рекомендуется выполнять пробный запуск перед выполнением команды удаления.</span><span class="sxs-lookup"><span data-stu-id="3fda4-223">Since this tool has a destructive behavior, it's **highly** recommended that you do a dry run before running the remove command.</span></span> <span data-ttu-id="3fda4-224">В ходе пробного запуска будут показаны пакеты SDK и среды .NET Core, подлежащие удалению при использовании команды `remove`.</span><span class="sxs-lookup"><span data-stu-id="3fda4-224">The dry run will show you what .NET Core SDKs and runtimes will be removed when you use the `remove` command.</span></span> <span data-ttu-id="3fda4-225">Чтобы узнать, какие пакеты SDK и среды выполнения безопасно удалять, обратитесь к разделу [Нужно ли удалять версию](../install/remove-runtime-sdk-versions.md#should-i-remove-a-version).</span><span class="sxs-lookup"><span data-stu-id="3fda4-225">Refer to [Should I remove a version?](../install/remove-runtime-sdk-versions.md#should-i-remove-a-version) to learn which SDKs and runtimes are safe to remove.</span></span>

> [!CAUTION]
> <span data-ttu-id="3fda4-226">Учитывайте следующие факторы.</span><span class="sxs-lookup"><span data-stu-id="3fda4-226">Keep in mind the following caveats:</span></span>
>
>- <span data-ttu-id="3fda4-227">Это средство может удалять версии пакета SDK для .NET Core, необходимые для файлов `global.json` на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3fda4-227">This tool can uninstall versions of the .NET Core SDK that are required by `global.json` files on your machine.</span></span> <span data-ttu-id="3fda4-228">Эти пакеты можно повторно установить, предварительно скачав их на [этой странице](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="3fda4-228">You can reinstall .NET Core SDKs from the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>
>- <span data-ttu-id="3fda4-229">Средство может удалять версии среды выполнения .NET Core, необходимые для зависимых от платформы приложений на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3fda4-229">This tool can uninstall versions of the .NET Core runtime that are required by framework dependent applications on your machine.</span></span> <span data-ttu-id="3fda4-230">Вы можете переустановить среду выполнения .NET Core, предварительно скачав ее с [этой страницы](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="3fda4-230">You can reinstall .NET Core runtimes from the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>
>- <span data-ttu-id="3fda4-231">Это средство может удалять версии пакета SDK и среды выполнения .NET Core, от которых зависит работа Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3fda4-231">This tool can uninstall versions of the .NET Core SDK and runtime that Visual Studio relies on.</span></span> <span data-ttu-id="3fda4-232">Если нарушите работу установленной версии Visual Studio, выполните команду "Исправить" в установщике Visual Studio, чтобы восстановить рабочее состояние.</span><span class="sxs-lookup"><span data-stu-id="3fda4-232">If you break your Visual Studio installation, run "Repair" in the Visual Studio installer to get back to a working state.</span></span>

<span data-ttu-id="3fda4-233">По умолчанию все команды поддерживают пакеты SDK и среды выполнения .NET Core, которые могут потребоваться для работы Visual Studio или других пакетов SDK.</span><span class="sxs-lookup"><span data-stu-id="3fda4-233">By default, all commands keep the .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs.</span></span> <span data-ttu-id="3fda4-234">Эти пакеты и среды выполнения можно удалить путем их явного перечисления в виде аргументов или с использованием параметра `--force`.</span><span class="sxs-lookup"><span data-stu-id="3fda4-234">These SDKs and runtimes can be uninstalled by listing them explicitly as arguments or by using the `--force` option.</span></span>

<span data-ttu-id="3fda4-235">Для удаления пакетов SDK и сред выполнения .NET Core средству требуются повышенные права.</span><span class="sxs-lookup"><span data-stu-id="3fda4-235">The tool requires elevation to uninstall .NET Core SDKs and runtimes.</span></span> <span data-ttu-id="3fda4-236">Запустите средство в командной строке администратора в ОС Windows или с помощью команды `sudo` в macOS.</span><span class="sxs-lookup"><span data-stu-id="3fda4-236">Run the tool in an Administrator command prompt on Windows and with `sudo` on macOS.</span></span> <span data-ttu-id="3fda4-237">Для команд `dry-run` и `whatif` повышение прав не требуется.</span><span class="sxs-lookup"><span data-stu-id="3fda4-237">The `dry-run` and `whatif` commands don't require elevation.</span></span>

<span data-ttu-id="3fda4-238">**dotnet-core-uninstall remove**</span><span class="sxs-lookup"><span data-stu-id="3fda4-238">**dotnet-core-uninstall remove**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="3fda4-239">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="3fda4-239">Synopsis</span></span>

```console
dotnet-core-uninstall remove [options] [<VERSION>...]
```

#### <a name="arguments"></a><span data-ttu-id="3fda4-240">Аргументы</span><span class="sxs-lookup"><span data-stu-id="3fda4-240">Arguments</span></span>

* **`VERSION`**

  <span data-ttu-id="3fda4-241">Указанная версия для удаления.</span><span class="sxs-lookup"><span data-stu-id="3fda4-241">The specified version to uninstall.</span></span> <span data-ttu-id="3fda4-242">Вы можете перечислить несколько версий одну за другой, разделяя их пробелами.</span><span class="sxs-lookup"><span data-stu-id="3fda4-242">You may list several versions one after the other, separated by spaces.</span></span> <span data-ttu-id="3fda4-243">Поддерживаются также файлы ответов.</span><span class="sxs-lookup"><span data-stu-id="3fda4-243">Response files are also supported.</span></span>

  > [!TIP]
  > <span data-ttu-id="3fda4-244">Файлы ответов можно использовать вместо того, чтобы указывать все версии в командной строке.</span><span class="sxs-lookup"><span data-stu-id="3fda4-244">Response files are an alternative to placing all the versions on the command line.</span></span>
  > <span data-ttu-id="3fda4-245">Это текстовые файлы, обычно с расширением \*.rsp. Каждая версия указывается в отдельной строке.</span><span class="sxs-lookup"><span data-stu-id="3fda4-245">They're text files, typically with a \*.rsp extension, and each version is listed on a separate line.</span></span>
  > <span data-ttu-id="3fda4-246">Чтобы указать файл ответов для аргумента `VERSION`, используйте символ \@ сразу после имени файла ответа.</span><span class="sxs-lookup"><span data-stu-id="3fda4-246">To specify a response file for the `VERSION` argument, use the \@ character immediately followed by the response file name.</span></span>

#### <a name="options"></a><span data-ttu-id="3fda4-247">Параметры</span><span class="sxs-lookup"><span data-stu-id="3fda4-247">Options</span></span>

## <a name="windows"></a>[<span data-ttu-id="3fda4-248">Windows</span><span class="sxs-lookup"><span data-stu-id="3fda4-248">Windows</span></span>](#tab/windows)

* **`--all`**

  <span data-ttu-id="3fda4-249">Удаляет все пакеты SDK и среды выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3fda4-249">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>[ <VERSION>...]`**

  <span data-ttu-id="3fda4-250">Удаляет только пакеты SDK и среды .NET Core, версия которых вышла раньше, чем указанная.</span><span class="sxs-lookup"><span data-stu-id="3fda4-250">Removes only the .NET Core SDKs and runtimes with a version smaller than the specified version.</span></span> <span data-ttu-id="3fda4-251">Указанная версия не удаляется.</span><span class="sxs-lookup"><span data-stu-id="3fda4-251">The specified version remains installed.</span></span>

* **`--all-but <VERSIONS>[ <VERSION>...]`**

  <span data-ttu-id="3fda4-252">Удаляет все пакеты SDK и среды выполнения .NET Core, за исключением указанных версий.</span><span class="sxs-lookup"><span data-stu-id="3fda4-252">Removes all .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="3fda4-253">Удаляет пакеты SDK и среды выполнения .NET Core, за исключением самых поздних версий.</span><span class="sxs-lookup"><span data-stu-id="3fda4-253">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="3fda4-254">Удаляет пакеты SDK и среды выполнения .NET Core, замененные более поздними исправлениями.</span><span class="sxs-lookup"><span data-stu-id="3fda4-254">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="3fda4-255">Этот параметр обеспечивает защиту файла global.json.</span><span class="sxs-lookup"><span data-stu-id="3fda4-255">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="3fda4-256">Удаляет пакеты SDK и среды выполнения .NET Core, помеченные как предварительные версии.</span><span class="sxs-lookup"><span data-stu-id="3fda4-256">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="3fda4-257">Удаляет пакеты SDK и среды выполнения .NET Core, помеченные как предварительные версии, за исключением самых поздних.</span><span class="sxs-lookup"><span data-stu-id="3fda4-257">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--aspnet-runtime`**

  <span data-ttu-id="3fda4-258">Удаляет только среды выполнения ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="3fda4-258">Removes ASP.NET Core runtimes only.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="3fda4-259">Удаляет только пакеты размещения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3fda4-259">Removes .NET Core hosting bundles only.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="3fda4-260">Удаляет пакеты SDK и среды выполнения .NET Core, соответствующие указанной версии `major.minor`.</span><span class="sxs-lookup"><span data-stu-id="3fda4-260">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="3fda4-261">Удаляет только среды выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3fda4-261">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="3fda4-262">Удаляет только пакеты SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3fda4-262">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="3fda4-263">Устанавливает уровень детализации.</span><span class="sxs-lookup"><span data-stu-id="3fda4-263">Sets the verbosity level.</span></span> <span data-ttu-id="3fda4-264">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="3fda4-264">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="3fda4-265">Значение по умолчанию — `normal`.</span><span class="sxs-lookup"><span data-stu-id="3fda4-265">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="3fda4-266">Необходимо использовать с `--sdk`, `--runtime` и `--aspnet-runtime` для удаления пакетов SDK или сред выполнения x64.</span><span class="sxs-lookup"><span data-stu-id="3fda4-266">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x64 SDKs or runtimes.</span></span>

* **`--x86`**

  <span data-ttu-id="3fda4-267">Необходимо использовать с `--sdk`, `--runtime` и `--aspnet-runtime` для удаления пакетов SDK или сред выполнения x86.</span><span class="sxs-lookup"><span data-stu-id="3fda4-267">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x86 SDKs or runtimes.</span></span>

* <span data-ttu-id="3fda4-268">**`-y, --yes`** Выполняет команду без подтверждения Yes или No.</span><span class="sxs-lookup"><span data-stu-id="3fda4-268">**`-y, --yes`** Executes the command without requiring a yes or no confirmation.</span></span>

* <span data-ttu-id="3fda4-269">**`--force`** Принудительно удаляет версии, которые могут использоваться в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3fda4-269">**`--force`** Forces removal of versions that might be used by Visual Studio.</span></span>

<span data-ttu-id="3fda4-270">Примечания.</span><span class="sxs-lookup"><span data-stu-id="3fda4-270">Notes:</span></span>

1. <span data-ttu-id="3fda4-271">Требуется только один из параметров `--sdk`, `--runtime`, `--aspnet-runtime` или `--hosting-bundle`.</span><span class="sxs-lookup"><span data-stu-id="3fda4-271">Exactly one of `--sdk`, `--runtime`, `--aspnet-runtime`, and `--hosting-bundle` is required.</span></span>
2. <span data-ttu-id="3fda4-272">Параметры `--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` и `[<VERSION>...]` служат для исключения.</span><span class="sxs-lookup"><span data-stu-id="3fda4-272">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>
3. <span data-ttu-id="3fda4-273">Если `--x64` или `--x86` не указаны, будут удалены обе версии.</span><span class="sxs-lookup"><span data-stu-id="3fda4-273">If `--x64` or `--x86` aren't specified, then both x64 and x86 will be removed.</span></span>

## <a name="macos"></a>[<span data-ttu-id="3fda4-274">macOS</span><span class="sxs-lookup"><span data-stu-id="3fda4-274">macOS</span></span>](#tab/macos)

* **`--all`**

  <span data-ttu-id="3fda4-275">Удаляет все пакеты SDK и среды выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3fda4-275">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>[ <VERSION>...]`**

  <span data-ttu-id="3fda4-276">Удаляет пакеты SDK и среды выполнения .NET Core, версия которых вышла ранее, чем указанная.</span><span class="sxs-lookup"><span data-stu-id="3fda4-276">Removes .NET Core SDKs and runtimes below the specified version.</span></span> <span data-ttu-id="3fda4-277">Указанная версия не будет удалена.</span><span class="sxs-lookup"><span data-stu-id="3fda4-277">The specified version will remain.</span></span>

* **`--all-but <VERSIONS>[ <VERSION>...]`**

  <span data-ttu-id="3fda4-278">Удаляет пакеты SDK и среды выполнения .NET Core, за исключением указанных версий.</span><span class="sxs-lookup"><span data-stu-id="3fda4-278">Removes .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="3fda4-279">Удаляет пакеты SDK и среды выполнения .NET Core, за исключением самых поздних версий.</span><span class="sxs-lookup"><span data-stu-id="3fda4-279">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="3fda4-280">Удаляет пакеты SDK и среды выполнения .NET Core, замененные более поздними исправлениями.</span><span class="sxs-lookup"><span data-stu-id="3fda4-280">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="3fda4-281">Этот параметр обеспечивает защиту файла global.json.</span><span class="sxs-lookup"><span data-stu-id="3fda4-281">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="3fda4-282">Удаляет пакеты SDK и среды выполнения .NET Core, помеченные как предварительные версии.</span><span class="sxs-lookup"><span data-stu-id="3fda4-282">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="3fda4-283">Удаляет пакеты SDK и среды выполнения .NET Core, помеченные как предварительные версии, за исключением самых поздних.</span><span class="sxs-lookup"><span data-stu-id="3fda4-283">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="3fda4-284">Удаляет пакеты SDK и среды выполнения .NET Core, соответствующие указанной версии `major.minor`.</span><span class="sxs-lookup"><span data-stu-id="3fda4-284">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="3fda4-285">Удаляет только среды выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3fda4-285">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="3fda4-286">Удаляет только пакеты SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3fda4-286">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="3fda4-287">Устанавливает уровень детализации.</span><span class="sxs-lookup"><span data-stu-id="3fda4-287">Sets the verbosity level.</span></span> <span data-ttu-id="3fda4-288">Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="3fda4-288">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="3fda4-289">Значение по умолчанию — `normal`.</span><span class="sxs-lookup"><span data-stu-id="3fda4-289">The default value is `normal`.</span></span>

* <span data-ttu-id="3fda4-290">**`-y, --yes`** Выполняет команду без подтверждения Yes или No.</span><span class="sxs-lookup"><span data-stu-id="3fda4-290">**`-y, --yes`** Executes the command without requiring Y/N confirmation.</span></span>
  
* <span data-ttu-id="3fda4-291">**`--force`** Принудительно удаляет версии, которые могут использоваться Visual Studio или пакетами SDK.</span><span class="sxs-lookup"><span data-stu-id="3fda4-291">**`--force`** Forces removal of versions that might be used by Visual Studio or SDKs.</span></span>

<span data-ttu-id="3fda4-292">Примечания.</span><span class="sxs-lookup"><span data-stu-id="3fda4-292">Notes:</span></span>

1. <span data-ttu-id="3fda4-293">Требуется указать только один параметр: `--sdk` или `--runtime`.</span><span class="sxs-lookup"><span data-stu-id="3fda4-293">Exactly one of `--sdk` and `--runtime` is required.</span></span>
2. <span data-ttu-id="3fda4-294">Параметры `--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` и `[<VERSION>...]` служат для исключения.</span><span class="sxs-lookup"><span data-stu-id="3fda4-294">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>

---

#### <a name="examples"></a><span data-ttu-id="3fda4-295">Примеры</span><span class="sxs-lookup"><span data-stu-id="3fda4-295">Examples</span></span>

> [!NOTE]
> <span data-ttu-id="3fda4-296">По умолчанию пакеты SDK и среды выполнения .NET Core, которые могут требоваться для работы Visual Studio или других пакетов SDK, сохраняются.</span><span class="sxs-lookup"><span data-stu-id="3fda4-296">By default, .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs are kept.</span></span> <span data-ttu-id="3fda4-297">В примерах ниже могут остаться некоторые из указанных пакетов SDK и сред выполнения в зависимости от состояния компьютера.</span><span class="sxs-lookup"><span data-stu-id="3fda4-297">In the following examples, some of the specified SDKs and runtimes may remain, depending on the state of the machine.</span></span> <span data-ttu-id="3fda4-298">Чтобы удалить все пакеты и среды выполнения, укажите их явно в качестве аргументов или используйте параметр `--force`.</span><span class="sxs-lookup"><span data-stu-id="3fda4-298">To remove all SDKs and runtimes, list them explicitly as arguments or use the `--force` option.</span></span>

* <span data-ttu-id="3fda4-299">Удаление всех сред выполнения .NET Core, кроме версии `3.0.0-preview6-27804-01` без подтверждения Yes или No:</span><span class="sxs-lookup"><span data-stu-id="3fda4-299">Remove all .NET Core runtimes except the version `3.0.0-preview6-27804-01` without requiring Y/N confirmation:</span></span>

  ```console
  dotnet-core-uninstall remove --all-but 3.0.0-preview6-27804-01 --runtime --yes
  ```

* <span data-ttu-id="3fda4-300">Удаление всех пакетов SDK для .NET Core 1.1 без подтверждения Yes или No:</span><span class="sxs-lookup"><span data-stu-id="3fda4-300">Remove all .NET Core 1.1 SDKs without requiring Y/n confirmation:</span></span>

  ```console
  dotnet-core-uninstall remove --sdk --major-minor 1.1 -y
  ```

* <span data-ttu-id="3fda4-301">Удаление пакета SDK для .NET Core 1.1.11 без вывода на консоль:</span><span class="sxs-lookup"><span data-stu-id="3fda4-301">Remove the .NET Core 1.1.11 SDK with no console output:</span></span>

  ```console
  dotnet-core-uninstall remove 1.1.11 --sdk --yes --verbosity q
  ```

* <span data-ttu-id="3fda4-302">Удаление всех пакетов SDK для .NET Core, которые можно безопасно удалить с помощью этого средства:</span><span class="sxs-lookup"><span data-stu-id="3fda4-302">Remove all .NET Core SDKs that can safely be removed by this tool:</span></span>

  ```console
  dotnet-core-uninstall remove --all --sdk
  ```

* <span data-ttu-id="3fda4-303">Удаление всех пакетов SDK для .NET Core, которые можно безопасно удалить с помощью этого средства, в том числе тех, которые могут требоваться для работы Visual Studio (не рекомендуется):</span><span class="sxs-lookup"><span data-stu-id="3fda4-303">Remove all .NET Core SDKs that can be removed by this tool, including those SDKs that may be required by Visual Studio (not recommended):</span></span>

  ```console
  dotnet-core-uninstall remove --all --sdk --force
  ```

* <span data-ttu-id="3fda4-304">Удаление всех пакетов SDK для .NET Core, указанных в файле ответов `versions.rsp`:</span><span class="sxs-lookup"><span data-stu-id="3fda4-304">Remove all .NET Core SDKs that are specified in the response file `versions.rsp`</span></span>

  ```console
  dotnet-core-uninstall remove --sdk @versions.rsp
  ```

  <span data-ttu-id="3fda4-305">В файле *versions.rsp* содержится следующее:</span><span class="sxs-lookup"><span data-stu-id="3fda4-305">The content of *versions.rsp* is as follows:</span></span>
  
  ```text
  2.2.300
  2.1.700
  ```

### <a name="step-4---delete-the-nuget-fallback-folder-optional"></a><span data-ttu-id="3fda4-306">Шаг 4. Удаление резервной папки NuGet (необязательный)</span><span class="sxs-lookup"><span data-stu-id="3fda4-306">Step 4 - Delete the NuGet fallback folder (optional)</span></span>

<span data-ttu-id="3fda4-307">В некоторых случаях папка `NuGetFallbackFolder` может больше не требоваться, и ее понадобится удалить.</span><span class="sxs-lookup"><span data-stu-id="3fda4-307">In some cases, you no longer need the `NuGetFallbackFolder` and may wish to delete it.</span></span> <span data-ttu-id="3fda4-308">Дополнительные сведения об удалении папки NuGetFallbackFolder см. в [этом разделе](../install/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder).</span><span class="sxs-lookup"><span data-stu-id="3fda4-308">For more information about deleting this folder, see [Remove the NuGetFallbackFolder](../install/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder).</span></span>

## <a name="uninstall-the-tool"></a><span data-ttu-id="3fda4-309">Удаление средства</span><span class="sxs-lookup"><span data-stu-id="3fda4-309">Uninstall the tool</span></span>

## <a name="windows"></a>[<span data-ttu-id="3fda4-310">Windows</span><span class="sxs-lookup"><span data-stu-id="3fda4-310">Windows</span></span>](#tab/windows)

1. <span data-ttu-id="3fda4-311">Откройте окно **Установка и удаление программ**.</span><span class="sxs-lookup"><span data-stu-id="3fda4-311">Open **Add or Remove Programs**.</span></span>
2. <span data-ttu-id="3fda4-312">Найдите `Microsoft .NET Core SDK Uninstall Tool`.</span><span class="sxs-lookup"><span data-stu-id="3fda4-312">Search for `Microsoft .NET Core SDK Uninstall Tool`.</span></span>
3. <span data-ttu-id="3fda4-313">Выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="3fda4-313">Select **Uninstall**.</span></span>

## <a name="macos"></a>[<span data-ttu-id="3fda4-314">macOS</span><span class="sxs-lookup"><span data-stu-id="3fda4-314">macOS</span></span>](#tab/macos)

<span data-ttu-id="3fda4-315">Удалите скачанный файл *dotnet-core-uninstall.tar.gz* из каталога, в котором он установлен.</span><span class="sxs-lookup"><span data-stu-id="3fda4-315">Delete the downloaded *dotnet-core-uninstall.tar.gz* file from the directory where it was installed.</span></span> <span data-ttu-id="3fda4-316">Если содержимое этого файла распаковано в другой каталог, необходимо также удалить это содержимое.</span><span class="sxs-lookup"><span data-stu-id="3fda4-316">If you unzipped the contents of this file into another directory, be sure to delete that content as well.</span></span>

---
