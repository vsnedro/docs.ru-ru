---
title: Установка .NET в Ubuntu — .NET
description: Здесь приводятся различные способы установки пакета SDK для .NET и среды выполнения .NET в Ubuntu.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 419bcf3ccd011cadba8f8c64e195d7dbdbf7e241
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2020
ms.locfileid: "94507028"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-ubuntu"></a><span data-ttu-id="83bb2-103">Установка пакета SDK для .NET или среды выполнения .NET в Ubuntu</span><span class="sxs-lookup"><span data-stu-id="83bb2-103">Install the .NET SDK or the .NET Runtime on Ubuntu</span></span>

<span data-ttu-id="83bb2-104">.NET поддерживается в Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="83bb2-104">.NET is supported on Ubuntu.</span></span> <span data-ttu-id="83bb2-105">В этой статье описано, как установить .NET в Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="83bb2-105">This article describes how to install .NET on Ubuntu.</span></span> <span data-ttu-id="83bb2-106">Если поддержка какой-либо версии Ubuntu прекращается, то .NET также перестает поддерживать ее.</span><span class="sxs-lookup"><span data-stu-id="83bb2-106">When an Ubuntu version falls out of support, .NET is no longer supported with that version.</span></span> <span data-ttu-id="83bb2-107">Но с помощью этих инструкций вы сможете запустить .NET даже в неподдерживаемых версиях.</span><span class="sxs-lookup"><span data-stu-id="83bb2-107">However, these instructions may help you to get .NET running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="83bb2-108">Поддерживаемые дистрибутивы</span><span class="sxs-lookup"><span data-stu-id="83bb2-108">Supported distributions</span></span>

<span data-ttu-id="83bb2-109">В приведенной ниже таблице содержится список поддерживаемых сейчас выпусков .NET и версий Ubuntu, в которых они поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="83bb2-109">The following table is a list of currently supported .NET releases and the versions of Ubuntu they're supported on.</span></span> <span data-ttu-id="83bb2-110">Эти версии поддерживаются до того же времени, что и версия [.NET](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) или [Ubuntu](https://wiki.ubuntu.com/Releases).</span><span class="sxs-lookup"><span data-stu-id="83bb2-110">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Ubuntu reaches end-of-life](https://wiki.ubuntu.com/Releases).</span></span>

