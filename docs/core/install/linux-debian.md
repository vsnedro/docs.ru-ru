---
title: Установка .NET Core в Debian (.NET Core)
description: Здесь приводятся различные способы установки пакета SDK для .NET Core и среды выполнения .NET Core в Debian.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: d0f7d4092ec420d031d0874a56b9e2148afdb865
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538556"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-debian"></a><span data-ttu-id="fd479-103">Установка пакета SDK для .NET Core или среды выполнения .NET Core в Debian</span><span class="sxs-lookup"><span data-stu-id="fd479-103">Install .NET Core SDK or .NET Core Runtime on Debian</span></span>

<span data-ttu-id="fd479-104">В этой статье описано, как установить .NET Core в Debian.</span><span class="sxs-lookup"><span data-stu-id="fd479-104">This article describes how to install .NET Core on Debian.</span></span> <span data-ttu-id="fd479-105">Если поддержка какой-либо версии Debian прекращается, то .NET Core также перестает поддерживать ее.</span><span class="sxs-lookup"><span data-stu-id="fd479-105">When a Debian version falls out of support, .NET Core is no longer supported with that version.</span></span> <span data-ttu-id="fd479-106">Но с помощью этих инструкций вы сможете запустить .NET Core даже в неподдерживаемых версиях.</span><span class="sxs-lookup"><span data-stu-id="fd479-106">However, these instructions may help you to get .NET Core running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="fd479-107">Поддерживаемые дистрибутивы</span><span class="sxs-lookup"><span data-stu-id="fd479-107">Supported distributions</span></span>

<span data-ttu-id="fd479-108">В приведенной ниже таблице содержится список поддерживаемых сейчас выпусков .NET Core и версий Debian, в которых они поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="fd479-108">The following table is a list of currently supported .NET Core releases and the versions of Debian they're supported on.</span></span> <span data-ttu-id="fd479-109">Эти версии поддерживаются до того же времени, что и версия [.NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) или [Debian](https://wiki.debian.org/DebianReleases).</span><span class="sxs-lookup"><span data-stu-id="fd479-109">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Debian reaches end-of-life](https://wiki.debian.org/DebianReleases).</span></span>

