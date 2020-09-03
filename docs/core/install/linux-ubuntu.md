---
title: Установка .NET Core в Ubuntu — .NET Core
description: Здесь приводятся различные способы установки пакета SDK для .NET Core и среды выполнения .NET Core в Ubuntu.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 9694dac719024264edee849044f048970b63b7b7
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89132951"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-ubuntu"></a><span data-ttu-id="5b561-103">Установка пакета SDK для .NET Core или среды выполнения .NET Core в Ubuntu</span><span class="sxs-lookup"><span data-stu-id="5b561-103">Install .NET Core SDK or .NET Core Runtime on Ubuntu</span></span>

<span data-ttu-id="5b561-104">.NET Core поддерживается в Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="5b561-104">.NET Core is supported on Ubuntu.</span></span> <span data-ttu-id="5b561-105">В этой статье описано, как установить .NET Core в Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="5b561-105">This article describes how to install .NET Core on Ubuntu.</span></span> <span data-ttu-id="5b561-106">Если поддержка какой-либо версии Ubuntu прекращается, то .NET Core также перестает поддерживать ее.</span><span class="sxs-lookup"><span data-stu-id="5b561-106">When an Ubuntu version falls out of support, .NET Core is no longer supported with that version.</span></span> <span data-ttu-id="5b561-107">Но с помощью этих инструкций вы сможете запустить .NET Core даже в неподдерживаемых версиях.</span><span class="sxs-lookup"><span data-stu-id="5b561-107">However, these instructions may help you to get .NET Core running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="5b561-108">Поддерживаемые дистрибутивы</span><span class="sxs-lookup"><span data-stu-id="5b561-108">Supported distributions</span></span>

<span data-ttu-id="5b561-109">В приведенной ниже таблице содержится список поддерживаемых сейчас выпусков .NET Core и версий Ubuntu, в которых они поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="5b561-109">The following table is a list of currently supported .NET Core releases and the versions of Ubuntu they're supported on.</span></span> <span data-ttu-id="5b561-110">Эти версии поддерживаются до того же времени, что и версия [.NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) или [Ubuntu](https://wiki.ubuntu.com/Releases).</span><span class="sxs-lookup"><span data-stu-id="5b561-110">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Ubuntu reaches end-of-life](https://wiki.ubuntu.com/Releases).</span></span>

