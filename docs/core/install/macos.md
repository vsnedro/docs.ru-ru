---
title: Установка .NET в macOS
description: Сведения о версиях macOS, в которых возможна установка .NET.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 983c5d2c04b87759b898f449bc092161b03c8ace
ms.sourcegitcommit: c38bf879a2611ff46aacdd529b9f2725f93e18a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2020
ms.locfileid: "94594460"
---
# <a name="install-net-on-macos"></a><span data-ttu-id="44e10-103">Установка .NET в macOS</span><span class="sxs-lookup"><span data-stu-id="44e10-103">Install .NET on macOS</span></span>

> [!div class="op_single_selector"]
>
> - [Установка в Windows](windows.md)
> - [Установка в macOS](macos.md)
> - [Установка на Linux](linux.md)

<span data-ttu-id="44e10-107">В этой статье вы узнаете, как установить .NET в macOS.</span><span class="sxs-lookup"><span data-stu-id="44e10-107">In this article, you'll learn how to install .NET on macOS.</span></span> <span data-ttu-id="44e10-108">.NET состоит из среды выполнения и пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="44e10-108">.NET is made up of the runtime and the SDK.</span></span> <span data-ttu-id="44e10-109">Среда выполнения используется для запуска приложения .NET и может не включаться в состав приложения.</span><span class="sxs-lookup"><span data-stu-id="44e10-109">The runtime is used to run a .NET app and may or may not be included with the app.</span></span> <span data-ttu-id="44e10-110">Пакет SDK используется для создания приложений и библиотек .NET.</span><span class="sxs-lookup"><span data-stu-id="44e10-110">The SDK is used to create .NET apps and libraries.</span></span> <span data-ttu-id="44e10-111">Среда выполнения .NET всегда устанавливается вместе с пакетом SDK.</span><span class="sxs-lookup"><span data-stu-id="44e10-111">The .NET runtime is always installed with the SDK.</span></span>

<span data-ttu-id="44e10-112">.NET 5.0 является последней версией.</span><span class="sxs-lookup"><span data-stu-id="44e10-112">The latest version of .NET is 5.0.</span></span>

