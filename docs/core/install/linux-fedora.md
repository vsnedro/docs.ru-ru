---
title: Установка .NET Core в Fedora — .NET Core
description: Здесь приводятся различные способы установки пакета SDK для .NET Core и среды выполнения .NET Core в Fedora.
author: thraka
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 52aa9409ec876e0d1eaef22fb739046941fda897
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602840"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-fedora"></a><span data-ttu-id="71518-103">Установка пакета SDK для .NET Core или среды выполнения .NET Core в Fedora</span><span class="sxs-lookup"><span data-stu-id="71518-103">Install .NET Core SDK or .NET Core Runtime on Fedora</span></span>

<span data-ttu-id="71518-104">.NET Core поддерживается в Fedora.</span><span class="sxs-lookup"><span data-stu-id="71518-104">.NET Core is supported on Fedora.</span></span> <span data-ttu-id="71518-105">В этой статье описано, как установить .NET Core в Fedora.</span><span class="sxs-lookup"><span data-stu-id="71518-105">This article describes how to install .NET Core on Fedora.</span></span> <span data-ttu-id="71518-106">Если поддержка какой-либо версии Fedora прекращается, то .NET Core также перестает поддерживать ее.</span><span class="sxs-lookup"><span data-stu-id="71518-106">When a Fedora version falls out of support, .NET Core is no longer supported with that version.</span></span> <span data-ttu-id="71518-107">Но с помощью этих инструкций вы сможете запустить .NET Core даже в неподдерживаемых версиях.</span><span class="sxs-lookup"><span data-stu-id="71518-107">However, these instructions may help you to get .NET Core running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="71518-108">Поддерживаемые дистрибутивы</span><span class="sxs-lookup"><span data-stu-id="71518-108">Supported distributions</span></span>

<span data-ttu-id="71518-109">В приведенной ниже таблице содержится список поддерживаемых сейчас выпусков .NET Core и версий Fedora, в которых они поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="71518-109">The following table is a list of currently supported .NET Core releases and the versions of Fedora they're supported on.</span></span> <span data-ttu-id="71518-110">Эти версии поддерживаются до того же времени, что и версия [.NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) или [Fedora](https://fedoraproject.org/wiki/End_of_life).</span><span class="sxs-lookup"><span data-stu-id="71518-110">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Fedora reaches end-of-life](https://fedoraproject.org/wiki/End_of_life).</span></span>