- <span data-ttu-id="5b561-111">Значок ✔️ означает, что версия Ubuntu или .NET Core поддерживается.</span><span class="sxs-lookup"><span data-stu-id="5b561-111">A ✔️ indicates that the version of Ubuntu or .NET Core is still supported.</span></span>
- <span data-ttu-id="5b561-112">Значок ❌ означает, что версия Ubuntu или версия .NET Core в таком выпуске Ubuntu не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="5b561-112">A ❌ indicates that the version of Ubuntu or .NET Core isn't supported on that Ubuntu release.</span></span>
- <span data-ttu-id="5b561-113">Если значок ✔️ стоит как напротив версии Ubuntu, так и напротив версии .NET Core, это значит, что такое сочетание ОС и .NET поддерживается.</span><span class="sxs-lookup"><span data-stu-id="5b561-113">When both a version of Ubuntu and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="5b561-114">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="5b561-114">Ubuntu</span></span>                   | <span data-ttu-id="5b561-115">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="5b561-115">.NET Core 2.1</span></span> | <span data-ttu-id="5b561-116">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="5b561-116">.NET Core 3.1</span></span> | <span data-ttu-id="5b561-117">Предварительная версия .NET 5 (только установка вручную)</span><span class="sxs-lookup"><span data-stu-id="5b561-117">.NET 5 Preview (manual install only)</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="5b561-118">✔️ [20.04 (LTS)](#2004-)</span><span class="sxs-lookup"><span data-stu-id="5b561-118">✔️ [20.04 (LTS)](#2004-)</span></span> | <span data-ttu-id="5b561-119">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="5b561-119">✔️ 2.1</span></span>        | <span data-ttu-id="5b561-120">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="5b561-120">✔️ 3.1</span></span>        | <span data-ttu-id="5b561-121">✔️ 5.0 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="5b561-121">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="5b561-122">❌ [19.10](#1910-)</span><span class="sxs-lookup"><span data-stu-id="5b561-122">❌ [19.10](#1910-)</span></span>       | <span data-ttu-id="5b561-123">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="5b561-123">✔️ 2.1</span></span>        | <span data-ttu-id="5b561-124">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="5b561-124">✔️ 3.1</span></span>        | <span data-ttu-id="5b561-125">✔️ 5.0 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="5b561-125">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="5b561-126">❌ [19.04](#1904-)</span><span class="sxs-lookup"><span data-stu-id="5b561-126">❌ [19.04](#1904-)</span></span>       | <span data-ttu-id="5b561-127">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="5b561-127">✔️ 2.1</span></span>        | <span data-ttu-id="5b561-128">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="5b561-128">✔️ 3.1</span></span>        | <span data-ttu-id="5b561-129">❌ 5.0 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="5b561-129">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="5b561-130">❌ [18.10](#1810-)</span><span class="sxs-lookup"><span data-stu-id="5b561-130">❌ [18.10](#1810-)</span></span>       | <span data-ttu-id="5b561-131">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="5b561-131">✔️ 2.1</span></span>        | <span data-ttu-id="5b561-132">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="5b561-132">❌ 3.1</span></span>        | <span data-ttu-id="5b561-133">❌ 5.0 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="5b561-133">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="5b561-134">✔️ [18.04 (LTS)](#1804-)</span><span class="sxs-lookup"><span data-stu-id="5b561-134">✔️ [18.04 (LTS)](#1804-)</span></span> | <span data-ttu-id="5b561-135">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="5b561-135">✔️ 2.1</span></span>        | <span data-ttu-id="5b561-136">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="5b561-136">✔️ 3.1</span></span>        | <span data-ttu-id="5b561-137">✔️ 5.0 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="5b561-137">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="5b561-138">❌ [17.10](#1710-)</span><span class="sxs-lookup"><span data-stu-id="5b561-138">❌ [17.10](#1710-)</span></span>       | <span data-ttu-id="5b561-139">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="5b561-139">✔️ 2.1</span></span>        | <span data-ttu-id="5b561-140">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="5b561-140">❌ 3.1</span></span>        | <span data-ttu-id="5b561-141">❌ 5.0 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="5b561-141">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="5b561-142">❌ [17.04](#1704-)</span><span class="sxs-lookup"><span data-stu-id="5b561-142">❌ [17.04](#1704-)</span></span>       | <span data-ttu-id="5b561-143">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="5b561-143">✔️ 2.1</span></span>        | <span data-ttu-id="5b561-144">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="5b561-144">❌ 3.1</span></span>        | <span data-ttu-id="5b561-145">❌ 5.0 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="5b561-145">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="5b561-146">❌ [16.10](#1610-)</span><span class="sxs-lookup"><span data-stu-id="5b561-146">❌ [16.10](#1610-)</span></span>       | <span data-ttu-id="5b561-147">❌ 2.1</span><span class="sxs-lookup"><span data-stu-id="5b561-147">❌ 2.1</span></span>        | <span data-ttu-id="5b561-148">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="5b561-148">❌ 3.1</span></span>        | <span data-ttu-id="5b561-149">❌ 5.0 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="5b561-149">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="5b561-150">✔️ [16.04 (LTS)](#1604-)</span><span class="sxs-lookup"><span data-stu-id="5b561-150">✔️ [16.04 (LTS)](#1604-)</span></span> | <span data-ttu-id="5b561-151">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="5b561-151">✔️ 2.1</span></span>        | <span data-ttu-id="5b561-152">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="5b561-152">✔️ 3.1</span></span>        | <span data-ttu-id="5b561-153">✔️ 5.0 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="5b561-153">✔️ 5.0 Preview</span></span> |

<span data-ttu-id="5b561-154">Следующие версии .NET Core больше не поддерживаются</span><span class="sxs-lookup"><span data-stu-id="5b561-154">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="5b561-155">(но остаются доступными для скачивания):</span><span class="sxs-lookup"><span data-stu-id="5b561-155">The downloads for these still remain published:</span></span>

- <span data-ttu-id="5b561-156">3.0</span><span class="sxs-lookup"><span data-stu-id="5b561-156">3.0</span></span>
- <span data-ttu-id="5b561-157">2.2</span><span class="sxs-lookup"><span data-stu-id="5b561-157">2.2</span></span>
- <span data-ttu-id="5b561-158">2.0</span><span class="sxs-lookup"><span data-stu-id="5b561-158">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="5b561-159">Установка других версий</span><span class="sxs-lookup"><span data-stu-id="5b561-159">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="2004-"></a><span data-ttu-id="5b561-160">20.04 ✔️</span><span class="sxs-lookup"><span data-stu-id="5b561-160">20.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1910-"></a><span data-ttu-id="5b561-161">19.10 ❌</span><span class="sxs-lookup"><span data-stu-id="5b561-161">19.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/19.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1904-"></a><span data-ttu-id="5b561-162">19.04 ❌</span><span class="sxs-lookup"><span data-stu-id="5b561-162">19.04 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/19.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1810-"></a><span data-ttu-id="5b561-163">18.10 ❌</span><span class="sxs-lookup"><span data-stu-id="5b561-163">18.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/18.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1804-"></a><span data-ttu-id="5b561-164">18.04 ✔️</span><span class="sxs-lookup"><span data-stu-id="5b561-164">18.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1710-"></a><span data-ttu-id="5b561-165">17.10 ❌</span><span class="sxs-lookup"><span data-stu-id="5b561-165">17.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/17.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1704-"></a><span data-ttu-id="5b561-166">17.04 ❌</span><span class="sxs-lookup"><span data-stu-id="5b561-166">17.04 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/17.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1610-"></a><span data-ttu-id="5b561-167">16.10 ❌</span><span class="sxs-lookup"><span data-stu-id="5b561-167">16.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/16.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1604-"></a><span data-ttu-id="5b561-168">16.04 ✔️</span><span class="sxs-lookup"><span data-stu-id="5b561-168">16.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/16.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="apt-update-sdk-or-runtime"></a><span data-ttu-id="5b561-169">Обновление пакета SDK или среды выполнения с помощью APT</span><span class="sxs-lookup"><span data-stu-id="5b561-169">APT update SDK or runtime</span></span>

<span data-ttu-id="5b561-170">Если для .NET Core доступен новый выпуск исправлений, можете выполнить обновление с помощью APT и следующих команд:</span><span class="sxs-lookup"><span data-stu-id="5b561-170">When a new patch release is available for .NET Core, you can simply upgrade it through APT with the following commands:</span></span>

```bash
sudo apt-get update
sudo apt-get upgrade
```

## <a name="apt-troubleshooting"></a><span data-ttu-id="5b561-171">Устранение неполадок с APT</span><span class="sxs-lookup"><span data-stu-id="5b561-171">APT troubleshooting</span></span>

<span data-ttu-id="5b561-172">В этом разделе описаны распространенные ошибки, которые могут возникнуть при использовании APT для установки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5b561-172">This section provides information on common errors you may get while using APT to install .NET Core.</span></span>

### <a name="unable-to-locate--some-packages-could-not-be-installed"></a><span data-ttu-id="5b561-173">Ошибка обнаружения \\. Не удалось установить некоторые пакеты</span><span class="sxs-lookup"><span data-stu-id="5b561-173">Unable to locate \\ Some packages could not be installed</span></span>

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

### <a name="failed-to-fetch"></a><span data-ttu-id="5b561-174">Ошибка получения</span><span class="sxs-lookup"><span data-stu-id="5b561-174">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]

## <a name="snap"></a><span data-ttu-id="5b561-175">Snap-пакеты</span><span class="sxs-lookup"><span data-stu-id="5b561-175">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="5b561-176">Зависимости</span><span class="sxs-lookup"><span data-stu-id="5b561-176">Dependencies</span></span>

<span data-ttu-id="5b561-177">Если для установки используется диспетчер пакетов, эти библиотеки устанавливаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="5b561-177">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="5b561-178">Но если вы устанавливаете .NET Core вручную или публикуете автономное приложение, вам потребуется установить эти библиотеки:</span><span class="sxs-lookup"><span data-stu-id="5b561-178">But, if you manually install .NET Core or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="5b561-179">libc6</span><span class="sxs-lookup"><span data-stu-id="5b561-179">libc6</span></span>
- <span data-ttu-id="5b561-180">libgcc1</span><span class="sxs-lookup"><span data-stu-id="5b561-180">libgcc1</span></span>
- <span data-ttu-id="5b561-181">libgssapi-krb5-2</span><span class="sxs-lookup"><span data-stu-id="5b561-181">libgssapi-krb5-2</span></span>
- <span data-ttu-id="5b561-182">libicu52 (для 14.x)</span><span class="sxs-lookup"><span data-stu-id="5b561-182">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="5b561-183">libicu55 (для 16.x)</span><span class="sxs-lookup"><span data-stu-id="5b561-183">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="5b561-184">libicu60 (для 18.x)</span><span class="sxs-lookup"><span data-stu-id="5b561-184">libicu60 (for 18.x)</span></span>
- <span data-ttu-id="5b561-185">libicu66 (для 20.x)</span><span class="sxs-lookup"><span data-stu-id="5b561-185">libicu66 (for 20.x)</span></span>
- <span data-ttu-id="5b561-186">libssl1.0.0 (для 14.x, 16.x)</span><span class="sxs-lookup"><span data-stu-id="5b561-186">libssl1.0.0 (for 14.x, 16.x)</span></span>
- <span data-ttu-id="5b561-187">libssl1.1 (для 18.x, 20.x)</span><span class="sxs-lookup"><span data-stu-id="5b561-187">libssl1.1 (for 18.x, 20.x)</span></span>
- <span data-ttu-id="5b561-188">libstdc++6</span><span class="sxs-lookup"><span data-stu-id="5b561-188">libstdc++6</span></span>
- <span data-ttu-id="5b561-189">zlib1g</span><span class="sxs-lookup"><span data-stu-id="5b561-189">zlib1g</span></span>

<span data-ttu-id="5b561-190">Для приложений .NET Core, использующих сборку *System.Drawing.Common*, необходима также следующая зависимость:</span><span class="sxs-lookup"><span data-stu-id="5b561-190">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="5b561-191">libgdiplus (версия 6.0.1 или выше)</span><span class="sxs-lookup"><span data-stu-id="5b561-191">libgdiplus (version 6.0.1 or later)</span></span>

  > [!WARNING]
  > <span data-ttu-id="5b561-192">Вы можете установить последнюю версию *libgdiplus*, добавив в систему репозиторий Mono.</span><span class="sxs-lookup"><span data-stu-id="5b561-192">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="5b561-193">Для получения дополнительной информации см. <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="5b561-193">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="scripted-install"></a><span data-ttu-id="5b561-194">Установка с помощью скрипта</span><span class="sxs-lookup"><span data-stu-id="5b561-194">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="5b561-195">Установка вручную</span><span class="sxs-lookup"><span data-stu-id="5b561-195">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="5b561-196">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="5b561-196">Next steps</span></span>

- [<span data-ttu-id="5b561-197">Учебник. Создание консольного приложения с помощью пакета SDK для .NET Core в Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="5b561-197">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