- <span data-ttu-id="83bb2-111">Значок ✔️ означает, что версия Ubuntu или .NET поддерживается.</span><span class="sxs-lookup"><span data-stu-id="83bb2-111">A ✔️ indicates that the version of Ubuntu or .NET is still supported.</span></span>
- <span data-ttu-id="83bb2-112">Значок ❌ означает, что версия Ubuntu или версия .NET в таком выпуске Ubuntu не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="83bb2-112">A ❌ indicates that the version of Ubuntu or .NET isn't supported on that Ubuntu release.</span></span>
- <span data-ttu-id="83bb2-113">Если значок ✔️ стоит как напротив версии Ubuntu, так и напротив версии .NET, это значит, что такое сочетание ОС и .NET поддерживается.</span><span class="sxs-lookup"><span data-stu-id="83bb2-113">When both a version of Ubuntu and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="83bb2-114">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="83bb2-114">Ubuntu</span></span>                   | <span data-ttu-id="83bb2-115">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="83bb2-115">.NET Core 2.1</span></span> | <span data-ttu-id="83bb2-116">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="83bb2-116">.NET Core 3.1</span></span> | <span data-ttu-id="83bb2-117">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="83bb2-117">.NET 5.0</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="83bb2-118">✔️ [20.10](#2010-)</span><span class="sxs-lookup"><span data-stu-id="83bb2-118">✔️ [20.10](#2010-)</span></span>       | <span data-ttu-id="83bb2-119">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="83bb2-119">✔️ 2.1</span></span>        | <span data-ttu-id="83bb2-120">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="83bb2-120">✔️ 3.1</span></span>        | <span data-ttu-id="83bb2-121">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="83bb2-121">✔️ 5.0</span></span> |
| <span data-ttu-id="83bb2-122">✔️ [20.04 (LTS)](#2004-)</span><span class="sxs-lookup"><span data-stu-id="83bb2-122">✔️ [20.04 (LTS)](#2004-)</span></span> | <span data-ttu-id="83bb2-123">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="83bb2-123">✔️ 2.1</span></span>        | <span data-ttu-id="83bb2-124">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="83bb2-124">✔️ 3.1</span></span>        | <span data-ttu-id="83bb2-125">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="83bb2-125">✔️ 5.0</span></span> |
| <span data-ttu-id="83bb2-126">❌ [19.10](#1910-)</span><span class="sxs-lookup"><span data-stu-id="83bb2-126">❌ [19.10](#1910-)</span></span>       | <span data-ttu-id="83bb2-127">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="83bb2-127">✔️ 2.1</span></span>        | <span data-ttu-id="83bb2-128">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="83bb2-128">✔️ 3.1</span></span>        | <span data-ttu-id="83bb2-129">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="83bb2-129">✔️ 5.0</span></span> |
| <span data-ttu-id="83bb2-130">❌ [19.04](#1904-)</span><span class="sxs-lookup"><span data-stu-id="83bb2-130">❌ [19.04](#1904-)</span></span>       | <span data-ttu-id="83bb2-131">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="83bb2-131">✔️ 2.1</span></span>        | <span data-ttu-id="83bb2-132">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="83bb2-132">✔️ 3.1</span></span>        | <span data-ttu-id="83bb2-133">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="83bb2-133">❌ 5.0</span></span> |
| <span data-ttu-id="83bb2-134">❌ [18.10](#1810-)</span><span class="sxs-lookup"><span data-stu-id="83bb2-134">❌ [18.10](#1810-)</span></span>       | <span data-ttu-id="83bb2-135">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="83bb2-135">✔️ 2.1</span></span>        | <span data-ttu-id="83bb2-136">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="83bb2-136">❌ 3.1</span></span>        | <span data-ttu-id="83bb2-137">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="83bb2-137">❌ 5.0</span></span> |
| <span data-ttu-id="83bb2-138">✔️ [18.04 (LTS)](#1804-)</span><span class="sxs-lookup"><span data-stu-id="83bb2-138">✔️ [18.04 (LTS)](#1804-)</span></span> | <span data-ttu-id="83bb2-139">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="83bb2-139">✔️ 2.1</span></span>        | <span data-ttu-id="83bb2-140">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="83bb2-140">✔️ 3.1</span></span>        | <span data-ttu-id="83bb2-141">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="83bb2-141">✔️ 5.0</span></span> |
| <span data-ttu-id="83bb2-142">❌ [17.10](#1710-)</span><span class="sxs-lookup"><span data-stu-id="83bb2-142">❌ [17.10](#1710-)</span></span>       | <span data-ttu-id="83bb2-143">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="83bb2-143">✔️ 2.1</span></span>        | <span data-ttu-id="83bb2-144">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="83bb2-144">❌ 3.1</span></span>        | <span data-ttu-id="83bb2-145">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="83bb2-145">❌ 5.0</span></span> |
| <span data-ttu-id="83bb2-146">❌ [17.04](#1704-)</span><span class="sxs-lookup"><span data-stu-id="83bb2-146">❌ [17.04](#1704-)</span></span>       | <span data-ttu-id="83bb2-147">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="83bb2-147">✔️ 2.1</span></span>        | <span data-ttu-id="83bb2-148">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="83bb2-148">❌ 3.1</span></span>        | <span data-ttu-id="83bb2-149">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="83bb2-149">❌ 5.0</span></span> |
| <span data-ttu-id="83bb2-150">❌ [16.10](#1610-)</span><span class="sxs-lookup"><span data-stu-id="83bb2-150">❌ [16.10](#1610-)</span></span>       | <span data-ttu-id="83bb2-151">❌ 2.1</span><span class="sxs-lookup"><span data-stu-id="83bb2-151">❌ 2.1</span></span>        | <span data-ttu-id="83bb2-152">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="83bb2-152">❌ 3.1</span></span>        | <span data-ttu-id="83bb2-153">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="83bb2-153">❌ 5.0</span></span> |
| <span data-ttu-id="83bb2-154">✔️ [16.04 (LTS)](#1604-)</span><span class="sxs-lookup"><span data-stu-id="83bb2-154">✔️ [16.04 (LTS)](#1604-)</span></span> | <span data-ttu-id="83bb2-155">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="83bb2-155">✔️ 2.1</span></span>        | <span data-ttu-id="83bb2-156">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="83bb2-156">✔️ 3.1</span></span>        | <span data-ttu-id="83bb2-157">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="83bb2-157">✔️ 5.0</span></span> |

<span data-ttu-id="83bb2-158">Следующие версии .NET больше не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="83bb2-158">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="83bb2-159">(но остаются доступными для скачивания):</span><span class="sxs-lookup"><span data-stu-id="83bb2-159">The downloads for these still remain published:</span></span>

- <span data-ttu-id="83bb2-160">3.0</span><span class="sxs-lookup"><span data-stu-id="83bb2-160">3.0</span></span>
- <span data-ttu-id="83bb2-161">2.2</span><span class="sxs-lookup"><span data-stu-id="83bb2-161">2.2</span></span>
- <span data-ttu-id="83bb2-162">2.0</span><span class="sxs-lookup"><span data-stu-id="83bb2-162">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="83bb2-163">Установка других версий</span><span class="sxs-lookup"><span data-stu-id="83bb2-163">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="2010-"></a><span data-ttu-id="83bb2-164">20.10 ✔️</span><span class="sxs-lookup"><span data-stu-id="83bb2-164">20.10 ✔️</span></span>

<span data-ttu-id="83bb2-165">В настоящее время в веб-каналах пакетов .NET 5 и .NET Core 3.1 для Ubuntu 20.10 имеется ошибка.</span><span class="sxs-lookup"><span data-stu-id="83bb2-165">.NET 5 and .NET Core 3.1 package feeds for Ubuntu 20.10 currently have an issue.</span></span> <span data-ttu-id="83bb2-166">Дополнительные сведения об этой ошибке см. в разделе [Проблема dotnet/core#5549, рассмотренная на сайте GitHub](https://github.com/dotnet/core/issues/5549).</span><span class="sxs-lookup"><span data-stu-id="83bb2-166">For more information about the issue, see [GitHub issue dotnet/core#5549](https://github.com/dotnet/core/issues/5549).</span></span> <span data-ttu-id="83bb2-167">Эта статья будет обновлена после устранения проблемы.</span><span class="sxs-lookup"><span data-stu-id="83bb2-167">This article will be updated when the issue is resolved.</span></span>

<span data-ttu-id="83bb2-168">Чтобы установить .NET 5 или .NET Core 3.1 в Ubuntu 20.10, следуйте инструкциям для версии [20.04](#2004-).</span><span class="sxs-lookup"><span data-stu-id="83bb2-168">To install .NET 5 or .NET Core 3.1 on Ubuntu 20.10, follow the instructions for [20.04](#2004-).</span></span>

## <a name="2004-"></a><span data-ttu-id="83bb2-169">20.04 ✔️</span><span class="sxs-lookup"><span data-stu-id="83bb2-169">20.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="1910-"></a><span data-ttu-id="83bb2-170">19.10 ❌</span><span class="sxs-lookup"><span data-stu-id="83bb2-170">19.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/19.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1904-"></a><span data-ttu-id="83bb2-171">19.04 ❌</span><span class="sxs-lookup"><span data-stu-id="83bb2-171">19.04 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/19.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1810-"></a><span data-ttu-id="83bb2-172">18.10 ❌</span><span class="sxs-lookup"><span data-stu-id="83bb2-172">18.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/18.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1804-"></a><span data-ttu-id="83bb2-173">18.04 ✔️</span><span class="sxs-lookup"><span data-stu-id="83bb2-173">18.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="1710-"></a><span data-ttu-id="83bb2-174">17.10 ❌</span><span class="sxs-lookup"><span data-stu-id="83bb2-174">17.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/17.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1704-"></a><span data-ttu-id="83bb2-175">17.04 ❌</span><span class="sxs-lookup"><span data-stu-id="83bb2-175">17.04 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/17.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1610-"></a><span data-ttu-id="83bb2-176">16.10 ❌</span><span class="sxs-lookup"><span data-stu-id="83bb2-176">16.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/16.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1604-"></a><span data-ttu-id="83bb2-177">16.04 ✔️</span><span class="sxs-lookup"><span data-stu-id="83bb2-177">16.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/16.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="apt-update-sdk-or-runtime"></a><span data-ttu-id="83bb2-178">Обновление пакета SDK или среды выполнения с помощью APT</span><span class="sxs-lookup"><span data-stu-id="83bb2-178">APT update SDK or runtime</span></span>

<span data-ttu-id="83bb2-179">Если для .NET доступен новый выпуск исправлений, можете выполнить обновление с помощью APT и следующих команд:</span><span class="sxs-lookup"><span data-stu-id="83bb2-179">When a new patch release is available for .NET, you can simply upgrade it through APT with the following commands:</span></span>

```bash
sudo apt-get update
sudo apt-get upgrade
```

## <a name="apt-troubleshooting"></a><span data-ttu-id="83bb2-180">Устранение неполадок с APT</span><span class="sxs-lookup"><span data-stu-id="83bb2-180">APT troubleshooting</span></span>

<span data-ttu-id="83bb2-181">В этом разделе описаны распространенные ошибки, которые могут возникнуть при использовании APT для установки .NET.</span><span class="sxs-lookup"><span data-stu-id="83bb2-181">This section provides information on common errors you may get while using APT to install .NET.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="83bb2-182">Не удалось найти пакет</span><span class="sxs-lookup"><span data-stu-id="83bb2-182">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="unable-to-locate--some-packages-could-not-be-installed"></a><span data-ttu-id="83bb2-183">Ошибка обнаружения \\. Не удалось установить некоторые пакеты</span><span class="sxs-lookup"><span data-stu-id="83bb2-183">Unable to locate \\ Some packages could not be installed</span></span>

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

### <a name="failed-to-fetch"></a><span data-ttu-id="83bb2-184">Ошибка получения</span><span class="sxs-lookup"><span data-stu-id="83bb2-184">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]

## <a name="snap"></a><span data-ttu-id="83bb2-185">Snap-пакеты</span><span class="sxs-lookup"><span data-stu-id="83bb2-185">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="83bb2-186">Зависимости</span><span class="sxs-lookup"><span data-stu-id="83bb2-186">Dependencies</span></span>

<span data-ttu-id="83bb2-187">Если для установки используется диспетчер пакетов, эти библиотеки устанавливаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="83bb2-187">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="83bb2-188">Но если вы устанавливаете .NET вручную или публикуете автономное приложение, вам потребуется установить эти библиотеки:</span><span class="sxs-lookup"><span data-stu-id="83bb2-188">But, if you manually install .NET or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="83bb2-189">libc6</span><span class="sxs-lookup"><span data-stu-id="83bb2-189">libc6</span></span>
- <span data-ttu-id="83bb2-190">libgcc1</span><span class="sxs-lookup"><span data-stu-id="83bb2-190">libgcc1</span></span>
- <span data-ttu-id="83bb2-191">libgssapi-krb5-2</span><span class="sxs-lookup"><span data-stu-id="83bb2-191">libgssapi-krb5-2</span></span>
- <span data-ttu-id="83bb2-192">libicu52 (для 14.x)</span><span class="sxs-lookup"><span data-stu-id="83bb2-192">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="83bb2-193">libicu55 (для 16.x)</span><span class="sxs-lookup"><span data-stu-id="83bb2-193">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="83bb2-194">libicu60 (для 18.x)</span><span class="sxs-lookup"><span data-stu-id="83bb2-194">libicu60 (for 18.x)</span></span>
- <span data-ttu-id="83bb2-195">libicu66 (для 20.x)</span><span class="sxs-lookup"><span data-stu-id="83bb2-195">libicu66 (for 20.x)</span></span>
- <span data-ttu-id="83bb2-196">libssl1.0.0 (для 14.x, 16.x)</span><span class="sxs-lookup"><span data-stu-id="83bb2-196">libssl1.0.0 (for 14.x, 16.x)</span></span>
- <span data-ttu-id="83bb2-197">libssl1.1 (для 18.x, 20.x)</span><span class="sxs-lookup"><span data-stu-id="83bb2-197">libssl1.1 (for 18.x, 20.x)</span></span>
- <span data-ttu-id="83bb2-198">libstdc++6</span><span class="sxs-lookup"><span data-stu-id="83bb2-198">libstdc++6</span></span>
- <span data-ttu-id="83bb2-199">zlib1g</span><span class="sxs-lookup"><span data-stu-id="83bb2-199">zlib1g</span></span>

<span data-ttu-id="83bb2-200">Для приложений .NET, использующих сборку *System.Drawing.Common*, необходима также следующая зависимость:</span><span class="sxs-lookup"><span data-stu-id="83bb2-200">For .NET apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="83bb2-201">libgdiplus (версия 6.0.1 или выше)</span><span class="sxs-lookup"><span data-stu-id="83bb2-201">libgdiplus (version 6.0.1 or later)</span></span>

  > [!WARNING]
  > <span data-ttu-id="83bb2-202">Вы можете установить последнюю версию *libgdiplus*, добавив в систему репозиторий Mono.</span><span class="sxs-lookup"><span data-stu-id="83bb2-202">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="83bb2-203">Для получения дополнительной информации см. <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="83bb2-203">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="scripted-install"></a><span data-ttu-id="83bb2-204">Установка с помощью скрипта</span><span class="sxs-lookup"><span data-stu-id="83bb2-204">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="83bb2-205">Установка вручную</span><span class="sxs-lookup"><span data-stu-id="83bb2-205">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="83bb2-206">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="83bb2-206">Next steps</span></span>

- [<span data-ttu-id="83bb2-207">Учебник. Создание консольного приложения с помощью пакета SDK для .NET в Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="83bb2-207">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