> [!div class="button"]
> [<span data-ttu-id="44e10-113">Загрузить .NET Core</span><span class="sxs-lookup"><span data-stu-id="44e10-113">Download .NET Core</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="supported-releases"></a><span data-ttu-id="44e10-114">Поддерживаемые выпуски</span><span class="sxs-lookup"><span data-stu-id="44e10-114">Supported releases</span></span>

<span data-ttu-id="44e10-115">В приведенной ниже таблице содержится список поддерживаемых сейчас выпусков .NET и версий macOS, в которых они поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="44e10-115">The following table is a list of currently supported .NET releases and the versions of macOS they're supported on.</span></span> <span data-ttu-id="44e10-116">Эти версии будут поддерживаться до [окончания срока поддержки .NET](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="44e10-116">These versions remain supported either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span></span>

- <span data-ttu-id="44e10-117">Значок ✔️ означает, что версия .NET Core поддерживается.</span><span class="sxs-lookup"><span data-stu-id="44e10-117">A ✔️ indicates that the version of .NET Core is still supported.</span></span>
- <span data-ttu-id="44e10-118">Значок ❌️ означает, что версия .NET Core не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="44e10-118">A ❌ indicates that the version of .NET Core isn't supported.</span></span>

| <span data-ttu-id="44e10-119">Операционная система</span><span class="sxs-lookup"><span data-stu-id="44e10-119">Operating System</span></span>          | <span data-ttu-id="44e10-120">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="44e10-120">.NET Core 2.1</span></span> | <span data-ttu-id="44e10-121">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="44e10-121">.NET Core 3.1</span></span> | <span data-ttu-id="44e10-122">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="44e10-122">.NET 5.0</span></span> |
|---------------------------|---------------|---------------|----------------|
| <span data-ttu-id="44e10-123">macOS 10.15 "Catalina"</span><span class="sxs-lookup"><span data-stu-id="44e10-123">macOS 10.15 "Catalina"</span></span>    | <span data-ttu-id="44e10-124">✔️ 2.1 ([заметки о выпуске][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="44e10-124">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="44e10-125">✔️ 3.1 ([заметки о выпуске][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="44e10-125">✔️ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="44e10-126">✔️ 5.0 ([заметки о выпуске][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="44e10-126">✔️ 5.0 ([Release notes][release-notes-50])</span></span> |
| <span data-ttu-id="44e10-127">macOS 10.14 "Mojave"</span><span class="sxs-lookup"><span data-stu-id="44e10-127">macOS 10.14 "Mojave"</span></span>      | <span data-ttu-id="44e10-128">✔️ 2.1 ([заметки о выпуске][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="44e10-128">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="44e10-129">✔️ 3.1 ([заметки о выпуске][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="44e10-129">✔️ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="44e10-130">✔️ 5.0 ([заметки о выпуске][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="44e10-130">✔️ 5.0 ([Release notes][release-notes-50])</span></span> |
| <span data-ttu-id="44e10-131">macOS 10.13 "High Sierra"</span><span class="sxs-lookup"><span data-stu-id="44e10-131">macOS 10.13 "High Sierra"</span></span> | <span data-ttu-id="44e10-132">✔️ 2.1 ([заметки о выпуске][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="44e10-132">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="44e10-133">✔️ 3.1 ([заметки о выпуске][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="44e10-133">✔️ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="44e10-134">✔️ 5.0 ([заметки о выпуске][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="44e10-134">✔️ 5.0 ([Release notes][release-notes-50])</span></span> |
| <span data-ttu-id="44e10-135">macOS 10.12 "Sierra"</span><span class="sxs-lookup"><span data-stu-id="44e10-135">macOS 10.12 "Sierra"</span></span>      | <span data-ttu-id="44e10-136">✔️ 2.1 ([заметки о выпуске][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="44e10-136">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="44e10-137">❌ 3.1 ([заметки о выпуске][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="44e10-137">❌ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="44e10-138">❌ 5.0 ([заметки о выпуске][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="44e10-138">❌ 5.0 ([Release notes][release-notes-50])</span></span> |

## <a name="unsupported-releases"></a><span data-ttu-id="44e10-139">Неподдерживаемые выпуски</span><span class="sxs-lookup"><span data-stu-id="44e10-139">Unsupported releases</span></span>

<span data-ttu-id="44e10-140">Следующие версии .NET больше не поддерживаются (❌).</span><span class="sxs-lookup"><span data-stu-id="44e10-140">The following versions of .NET are ❌ no longer supported.</span></span> <span data-ttu-id="44e10-141">(но остаются доступными для скачивания):</span><span class="sxs-lookup"><span data-stu-id="44e10-141">The downloads for these still remain published:</span></span>

- <span data-ttu-id="44e10-142">3.0 ([заметки о выпуске][release-notes-30])</span><span class="sxs-lookup"><span data-stu-id="44e10-142">3.0 ([Release notes][release-notes-30])</span></span>
- <span data-ttu-id="44e10-143">2.2 ([заметки о выпуске][release-notes-22])</span><span class="sxs-lookup"><span data-stu-id="44e10-143">2.2 ([Release notes][release-notes-22])</span></span>
- <span data-ttu-id="44e10-144">2.0 ([заметки о выпуске][release-notes-20])</span><span class="sxs-lookup"><span data-stu-id="44e10-144">2.0 ([Release notes][release-notes-20])</span></span>

## <a name="runtime-information"></a><span data-ttu-id="44e10-145">Сведения о среде выполнения</span><span class="sxs-lookup"><span data-stu-id="44e10-145">Runtime information</span></span>

<span data-ttu-id="44e10-146">Среда выполнения используется для запуска приложений, созданных с помощью .NET.</span><span class="sxs-lookup"><span data-stu-id="44e10-146">The runtime is used to run apps created with .NET.</span></span> <span data-ttu-id="44e10-147">При публикации приложения автор может включить среду выполнения в его состав.</span><span class="sxs-lookup"><span data-stu-id="44e10-147">When an app author publishes an app, they can include the runtime with their app.</span></span> <span data-ttu-id="44e10-148">В противном случае устанавливать среду выполнения будет пользователь.</span><span class="sxs-lookup"><span data-stu-id="44e10-148">If they don't include the runtime, it's up to the user to install the runtime.</span></span>

<span data-ttu-id="44e10-149">В macOS можно установить три различные версии среды выполнения:</span><span class="sxs-lookup"><span data-stu-id="44e10-149">There are three different runtimes you can install on macOS:</span></span>

<span data-ttu-id="44e10-150">*Среда выполнения ASP.NET Core*</span><span class="sxs-lookup"><span data-stu-id="44e10-150">*ASP.NET Core runtime*</span></span>\
<span data-ttu-id="44e10-151">Используется для запуска приложений ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="44e10-151">Runs ASP.NET Core apps.</span></span> <span data-ttu-id="44e10-152">Включает среду выполнения .NET.</span><span class="sxs-lookup"><span data-stu-id="44e10-152">Includes the .NET runtime.</span></span>

<span data-ttu-id="44e10-153">*Среда выполнения .NET*</span><span class="sxs-lookup"><span data-stu-id="44e10-153">*.NET runtime*</span></span>\
<span data-ttu-id="44e10-154">Простейшая среда выполнения, в состав которой не входят какие-либо другие среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="44e10-154">This runtime is the simplest runtime and doesn't include any other runtime.</span></span> <span data-ttu-id="44e10-155">Чтобы обеспечить максимальный уровень совместимости с приложениями .NET, настоятельно рекомендуется устанавливать *среду выполнения ASP.NET Core*.</span><span class="sxs-lookup"><span data-stu-id="44e10-155">It's highly recommended that you install *ASP.NET Core runtime* for the best compatibility with .NET apps.</span></span>

> [!div class="button"]
> [<span data-ttu-id="44e10-156">Загрузка среды выполнения .NET</span><span class="sxs-lookup"><span data-stu-id="44e10-156">Download .NET Runtime</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="sdk-information"></a><span data-ttu-id="44e10-157">Сведения о пакете SDK</span><span class="sxs-lookup"><span data-stu-id="44e10-157">SDK information</span></span>

<span data-ttu-id="44e10-158">Пакет SDK используется для создания и публикации приложений и библиотек .NET.</span><span class="sxs-lookup"><span data-stu-id="44e10-158">The SDK is used to build and publish .NET apps and libraries.</span></span> <span data-ttu-id="44e10-159">При установке пакета SDK также устанавливаются обе [среды выполнения](#runtime-information): ASP.NET Core и .NET.</span><span class="sxs-lookup"><span data-stu-id="44e10-159">Installing the SDK includes both [runtimes](#runtime-information): ASP.NET Core and .NET.</span></span>

## <a name="dependencies"></a><span data-ttu-id="44e10-160">Зависимости</span><span class="sxs-lookup"><span data-stu-id="44e10-160">Dependencies</span></span>

<span data-ttu-id="44e10-161">Платформа .NET поддерживается в следующих выпусках macOS:</span><span class="sxs-lookup"><span data-stu-id="44e10-161">.NET is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="44e10-162">Символ `+` представляет минимальную версию.</span><span class="sxs-lookup"><span data-stu-id="44e10-162">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="44e10-163">Версия .NET Core</span><span class="sxs-lookup"><span data-stu-id="44e10-163">.NET Core Version</span></span> | <span data-ttu-id="44e10-164">macOS</span><span class="sxs-lookup"><span data-stu-id="44e10-164">macOS</span></span>                 | <span data-ttu-id="44e10-165">Архитектуры</span><span class="sxs-lookup"><span data-stu-id="44e10-165">Architectures</span></span> | <span data-ttu-id="44e10-166">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="44e10-166">More information</span></span>    |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="44e10-167">5,0</span><span class="sxs-lookup"><span data-stu-id="44e10-167">5.0</span></span>               | <span data-ttu-id="44e10-168">High Sierra (10.13+)</span><span class="sxs-lookup"><span data-stu-id="44e10-168">High Sierra (10.13+)</span></span>  | <span data-ttu-id="44e10-169">X64</span><span class="sxs-lookup"><span data-stu-id="44e10-169">x64</span></span> | [<span data-ttu-id="44e10-170">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="44e10-170">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/5.0/5.0-supported-os.md) |
| <span data-ttu-id="44e10-171">3.1</span><span class="sxs-lookup"><span data-stu-id="44e10-171">3.1</span></span>               | <span data-ttu-id="44e10-172">High Sierra (10.13+)</span><span class="sxs-lookup"><span data-stu-id="44e10-172">High Sierra (10.13+)</span></span>  | <span data-ttu-id="44e10-173">X64</span><span class="sxs-lookup"><span data-stu-id="44e10-173">x64</span></span> | [<span data-ttu-id="44e10-174">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="44e10-174">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="44e10-175">3.0</span><span class="sxs-lookup"><span data-stu-id="44e10-175">3.0</span></span>               | <span data-ttu-id="44e10-176">High Sierra (10.13+)</span><span class="sxs-lookup"><span data-stu-id="44e10-176">High Sierra (10.13+)</span></span>  | <span data-ttu-id="44e10-177">X64</span><span class="sxs-lookup"><span data-stu-id="44e10-177">x64</span></span> | [<span data-ttu-id="44e10-178">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="44e10-178">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="44e10-179">2.2</span><span class="sxs-lookup"><span data-stu-id="44e10-179">2.2</span></span>               | <span data-ttu-id="44e10-180">Sierra (10.12+)</span><span class="sxs-lookup"><span data-stu-id="44e10-180">Sierra (10.12+)</span></span>       | <span data-ttu-id="44e10-181">X64</span><span class="sxs-lookup"><span data-stu-id="44e10-181">x64</span></span> | [<span data-ttu-id="44e10-182">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="44e10-182">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="44e10-183">2.1</span><span class="sxs-lookup"><span data-stu-id="44e10-183">2.1</span></span>               | <span data-ttu-id="44e10-184">Sierra (10.12+)</span><span class="sxs-lookup"><span data-stu-id="44e10-184">Sierra (10.12+)</span></span>       | <span data-ttu-id="44e10-185">X64</span><span class="sxs-lookup"><span data-stu-id="44e10-185">x64</span></span> | [<span data-ttu-id="44e10-186">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="44e10-186">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

<span data-ttu-id="44e10-187">Начиная с macOS Catalina (версия 10.15) все программное обеспечение, созданное после 1 июня 2019 года и распространяемое с идентификатором разработчика, должно быть заверено.</span><span class="sxs-lookup"><span data-stu-id="44e10-187">Beginning with macOS Catalina (version 10.15), all software built after June 1, 2019 that is distributed with Developer ID, must be notarized.</span></span> <span data-ttu-id="44e10-188">Это требование относится к среде выполнения .NET, пакету SDK для .NET и программному обеспечению, созданному с помощью .NET.</span><span class="sxs-lookup"><span data-stu-id="44e10-188">This requirement applies to the .NET runtime, .NET SDK, and software created with .NET.</span></span>

<span data-ttu-id="44e10-189">Среда выполнения и установщики пакета SDK для .NET версии 5.0 и .NET Core 3.1, 3.0 и 2.1 были заверены с 18 февраля 2020 г.</span><span class="sxs-lookup"><span data-stu-id="44e10-189">The runtime and SDK installers for .NET 5.0 and .NET Core 3.1, 3.0, and 2.1, have been notarized since February 18, 2020.</span></span> <span data-ttu-id="44e10-190">Более ранние версии не заверены.</span><span class="sxs-lookup"><span data-stu-id="44e10-190">Prior released versions aren't notarized.</span></span> <span data-ttu-id="44e10-191">При запуске незаверенного приложения появится ошибка, аналогичная следующей:</span><span class="sxs-lookup"><span data-stu-id="44e10-191">If you run a non-notarized app, you'll see an error similar to the following image:</span></span>

![Оповещение о заверении macOS Catalina](media/dependencies/macos-notarized-pkg-warning.png)

<span data-ttu-id="44e10-193">Дополнительные сведения о том, как принудительное заверение влияет на .NET (и ваши приложения .NET), см. в разделе [Работа с заверением macOS Catalina](macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="44e10-193">For more information about how enforced-notarization affects .NET (and your .NET apps), see [Working with macOS Catalina Notarization](macos-notarization-issues.md).</span></span>

## <a name="libgdiplus"></a><span data-ttu-id="44e10-194">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="44e10-194">libgdiplus</span></span>

<span data-ttu-id="44e10-195">Приложения .NET, которые используют сборку *System.Drawing.Common*, требуют установки libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="44e10-195">.NET applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="44e10-196">Легко получить libgdiplus можно с помощью диспетчера пакетов [Homebrew ("brew")](https://brew.sh/) для macOS.</span><span class="sxs-lookup"><span data-stu-id="44e10-196">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="44e10-197">После установки *brew* установите libgdiplus, выполнив следующие команды в окне терминала (аналог командной строки):</span><span class="sxs-lookup"><span data-stu-id="44e10-197">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

## <a name="install-with-an-installer"></a><span data-ttu-id="44e10-198">Установка с помощью установщика</span><span class="sxs-lookup"><span data-stu-id="44e10-198">Install with an installer</span></span>

<span data-ttu-id="44e10-199">В macOS есть автономные установщики, которые можно использовать для установки пакета SDK для .NET 5.0:</span><span class="sxs-lookup"><span data-stu-id="44e10-199">macOS has standalone installers that can be used to install the .NET 5.0 SDK:</span></span>

- [<span data-ttu-id="44e10-200">Процессоры x64 (64-разрядные)</span><span class="sxs-lookup"><span data-stu-id="44e10-200">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/5.0)

## <a name="download-and-manually-install"></a><span data-ttu-id="44e10-201">Скачивание и установка вручную</span><span class="sxs-lookup"><span data-stu-id="44e10-201">Download and manually install</span></span>

<!-- Note, this content is taken from includes/linux-install-manual.md but changed for macOS. Any fixes should be applied there too, though content may be different -->

<span data-ttu-id="44e10-202">В качестве альтернативы установщикам macOS для .NET можно скачать и вручную установить пакет SDK и среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="44e10-202">As an alternative to the macOS installers for .NET, you can download and manually install the SDK and runtime.</span></span> <span data-ttu-id="44e10-203">Ручная установка как правило выполняется в рамках тестирования непрерывной интеграции.</span><span class="sxs-lookup"><span data-stu-id="44e10-203">Manual install is usually performed as part of continuous integration testing.</span></span> <span data-ttu-id="44e10-204">В большинстве случаев разработчикам и пользователям рекомендуется использовать [установщик](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="44e10-204">For a developer or user, it's generally better to use an [installer](https://dotnet.microsoft.com/download/dotnet-core).</span></span>

<span data-ttu-id="44e10-205">При установке пакета SDK для .NET не нужно устанавливать соответствующую среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="44e10-205">If you install .NET SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="44e10-206">Сначала скачайте **двоичный** выпуск пакета SDK или среды выполнения с одного из следующих сайтов:</span><span class="sxs-lookup"><span data-stu-id="44e10-206">First, download a **binary** release for either the SDK or the runtime from one of the following sites:</span></span>

- <span data-ttu-id="44e10-207">✔️ [Скачиваемые файлы для .NET 5.0](https://dotnet.microsoft.com/download/dotnet/5.0)</span><span class="sxs-lookup"><span data-stu-id="44e10-207">✔️ [.NET 5.0 downloads](https://dotnet.microsoft.com/download/dotnet/5.0)</span></span>
- <span data-ttu-id="44e10-208">✔️ [Скачиваемые файлы .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span><span class="sxs-lookup"><span data-stu-id="44e10-208">✔️ [.NET Core 3.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span></span>
- <span data-ttu-id="44e10-209">✔️ [Скачиваемые файлы .NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span><span class="sxs-lookup"><span data-stu-id="44e10-209">✔️ [.NET Core 2.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span></span>
- [<span data-ttu-id="44e10-210">Все скачиваемые файлы для .NET Core</span><span class="sxs-lookup"><span data-stu-id="44e10-210">All .NET Core downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

<span data-ttu-id="44e10-211">Извлеките скачанный файл и используйте команду `export`, чтобы задать переменные, используемые .NET, а затем проверьте включение .NET в переменную PATH.</span><span class="sxs-lookup"><span data-stu-id="44e10-211">Next, extract the downloaded file and use the `export` command to set variables used by .NET and then ensure .NET is in PATH.</span></span>

<span data-ttu-id="44e10-212">Чтобы извлечь среду выполнения и сделать команды .NET CLI доступными в терминале, сначала скачайте двоичный выпуск .NET.</span><span class="sxs-lookup"><span data-stu-id="44e10-212">To extract the runtime and make the .NET CLI commands available at the terminal, first download a .NET binary release.</span></span> <span data-ttu-id="44e10-213">Затем откройте терминал и выполните следующие команды в каталоге с сохраненным файлом.</span><span class="sxs-lookup"><span data-stu-id="44e10-213">Then, open a terminal and run the following commands from the directory where the file was saved.</span></span> <span data-ttu-id="44e10-214">Имя файла архива может отличаться в зависимости от скачанных файлов.</span><span class="sxs-lookup"><span data-stu-id="44e10-214">The archive file name may be different depending on what you downloaded.</span></span>

<span data-ttu-id="44e10-215">**Извлеките среду выполнения, используя следующую команду**:</span><span class="sxs-lookup"><span data-stu-id="44e10-215">**Use the following command to extract the runtime**:</span></span>

```bash
mkdir -p "$HOME/dotnet" && tar zxf aspnetcore-runtime-5.0.0-osx-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

<span data-ttu-id="44e10-216">**Извлеките пакет SDK, используя следующую команду**:</span><span class="sxs-lookup"><span data-stu-id="44e10-216">**Use the following command to extract the SDK**:</span></span>

```bash
mkdir -p "$HOME/dotnet" && tar zxf dotnet-sdk-5.0.100-osx-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="44e10-217">Приведенные выше команды `export` сделают команды .NET CLI доступными только для сеанса терминала, в котором производился запуск.</span><span class="sxs-lookup"><span data-stu-id="44e10-217">The preceding `export` commands only make the .NET CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="44e10-218">Вы можете изменить профиль оболочки, чтобы добавить команды окончательно.</span><span class="sxs-lookup"><span data-stu-id="44e10-218">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="44e10-219">Существует несколько различных оболочек, доступных для Linux, и каждая из них имеет свой профиль.</span><span class="sxs-lookup"><span data-stu-id="44e10-219">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="44e10-220">Пример:</span><span class="sxs-lookup"><span data-stu-id="44e10-220">For example:</span></span>
>
> - <span data-ttu-id="44e10-221">**Оболочка Bash**: *~/.bash_profile*, *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="44e10-221">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="44e10-222">**Оболочка Korn**: *~/.kshrc* или *.profile*</span><span class="sxs-lookup"><span data-stu-id="44e10-222">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="44e10-223">**Оболочка Z**: *~/.zshrc* или *.zprofile*</span><span class="sxs-lookup"><span data-stu-id="44e10-223">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
>
> <span data-ttu-id="44e10-224">Измените соответствующий исходный файл оболочки и добавьте `:$HOME/dotnet` в конец существующего оператора `PATH`.</span><span class="sxs-lookup"><span data-stu-id="44e10-224">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="44e10-225">Если оператор `PATH` не указан, добавьте новую строку с `export PATH=$PATH:$HOME/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="44e10-225">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="44e10-226">Кроме того, добавьте `export DOTNET_ROOT=$HOME/dotnet` в конец файла.</span><span class="sxs-lookup"><span data-stu-id="44e10-226">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

<span data-ttu-id="44e10-227">Такой подход позволяет устанавливать разные версии в отдельные расположения и выбирать, какие из них следует использовать для каждого приложения.</span><span class="sxs-lookup"><span data-stu-id="44e10-227">This approach lets you install different versions into separate locations and choose explicitly which one to use by which application.</span></span>

## <a name="install-with-visual-studio-for-mac"></a><span data-ttu-id="44e10-228">Установка с помощью Visual Studio для Mac</span><span class="sxs-lookup"><span data-stu-id="44e10-228">Install with Visual Studio for Mac</span></span>

<span data-ttu-id="44e10-229">Visual Studio для Mac устанавливает пакет SDK для .NET, если выбрана рабочая нагрузка **.NET**.</span><span class="sxs-lookup"><span data-stu-id="44e10-229">Visual Studio for Mac installs the .NET SDK when the **.NET** workload is selected.</span></span> <span data-ttu-id="44e10-230">Чтобы приступить к разработке в .NET на macOS, ознакомьтесь со статьей [Установка Visual Studio 2019 для Mac](/visualstudio/mac/installation).</span><span class="sxs-lookup"><span data-stu-id="44e10-230">To get started with .NET development on macOS, see [Install Visual Studio 2019 for Mac](/visualstudio/mac/installation).</span></span>

| <span data-ttu-id="44e10-231">Версия пакета SDK для .NET</span><span class="sxs-lookup"><span data-stu-id="44e10-231">.NET SDK version</span></span>      | <span data-ttu-id="44e10-232">Версия Visual Studio</span><span class="sxs-lookup"><span data-stu-id="44e10-232">Visual Studio version</span></span>                      |
| --------------------- | ------------------------------------------ |
| <span data-ttu-id="44e10-233">5,0</span><span class="sxs-lookup"><span data-stu-id="44e10-233">5.0</span></span>                   | <span data-ttu-id="44e10-234">Visual Studio 2019 для Mac версии 8.8 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="44e10-234">Visual Studio 2019 for Mac version 8.8 or higher.</span></span> |
| <span data-ttu-id="44e10-235">3.1</span><span class="sxs-lookup"><span data-stu-id="44e10-235">3.1</span></span>                   | <span data-ttu-id="44e10-236">Visual Studio 2019 для Mac версии 8.4 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="44e10-236">Visual Studio 2019 for Mac version 8.4 or higher.</span></span> |
| <span data-ttu-id="44e10-237">2.1</span><span class="sxs-lookup"><span data-stu-id="44e10-237">2.1</span></span>                   | <span data-ttu-id="44e10-238">Visual Studio 2019 для Mac версии 8.0 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="44e10-238">Visual Studio 2019 for Mac version 8.0 or higher.</span></span> |

<span data-ttu-id="44e10-239">[![Visual Studio 2019 для Mac с компонентом рабочей нагрузки .NET в macOS](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="44e10-239">[![macOS Visual Studio 2019 for Mac with .NET workload feature](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span></span>

## <a name="install-alongside-visual-studio-code"></a><span data-ttu-id="44e10-240">Установка вместе с Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="44e10-240">Install alongside Visual Studio Code</span></span>

<span data-ttu-id="44e10-241">Visual Studio Code — это эффективный и облегченный редактор исходного кода, который работает на компьютере.</span><span class="sxs-lookup"><span data-stu-id="44e10-241">Visual Studio Code is a powerful and lightweight source code editor that runs on your desktop.</span></span> <span data-ttu-id="44e10-242">Visual Studio Code доступен для Windows, macOS и Linux.</span><span class="sxs-lookup"><span data-stu-id="44e10-242">Visual Studio Code is available for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="44e10-243">Хотя Visual Studio Code не поставляется с автоматическим установщиком .NET, таким как Visual Studio, добавление поддержки .NET не вызывает затруднений.</span><span class="sxs-lookup"><span data-stu-id="44e10-243">While Visual Studio Code doesn't come with an automated .NET installer like Visual Studio does, adding .NET support is simple.</span></span>

01. <span data-ttu-id="44e10-244">[Скачайте и установите Visual Studio Code](https://code.visualstudio.com/Download).</span><span class="sxs-lookup"><span data-stu-id="44e10-244">[Download and install Visual Studio Code](https://code.visualstudio.com/Download).</span></span>
01. <span data-ttu-id="44e10-245">[Скачайте и установите пакет SDK для .NET](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="44e10-245">[Download and install the .NET SDK](https://dotnet.microsoft.com/download/dotnet-core).</span></span>
01. <span data-ttu-id="44e10-246">[Установите расширение C# из Marketplace для Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span><span class="sxs-lookup"><span data-stu-id="44e10-246">[Install the C# extension from the Visual Studio Code marketplace](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span></span>

## <a name="install-with-bash-automation"></a><span data-ttu-id="44e10-247">Установка с помощью функции автоматизации Bash</span><span class="sxs-lookup"><span data-stu-id="44e10-247">Install with bash automation</span></span>

<span data-ttu-id="44e10-248">[Сценарии dotnet-install](../tools/dotnet-install-script.md) используются для автоматизации установок среды выполнения и их осуществления без прав администратора.</span><span class="sxs-lookup"><span data-stu-id="44e10-248">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="44e10-249">Вы можете скачать сценарий со [страницы справочника по сценариям dotnet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="44e10-249">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="44e10-250">Этот сценарий по умолчанию устанавливает последнюю версию [с долгосрочной поддержкой (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), которой сейчас является .NET 3.1.</span><span class="sxs-lookup"><span data-stu-id="44e10-250">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET 3.1.</span></span> <span data-ttu-id="44e10-251">Вы можете выбрать конкретный выпуск, указав параметр `current`.</span><span class="sxs-lookup"><span data-stu-id="44e10-251">You can choose a specific release by specifying the `current` switch.</span></span> <span data-ttu-id="44e10-252">Включите параметр `runtime` для установки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="44e10-252">Include the `runtime` switch to install a runtime.</span></span> <span data-ttu-id="44e10-253">В противном случае сценарий устанавливает пакет [SDK](./windows.md).</span><span class="sxs-lookup"><span data-stu-id="44e10-253">Otherwise, the script installs the [SDK](./windows.md).</span></span>

```bash
./dotnet-install.sh --channel 5.0 --runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="44e10-254">Приведенная выше команда устанавливает среду выполнения ASP.NET Core для максимальной совместимости.</span><span class="sxs-lookup"><span data-stu-id="44e10-254">The previous command installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="44e10-255">Среда выполнения ASP.NET Core также включает в себя стандартную среду выполнения .NET.</span><span class="sxs-lookup"><span data-stu-id="44e10-255">The ASP.NET Core runtime also includes the standard .NET runtime.</span></span>

## <a name="docker"></a><span data-ttu-id="44e10-256">Docker</span><span class="sxs-lookup"><span data-stu-id="44e10-256">Docker</span></span>

<span data-ttu-id="44e10-257">Контейнеры обеспечивают простой способ изоляции приложения от остальной части основной системы.</span><span class="sxs-lookup"><span data-stu-id="44e10-257">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="44e10-258">Контейнеры на одном компьютере совместно использую только ядро, а также используют ресурсы, которые передаются в приложение.</span><span class="sxs-lookup"><span data-stu-id="44e10-258">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="44e10-259">.NET можно выполнять в контейнере Docker.</span><span class="sxs-lookup"><span data-stu-id="44e10-259">.NET can run in a Docker container.</span></span> <span data-ttu-id="44e10-260">Официальные образы Docker для .NET публикуются в реестре контейнеров Microsoft (MCR), и доступ к ним можно получить в [репозитории Microsoft .NET Core Docker Hub](https://hub.docker.com/_/microsoft-dotnet/).</span><span class="sxs-lookup"><span data-stu-id="44e10-260">Official .NET Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet/).</span></span> <span data-ttu-id="44e10-261">Каждый репозиторий содержит рабочие образы для разных сочетаний .NET (пакета SDK или среды выполнения) и операционной системы.</span><span class="sxs-lookup"><span data-stu-id="44e10-261">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="44e10-262">Корпорация Майкрософт предоставляет образы, которые предназначены для конкретных сценариев.</span><span class="sxs-lookup"><span data-stu-id="44e10-262">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="44e10-263">Например [репозиторий ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-aspnet) содержит образы, которые предназначены для запуска приложений ASP.NET Core в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="44e10-263">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-aspnet) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="44e10-264">Дополнительные сведения об использовании .NET Core в контейнере Docker см. в статьях [Введение в .NET и Docker](../docker/introduction.md) и [Примеры](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="44e10-264">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="44e10-265">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="44e10-265">Next steps</span></span>

- <span data-ttu-id="44e10-266">[Проверка того, установлена ли платформа .NET Core](how-to-detect-installed-versions.md?pivots=os-macos).</span><span class="sxs-lookup"><span data-stu-id="44e10-266">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md?pivots=os-macos).</span></span>
- <span data-ttu-id="44e10-267">[Работа с заверением macOS Catalina](macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="44e10-267">[Working with macOS Catalina notarization](macos-notarization-issues.md).</span></span>
- <span data-ttu-id="44e10-268">[Учебник. Начало работы с macOS](../tutorials/with-visual-studio-mac.md).</span><span class="sxs-lookup"><span data-stu-id="44e10-268">[Tutorial: Get started on macOS](../tutorials/with-visual-studio-mac.md).</span></span>
- <span data-ttu-id="44e10-269">[Учебник. Создание приложения с помощью Visual Studio Code](../tutorials/with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="44e10-269">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="44e10-270">[Учебник. Контейнеризация приложения .NET Core](../docker/build-container.md).</span><span class="sxs-lookup"><span data-stu-id="44e10-270">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

[release-notes-21]: https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md
[release-notes-31]: https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md
[release-notes-50]: https://github.com/dotnet/core/blob/master/release-notes/5.0/5.0-supported-os.md
[release-notes-20]: https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md
[release-notes-22]: https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md
[release-notes-30]: https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md
