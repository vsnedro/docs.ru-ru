---
title: Установка пакета SDK для .NET Core в Windows, Linux и macOS — .NET Core
description: Сведения об установке .NET Core в Windows, Linux и macOS. Узнайте о зависимостях, необходимых для разработки приложений .NET Core.
author: thraka
ms.author: adegeo
ms.date: 05/04/2020
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 9b170765740600641f96056adc08ff0b69a03338
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768318"
---
# <a name="install-the-net-core-sdk"></a><span data-ttu-id="e92e5-104">Установка пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="e92e5-104">Install the .NET Core SDK</span></span>

<span data-ttu-id="e92e5-105">В этой статье вы узнаете, как установить пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e92e5-105">In this article, you'll learn how to install the .NET Core SDK.</span></span> <span data-ttu-id="e92e5-106">Пакет SDK для .NET Core используется для создания приложений и библиотек .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e92e5-106">The .NET Core SDK is used to create .NET Core apps and libraries.</span></span> <span data-ttu-id="e92e5-107">Среда выполнения .NET Core всегда устанавливается вместе с пакетом SDK.</span><span class="sxs-lookup"><span data-stu-id="e92e5-107">The .NET Core runtime is always installed with the SDK.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="e92e5-108">Установка с помощью установщика</span><span class="sxs-lookup"><span data-stu-id="e92e5-108">Install with an installer</span></span>

<span data-ttu-id="e92e5-109">В Windows есть автономные установщики, которые можно использовать для установки пакета SDK для .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="e92e5-109">Windows has standalone installers that can be used to install the .NET Core 3.1 SDK:</span></span>

