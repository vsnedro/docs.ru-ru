---
title: Установка .NET Core в Debian (.NET Core)
description: Здесь приводятся различные способы установки пакета SDK для .NET Core и среды выполнения .NET Core в Debian.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 68a3e848b3d80806e875dfb2fb7e2cbf223f8ad5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619498"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-debian"></a><span data-ttu-id="74ba9-103">Установка пакета SDK для .NET Core или среды выполнения .NET Core в Debian</span><span class="sxs-lookup"><span data-stu-id="74ba9-103">Install .NET Core SDK or .NET Core Runtime on Debian</span></span>

<span data-ttu-id="74ba9-104">В этой статье описано, как установить .NET Core в Debian.</span><span class="sxs-lookup"><span data-stu-id="74ba9-104">This article describes how to install .NET Core on Debian.</span></span> <span data-ttu-id="74ba9-105">Если поддержка какой-либо версии Debian прекращается, то .NET Core также перестает поддерживать ее.</span><span class="sxs-lookup"><span data-stu-id="74ba9-105">When a Debian version falls out of support, .NET Core is no longer supported with that version.</span></span> <span data-ttu-id="74ba9-106">Но с помощью этих инструкций вы сможете запустить .NET Core даже в неподдерживаемых версиях.</span><span class="sxs-lookup"><span data-stu-id="74ba9-106">However, these instructions may help you to get .NET Core running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="74ba9-107">Поддерживаемые дистрибутивы</span><span class="sxs-lookup"><span data-stu-id="74ba9-107">Supported distributions</span></span>

<span data-ttu-id="74ba9-108">В приведенной ниже таблице содержится список поддерживаемых сейчас выпусков .NET Core и версий Debian, в которых они поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="74ba9-108">The following table is a list of currently supported .NET Core releases and the versions of Debian they're supported on.</span></span> <span data-ttu-id="74ba9-109">Эти версии поддерживаются до того же времени, что и версия [.NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) или [Debian](https://wiki.debian.org/DebianReleases).</span><span class="sxs-lookup"><span data-stu-id="74ba9-109">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Debian reaches end-of-life](https://wiki.debian.org/DebianReleases).</span></span>