- <span data-ttu-id="71518-111">Значок ✔️ означает, что версия Fedora или .NET Core поддерживается.</span><span class="sxs-lookup"><span data-stu-id="71518-111">A ✔️ indicates that the version of Fedora or .NET Core is still supported.</span></span>
- <span data-ttu-id="71518-112">Значок ❌ означает, что версия Fedora или версия .NET Core в таком выпуске Fedora не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="71518-112">A ❌ indicates that the version of Fedora or .NET Core isn't supported on that Fedora release.</span></span>
- <span data-ttu-id="71518-113">Если значок ✔️ стоит как напротив версии Fedora, так и напротив версии .NET Core, это значит, что такое сочетание ОС и .NET поддерживается.</span><span class="sxs-lookup"><span data-stu-id="71518-113">When both a version of Fedora and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="71518-114">Fedora</span><span class="sxs-lookup"><span data-stu-id="71518-114">Fedora</span></span>                   | <span data-ttu-id="71518-115">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="71518-115">.NET Core 2.1</span></span> | <span data-ttu-id="71518-116">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="71518-116">.NET Core 3.1</span></span> | <span data-ttu-id="71518-117">Предварительная версия .NET 5 (только установка вручную)</span><span class="sxs-lookup"><span data-stu-id="71518-117">.NET 5 Preview (manual install only)</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="71518-118">✔️ [32](linux-fedora.md#fedora-32-)</span><span class="sxs-lookup"><span data-stu-id="71518-118">✔️ [32](linux-fedora.md#fedora-32-)</span></span> | <span data-ttu-id="71518-119">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="71518-119">✔️ 2.1</span></span>        | <span data-ttu-id="71518-120">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="71518-120">✔️ 3.1</span></span>        | <span data-ttu-id="71518-121">✔️ 5.0 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="71518-121">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="71518-122">✔️ [31](linux-fedora.md#fedora-31-)</span><span class="sxs-lookup"><span data-stu-id="71518-122">✔️ [31](linux-fedora.md#fedora-31-)</span></span> | <span data-ttu-id="71518-123">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="71518-123">✔️ 2.1</span></span>        | <span data-ttu-id="71518-124">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="71518-124">✔️ 3.1</span></span>        | <span data-ttu-id="71518-125">✔️ 5.0 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="71518-125">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="71518-126">❌ [30](linux-fedora.md#fedora-30-)</span><span class="sxs-lookup"><span data-stu-id="71518-126">❌ [30](linux-fedora.md#fedora-30-)</span></span> | <span data-ttu-id="71518-127">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="71518-127">✔️ 2.1</span></span>        | <span data-ttu-id="71518-128">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="71518-128">✔️ 3.1</span></span>        | <span data-ttu-id="71518-129">❌ 5.0 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="71518-129">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="71518-130">❌ [29](linux-fedora.md#fedora-29-)</span><span class="sxs-lookup"><span data-stu-id="71518-130">❌ [29](linux-fedora.md#fedora-29-)</span></span> | <span data-ttu-id="71518-131">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="71518-131">✔️ 2.1</span></span>        | <span data-ttu-id="71518-132">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="71518-132">✔️ 3.1</span></span>        | <span data-ttu-id="71518-133">❌ 5.0 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="71518-133">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="71518-134">❌ [28](linux-fedora.md#fedora-28-)</span><span class="sxs-lookup"><span data-stu-id="71518-134">❌ [28](linux-fedora.md#fedora-28-)</span></span> | <span data-ttu-id="71518-135">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="71518-135">✔️ 2.1</span></span>        | <span data-ttu-id="71518-136">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="71518-136">❌ 3.1</span></span>        | <span data-ttu-id="71518-137">❌ 5.0 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="71518-137">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="71518-138">❌ [27](linux-fedora.md#fedora-27-)</span><span class="sxs-lookup"><span data-stu-id="71518-138">❌ [27](linux-fedora.md#fedora-27-)</span></span> | <span data-ttu-id="71518-139">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="71518-139">✔️ 2.1</span></span>        | <span data-ttu-id="71518-140">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="71518-140">❌ 3.1</span></span>        | <span data-ttu-id="71518-141">❌ 5.0 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="71518-141">❌ 5.0 Preview</span></span> |

<span data-ttu-id="71518-142">Следующие версии .NET Core больше не поддерживаются,</span><span class="sxs-lookup"><span data-stu-id="71518-142">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="71518-143">но остаются доступными для скачивания:</span><span class="sxs-lookup"><span data-stu-id="71518-143">The downloads for these still remain published:</span></span>

- <span data-ttu-id="71518-144">3.0</span><span class="sxs-lookup"><span data-stu-id="71518-144">3.0</span></span>
- <span data-ttu-id="71518-145">2.2</span><span class="sxs-lookup"><span data-stu-id="71518-145">2.2</span></span>
- <span data-ttu-id="71518-146">2.0</span><span class="sxs-lookup"><span data-stu-id="71518-146">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="71518-147">Установка других версий</span><span class="sxs-lookup"><span data-stu-id="71518-147">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="fedora-32-"></a><span data-ttu-id="71518-148">Fedora 32 ✔️</span><span class="sxs-lookup"><span data-stu-id="71518-148">Fedora 32 ✔️</span></span>

<span data-ttu-id="71518-149">.NET Core 3.1 предоставляется в репозиториях пакетов по умолчанию для Fedora 32.</span><span class="sxs-lookup"><span data-stu-id="71518-149">.NET Core 3.1 is available in the default package repositories for Fedora 32.</span></span>

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="fedora-31-"></a><span data-ttu-id="71518-150">Fedora 31 ✔️</span><span class="sxs-lookup"><span data-stu-id="71518-150">Fedora 31 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/31/prod.repo
```

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="fedora-30-"></a><span data-ttu-id="71518-151">Fedora 30 ❌</span><span class="sxs-lookup"><span data-stu-id="71518-151">Fedora 30 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/30/prod.repo
```

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="fedora-29-"></a><span data-ttu-id="71518-152">Fedora 29 ❌</span><span class="sxs-lookup"><span data-stu-id="71518-152">Fedora 29 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/29/prod.repo
```

[!INCLUDE [linux-dnf-install-30](includes/linux-install-30-dnf.md)]

## <a name="fedora-28-"></a><span data-ttu-id="71518-153">Fedora 28 ❌</span><span class="sxs-lookup"><span data-stu-id="71518-153">Fedora 28 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/28/prod.repo
```

[!INCLUDE [linux-dnf-install-20](includes/linux-install-20-dnf.md)]

## <a name="fedora-27-"></a><span data-ttu-id="71518-154">Fedora 27 ❌</span><span class="sxs-lookup"><span data-stu-id="71518-154">Fedora 27 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/27/prod.repo
```

[!INCLUDE [linux-dnf-install-20](includes/linux-install-20-dnf.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="71518-155">Устранение неполадок диспетчера пакетов</span><span class="sxs-lookup"><span data-stu-id="71518-155">Troubleshoot the package manager</span></span>

<span data-ttu-id="71518-156">В этом разделе описаны распространенные ошибки, которые могут возникнуть при использовании диспетчера пакетов для установки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="71518-156">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="71518-157">Ошибка получения</span><span class="sxs-lookup"><span data-stu-id="71518-157">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="snap"></a><span data-ttu-id="71518-158">Snap-пакеты</span><span class="sxs-lookup"><span data-stu-id="71518-158">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="71518-159">Зависимости</span><span class="sxs-lookup"><span data-stu-id="71518-159">Dependencies</span></span>

[!INCLUDE [linux-install-dependencies](includes/linux-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="71518-160">Установка с помощью скрипта</span><span class="sxs-lookup"><span data-stu-id="71518-160">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="71518-161">Установка вручную</span><span class="sxs-lookup"><span data-stu-id="71518-161">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="71518-162">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="71518-162">Next steps</span></span>

- [<span data-ttu-id="71518-163">Учебник. Создание консольного приложения с помощью пакета SDK для .NET Core в Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="71518-163">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