- [<span data-ttu-id="e92e5-110">Процессоры x64 (64-разрядные)</span><span class="sxs-lookup"><span data-stu-id="e92e5-110">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="e92e5-111">Процессоры x86 (32-разрядные)</span><span class="sxs-lookup"><span data-stu-id="e92e5-111">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="e92e5-112">Установка с помощью установщика</span><span class="sxs-lookup"><span data-stu-id="e92e5-112">Install with an installer</span></span>

<span data-ttu-id="e92e5-113">В macOS есть автономные установщики, которые можно использовать для установки пакета SDK для .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="e92e5-113">macOS has standalone installers that can be used to install the .NET Core 3.1 SDK:</span></span>

- [<span data-ttu-id="e92e5-114">Процессоры x64 (64-разрядные)</span><span class="sxs-lookup"><span data-stu-id="e92e5-114">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## <a name="download-and-manually-install"></a><span data-ttu-id="e92e5-115">Скачивание и установка вручную</span><span class="sxs-lookup"><span data-stu-id="e92e5-115">Download and manually install</span></span>

<span data-ttu-id="e92e5-116">В качестве альтернативы установщикам macOS для .NET Core можно скачать и вручную установить пакет SDK.</span><span class="sxs-lookup"><span data-stu-id="e92e5-116">As an alternative to the macOS installers for .NET Core, you can download and manually install the SDK.</span></span>

<span data-ttu-id="e92e5-117">Чтобы извлечь пакет SDK и сделать команды .NET Core CLI доступными в терминале, сначала [скачайте](#all-net-core-downloads) двоичный выпуск .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e92e5-117">To extract the SDK and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="e92e5-118">Затем откройте терминал и выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="e92e5-118">Then, open a terminal and run the following commands.</span></span> <span data-ttu-id="e92e5-119">Предполагается, что среда выполнения скачивается в файл `~/Downloads/dotnet-sdk.pkg`.</span><span class="sxs-lookup"><span data-stu-id="e92e5-119">It's assumed the runtime is downloaded to the `~/Downloads/dotnet-sdk.pkg` file.</span></span>

```bash
mkdir -p $HOME/dotnet
sudo installer -pkg ~/Downloads/dotnet-sdk.pkg -target $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

::: zone-end

::: zone pivot="os-linux"

## <a name="install-on-linux"></a><span data-ttu-id="e92e5-120">Установка на Linux</span><span class="sxs-lookup"><span data-stu-id="e92e5-120">Install on Linux</span></span>

<span data-ttu-id="e92e5-121">Скоро эта статья будет удалена.</span><span class="sxs-lookup"><span data-stu-id="e92e5-121">This article will be removed soon.</span></span> <span data-ttu-id="e92e5-122">Вместо нее доступна статья [Установка .NET Core на Linux](linux.md).</span><span class="sxs-lookup"><span data-stu-id="e92e5-122">It is currently replaced by [Install .NET Core on Linux](linux.md).</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-visual-studio"></a><span data-ttu-id="e92e5-123">Установка с помощью Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e92e5-123">Install with Visual Studio</span></span>

<span data-ttu-id="e92e5-124">Если вы используете Visual Studio для разработки приложений .NET Core, в следующей таблице указана минимальная требуемая версия Visual Studio на основе целевой версии пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e92e5-124">If you're using Visual Studio to develop .NET Core apps, the following table describes the minimum required version of Visual Studio based on the target .NET Core SDK version.</span></span>

| <span data-ttu-id="e92e5-125">Версия пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="e92e5-125">.NET Core SDK version</span></span> | <span data-ttu-id="e92e5-126">Версия Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e92e5-126">Visual Studio version</span></span>                      |
| --------------------- | ------------------------------------------ |
| <span data-ttu-id="e92e5-127">3.1</span><span class="sxs-lookup"><span data-stu-id="e92e5-127">3.1</span></span>                   | <span data-ttu-id="e92e5-128">Visual Studio 2019 версии 16.4 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="e92e5-128">Visual Studio 2019 version 16.4 or higher.</span></span> |
| <span data-ttu-id="e92e5-129">3.0</span><span class="sxs-lookup"><span data-stu-id="e92e5-129">3.0</span></span>                   | <span data-ttu-id="e92e5-130">Visual Studio 2019 версии 16.3 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="e92e5-130">Visual Studio 2019 version 16.3 or higher.</span></span> |
| <span data-ttu-id="e92e5-131">2.2</span><span class="sxs-lookup"><span data-stu-id="e92e5-131">2.2</span></span>                   | <span data-ttu-id="e92e5-132">Visual Studio 2017 версии 15.9 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="e92e5-132">Visual Studio 2017 version 15.9 or higher.</span></span> |
| <span data-ttu-id="e92e5-133">2.1</span><span class="sxs-lookup"><span data-stu-id="e92e5-133">2.1</span></span>                   | <span data-ttu-id="e92e5-134">Visual Studio 2017 версии 15.7 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="e92e5-134">Visual Studio 2017 version 15.7 or higher.</span></span> |

<span data-ttu-id="e92e5-135">Если среда Visual Studio уже установлена, вы можете проверить ее версию, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="e92e5-135">If you already have Visual Studio installed, you can check your version with the following steps.</span></span>

01. <span data-ttu-id="e92e5-136">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e92e5-136">Open Visual Studio.</span></span>
01. <span data-ttu-id="e92e5-137">Выберите **Справка** > **О Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="e92e5-137">Select **Help** > **About Microsoft Visual Studio**.</span></span>
01. <span data-ttu-id="e92e5-138">Считайте номер версии из диалогового окна **О программе**.</span><span class="sxs-lookup"><span data-stu-id="e92e5-138">Read the version number from the **About** dialog.</span></span>

<span data-ttu-id="e92e5-139">Visual Studio может установить последнюю пакета SDK для .NET Core и среды выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e92e5-139">Visual Studio can install the latest .NET Core SDK and runtime.</span></span>

- <span data-ttu-id="e92e5-140">[Скачайте Visual Studio.](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)</span><span class="sxs-lookup"><span data-stu-id="e92e5-140">[Download Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019).</span></span>

### <a name="select-a-workload"></a><span data-ttu-id="e92e5-141">Выбор рабочей нагрузки</span><span class="sxs-lookup"><span data-stu-id="e92e5-141">Select a workload</span></span>

<span data-ttu-id="e92e5-142">При установке или изменении Visual Studio выберите одну или несколько из следующих рабочих нагрузок в зависимости от типа создаваемого приложения:</span><span class="sxs-lookup"><span data-stu-id="e92e5-142">When installing or modifying Visual Studio, select one or more of the following workloads, depending on the kind of application you're building:</span></span>

- <span data-ttu-id="e92e5-143">рабочая нагрузка **Кроссплатформенная разработка .NET Core** в разделе **Другие наборы инструментов**;</span><span class="sxs-lookup"><span data-stu-id="e92e5-143">The **.NET Core cross-platform development** workload in the **Other Toolsets** section.</span></span>
- <span data-ttu-id="e92e5-144">рабочая нагрузка **ASP.NET и разработка веб-приложений** в разделе **Веб-разработка и облако**;</span><span class="sxs-lookup"><span data-stu-id="e92e5-144">The **ASP.NET and web development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="e92e5-145">рабочая нагрузка **Разработка для Azure** в разделе **Веб-разработка и облако**;</span><span class="sxs-lookup"><span data-stu-id="e92e5-145">The **Azure development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="e92e5-146">рабочая нагрузка **Разработка классических приложений .NET** в разделе **Классические и мобильные**.</span><span class="sxs-lookup"><span data-stu-id="e92e5-146">The **.NET desktop development** workload in the **Desktop & Mobile** section.</span></span>

<span data-ttu-id="e92e5-147">[![Windows Visual Studio 2019 с рабочей нагрузкой .NET Core](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="e92e5-147">[![Windows Visual Studio 2019 with .NET Core workload](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="e92e5-148">Скачивание и установка вручную</span><span class="sxs-lookup"><span data-stu-id="e92e5-148">Download and manually install</span></span>

<span data-ttu-id="e92e5-149">Чтобы извлечь среду выполнения и сделать команды .NET Core CLI доступными в терминале, сначала [скачайте](#all-net-core-downloads) двоичный выпуск .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e92e5-149">To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="e92e5-150">Затем создайте каталог в котором будете выполнять установку, например `%USERPROFILE%\dotnet`.</span><span class="sxs-lookup"><span data-stu-id="e92e5-150">Then, create a directory to install to, for example `%USERPROFILE%\dotnet`.</span></span> <span data-ttu-id="e92e5-151">Наконец, извлеките скачанный ZIP-файл в этот каталог.</span><span class="sxs-lookup"><span data-stu-id="e92e5-151">Finally, extract the downloaded zip file into that directory.</span></span>

<span data-ttu-id="e92e5-152">По умолчанию команды и приложения .NET Core CLI не будут использовать платформу .NET Core, установленную таким образом. Вам нужно выбрать ее явно.</span><span class="sxs-lookup"><span data-stu-id="e92e5-152">By default, .NET Core CLI commands and apps won't use .NET Core installed in this way and you must explicitly choose to use it.</span></span> <span data-ttu-id="e92e5-153">Для этого измените переменные среды, с которыми запускается приложение:</span><span class="sxs-lookup"><span data-stu-id="e92e5-153">To do so, change the environment variables with which an application is started:</span></span>

```console
set DOTNET_ROOT=%USERPROFILE%\dotnet
set PATH=%USERPROFILE%\dotnet;%PATH%
```

<span data-ttu-id="e92e5-154">Такой подход позволяет установить несколько версий в отдельные расположения, а затем явно выбрать расположение установки, которое должно использовать приложение, запустив приложение с переменными среды, указывающими на это расположение.</span><span class="sxs-lookup"><span data-stu-id="e92e5-154">This approach lets you install multiple versions into separate locations, then explicitly choose which install location an application should use by running the application with environment variables pointing at that location.</span></span>

<span data-ttu-id="e92e5-155">Даже если эти переменные среды заданы, .NET Core по-прежнему учитывает глобальное расположение установки по умолчанию при выборе лучшей платформы для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="e92e5-155">Even when these environment variables are set, .NET Core still considers the default global install location when selecting the best framework for running the application.</span></span> <span data-ttu-id="e92e5-156">По умолчанию обычно это расположение `C:\Program Files\dotnet`, которое используют установщики.</span><span class="sxs-lookup"><span data-stu-id="e92e5-156">The default is typically `C:\Program Files\dotnet`, which the installers use.</span></span> <span data-ttu-id="e92e5-157">Вы можете указать среде выполнения использовать только пользовательское расположение установки, задав эту переменную среды.</span><span class="sxs-lookup"><span data-stu-id="e92e5-157">You can instruct the runtime to only use the custom install location by setting this environment variable as well:</span></span>

```console
set DOTNET_MULTILEVEL_LOOKUP=0
```

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-visual-studio-for-mac"></a><span data-ttu-id="e92e5-158">Установка с помощью Visual Studio для Mac</span><span class="sxs-lookup"><span data-stu-id="e92e5-158">Install with Visual Studio for Mac</span></span>

<span data-ttu-id="e92e5-159">Visual Studio для Mac устанавливает пакет SDK для .NET Core, если выбрана рабочая нагрузка **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="e92e5-159">Visual Studio for Mac installs the .NET Core SDK when the **.NET Core** workload is selected.</span></span> <span data-ttu-id="e92e5-160">Чтобы приступить к разработке в .NET Core на macOS, ознакомьтесь со статьей [Установка Visual Studio 2019 для Mac](/visualstudio/mac/installation).</span><span class="sxs-lookup"><span data-stu-id="e92e5-160">To get started with .NET Core development on macOS, see [Install Visual Studio 2019 for Mac](/visualstudio/mac/installation).</span></span> <span data-ttu-id="e92e5-161">В последнем выпуске .NET Core 3.1 необходимо использовать предварительную версию Visual Studio для Mac 8.4.</span><span class="sxs-lookup"><span data-stu-id="e92e5-161">For the latest release, .NET Core 3.1, you must use the Visual Studio for Mac 8.4 Preview.</span></span>

<span data-ttu-id="e92e5-162">[![Visual Studio 2019 для Mac с компонентом рабочей нагрузки .NET Core в macOS](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="e92e5-162">[![macOS Visual Studio 2019 for Mac with .NET Core workload feature](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span></span>

::: zone-end

::: zone pivot="os-windows,os-macos"

## <a name="install-alongside-visual-studio-code"></a><span data-ttu-id="e92e5-163">Установка вместе с Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="e92e5-163">Install alongside Visual Studio Code</span></span>

<span data-ttu-id="e92e5-164">Visual Studio Code — это эффективный и облегченный редактор исходного кода, который работает на компьютере.</span><span class="sxs-lookup"><span data-stu-id="e92e5-164">Visual Studio Code is a powerful and lightweight source code editor that runs on your desktop.</span></span> <span data-ttu-id="e92e5-165">Visual Studio Code доступен для Windows, macOS и Linux.</span><span class="sxs-lookup"><span data-stu-id="e92e5-165">Visual Studio Code is available for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="e92e5-166">Хотя Visual Studio Code не поставляется с автоматическим установщиком .NET Core, таким как Visual Studio, добавление поддержки .NET Core не вызывает затруднений.</span><span class="sxs-lookup"><span data-stu-id="e92e5-166">While Visual Studio Code doesn't come with an automated .NET Core installer like Visual Studio does, adding .NET Core support is simple.</span></span>

01. <span data-ttu-id="e92e5-167">[Скачайте и установите Visual Studio Code](https://code.visualstudio.com/Download).</span><span class="sxs-lookup"><span data-stu-id="e92e5-167">[Download and install Visual Studio Code](https://code.visualstudio.com/Download).</span></span>
01. <span data-ttu-id="e92e5-168">[Скачайте и установите пакет SDK для .NET Core](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="e92e5-168">[Download and install the .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core).</span></span>
01. <span data-ttu-id="e92e5-169">[Установите расширение C# из Marketplace для Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span><span class="sxs-lookup"><span data-stu-id="e92e5-169">[Install the C# extension from the Visual Studio Code marketplace](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="e92e5-170">Установка с помощью функции автоматизации PowerShell</span><span class="sxs-lookup"><span data-stu-id="e92e5-170">Install with PowerShell automation</span></span>

<span data-ttu-id="e92e5-171">[Сценарии dotnet-install](../tools/dotnet-install-script.md) используются для автоматизации установок пакета SDK и их осуществления без прав администратора.</span><span class="sxs-lookup"><span data-stu-id="e92e5-171">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the SDK.</span></span> <span data-ttu-id="e92e5-172">Вы можете скачать сценарий со [страницы справочника по сценариям dotnet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="e92e5-172">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="e92e5-173">Этот сценарий по умолчанию устанавливает последнюю версию [с долгосрочной поддержкой (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), которой сейчас является .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="e92e5-173">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="e92e5-174">Чтобы установить текущий выпуск .NET Core, запустите сценарий с указанным ниже параметром.</span><span class="sxs-lookup"><span data-stu-id="e92e5-174">To install the current release of .NET Core, run the script with the following switch.</span></span>

```powershell
dotnet-install.ps1 -Channel Current
```

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="e92e5-175">Установка с помощью функции автоматизации Bash</span><span class="sxs-lookup"><span data-stu-id="e92e5-175">Install with bash automation</span></span>

<span data-ttu-id="e92e5-176">[Сценарии dotnet-install](../tools/dotnet-install-script.md) используются для автоматизации установок пакета SDK и их осуществления без прав администратора.</span><span class="sxs-lookup"><span data-stu-id="e92e5-176">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the SDK.</span></span> <span data-ttu-id="e92e5-177">Вы можете скачать сценарий со [страницы справочника по сценариям dotnet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="e92e5-177">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="e92e5-178">Этот сценарий по умолчанию устанавливает последнюю версию [с долгосрочной поддержкой (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), которой сейчас является .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="e92e5-178">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="e92e5-179">Чтобы установить текущий выпуск .NET Core, запустите сценарий с указанным ниже параметром.</span><span class="sxs-lookup"><span data-stu-id="e92e5-179">To install the current release of .NET Core, run the script with the following switch.</span></span>

```bash
./dotnet-install.sh -c Current
```

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="e92e5-180">Все скачиваемые файлы для .NET Core</span><span class="sxs-lookup"><span data-stu-id="e92e5-180">All .NET Core downloads</span></span>

<span data-ttu-id="e92e5-181">Вы можете скачать и установить .NET Core напрямую, используя одну из следующих ссылок:</span><span class="sxs-lookup"><span data-stu-id="e92e5-181">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="e92e5-182">Скачиваемые файлы для .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="e92e5-182">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="e92e5-183">Скачиваемые файлы для .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="e92e5-183">.NET Core 3.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [<span data-ttu-id="e92e5-184">Скачиваемые файлы для .NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="e92e5-184">.NET Core 2.2 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [<span data-ttu-id="e92e5-185">Скачиваемые файлы для .NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="e92e5-185">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="e92e5-186">Docker</span><span class="sxs-lookup"><span data-stu-id="e92e5-186">Docker</span></span>

<span data-ttu-id="e92e5-187">Контейнеры обеспечивают простой способ изоляции приложения от остальной части основной системы.</span><span class="sxs-lookup"><span data-stu-id="e92e5-187">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="e92e5-188">Контейнеры на одном компьютере совместно использую только ядро, а также используют ресурсы, которые передаются в приложение.</span><span class="sxs-lookup"><span data-stu-id="e92e5-188">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="e92e5-189">.NET Core можно выполнять в контейнере Docker.</span><span class="sxs-lookup"><span data-stu-id="e92e5-189">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="e92e5-190">Официальные образы Docker для .NET Core публикуются в реестре контейнеров Microsoft (MCR) и доступ к ним можно получить в [репозитории Microsoft .NET Core Docker Hub](https://hub.docker.com/_/microsoft-dotnet-core/).</span><span class="sxs-lookup"><span data-stu-id="e92e5-190">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="e92e5-191">Каждый репозиторий содержит рабочие образы для разных сочетаний .NET (пакета SDK или среды выполнения) и операционной системы.</span><span class="sxs-lookup"><span data-stu-id="e92e5-191">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="e92e5-192">Корпорация Майкрософт предоставляет образы, которые предназначены для конкретных сценариев.</span><span class="sxs-lookup"><span data-stu-id="e92e5-192">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="e92e5-193">Например [репозиторий ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) содержит образы, которые предназначены для запуска приложений ASP.NET Core в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="e92e5-193">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="e92e5-194">Дополнительные сведения об использовании .NET Core в контейнере Docker см. в статьях [Введение в .NET и Docker](../docker/introduction.md) и [Примеры](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="e92e5-194">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="e92e5-195">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="e92e5-195">Next steps</span></span>

::: zone pivot="os-windows"

- <span data-ttu-id="e92e5-196">[Учебник. Hello World](../tutorials/with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="e92e5-196">[Tutorial: Hello World tutorial](../tutorials/with-visual-studio.md).</span></span>
- <span data-ttu-id="e92e5-197">[Учебник. Создание приложения с помощью Visual Studio Code](../tutorials/with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="e92e5-197">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="e92e5-198">[Учебник. Контейнеризация приложения .NET Core](../docker/build-container.md).</span><span class="sxs-lookup"><span data-stu-id="e92e5-198">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end

::: zone pivot="os-macos"

- <span data-ttu-id="e92e5-199">[Работа с заверением macOS Catalina](macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e92e5-199">[Working with macOS Catalina notarization](macos-notarization-issues.md).</span></span>
- <span data-ttu-id="e92e5-200">[Учебник. Начало работы с macOS](../tutorials/using-on-mac-vs.md).</span><span class="sxs-lookup"><span data-stu-id="e92e5-200">[Tutorial: Get started on macOS](../tutorials/using-on-mac-vs.md).</span></span>
- <span data-ttu-id="e92e5-201">[Учебник. Создание приложения с помощью Visual Studio Code](../tutorials/with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="e92e5-201">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="e92e5-202">[Учебник. Контейнеризация приложения .NET Core](../docker/build-container.md).</span><span class="sxs-lookup"><span data-stu-id="e92e5-202">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end

::: zone pivot="os-linux"

- <span data-ttu-id="e92e5-203">[Учебник. Создание приложения с помощью Visual Studio Code](../tutorials/with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="e92e5-203">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="e92e5-204">[Учебник. Контейнеризация приложения .NET Core](../docker/build-container.md).</span><span class="sxs-lookup"><span data-stu-id="e92e5-204">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end
