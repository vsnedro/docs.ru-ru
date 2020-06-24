---
title: Установка среды выполнения .NET Core в Windows, Linux и macOS — .NET Core
description: Сведения об установке .NET Core в Windows, Linux и macOS. Узнайте о зависимостях, необходимых для запуска приложений .NET Core.
author: thraka
ms.author: adegeo
ms.date: 05/04/2020
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: d3f7083366e2019d01884b5dff6e60d05ed565dd
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768291"
---
# <a name="install-the-net-core-runtime"></a><span data-ttu-id="8f65b-104">Установка среды выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="8f65b-104">Install the .NET Core Runtime</span></span>

<span data-ttu-id="8f65b-105">В этой статье вы узнаете, как скачать и установить среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8f65b-105">In this article, you'll learn how to download and install the .NET Core runtime.</span></span> <span data-ttu-id="8f65b-106">Среда выполнения .NET Core используется для запуска приложений, созданных с помощью .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8f65b-106">The .NET Core runtime is used to run apps created with .NET Core.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="8f65b-107">Установка с помощью установщика</span><span class="sxs-lookup"><span data-stu-id="8f65b-107">Install with an installer</span></span>

<span data-ttu-id="8f65b-108">В Windows есть автономные установщики, которые можно использовать для установки среды выполнения .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="8f65b-108">Windows has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="8f65b-109">Процессоры x64 (64-разрядные)</span><span class="sxs-lookup"><span data-stu-id="8f65b-109">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="8f65b-110">Процессоры x86 (32-разрядные)</span><span class="sxs-lookup"><span data-stu-id="8f65b-110">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="8f65b-111">Установка с помощью установщика</span><span class="sxs-lookup"><span data-stu-id="8f65b-111">Install with an installer</span></span>

<span data-ttu-id="8f65b-112">В macOS есть автономные установщики, которые можно использовать для установки среды выполнения .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="8f65b-112">macOS has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="8f65b-113">Процессоры x64 (64-разрядные)</span><span class="sxs-lookup"><span data-stu-id="8f65b-113">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## <a name="download-and-manually-install"></a><span data-ttu-id="8f65b-114">Скачивание и установка вручную</span><span class="sxs-lookup"><span data-stu-id="8f65b-114">Download and manually install</span></span>

<span data-ttu-id="8f65b-115">В качестве альтернативы установщикам macOS для .NET Core можно скачать и вручную установить среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="8f65b-115">As an alternative to the macOS installers for .NET Core, you can download and manually install the runtime.</span></span>