- <span data-ttu-id="fd479-110">Значок ✔️ означает, что версия Debian или .NET Core поддерживается.</span><span class="sxs-lookup"><span data-stu-id="fd479-110">A ✔️ indicates that the version of Debian or .NET Core is still supported.</span></span>
- <span data-ttu-id="fd479-111">Значок ❌ означает, что версия Debian или версия .NET Core в таком выпуске Debian не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="fd479-111">A ❌ indicates that the version of Debian or .NET Core isn't supported on that Debian release.</span></span>
- <span data-ttu-id="fd479-112">Если значок ✔️ стоит как напротив версии Debian, так и напротив версии .NET Core, это значит, что такое сочетание ОС и .NET поддерживается.</span><span class="sxs-lookup"><span data-stu-id="fd479-112">When both a version of Debian and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="fd479-113">Debian</span><span class="sxs-lookup"><span data-stu-id="fd479-113">Debian</span></span>                   | <span data-ttu-id="fd479-114">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="fd479-114">.NET Core 2.1</span></span> | <span data-ttu-id="fd479-115">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="fd479-115">.NET Core 3.1</span></span> | <span data-ttu-id="fd479-116">Предварительная версия .NET 5 (только установка вручную)</span><span class="sxs-lookup"><span data-stu-id="fd479-116">.NET 5 Preview (manual install only)</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="fd479-117">✔️ [10](#debian-10-)</span><span class="sxs-lookup"><span data-stu-id="fd479-117">✔️ [10](#debian-10-)</span></span>     | <span data-ttu-id="fd479-118">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="fd479-118">✔️ 2.1</span></span>        | <span data-ttu-id="fd479-119">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="fd479-119">✔️ 3.1</span></span>        | <span data-ttu-id="fd479-120">✔️ 5.0 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="fd479-120">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="fd479-121">✔️ [9](#debian-9-)</span><span class="sxs-lookup"><span data-stu-id="fd479-121">✔️ [9](#debian-9-)</span></span>       | <span data-ttu-id="fd479-122">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="fd479-122">✔️ 2.1</span></span>        | <span data-ttu-id="fd479-123">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="fd479-123">✔️ 3.1</span></span>        | <span data-ttu-id="fd479-124">✔️ 5.0 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="fd479-124">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="fd479-125">❌ [8](#debian-8-)</span><span class="sxs-lookup"><span data-stu-id="fd479-125">❌ [8](#debian-8-)</span></span>       | <span data-ttu-id="fd479-126">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="fd479-126">✔️ 2.1</span></span>        | <span data-ttu-id="fd479-127">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="fd479-127">❌ 3.1</span></span>        | <span data-ttu-id="fd479-128">❌ 5.0 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="fd479-128">❌ 5.0 Preview</span></span> |

<span data-ttu-id="fd479-129">Следующие версии .NET Core больше не поддерживаются,</span><span class="sxs-lookup"><span data-stu-id="fd479-129">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="fd479-130">(но остаются доступными для скачивания):</span><span class="sxs-lookup"><span data-stu-id="fd479-130">The downloads for these still remain published:</span></span>

- <span data-ttu-id="fd479-131">3.0</span><span class="sxs-lookup"><span data-stu-id="fd479-131">3.0</span></span>
- <span data-ttu-id="fd479-132">2.2</span><span class="sxs-lookup"><span data-stu-id="fd479-132">2.2</span></span>
- <span data-ttu-id="fd479-133">2.0</span><span class="sxs-lookup"><span data-stu-id="fd479-133">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="fd479-134">Установка других версий</span><span class="sxs-lookup"><span data-stu-id="fd479-134">How to install other versions</span></span>

[!INCLUDE [hack-pkgname](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="debian-10-"></a><span data-ttu-id="fd479-135">Debian 10 ✔️</span><span class="sxs-lookup"><span data-stu-id="fd479-135">Debian 10 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/debian/10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="debian-9-"></a><span data-ttu-id="fd479-136">Debian 9 ✔️</span><span class="sxs-lookup"><span data-stu-id="fd479-136">Debian 9 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/9/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="debian-8-"></a><span data-ttu-id="fd479-137">Debian 8 ❌</span><span class="sxs-lookup"><span data-stu-id="fd479-137">Debian 8 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-debian.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/8/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="apt-update-sdk-or-runtime"></a><span data-ttu-id="fd479-138">Обновление пакета SDK или среды выполнения с помощью APT</span><span class="sxs-lookup"><span data-stu-id="fd479-138">APT update SDK or runtime</span></span>

<span data-ttu-id="fd479-139">Если для .NET Core доступен новый выпуск исправлений, можете выполнить обновление с помощью APT и следующих команд:</span><span class="sxs-lookup"><span data-stu-id="fd479-139">When a new patch release is available for .NET Core, you can simply upgrade it through APT with the following commands:</span></span>

```bash
sudo apt-get update
sudo apt-get upgrade
```

## <a name="apt-troubleshooting"></a><span data-ttu-id="fd479-140">Устранение неполадок с APT</span><span class="sxs-lookup"><span data-stu-id="fd479-140">APT troubleshooting</span></span>

<span data-ttu-id="fd479-141">В этом разделе описаны распространенные ошибки, которые могут возникнуть при использовании APT для установки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="fd479-141">This section provides information on common errors you may get while using APT to install .NET Core.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="fd479-142">Не удалось найти пакет</span><span class="sxs-lookup"><span data-stu-id="fd479-142">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="unable-to-locate--some-packages-could-not-be-installed"></a><span data-ttu-id="fd479-143">Ошибка обнаружения \\. Не удалось установить некоторые пакеты</span><span class="sxs-lookup"><span data-stu-id="fd479-143">Unable to locate \\ Some packages could not be installed</span></span>

[!INCLUDE [package-manager-failed-to-find-deb](includes/package-manager-failed-to-find-deb.md)]

```bash
sudo apt-get install -y gpg
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor -o microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/{os-version}/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y {dotnet-package}
```

### <a name="failed-to-fetch"></a><span data-ttu-id="fd479-144">Ошибка получения</span><span class="sxs-lookup"><span data-stu-id="fd479-144">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]

## <a name="snap"></a><span data-ttu-id="fd479-145">Snap-пакеты</span><span class="sxs-lookup"><span data-stu-id="fd479-145">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="fd479-146">Зависимости</span><span class="sxs-lookup"><span data-stu-id="fd479-146">Dependencies</span></span>

<span data-ttu-id="fd479-147">Если для установки используется диспетчер пакетов, эти библиотеки устанавливаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="fd479-147">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="fd479-148">Но если вы устанавливаете .NET Core вручную или публикуете автономное приложение, вам потребуется установить эти библиотеки:</span><span class="sxs-lookup"><span data-stu-id="fd479-148">But, if you manually install .NET Core or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="fd479-149">libc6</span><span class="sxs-lookup"><span data-stu-id="fd479-149">libc6</span></span>
- <span data-ttu-id="fd479-150">libgcc1</span><span class="sxs-lookup"><span data-stu-id="fd479-150">libgcc1</span></span>
- <span data-ttu-id="fd479-151">libgssapi-krb5-2</span><span class="sxs-lookup"><span data-stu-id="fd479-151">libgssapi-krb5-2</span></span>
- <span data-ttu-id="fd479-152">libicu52 (для 8.x)</span><span class="sxs-lookup"><span data-stu-id="fd479-152">libicu52 (for 8.x)</span></span>
- <span data-ttu-id="fd479-153">libicu57 (для 9.x)</span><span class="sxs-lookup"><span data-stu-id="fd479-153">libicu57 (for 9.x)</span></span>
- <span data-ttu-id="fd479-154">libicu63 (для 10.x)</span><span class="sxs-lookup"><span data-stu-id="fd479-154">libicu63 (for 10.x)</span></span>
- <span data-ttu-id="fd479-155">libicu67 (для 11.x)</span><span class="sxs-lookup"><span data-stu-id="fd479-155">libicu67 (for 11.x)</span></span>
- <span data-ttu-id="fd479-156">libssl1.0.0 (для 8.x)</span><span class="sxs-lookup"><span data-stu-id="fd479-156">libssl1.0.0 (for 8.x)</span></span>
- <span data-ttu-id="fd479-157">libssl1.1 (для 9.x-11.x)</span><span class="sxs-lookup"><span data-stu-id="fd479-157">libssl1.1 (for 9.x-11.x)</span></span>
- <span data-ttu-id="fd479-158">libstdc++6</span><span class="sxs-lookup"><span data-stu-id="fd479-158">libstdc++6</span></span>
- <span data-ttu-id="fd479-159">zlib1g</span><span class="sxs-lookup"><span data-stu-id="fd479-159">zlib1g</span></span>

<span data-ttu-id="fd479-160">Для приложений .NET Core, использующих сборку *System.Drawing.Common*, необходима также следующая зависимость:</span><span class="sxs-lookup"><span data-stu-id="fd479-160">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="fd479-161">libgdiplus (версия 6.0.1 или выше)</span><span class="sxs-lookup"><span data-stu-id="fd479-161">libgdiplus (version 6.0.1 or later)</span></span>

  > [!WARNING]
  > <span data-ttu-id="fd479-162">Вы можете установить последнюю версию *libgdiplus*, добавив в систему репозиторий Mono.</span><span class="sxs-lookup"><span data-stu-id="fd479-162">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="fd479-163">Для получения дополнительной информации см. <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="fd479-163">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="scripted-install"></a><span data-ttu-id="fd479-164">Установка с помощью скрипта</span><span class="sxs-lookup"><span data-stu-id="fd479-164">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="fd479-165">Установка вручную</span><span class="sxs-lookup"><span data-stu-id="fd479-165">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="fd479-166">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="fd479-166">Next steps</span></span>

- [<span data-ttu-id="fd479-167">Учебник. Создание консольного приложения с помощью пакета SDK для .NET Core в Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="fd479-167">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
