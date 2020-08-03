---
title: Установка .NET Core в macOS
description: Сведения о версиях macOS, в которых возможна установка .NET Core.
author: adegeo
ms.author: adegeo
ms.date: 06/25/2020
ms.openlocfilehash: 951e9b6a64d55274729e233b4a2d7728c75d05d4
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302936"
---
# <a name="install-net-core-on-macos"></a><span data-ttu-id="3dc6d-103">Установка .NET Core в macOS</span><span class="sxs-lookup"><span data-stu-id="3dc6d-103">Install .NET Core on macOS</span></span>

> [!div class="op_single_selector"]
>
> - [Установка в Windows](windows.md)
> - [Установка в macOS](macos.md)
> - [Установка на Linux](linux.md)

<span data-ttu-id="3dc6d-107">В этой статье вы узнаете, как установить .NET Core в macOS.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-107">In this article, you'll learn how to install .NET Core on macOS.</span></span> <span data-ttu-id="3dc6d-108">.NET Core состоит из среды выполнения и пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-108">.NET Core is made up of the runtime and the SDK.</span></span> <span data-ttu-id="3dc6d-109">Среда выполнения используется для запуска приложения .NET Core и может не включаться в состав приложения.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-109">The runtime is used to run a .NET Core app and may or may not be included with the app.</span></span> <span data-ttu-id="3dc6d-110">Пакет SDK используется для создания приложений и библиотек .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-110">The SDK is used to create .NET Core apps and libraries.</span></span> <span data-ttu-id="3dc6d-111">Среда выполнения .NET Core всегда устанавливается вместе с пакетом SDK.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-111">The .NET Core runtime is always installed with the SDK.</span></span>

<span data-ttu-id="3dc6d-112">.NET Core 3.1 является последней версией.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-112">The latest version of .NET Core is 3.1.</span></span>