<span data-ttu-id="8f65b-116">Чтобы установить среду выполнения и сделать команды .NET Core CLI доступными в терминале, сначала [скачайте](#all-net-core-downloads) двоичный выпуск .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8f65b-116">To install the runtime and enable the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="8f65b-117">Затем откройте терминал и выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="8f65b-117">Then, open a terminal and run the following commands.</span></span> <span data-ttu-id="8f65b-118">Предполагается, что среда выполнения скачивается в файл `~/Downloads/dotnet-runtime.pkg`.</span><span class="sxs-lookup"><span data-stu-id="8f65b-118">It's assumed the runtime is downloaded to the `~/Downloads/dotnet-runtime.pkg` file.</span></span>

```bash
mkdir -p $HOME/dotnet
sudo installer -pkg ~/Downloads/dotnet-runtime.pkg -target $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

::: zone-end

::: zone pivot="os-linux"

## <a name="install-on-linux"></a><span data-ttu-id="8f65b-119">Установка на Linux</span><span class="sxs-lookup"><span data-stu-id="8f65b-119">Install on Linux</span></span>

<span data-ttu-id="8f65b-120">Скоро эта статья будет удалена.</span><span class="sxs-lookup"><span data-stu-id="8f65b-120">This article will be removed soon.</span></span> <span data-ttu-id="8f65b-121">Вместо нее доступна статья [Установка .NET Core на Linux](linux.md).</span><span class="sxs-lookup"><span data-stu-id="8f65b-121">It is currently replaced by [Install .NET Core on Linux](linux.md).</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="8f65b-122">Установка с помощью функции автоматизации PowerShell</span><span class="sxs-lookup"><span data-stu-id="8f65b-122">Install with PowerShell automation</span></span>

<span data-ttu-id="8f65b-123">[Сценарии dotnet-install](../tools/dotnet-install-script.md) используются для автоматизации установок среды выполнения и их осуществления без прав администратора.</span><span class="sxs-lookup"><span data-stu-id="8f65b-123">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="8f65b-124">Вы можете скачать сценарий со [страницы справочника по сценариям dotnet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="8f65b-124">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="8f65b-125">Этот сценарий по умолчанию устанавливает последнюю версию [с долгосрочной поддержкой (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), которой сейчас является .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="8f65b-125">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="8f65b-126">Вы можете выбрать конкретный выпуск, указав параметр `Channel`.</span><span class="sxs-lookup"><span data-stu-id="8f65b-126">You can choose a specific release by specifying the `Channel` switch.</span></span> <span data-ttu-id="8f65b-127">Включите параметр `Runtime` для установки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="8f65b-127">Include the `Runtime` switch to install a runtime.</span></span> <span data-ttu-id="8f65b-128">В противном случае сценарий устанавливает пакет [SDK](sdk.md).</span><span class="sxs-lookup"><span data-stu-id="8f65b-128">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="8f65b-129">Приведенная выше команда устанавливает среду выполнения ASP.NET Core для максимальной совместимости.</span><span class="sxs-lookup"><span data-stu-id="8f65b-129">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="8f65b-130">Среда выполнения ASP.NET Core также включает в себя стандартную среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8f65b-130">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="8f65b-131">Скачивание и установка вручную</span><span class="sxs-lookup"><span data-stu-id="8f65b-131">Download and manually install</span></span>

<span data-ttu-id="8f65b-132">Чтобы извлечь среду выполнения и сделать команды .NET Core CLI доступными в терминале, сначала [скачайте](#all-net-core-downloads) двоичный выпуск .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8f65b-132">To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="8f65b-133">Затем создайте каталог в котором будете выполнять установку, например `%USERPROFILE%\dotnet`.</span><span class="sxs-lookup"><span data-stu-id="8f65b-133">Then, create a directory to install to, for example `%USERPROFILE%\dotnet`.</span></span> <span data-ttu-id="8f65b-134">Наконец, извлеките скачанный ZIP-файл в этот каталог.</span><span class="sxs-lookup"><span data-stu-id="8f65b-134">Finally, extract the downloaded zip file into that directory.</span></span>

<span data-ttu-id="8f65b-135">По умолчанию команды и приложения .NET Core CLI не будут использовать платформу .NET Core, установленную таким образом. Вам нужно выбрать ее явно.</span><span class="sxs-lookup"><span data-stu-id="8f65b-135">By default, .NET Core CLI commands and apps won't use .NET Core installed in this way and you must explicitly choose to use it.</span></span> <span data-ttu-id="8f65b-136">Для этого измените переменные среды, с которыми запускается приложение:</span><span class="sxs-lookup"><span data-stu-id="8f65b-136">To do so, change the environment variables with which an application is started:</span></span>

```console
set DOTNET_ROOT=%USERPROFILE%\dotnet
set PATH=%USERPROFILE%\dotnet;%PATH%
```

<span data-ttu-id="8f65b-137">Такой подход позволяет установить несколько версий в отдельные расположения, а затем явно выбрать расположение установки, которое должно использовать приложение, запустив приложение с переменными среды, указывающими на это расположение.</span><span class="sxs-lookup"><span data-stu-id="8f65b-137">This approach lets you install multiple versions into separate locations, then explicitly choose which install location an application should use by running the application with environment variables pointing at that location.</span></span>

<span data-ttu-id="8f65b-138">Даже если эти переменные среды заданы, .NET Core по-прежнему учитывает глобальное расположение установки по умолчанию при выборе лучшей платформы для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="8f65b-138">Even when these environment variables are set, .NET Core still considers the default global install location when selecting the best framework for running the application.</span></span> <span data-ttu-id="8f65b-139">По умолчанию обычно это расположение `C:\Program Files\dotnet`, которое используют установщики.</span><span class="sxs-lookup"><span data-stu-id="8f65b-139">The default is typically `C:\Program Files\dotnet`, which the installers use.</span></span> <span data-ttu-id="8f65b-140">Вы можете указать среде выполнения использовать только пользовательское расположение установки, задав эту переменную среды.</span><span class="sxs-lookup"><span data-stu-id="8f65b-140">You can instruct the runtime to only use the custom install location by setting this environment variable as well:</span></span>

```console
set DOTNET_MULTILEVEL_LOOKUP=0
```

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="8f65b-141">Установка с помощью функции автоматизации Bash</span><span class="sxs-lookup"><span data-stu-id="8f65b-141">Install with bash automation</span></span>

<span data-ttu-id="8f65b-142">[Сценарии dotnet-install](../tools/dotnet-install-script.md) используются для автоматизации установок среды выполнения и их осуществления без прав администратора.</span><span class="sxs-lookup"><span data-stu-id="8f65b-142">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="8f65b-143">Вы можете скачать сценарий со [страницы справочника по сценариям dotnet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="8f65b-143">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="8f65b-144">Этот сценарий по умолчанию устанавливает последнюю версию [с долгосрочной поддержкой (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), которой сейчас является .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="8f65b-144">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="8f65b-145">Вы можете выбрать конкретный выпуск, указав параметр `current`.</span><span class="sxs-lookup"><span data-stu-id="8f65b-145">You can choose a specific release by specifying the `current` switch.</span></span> <span data-ttu-id="8f65b-146">Включите параметр `runtime` для установки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="8f65b-146">Include the `runtime` switch to install a runtime.</span></span> <span data-ttu-id="8f65b-147">В противном случае сценарий устанавливает пакет [SDK](sdk.md).</span><span class="sxs-lookup"><span data-stu-id="8f65b-147">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```bash
./dotnet-install.sh --channel 3.1 --runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="8f65b-148">Приведенная выше команда устанавливает среду выполнения ASP.NET Core для максимальной совместимости.</span><span class="sxs-lookup"><span data-stu-id="8f65b-148">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="8f65b-149">Среда выполнения ASP.NET Core также включает в себя стандартную среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8f65b-149">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="8f65b-150">Все скачиваемые файлы для .NET Core</span><span class="sxs-lookup"><span data-stu-id="8f65b-150">All .NET Core downloads</span></span>

<span data-ttu-id="8f65b-151">Вы можете скачать и установить .NET Core напрямую, используя одну из следующих ссылок:</span><span class="sxs-lookup"><span data-stu-id="8f65b-151">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="8f65b-152">Скачиваемые файлы для .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="8f65b-152">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="8f65b-153">Скачиваемые файлы для .NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="8f65b-153">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="8f65b-154">Docker</span><span class="sxs-lookup"><span data-stu-id="8f65b-154">Docker</span></span>

<span data-ttu-id="8f65b-155">Контейнеры обеспечивают простой способ изоляции приложения от остальной части основной системы.</span><span class="sxs-lookup"><span data-stu-id="8f65b-155">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="8f65b-156">Контейнеры на одном компьютере совместно использую только ядро, а также используют ресурсы, которые передаются в приложение.</span><span class="sxs-lookup"><span data-stu-id="8f65b-156">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="8f65b-157">.NET Core можно выполнять в контейнере Docker.</span><span class="sxs-lookup"><span data-stu-id="8f65b-157">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="8f65b-158">Официальные образы Docker для .NET Core публикуются в реестре контейнеров Microsoft (MCR) и доступ к ним можно получить в [репозитории Microsoft .NET Core Docker Hub](https://hub.docker.com/_/microsoft-dotnet-core/).</span><span class="sxs-lookup"><span data-stu-id="8f65b-158">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="8f65b-159">Каждый репозиторий содержит рабочие образы для разных сочетаний .NET (пакета SDK или среды выполнения) и операционной системы.</span><span class="sxs-lookup"><span data-stu-id="8f65b-159">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="8f65b-160">Корпорация Майкрософт предоставляет образы, которые предназначены для конкретных сценариев.</span><span class="sxs-lookup"><span data-stu-id="8f65b-160">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="8f65b-161">Например [репозиторий ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) содержит образы, которые предназначены для запуска приложений ASP.NET Core в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="8f65b-161">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="8f65b-162">Дополнительные сведения об использовании .NET Core в контейнере Docker см. в статьях [Введение в .NET и Docker](../docker/introduction.md) и [Примеры](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="8f65b-162">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="8f65b-163">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="8f65b-163">Next steps</span></span>

- <span data-ttu-id="8f65b-164">[Проверка того, установлена ли платформа .NET Core](how-to-detect-installed-versions.md).</span><span class="sxs-lookup"><span data-stu-id="8f65b-164">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md).</span></span>
