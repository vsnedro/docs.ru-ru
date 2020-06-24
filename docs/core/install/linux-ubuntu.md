---
title: Установка .NET Core в Ubuntu — .NET Core
description: Здесь приводятся различные способы установки пакета SDK для .NET Core и среды выполнения .NET Core в Ubuntu.
author: thraka
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 7045d4d1c3585ba6d26c55ded4653775c9413841
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602726"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-ubuntu"></a><span data-ttu-id="fc0a3-103">Установка пакета SDK для .NET Core или среды выполнения .NET Core в Ubuntu</span><span class="sxs-lookup"><span data-stu-id="fc0a3-103">Install .NET Core SDK or .NET Core Runtime on Ubuntu</span></span>

<span data-ttu-id="fc0a3-104">.NET Core поддерживается в Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="fc0a3-104">.NET Core is supported on Ubuntu.</span></span> <span data-ttu-id="fc0a3-105">В этой статье описано, как установить .NET Core в Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="fc0a3-105">This article describes how to install .NET Core on Ubuntu.</span></span> <span data-ttu-id="fc0a3-106">Если поддержка какой-либо версии Ubuntu прекращается, то .NET Core также перестает поддерживать ее.</span><span class="sxs-lookup"><span data-stu-id="fc0a3-106">When an Ubuntu version falls out of support, .NET Core is no longer supported with that version.</span></span> <span data-ttu-id="fc0a3-107">Но с помощью этих инструкций вы сможете запустить .NET Core даже в неподдерживаемых версиях.</span><span class="sxs-lookup"><span data-stu-id="fc0a3-107">However, these instructions may help you to get .NET Core running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="fc0a3-108">Поддерживаемые дистрибутивы</span><span class="sxs-lookup"><span data-stu-id="fc0a3-108">Supported distributions</span></span>

<span data-ttu-id="fc0a3-109">В приведенной ниже таблице содержится список поддерживаемых сейчас выпусков .NET Core и версий Ubuntu, в которых они поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="fc0a3-109">The following table is a list of currently supported .NET Core releases and the versions of Ubuntu they're supported on.</span></span> <span data-ttu-id="fc0a3-110">Эти версии поддерживаются до того же времени, что и версия [.NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) или [Ubuntu](https://wiki.ubuntu.com/Releases).</span><span class="sxs-lookup"><span data-stu-id="fc0a3-110">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Ubuntu reaches end-of-life](https://wiki.ubuntu.com/Releases).</span></span>

