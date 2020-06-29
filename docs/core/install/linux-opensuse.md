---
title: Установка .NET Core в openSUSE (.NET Core)
description: Здесь приводятся различные способы установки пакета SDK для .NET Core и среды выполнения .NET Core в openSUSE.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 3a2ff1ca1519428f42c88048dde22aa11baaaa01
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324751"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-opensuse"></a><span data-ttu-id="8155b-103">Установка пакета SDK для .NET Core или среды выполнения .NET Core в openSUSE</span><span class="sxs-lookup"><span data-stu-id="8155b-103">Install .NET Core SDK or .NET Core Runtime on openSUSE</span></span>

<span data-ttu-id="8155b-104">.NET Core поддерживается в openSUSE.</span><span class="sxs-lookup"><span data-stu-id="8155b-104">.NET Core is supported on openSUSE.</span></span> <span data-ttu-id="8155b-105">В этой статье описано, как установить .NET Core в openSUSE.</span><span class="sxs-lookup"><span data-stu-id="8155b-105">This article describes how to install .NET Core on openSUSE.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="8155b-106">Поддерживаемые дистрибутивы</span><span class="sxs-lookup"><span data-stu-id="8155b-106">Supported distributions</span></span>

<span data-ttu-id="8155b-107">В следующей таблице приведен список выпусков .NET Core, которые сейчас поддерживаются в openSUSE 15.</span><span class="sxs-lookup"><span data-stu-id="8155b-107">The following table is a list of currently supported .NET Core releases on openSUSE 15.</span></span> <span data-ttu-id="8155b-108">Эти версии поддерживаются до тех пор, пока для версии [.NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) или версии openSUSE не будет прекращена поддержка.</span><span class="sxs-lookup"><span data-stu-id="8155b-108">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of openSUSE is no longer supported.</span></span>

- <span data-ttu-id="8155b-109">Значок ✔️ означает, что версия openSUSE или .NET Core поддерживается.</span><span class="sxs-lookup"><span data-stu-id="8155b-109">A ✔️ indicates that the version of openSUSE or .NET Core is still supported.</span></span>
- <span data-ttu-id="8155b-110">Значок ❌ означает, что версия openSUSE или версия .NET Core в таком выпуске openSUSE не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="8155b-110">A ❌ indicates that the version of openSUSE or .NET Core isn't supported on that openSUSE release.</span></span>
- <span data-ttu-id="8155b-111">Если значок ✔️ стоит как напротив версии openSUSE, так и напротив версии .NET Core, это значит, что такое сочетание ОС и .NET поддерживается.</span><span class="sxs-lookup"><span data-stu-id="8155b-111">When both a version of openSUSE and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="8155b-112">openSUSE</span><span class="sxs-lookup"><span data-stu-id="8155b-112">openSUSE</span></span>                   | <span data-ttu-id="8155b-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="8155b-113">.NET Core 2.1</span></span> | <span data-ttu-id="8155b-114">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="8155b-114">.NET Core 3.1</span></span> | <span data-ttu-id="8155b-115">Предварительная версия .NET 5 (только установка вручную)</span><span class="sxs-lookup"><span data-stu-id="8155b-115">.NET 5 Preview (manual install only)</span></span> |
|----------------------------|---------------|---------------|----------------|
| <span data-ttu-id="8155b-116">✔️ [15](#opensuse-15-)</span><span class="sxs-lookup"><span data-stu-id="8155b-116">✔️ [15](#opensuse-15-)</span></span>     | <span data-ttu-id="8155b-117">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="8155b-117">✔️ 2.1</span></span>        | <span data-ttu-id="8155b-118">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="8155b-118">✔️ 3.1</span></span>        | <span data-ttu-id="8155b-119">✔️ 5.0 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="8155b-119">✔️ 5.0 Preview</span></span> |

<span data-ttu-id="8155b-120">Следующие версии .NET Core больше не поддерживаются</span><span class="sxs-lookup"><span data-stu-id="8155b-120">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="8155b-121">(но остаются доступными для скачивания):</span><span class="sxs-lookup"><span data-stu-id="8155b-121">The downloads for these still remain published:</span></span>

- <span data-ttu-id="8155b-122">3.0</span><span class="sxs-lookup"><span data-stu-id="8155b-122">3.0</span></span>
- <span data-ttu-id="8155b-123">2.2</span><span class="sxs-lookup"><span data-stu-id="8155b-123">2.2</span></span>
- <span data-ttu-id="8155b-124">2.0</span><span class="sxs-lookup"><span data-stu-id="8155b-124">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="8155b-125">Установка других версий</span><span class="sxs-lookup"><span data-stu-id="8155b-125">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="opensuse-15-"></a><span data-ttu-id="8155b-126">openSUSE 15 ✔️</span><span class="sxs-lookup"><span data-stu-id="8155b-126">openSUSE 15 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

[!INCLUDE [linux-zyp-install-31](includes/linux-install-31-zyp.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="8155b-127">Устранение неполадок диспетчера пакетов</span><span class="sxs-lookup"><span data-stu-id="8155b-127">Troubleshoot the package manager</span></span>

<span data-ttu-id="8155b-128">В этом разделе описаны распространенные ошибки, которые могут возникнуть при использовании диспетчера пакетов для установки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8155b-128">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="8155b-129">Ошибка получения</span><span class="sxs-lookup"><span data-stu-id="8155b-129">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="snap"></a><span data-ttu-id="8155b-130">Snap-пакеты</span><span class="sxs-lookup"><span data-stu-id="8155b-130">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="8155b-131">Зависимости</span><span class="sxs-lookup"><span data-stu-id="8155b-131">Dependencies</span></span>

[!INCLUDE [linux-install-dependencies](includes/linux-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="8155b-132">Установка с помощью скрипта</span><span class="sxs-lookup"><span data-stu-id="8155b-132">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="8155b-133">Установка вручную</span><span class="sxs-lookup"><span data-stu-id="8155b-133">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="8155b-134">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="8155b-134">Next steps</span></span>

- [<span data-ttu-id="8155b-135">Учебник. Создание консольного приложения с помощью пакета SDK для .NET Core в Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="8155b-135">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