- <span data-ttu-id="74ba9-110">Значок ✔️ означает, что версия Debian или .NET Core поддерживается.</span><span class="sxs-lookup"><span data-stu-id="74ba9-110">A ✔️ indicates that the version of Debian or .NET Core is still supported.</span></span>
- <span data-ttu-id="74ba9-111">Значок ❌ означает, что версия Debian или версия .NET Core в таком выпуске Debian не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="74ba9-111">A ❌ indicates that the version of Debian or .NET Core isn't supported on that Debian release.</span></span>
- <span data-ttu-id="74ba9-112">Если значок ✔️ стоит как напротив версии Debian, так и напротив версии .NET Core, это значит, что такое сочетание ОС и .NET поддерживается.</span><span class="sxs-lookup"><span data-stu-id="74ba9-112">When both a version of Debian and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="74ba9-113">Debian</span><span class="sxs-lookup"><span data-stu-id="74ba9-113">Debian</span></span>                   | <span data-ttu-id="74ba9-114">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="74ba9-114">.NET Core 2.1</span></span> | <span data-ttu-id="74ba9-115">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="74ba9-115">.NET Core 3.1</span></span> | <span data-ttu-id="74ba9-116">Предварительная версия .NET 5 (только установка вручную)</span><span class="sxs-lookup"><span data-stu-id="74ba9-116">.NET 5 Preview (manual install only)</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="74ba9-117">✔️ [10](#debian-10-)</span><span class="sxs-lookup"><span data-stu-id="74ba9-117">✔️ [10](#debian-10-)</span></span>     | <span data-ttu-id="74ba9-118">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="74ba9-118">✔️ 2.1</span></span>        | <span data-ttu-id="74ba9-119">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="74ba9-119">✔️ 3.1</span></span>        | <span data-ttu-id="74ba9-120">✔️ 5.0 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="74ba9-120">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="74ba9-121">✔️ [9](#debian-9-)</span><span class="sxs-lookup"><span data-stu-id="74ba9-121">✔️ [9](#debian-9-)</span></span>       | <span data-ttu-id="74ba9-122">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="74ba9-122">✔️ 2.1</span></span>        | <span data-ttu-id="74ba9-123">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="74ba9-123">✔️ 3.1</span></span>        | <span data-ttu-id="74ba9-124">✔️ 5.0 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="74ba9-124">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="74ba9-125">❌ [8](#debian-8-)</span><span class="sxs-lookup"><span data-stu-id="74ba9-125">❌ [8](#debian-8-)</span></span>       | <span data-ttu-id="74ba9-126">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="74ba9-126">✔️ 2.1</span></span>        | <span data-ttu-id="74ba9-127">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="74ba9-127">❌ 3.1</span></span>        | <span data-ttu-id="74ba9-128">❌ 5.0 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="74ba9-128">❌ 5.0 Preview</span></span> |

<span data-ttu-id="74ba9-129">Следующие версии .NET Core больше не поддерживаются,</span><span class="sxs-lookup"><span data-stu-id="74ba9-129">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="74ba9-130">(но остаются доступными для скачивания):</span><span class="sxs-lookup"><span data-stu-id="74ba9-130">The downloads for these still remain published:</span></span>

- <span data-ttu-id="74ba9-131">3.0</span><span class="sxs-lookup"><span data-stu-id="74ba9-131">3.0</span></span>
- <span data-ttu-id="74ba9-132">2.2</span><span class="sxs-lookup"><span data-stu-id="74ba9-132">2.2</span></span>
- <span data-ttu-id="74ba9-133">2.0</span><span class="sxs-lookup"><span data-stu-id="74ba9-133">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="74ba9-134">Установка других версий</span><span class="sxs-lookup"><span data-stu-id="74ba9-134">How to install other versions</span></span>

[!INCLUDE [hack-pkgname](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="debian-10-"></a><span data-ttu-id="74ba9-135">Debian 10 ✔️</span><span class="sxs-lookup"><span data-stu-id="74ba9-135">Debian 10 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/debian/10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="debian-9-"></a><span data-ttu-id="74ba9-136">Debian 9 ✔️</span><span class="sxs-lookup"><span data-stu-id="74ba9-136">Debian 9 ✔️</span></span>

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

## <a name="debian-8-"></a><span data-ttu-id="74ba9-137">Debian 8 ❌</span><span class="sxs-lookup"><span data-stu-id="74ba9-137">Debian 8 ❌</span></span>

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

## <a name="apt-update-sdk-or-runtime"></a><span data-ttu-id="74ba9-138">Обновление пакета SDK или среды выполнения с помощью APT</span><span class="sxs-lookup"><span data-stu-id="74ba9-138">APT update SDK or runtime</span></span>

<span data-ttu-id="74ba9-139">Если для .NET Core доступен новый выпуск исправлений, можете выполнить обновление с помощью APT и следующих команд:</span><span class="sxs-lookup"><span data-stu-id="74ba9-139">When a new patch release is available for .NET Core, you can simply upgrade it through APT with the following commands:</span></span>

```bash
sudo apt-get update
sudo apt-get upgrade
```

## <a name="apt-troubleshooting"></a><span data-ttu-id="74ba9-140">Устранение неполадок с APT</span><span class="sxs-lookup"><span data-stu-id="74ba9-140">APT troubleshooting</span></span>

<span data-ttu-id="74ba9-141">В этом разделе описаны распространенные ошибки, которые могут возникнуть при использовании APT для установки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="74ba9-141">This section provides information on common errors you may get while using APT to install .NET Core.</span></span>

### <a name="unable-to-locate"></a><span data-ttu-id="74ba9-142">Ошибка обнаружения</span><span class="sxs-lookup"><span data-stu-id="74ba9-142">Unable to locate</span></span>

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

### <a name="failed-to-fetch"></a><span data-ttu-id="74ba9-143">Ошибка получения</span><span class="sxs-lookup"><span data-stu-id="74ba9-143">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]

## <a name="snap"></a><span data-ttu-id="74ba9-144">Snap-пакеты</span><span class="sxs-lookup"><span data-stu-id="74ba9-144">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="74ba9-145">Зависимости</span><span class="sxs-lookup"><span data-stu-id="74ba9-145">Dependencies</span></span>

<span data-ttu-id="74ba9-146">Если для установки используется диспетчер пакетов, эти библиотеки устанавливаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="74ba9-146">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="74ba9-147">Но если вы устанавливаете .NET Core вручную или публикуете автономное приложение, вам потребуется установить эти библиотеки:</span><span class="sxs-lookup"><span data-stu-id="74ba9-147">But, if you manually install .NET Core or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="74ba9-148">libc6</span><span class="sxs-lookup"><span data-stu-id="74ba9-148">libc6</span></span>
- <span data-ttu-id="74ba9-149">libgcc1</span><span class="sxs-lookup"><span data-stu-id="74ba9-149">libgcc1</span></span>
- <span data-ttu-id="74ba9-150">libgssapi-krb5-2</span><span class="sxs-lookup"><span data-stu-id="74ba9-150">libgssapi-krb5-2</span></span>
- <span data-ttu-id="74ba9-151">libicu52 (для 8.x)</span><span class="sxs-lookup"><span data-stu-id="74ba9-151">libicu52 (for 8.x)</span></span>
- <span data-ttu-id="74ba9-152">libicu57 (для 9.x)</span><span class="sxs-lookup"><span data-stu-id="74ba9-152">libicu57 (for 9.x)</span></span>
- <span data-ttu-id="74ba9-153">libicu63 (для 10.x)</span><span class="sxs-lookup"><span data-stu-id="74ba9-153">libicu63 (for 10.x)</span></span>
- <span data-ttu-id="74ba9-154">libicu67 (для 11.x)</span><span class="sxs-lookup"><span data-stu-id="74ba9-154">libicu67 (for 11.x)</span></span>
- <span data-ttu-id="74ba9-155">libssl1.0.0 (для 8.x)</span><span class="sxs-lookup"><span data-stu-id="74ba9-155">libssl1.0.0 (for 8.x)</span></span>
- <span data-ttu-id="74ba9-156">libssl1.1 (для 9.x-11.x)</span><span class="sxs-lookup"><span data-stu-id="74ba9-156">libssl1.1 (for 9.x-11.x)</span></span>
- <span data-ttu-id="74ba9-157">libstdc++6</span><span class="sxs-lookup"><span data-stu-id="74ba9-157">libstdc++6</span></span>
- <span data-ttu-id="74ba9-158">zlib1g</span><span class="sxs-lookup"><span data-stu-id="74ba9-158">zlib1g</span></span>

<span data-ttu-id="74ba9-159">Для приложений .NET Core, использующих сборку *System.Drawing.Common*, необходима также следующая зависимость:</span><span class="sxs-lookup"><span data-stu-id="74ba9-159">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="74ba9-160">libgdiplus (версия 6.0.1 или выше)</span><span class="sxs-lookup"><span data-stu-id="74ba9-160">libgdiplus (version 6.0.1 or later)</span></span>

  > [!WARNING]
  > <span data-ttu-id="74ba9-161">Вы можете установить последнюю версию *libgdiplus*, добавив в систему репозиторий Mono.</span><span class="sxs-lookup"><span data-stu-id="74ba9-161">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="74ba9-162">Для получения дополнительной информации см. <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="74ba9-162">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="scripted-install"></a><span data-ttu-id="74ba9-163">Установка с помощью скрипта</span><span class="sxs-lookup"><span data-stu-id="74ba9-163">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="74ba9-164">Установка вручную</span><span class="sxs-lookup"><span data-stu-id="74ba9-164">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="74ba9-165">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="74ba9-165">Next steps</span></span>

- [<span data-ttu-id="74ba9-166">Учебник. Создание консольного приложения с помощью пакета SDK для .NET Core в Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="74ba9-166">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