- <span data-ttu-id="fc0a3-111">Значок ✔️ означает, что версия Ubuntu или .NET Core поддерживается.</span><span class="sxs-lookup"><span data-stu-id="fc0a3-111">A ✔️ indicates that the version of Ubuntu or .NET Core is still supported.</span></span>
- <span data-ttu-id="fc0a3-112">Значок ❌ означает, что версия Ubuntu или версия .NET Core в таком выпуске Ubuntu не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="fc0a3-112">A ❌ indicates that the version of Ubuntu or .NET Core isn't supported on that Ubuntu release.</span></span>
- <span data-ttu-id="fc0a3-113">Если значок ✔️ стоит как напротив версии Ubuntu, так и напротив версии .NET Core, это значит, что такое сочетание ОС и .NET поддерживается.</span><span class="sxs-lookup"><span data-stu-id="fc0a3-113">When both a version of Ubuntu and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="fc0a3-114">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="fc0a3-114">Ubuntu</span></span>                   | <span data-ttu-id="fc0a3-115">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="fc0a3-115">.NET Core 2.1</span></span> | <span data-ttu-id="fc0a3-116">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="fc0a3-116">.NET Core 3.1</span></span> | <span data-ttu-id="fc0a3-117">Предварительная версия .NET 5 (только установка вручную)</span><span class="sxs-lookup"><span data-stu-id="fc0a3-117">.NET 5 Preview (manual install only)</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="fc0a3-118">✔️ [20.04 (LTS)](#2004-)</span><span class="sxs-lookup"><span data-stu-id="fc0a3-118">✔️ [20.04 (LTS)](#2004-)</span></span> | <span data-ttu-id="fc0a3-119">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="fc0a3-119">✔️ 2.1</span></span>        | <span data-ttu-id="fc0a3-120">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="fc0a3-120">✔️ 3.1</span></span>        | <span data-ttu-id="fc0a3-121">✔️ 5.0 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="fc0a3-121">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="fc0a3-122">✔️ [19.10](#1910-)</span><span class="sxs-lookup"><span data-stu-id="fc0a3-122">✔️ [19.10](#1910-)</span></span>       | <span data-ttu-id="fc0a3-123">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="fc0a3-123">✔️ 2.1</span></span>        | <span data-ttu-id="fc0a3-124">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="fc0a3-124">✔️ 3.1</span></span>        | <span data-ttu-id="fc0a3-125">✔️ 5.0 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="fc0a3-125">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="fc0a3-126">❌ [19.04](#1904-)</span><span class="sxs-lookup"><span data-stu-id="fc0a3-126">❌ [19.04](#1904-)</span></span>       | <span data-ttu-id="fc0a3-127">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="fc0a3-127">✔️ 2.1</span></span>        | <span data-ttu-id="fc0a3-128">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="fc0a3-128">✔️ 3.1</span></span>        | <span data-ttu-id="fc0a3-129">❌ 5.0 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="fc0a3-129">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="fc0a3-130">❌ [18.10](#1810-)</span><span class="sxs-lookup"><span data-stu-id="fc0a3-130">❌ [18.10](#1810-)</span></span>       | <span data-ttu-id="fc0a3-131">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="fc0a3-131">✔️ 2.1</span></span>        | <span data-ttu-id="fc0a3-132">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="fc0a3-132">❌ 3.1</span></span>        | <span data-ttu-id="fc0a3-133">❌ 5.0 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="fc0a3-133">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="fc0a3-134">✔️ [18.04 (LTS)](#1804-)</span><span class="sxs-lookup"><span data-stu-id="fc0a3-134">✔️ [18.04 (LTS)](#1804-)</span></span> | <span data-ttu-id="fc0a3-135">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="fc0a3-135">✔️ 2.1</span></span>        | <span data-ttu-id="fc0a3-136">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="fc0a3-136">✔️ 3.1</span></span>        | <span data-ttu-id="fc0a3-137">✔️ 5.0 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="fc0a3-137">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="fc0a3-138">❌ [17.10](#1710-)</span><span class="sxs-lookup"><span data-stu-id="fc0a3-138">❌ [17.10](#1710-)</span></span>       | <span data-ttu-id="fc0a3-139">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="fc0a3-139">✔️ 2.1</span></span>        | <span data-ttu-id="fc0a3-140">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="fc0a3-140">❌ 3.1</span></span>        | <span data-ttu-id="fc0a3-141">❌ 5.0 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="fc0a3-141">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="fc0a3-142">❌ [17.04](#1704-)</span><span class="sxs-lookup"><span data-stu-id="fc0a3-142">❌ [17.04](#1704-)</span></span>       | <span data-ttu-id="fc0a3-143">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="fc0a3-143">✔️ 2.1</span></span>        | <span data-ttu-id="fc0a3-144">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="fc0a3-144">❌ 3.1</span></span>        | <span data-ttu-id="fc0a3-145">❌ 5.0 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="fc0a3-145">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="fc0a3-146">❌ [16.10](#1610-)</span><span class="sxs-lookup"><span data-stu-id="fc0a3-146">❌ [16.10](#1610-)</span></span>       | <span data-ttu-id="fc0a3-147">❌ 2.1</span><span class="sxs-lookup"><span data-stu-id="fc0a3-147">❌ 2.1</span></span>        | <span data-ttu-id="fc0a3-148">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="fc0a3-148">❌ 3.1</span></span>        | <span data-ttu-id="fc0a3-149">❌ 5.0 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="fc0a3-149">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="fc0a3-150">✔️ [16.04 (LTS)](#1604-)</span><span class="sxs-lookup"><span data-stu-id="fc0a3-150">✔️ [16.04 (LTS)](#1604-)</span></span> | <span data-ttu-id="fc0a3-151">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="fc0a3-151">✔️ 2.1</span></span>        | <span data-ttu-id="fc0a3-152">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="fc0a3-152">✔️ 3.1</span></span>        | <span data-ttu-id="fc0a3-153">✔️ 5.0 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="fc0a3-153">✔️ 5.0 Preview</span></span> |

<span data-ttu-id="fc0a3-154">Следующие версии .NET Core больше не поддерживаются</span><span class="sxs-lookup"><span data-stu-id="fc0a3-154">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="fc0a3-155">(но остаются доступными для скачивания):</span><span class="sxs-lookup"><span data-stu-id="fc0a3-155">The downloads for these still remain published:</span></span>

- <span data-ttu-id="fc0a3-156">3.0</span><span class="sxs-lookup"><span data-stu-id="fc0a3-156">3.0</span></span>
- <span data-ttu-id="fc0a3-157">2.2</span><span class="sxs-lookup"><span data-stu-id="fc0a3-157">2.2</span></span>
- <span data-ttu-id="fc0a3-158">2.0</span><span class="sxs-lookup"><span data-stu-id="fc0a3-158">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="fc0a3-159">Установка других версий</span><span class="sxs-lookup"><span data-stu-id="fc0a3-159">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="2004-"></a><span data-ttu-id="fc0a3-160">20.04 ✔️</span><span class="sxs-lookup"><span data-stu-id="fc0a3-160">20.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1910-"></a><span data-ttu-id="fc0a3-161">19.10 ✔️</span><span class="sxs-lookup"><span data-stu-id="fc0a3-161">19.10 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/19.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1904-"></a><span data-ttu-id="fc0a3-162">19.04 ❌</span><span class="sxs-lookup"><span data-stu-id="fc0a3-162">19.04 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/19.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1810-"></a><span data-ttu-id="fc0a3-163">18.10 ❌</span><span class="sxs-lookup"><span data-stu-id="fc0a3-163">18.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/18.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1804-"></a><span data-ttu-id="fc0a3-164">18.04 ✔️</span><span class="sxs-lookup"><span data-stu-id="fc0a3-164">18.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1710-"></a><span data-ttu-id="fc0a3-165">17.10 ❌</span><span class="sxs-lookup"><span data-stu-id="fc0a3-165">17.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/17.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1704-"></a><span data-ttu-id="fc0a3-166">17.04 ❌</span><span class="sxs-lookup"><span data-stu-id="fc0a3-166">17.04 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/17.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1610-"></a><span data-ttu-id="fc0a3-167">16.10 ❌</span><span class="sxs-lookup"><span data-stu-id="fc0a3-167">16.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/16.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1604-"></a><span data-ttu-id="fc0a3-168">16.04 ✔️</span><span class="sxs-lookup"><span data-stu-id="fc0a3-168">16.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/16.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="apt-update-sdk-or-runtime"></a><span data-ttu-id="fc0a3-169">Обновление пакета SDK или среды выполнения с помощью APT</span><span class="sxs-lookup"><span data-stu-id="fc0a3-169">APT update SDK or runtime</span></span>

<span data-ttu-id="fc0a3-170">Если для .NET Core доступен новый выпуск исправлений, можете выполнить обновление с помощью APT и следующих команд:</span><span class="sxs-lookup"><span data-stu-id="fc0a3-170">When a new patch release is available for .NET Core, you can simply upgrade it through APT with the following commands:</span></span>

```bash
sudo apt-get update
sudo apt-get upgrade
```

## <a name="apt-troubleshooting"></a><span data-ttu-id="fc0a3-171">Устранение неполадок с APT</span><span class="sxs-lookup"><span data-stu-id="fc0a3-171">APT troubleshooting</span></span>

<span data-ttu-id="fc0a3-172">В этом разделе описаны распространенные ошибки, которые могут возникнуть при использовании APT для установки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="fc0a3-172">This section provides information on common errors you may get while using APT to install .NET Core.</span></span>

### <a name="unable-to-locate"></a><span data-ttu-id="fc0a3-173">Ошибка обнаружения</span><span class="sxs-lookup"><span data-stu-id="fc0a3-173">Unable to locate</span></span>

[!INCLUDE [package-manager-failed-to-find-deb](includes/package-manager-failed-to-find-deb.md)]

```bash
sudo apt-get install -y gpg
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor -o microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/ubuntu/{os-version}/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y {dotnet-package}
```

### <a name="failed-to-fetch"></a><span data-ttu-id="fc0a3-174">Ошибка получения</span><span class="sxs-lookup"><span data-stu-id="fc0a3-174">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]

## <a name="snap"></a><span data-ttu-id="fc0a3-175">Snap-пакеты</span><span class="sxs-lookup"><span data-stu-id="fc0a3-175">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="fc0a3-176">Зависимости</span><span class="sxs-lookup"><span data-stu-id="fc0a3-176">Dependencies</span></span>

<span data-ttu-id="fc0a3-177">Если для установки используется диспетчер пакетов, эти библиотеки устанавливаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="fc0a3-177">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="fc0a3-178">Но если вы устанавливаете .NET Core вручную или публикуете автономное приложение, вам потребуется установить эти библиотеки:</span><span class="sxs-lookup"><span data-stu-id="fc0a3-178">But, if you manually install .NET Core or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="fc0a3-179">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="fc0a3-179">liblttng-ust0</span></span>
- <span data-ttu-id="fc0a3-180">libcurl3 (для 14.x и 16.x)</span><span class="sxs-lookup"><span data-stu-id="fc0a3-180">libcurl3 (for 14.x and 16.x)</span></span>
- <span data-ttu-id="fc0a3-181">libcurl4 (для 18.x)</span><span class="sxs-lookup"><span data-stu-id="fc0a3-181">libcurl4 (for 18.x)</span></span>
- <span data-ttu-id="fc0a3-182">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="fc0a3-182">libssl1.0.0</span></span>
- <span data-ttu-id="fc0a3-183">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="fc0a3-183">libkrb5-3</span></span>
- <span data-ttu-id="fc0a3-184">zlib1g</span><span class="sxs-lookup"><span data-stu-id="fc0a3-184">zlib1g</span></span>
- <span data-ttu-id="fc0a3-185">libicu52 (для 14.x)</span><span class="sxs-lookup"><span data-stu-id="fc0a3-185">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="fc0a3-186">libicu55 (для 16.x)</span><span class="sxs-lookup"><span data-stu-id="fc0a3-186">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="fc0a3-187">libicu57 (для 17.x)</span><span class="sxs-lookup"><span data-stu-id="fc0a3-187">libicu57 (for 17.x)</span></span>
- <span data-ttu-id="fc0a3-188">libicu60 (для 18.x)</span><span class="sxs-lookup"><span data-stu-id="fc0a3-188">libicu60 (for 18.x)</span></span>

<span data-ttu-id="fc0a3-189">Для приложений .NET Core, использующих сборку *System.Drawing.Common*, необходима также следующая зависимость:</span><span class="sxs-lookup"><span data-stu-id="fc0a3-189">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="fc0a3-190">libgdiplus (версия 6.0.1 или выше)</span><span class="sxs-lookup"><span data-stu-id="fc0a3-190">libgdiplus (version 6.0.1 or later)</span></span>

  > [!WARNING]
  > <span data-ttu-id="fc0a3-191">Вы можете установить последнюю версию *libgdiplus*, добавив в систему репозиторий Mono.</span><span class="sxs-lookup"><span data-stu-id="fc0a3-191">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="fc0a3-192">Для получения дополнительной информации см. <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="fc0a3-192">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="scripted-install"></a><span data-ttu-id="fc0a3-193">Установка с помощью скрипта</span><span class="sxs-lookup"><span data-stu-id="fc0a3-193">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="fc0a3-194">Установка вручную</span><span class="sxs-lookup"><span data-stu-id="fc0a3-194">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="fc0a3-195">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="fc0a3-195">Next steps</span></span>

- [<span data-ttu-id="fc0a3-196">Учебник. Создание консольного приложения с помощью пакета SDK для .NET Core в Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="fc0a3-196">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