> [!div class="button"]
> [<span data-ttu-id="3dc6d-113">Загрузить .NET Core</span><span class="sxs-lookup"><span data-stu-id="3dc6d-113">Download .NET Core</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="supported-releases"></a><span data-ttu-id="3dc6d-114">Поддерживаемые выпуски</span><span class="sxs-lookup"><span data-stu-id="3dc6d-114">Supported releases</span></span>

<span data-ttu-id="3dc6d-115">В приведенной ниже таблице содержится список поддерживаемых сейчас выпусков .NET Core и версий macOS, в которых они поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-115">The following table is a list of currently supported .NET Core releases and the versions of macOS they're supported on.</span></span> <span data-ttu-id="3dc6d-116">Эти версии будут поддерживаться до [окончания срока поддержки .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="3dc6d-116">These versions remain supported either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span></span>

- <span data-ttu-id="3dc6d-117">Значок ✔️ означает, что версия .NET Core поддерживается.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-117">A ✔️ indicates that the version of .NET Core is still supported.</span></span>
- <span data-ttu-id="3dc6d-118">Значок ❌️ означает, что версия .NET Core не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-118">A ❌ indicates that the version of .NET Core isn't supported.</span></span>

| <span data-ttu-id="3dc6d-119">Операционная система</span><span class="sxs-lookup"><span data-stu-id="3dc6d-119">Operating System</span></span>          | <span data-ttu-id="3dc6d-120">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="3dc6d-120">.NET Core 2.1</span></span> | <span data-ttu-id="3dc6d-121">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="3dc6d-121">.NET Core 3.1</span></span> | <span data-ttu-id="3dc6d-122">Предварительная версия .NET 5</span><span class="sxs-lookup"><span data-stu-id="3dc6d-122">.NET 5 Preview</span></span> |
|---------------------------|---------------|---------------|----------------|
| <span data-ttu-id="3dc6d-123">macOS 10.15 "Catalina"</span><span class="sxs-lookup"><span data-stu-id="3dc6d-123">macOS 10.15 "Catalina"</span></span>    | <span data-ttu-id="3dc6d-124">✔️ 2.1 ([заметки о выпуске][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="3dc6d-124">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="3dc6d-125">✔️ 3.1 ([заметки о выпуске][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="3dc6d-125">✔️ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="3dc6d-126">✔️ 5.0, предварительная версия ([заметки о выпуске][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="3dc6d-126">✔️ 5.0 Preview ([Release notes][release-notes-50])</span></span> |
| <span data-ttu-id="3dc6d-127">macOS 10.14 "Mojave"</span><span class="sxs-lookup"><span data-stu-id="3dc6d-127">macOS 10.14 "Mojave"</span></span>      | <span data-ttu-id="3dc6d-128">✔️ 2.1 ([заметки о выпуске][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="3dc6d-128">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="3dc6d-129">✔️ 3.1 ([заметки о выпуске][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="3dc6d-129">✔️ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="3dc6d-130">✔️ 5.0, предварительная версия ([заметки о выпуске][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="3dc6d-130">✔️ 5.0 Preview ([Release notes][release-notes-50])</span></span> |
| <span data-ttu-id="3dc6d-131">macOS 10.13 "High Sierra"</span><span class="sxs-lookup"><span data-stu-id="3dc6d-131">macOS 10.13 "High Sierra"</span></span> | <span data-ttu-id="3dc6d-132">✔️ 2.1 ([заметки о выпуске][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="3dc6d-132">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="3dc6d-133">✔️ 3.1 ([заметки о выпуске][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="3dc6d-133">✔️ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="3dc6d-134">✔️ 5.0, предварительная версия ([заметки о выпуске][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="3dc6d-134">✔️ 5.0 Preview ([Release notes][release-notes-50])</span></span> |
| <span data-ttu-id="3dc6d-135">macOS 10.12 "Sierra"</span><span class="sxs-lookup"><span data-stu-id="3dc6d-135">macOS 10.12 "Sierra"</span></span>      | <span data-ttu-id="3dc6d-136">✔️ 2.1 ([заметки о выпуске][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="3dc6d-136">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="3dc6d-137">❌ 3.1 ([заметки о выпуске][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="3dc6d-137">❌ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="3dc6d-138">❌ 5.0, предварительная версия ([заметки о выпуске][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="3dc6d-138">❌ 5.0 Preview ([Release notes][release-notes-50])</span></span> |

## <a name="unsupported-releases"></a><span data-ttu-id="3dc6d-139">Неподдерживаемые выпуски</span><span class="sxs-lookup"><span data-stu-id="3dc6d-139">Unsupported releases</span></span>

<span data-ttu-id="3dc6d-140">Следующие версии .NET Core больше ❌ не поддерживаются</span><span class="sxs-lookup"><span data-stu-id="3dc6d-140">The following versions of .NET Core are ❌ no longer supported.</span></span> <span data-ttu-id="3dc6d-141">(но остаются доступными для скачивания):</span><span class="sxs-lookup"><span data-stu-id="3dc6d-141">The downloads for these still remain published:</span></span>

- <span data-ttu-id="3dc6d-142">3.0 ([заметки о выпуске][release-notes-30])</span><span class="sxs-lookup"><span data-stu-id="3dc6d-142">3.0 ([Release notes][release-notes-30])</span></span>
- <span data-ttu-id="3dc6d-143">2.2 ([заметки о выпуске][release-notes-22])</span><span class="sxs-lookup"><span data-stu-id="3dc6d-143">2.2 ([Release notes][release-notes-22])</span></span>
- <span data-ttu-id="3dc6d-144">2.0 ([заметки о выпуске][release-notes-20])</span><span class="sxs-lookup"><span data-stu-id="3dc6d-144">2.0 ([Release notes][release-notes-20])</span></span>

## <a name="runtime-information"></a><span data-ttu-id="3dc6d-145">Сведения о среде выполнения</span><span class="sxs-lookup"><span data-stu-id="3dc6d-145">Runtime information</span></span>

<span data-ttu-id="3dc6d-146">Среда выполнения используется для запуска приложений, созданных с помощью .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-146">The runtime is used to run apps created with .NET Core.</span></span> <span data-ttu-id="3dc6d-147">При публикации приложения автор может включить среду выполнения в его состав.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-147">When an app author publishes an app, they can include the runtime with their app.</span></span> <span data-ttu-id="3dc6d-148">В противном случае устанавливать среду выполнения будет пользователь.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-148">If they don't include the runtime, it's up to the user to install the runtime.</span></span>

<span data-ttu-id="3dc6d-149">В macOS можно установить три различные версии среды выполнения:</span><span class="sxs-lookup"><span data-stu-id="3dc6d-149">There are three different runtimes you can install on macOS:</span></span>

<span data-ttu-id="3dc6d-150">*Среда выполнения ASP.NET Core*</span><span class="sxs-lookup"><span data-stu-id="3dc6d-150">*ASP.NET Core runtime*</span></span>\
<span data-ttu-id="3dc6d-151">Используется для запуска приложений ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-151">Runs ASP.NET Core apps.</span></span> <span data-ttu-id="3dc6d-152">Включает среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-152">Includes the .NET Core runtime.</span></span>

<span data-ttu-id="3dc6d-153">*Среда выполнения .NET Core*</span><span class="sxs-lookup"><span data-stu-id="3dc6d-153">*.NET Core runtime*</span></span>\
<span data-ttu-id="3dc6d-154">Простейшая среда выполнения, в состав которой не входят какие-либо другие среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-154">This runtime is the simplest runtime and doesn't include any other runtime.</span></span> <span data-ttu-id="3dc6d-155">Чтобы обеспечить максимальный уровень совместимости с приложениями .NET Core, настоятельно рекомендуется устанавливать *среду выполнения ASP.NET Core*.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-155">It's highly recommended that you install *ASP.NET Core runtime* for the best compatibility with .NET Core apps.</span></span>

> [!div class="button"]
> [<span data-ttu-id="3dc6d-156">Скачать среду выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="3dc6d-156">Download .NET Core Runtime</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="sdk-information"></a><span data-ttu-id="3dc6d-157">Сведения о пакете SDK</span><span class="sxs-lookup"><span data-stu-id="3dc6d-157">SDK information</span></span>

<span data-ttu-id="3dc6d-158">Пакет SDK используется для создания и публикации приложений и библиотек .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-158">The SDK is used to build and publish .NET Core apps and libraries.</span></span> <span data-ttu-id="3dc6d-159">При установке пакета SDK также устанавливаются обе [среды выполнения](#runtime-information): ASP.NET Core и .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-159">Installing the SDK includes both [runtimes](#runtime-information): ASP.NET Core and .NET Core.</span></span>

> [!div class="button"]
> [<span data-ttu-id="3dc6d-160">Скачать пакет SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="3dc6d-160">Download .NET Core SDK</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="dependencies"></a><span data-ttu-id="3dc6d-161">Зависимости</span><span class="sxs-lookup"><span data-stu-id="3dc6d-161">Dependencies</span></span>

<span data-ttu-id="3dc6d-162">Платформа .NET Core поддерживается в следующих выпусках macOS:</span><span class="sxs-lookup"><span data-stu-id="3dc6d-162">.NET Core is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="3dc6d-163">Символ `+` представляет минимальную версию.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-163">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="3dc6d-164">Версия .NET Core</span><span class="sxs-lookup"><span data-stu-id="3dc6d-164">.NET Core Version</span></span> | <span data-ttu-id="3dc6d-165">macOS</span><span class="sxs-lookup"><span data-stu-id="3dc6d-165">macOS</span></span>                 | <span data-ttu-id="3dc6d-166">Архитектуры</span><span class="sxs-lookup"><span data-stu-id="3dc6d-166">Architectures</span></span> |     |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="3dc6d-167">3.1</span><span class="sxs-lookup"><span data-stu-id="3dc6d-167">3.1</span></span>               | <span data-ttu-id="3dc6d-168">High Sierra (10.13+)</span><span class="sxs-lookup"><span data-stu-id="3dc6d-168">High Sierra (10.13+)</span></span>  | <span data-ttu-id="3dc6d-169">X64</span><span class="sxs-lookup"><span data-stu-id="3dc6d-169">x64</span></span> | [<span data-ttu-id="3dc6d-170">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="3dc6d-170">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="3dc6d-171">3.0</span><span class="sxs-lookup"><span data-stu-id="3dc6d-171">3.0</span></span>               | <span data-ttu-id="3dc6d-172">High Sierra (10.13+)</span><span class="sxs-lookup"><span data-stu-id="3dc6d-172">High Sierra (10.13+)</span></span>  | <span data-ttu-id="3dc6d-173">X64</span><span class="sxs-lookup"><span data-stu-id="3dc6d-173">x64</span></span> | [<span data-ttu-id="3dc6d-174">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="3dc6d-174">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="3dc6d-175">2.2</span><span class="sxs-lookup"><span data-stu-id="3dc6d-175">2.2</span></span>               | <span data-ttu-id="3dc6d-176">Sierra (10.12+)</span><span class="sxs-lookup"><span data-stu-id="3dc6d-176">Sierra (10.12+)</span></span>       | <span data-ttu-id="3dc6d-177">X64</span><span class="sxs-lookup"><span data-stu-id="3dc6d-177">x64</span></span> | [<span data-ttu-id="3dc6d-178">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="3dc6d-178">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="3dc6d-179">2.1</span><span class="sxs-lookup"><span data-stu-id="3dc6d-179">2.1</span></span>               | <span data-ttu-id="3dc6d-180">Sierra (10.12+)</span><span class="sxs-lookup"><span data-stu-id="3dc6d-180">Sierra (10.12+)</span></span>       | <span data-ttu-id="3dc6d-181">X64</span><span class="sxs-lookup"><span data-stu-id="3dc6d-181">x64</span></span> | [<span data-ttu-id="3dc6d-182">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="3dc6d-182">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

<span data-ttu-id="3dc6d-183">Начиная с macOS Catalina (версия 10.15) все программное обеспечение, созданное после 1 июня 2019 года и распространяемое с идентификатором разработчика, должно быть заверено.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-183">Beginning with macOS Catalina (version 10.15), all software built after June 1, 2019 that is distributed with Developer ID, must be notarized.</span></span> <span data-ttu-id="3dc6d-184">Это требование относится к среде выполнения .NET Core, пакету SDK для .NET Core и программному обеспечению, созданному с помощью .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-184">This requirement applies to the .NET Core runtime, .NET Core SDK, and software created with .NET Core.</span></span>

<span data-ttu-id="3dc6d-185">Установщики для .NET Core (среда выполнения и пакет SDK) версии 3.1, 3.0 и 2.1 были заверены с 18 февраля 2020 г.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-185">The installers for .NET Core (both runtime and SDK) versions 3.1, 3.0, and 2.1, have been notarized since February 18, 2020.</span></span> <span data-ttu-id="3dc6d-186">Более ранние версии не заверены.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-186">Prior released versions aren't notarized.</span></span> <span data-ttu-id="3dc6d-187">При запуске незаверенного приложения появится ошибка, аналогичная следующей:</span><span class="sxs-lookup"><span data-stu-id="3dc6d-187">If you run a non-notarized app, you'll see an error similar to the following image:</span></span>

![Оповещение о заверении macOS Catalina](media/dependencies/macos-notarized-pkg-warning.png)

<span data-ttu-id="3dc6d-189">Дополнительные сведения о том, как принудительное заверение влияет на .NET Core (и ваши приложения .NET Core), см. в разделе [Работа с заверением macOS Catalina](macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3dc6d-189">For more information about how enforced-notarization affects .NET Core (and your .NET Core apps), see [Working with macOS Catalina Notarization](macos-notarization-issues.md).</span></span>

## <a name="libgdiplus"></a><span data-ttu-id="3dc6d-190">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="3dc6d-190">libgdiplus</span></span>

<span data-ttu-id="3dc6d-191">Приложения .NET Core, которые используют сборку *System.Drawing.Common*, требуют установки libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-191">.NET Core applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="3dc6d-192">Легко получить libgdiplus можно с помощью диспетчера пакетов [Homebrew ("brew")](https://brew.sh/) для macOS.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-192">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="3dc6d-193">После установки *brew* установите libgdiplus, выполнив следующие команды в окне терминала (аналог командной строки):</span><span class="sxs-lookup"><span data-stu-id="3dc6d-193">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

## <a name="install-with-an-installer"></a><span data-ttu-id="3dc6d-194">Установка с помощью установщика</span><span class="sxs-lookup"><span data-stu-id="3dc6d-194">Install with an installer</span></span>

<span data-ttu-id="3dc6d-195">В macOS есть автономные установщики, которые можно использовать для установки пакета SDK для .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="3dc6d-195">macOS has standalone installers that can be used to install the .NET Core 3.1 SDK:</span></span>

- [<span data-ttu-id="3dc6d-196">Процессоры x64 (64-разрядные)</span><span class="sxs-lookup"><span data-stu-id="3dc6d-196">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## <a name="download-and-manually-install"></a><span data-ttu-id="3dc6d-197">Скачивание и установка вручную</span><span class="sxs-lookup"><span data-stu-id="3dc6d-197">Download and manually install</span></span>

<!-- Note, this content is taken from includes/linux-install-manual.md but changed for macOS. Any fixes should be applied there too, though content may be different -->

<span data-ttu-id="3dc6d-198">В качестве альтернативы установщикам macOS для .NET Core можно скачать и вручную установить пакет SDK и среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-198">As an alternative to the macOS installers for .NET Core, you can download and manually install the SDK and runtime.</span></span> <span data-ttu-id="3dc6d-199">Ручная установка как правило выполняется в рамках тестирования непрерывной интеграции.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-199">Manual install is usually performed as part of continuous integration testing.</span></span> <span data-ttu-id="3dc6d-200">В большинстве случаев разработчикам и пользователям рекомендуется использовать [установщик](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="3dc6d-200">For a developer or user, it's generally better to use an [installer](https://dotnet.microsoft.com/download/dotnet-core).</span></span>

<span data-ttu-id="3dc6d-201">При установке пакета SDK для .NET Core не нужно устанавливать соответствующую среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-201">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="3dc6d-202">Сначала скачайте **двоичный** выпуск пакета SDK или среды выполнения с одного из следующих сайтов:</span><span class="sxs-lookup"><span data-stu-id="3dc6d-202">First, download a **binary** release for either the SDK or the runtime from one of the following sites:</span></span>

- <span data-ttu-id="3dc6d-203">✔️ [Предварительные версии скачиваемых файлов .NET 5.0](https://dotnet.microsoft.com/download/dotnet/5.0)</span><span class="sxs-lookup"><span data-stu-id="3dc6d-203">✔️ [.NET 5.0 preview downloads](https://dotnet.microsoft.com/download/dotnet/5.0)</span></span>
- <span data-ttu-id="3dc6d-204">✔️ [Скачиваемые файлы .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span><span class="sxs-lookup"><span data-stu-id="3dc6d-204">✔️ [.NET Core 3.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span></span>
- <span data-ttu-id="3dc6d-205">✔️ [Скачиваемые файлы .NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span><span class="sxs-lookup"><span data-stu-id="3dc6d-205">✔️ [.NET Core 2.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span></span>
- [<span data-ttu-id="3dc6d-206">Все скачиваемые файлы для .NET Core</span><span class="sxs-lookup"><span data-stu-id="3dc6d-206">All .NET Core downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

<span data-ttu-id="3dc6d-207">Извлеките скачанный файл и используйте команду `export`, чтобы задать переменные, используемые .NET Core, а затем проверьте включение .NET Core в переменную PATH.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-207">Next, extract the downloaded file and use the `export` command to set variables used by .NET Core and then ensure .NET Core is in PATH.</span></span>

<span data-ttu-id="3dc6d-208">Чтобы извлечь среду выполнения и сделать команды .NET Core CLI доступными в терминале, сначала скачайте двоичный выпуск .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-208">To extract the runtime and make the .NET Core CLI commands available at the terminal, first download a .NET Core binary release.</span></span> <span data-ttu-id="3dc6d-209">Затем откройте терминал и выполните следующие команды в каталоге с сохраненным файлом.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-209">Then, open a terminal and run the following commands from the directory where the file was saved.</span></span> <span data-ttu-id="3dc6d-210">Имя файла архива может отличаться в зависимости от скачанных файлов.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-210">The archive file name may be different depending on what you downloaded.</span></span>

<span data-ttu-id="3dc6d-211">**Извлеките среду выполнения, используя следующую команду**:</span><span class="sxs-lookup"><span data-stu-id="3dc6d-211">**Use the following command to extract the runtime**:</span></span>

```bash
mkdir -p "$HOME/dotnet" && tar zxf aspnetcore-runtime-3.1.5-osx-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

<span data-ttu-id="3dc6d-212">**Извлеките пакет SDK, используя следующую команду**:</span><span class="sxs-lookup"><span data-stu-id="3dc6d-212">**Use the following command to extract the SDK**:</span></span>

```bash
mkdir -p "$HOME/dotnet" && tar zxf dotnet-sdk-3.1.301-osx-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="3dc6d-213">Приведенные выше команды `export` сделают команды .NET Core CLI доступными только для сеанса терминала, в котором производился запуск.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-213">The preceding `export` commands only make the .NET Core CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="3dc6d-214">Вы можете изменить профиль оболочки, чтобы добавить команды окончательно.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-214">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="3dc6d-215">Существует несколько различных оболочек, доступных для Linux, и каждая из них имеет свой профиль.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-215">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="3dc6d-216">Пример:</span><span class="sxs-lookup"><span data-stu-id="3dc6d-216">For example:</span></span>
>
> - <span data-ttu-id="3dc6d-217">**Оболочка Bash**: *~/.bash_profile*, *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="3dc6d-217">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="3dc6d-218">**Оболочка Korn**: *~/.kshrc* или *.profile*</span><span class="sxs-lookup"><span data-stu-id="3dc6d-218">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="3dc6d-219">**Оболочка Z**: *~/.zshrc* или *.zprofile*</span><span class="sxs-lookup"><span data-stu-id="3dc6d-219">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
>
> <span data-ttu-id="3dc6d-220">Измените соответствующий исходный файл оболочки и добавьте `:$HOME/dotnet` в конец существующего оператора `PATH`.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-220">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="3dc6d-221">Если оператор `PATH` не указан, добавьте новую строку с `export PATH=$PATH:$HOME/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-221">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="3dc6d-222">Кроме того, добавьте `export DOTNET_ROOT=$HOME/dotnet` в конец файла.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-222">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

<span data-ttu-id="3dc6d-223">Такой подход позволяет устанавливать разные версии в отдельные расположения и выбирать, какие из них следует использовать для каждого приложения.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-223">This approach lets you install different versions into separate locations and choose explicitly which one to use by which application.</span></span>

## <a name="install-with-visual-studio-for-mac"></a><span data-ttu-id="3dc6d-224">Установка с помощью Visual Studio для Mac</span><span class="sxs-lookup"><span data-stu-id="3dc6d-224">Install with Visual Studio for Mac</span></span>

<span data-ttu-id="3dc6d-225">Visual Studio для Mac устанавливает пакет SDK для .NET Core, если выбрана рабочая нагрузка **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-225">Visual Studio for Mac installs the .NET Core SDK when the **.NET Core** workload is selected.</span></span> <span data-ttu-id="3dc6d-226">Чтобы приступить к разработке в .NET Core на macOS, ознакомьтесь со статьей [Установка Visual Studio 2019 для Mac](/visualstudio/mac/installation).</span><span class="sxs-lookup"><span data-stu-id="3dc6d-226">To get started with .NET Core development on macOS, see [Install Visual Studio 2019 for Mac](/visualstudio/mac/installation).</span></span> <span data-ttu-id="3dc6d-227">В последнем выпуске .NET Core 3.1 необходимо использовать предварительную версию Visual Studio для Mac 8.4.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-227">For the latest release, .NET Core 3.1, you must use the Visual Studio for Mac 8.4 Preview.</span></span>

<span data-ttu-id="3dc6d-228">[![Visual Studio 2019 для Mac с компонентом рабочей нагрузки .NET Core в macOS](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="3dc6d-228">[![macOS Visual Studio 2019 for Mac with .NET Core workload feature](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span></span>

## <a name="install-alongside-visual-studio-code"></a><span data-ttu-id="3dc6d-229">Установка вместе с Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="3dc6d-229">Install alongside Visual Studio Code</span></span>

<span data-ttu-id="3dc6d-230">Visual Studio Code — это эффективный и облегченный редактор исходного кода, который работает на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-230">Visual Studio Code is a powerful and lightweight source code editor that runs on your desktop.</span></span> <span data-ttu-id="3dc6d-231">Visual Studio Code доступен для Windows, macOS и Linux.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-231">Visual Studio Code is available for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="3dc6d-232">Хотя Visual Studio Code не поставляется с автоматическим установщиком .NET Core, таким как Visual Studio, добавление поддержки .NET Core не вызывает затруднений.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-232">While Visual Studio Code doesn't come with an automated .NET Core installer like Visual Studio does, adding .NET Core support is simple.</span></span>

01. <span data-ttu-id="3dc6d-233">[Скачайте и установите Visual Studio Code](https://code.visualstudio.com/Download).</span><span class="sxs-lookup"><span data-stu-id="3dc6d-233">[Download and install Visual Studio Code](https://code.visualstudio.com/Download).</span></span>
01. <span data-ttu-id="3dc6d-234">[Скачайте и установите пакет SDK для .NET Core](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="3dc6d-234">[Download and install the .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core).</span></span>
01. <span data-ttu-id="3dc6d-235">[Установите расширение C# из Marketplace для Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span><span class="sxs-lookup"><span data-stu-id="3dc6d-235">[Install the C# extension from the Visual Studio Code marketplace](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span></span>

## <a name="install-with-bash-automation"></a><span data-ttu-id="3dc6d-236">Установка с помощью функции автоматизации Bash</span><span class="sxs-lookup"><span data-stu-id="3dc6d-236">Install with bash automation</span></span>

<span data-ttu-id="3dc6d-237">[Сценарии dotnet-install](../tools/dotnet-install-script.md) используются для автоматизации установок среды выполнения и их осуществления без прав администратора.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-237">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="3dc6d-238">Вы можете скачать сценарий со [страницы справочника по сценариям dotnet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="3dc6d-238">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="3dc6d-239">Этот сценарий по умолчанию устанавливает последнюю версию [с долгосрочной поддержкой (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), которой сейчас является .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-239">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="3dc6d-240">Вы можете выбрать конкретный выпуск, указав параметр `current`.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-240">You can choose a specific release by specifying the `current` switch.</span></span> <span data-ttu-id="3dc6d-241">Включите параметр `runtime` для установки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-241">Include the `runtime` switch to install a runtime.</span></span> <span data-ttu-id="3dc6d-242">В противном случае сценарий устанавливает пакет [SDK](sdk.md).</span><span class="sxs-lookup"><span data-stu-id="3dc6d-242">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```bash
./dotnet-install.sh --channel 3.1 --runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="3dc6d-243">Приведенная выше команда устанавливает среду выполнения ASP.NET Core для максимальной совместимости.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-243">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="3dc6d-244">Среда выполнения ASP.NET Core также включает в себя стандартную среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-244">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

## <a name="docker"></a><span data-ttu-id="3dc6d-245">Docker</span><span class="sxs-lookup"><span data-stu-id="3dc6d-245">Docker</span></span>

<span data-ttu-id="3dc6d-246">Контейнеры обеспечивают простой способ изоляции приложения от остальной части основной системы.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-246">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="3dc6d-247">Контейнеры на одном компьютере совместно использую только ядро, а также используют ресурсы, которые передаются в приложение.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-247">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="3dc6d-248">.NET Core можно выполнять в контейнере Docker.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-248">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="3dc6d-249">Официальные образы Docker для .NET Core публикуются в реестре контейнеров Microsoft (MCR) и доступ к ним можно получить в [репозитории Microsoft .NET Core Docker Hub](https://hub.docker.com/_/microsoft-dotnet-core/).</span><span class="sxs-lookup"><span data-stu-id="3dc6d-249">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="3dc6d-250">Каждый репозиторий содержит рабочие образы для разных сочетаний .NET (пакета SDK или среды выполнения) и операционной системы.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-250">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="3dc6d-251">Корпорация Майкрософт предоставляет образы, которые предназначены для конкретных сценариев.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-251">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="3dc6d-252">Например [репозиторий ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) содержит образы, которые предназначены для запуска приложений ASP.NET Core в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="3dc6d-252">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="3dc6d-253">Дополнительные сведения об использовании .NET Core в контейнере Docker см. в статьях [Введение в .NET и Docker](../docker/introduction.md) и [Примеры](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="3dc6d-253">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="3dc6d-254">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="3dc6d-254">Next steps</span></span>

- <span data-ttu-id="3dc6d-255">[Проверка того, установлена ли платформа .NET Core](how-to-detect-installed-versions.md?pivots=os-macos).</span><span class="sxs-lookup"><span data-stu-id="3dc6d-255">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md?pivots=os-macos).</span></span>
- <span data-ttu-id="3dc6d-256">[Работа с заверением macOS Catalina](macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3dc6d-256">[Working with macOS Catalina notarization](macos-notarization-issues.md).</span></span>
- <span data-ttu-id="3dc6d-257">[Учебник. Начало работы с macOS](../tutorials/with-visual-studio-mac.md).</span><span class="sxs-lookup"><span data-stu-id="3dc6d-257">[Tutorial: Get started on macOS](../tutorials/with-visual-studio-mac.md).</span></span>
- <span data-ttu-id="3dc6d-258">[Учебник. Создание приложения с помощью Visual Studio Code](../tutorials/with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="3dc6d-258">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="3dc6d-259">[Учебник. Контейнеризация приложения .NET Core](../docker/build-container.md).</span><span class="sxs-lookup"><span data-stu-id="3dc6d-259">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

[release-notes-21]: https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md
[release-notes-31]: https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md
[release-notes-50]: https://github.com/dotnet/core/blob/master/release-notes/5.0/5.0-supported-os.md
[release-notes-20]: https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md
[release-notes-22]: https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md
[release-notes-30]: https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md
