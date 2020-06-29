---
title: Установка .NET Core на SLES (.NET Core)
description: Здесь приводятся различные способы установки пакета SDK для .NET Core и среды выполнения .NET Core в SLES.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: e1a2490c1d653eb07aebdd51e34e1bf462906482
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324697"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-sles"></a><span data-ttu-id="3e18e-103">Установка пакета SDK для .NET Core или среды выполнения .NET Core в SLES</span><span class="sxs-lookup"><span data-stu-id="3e18e-103">Install .NET Core SDK or .NET Core Runtime on SLES</span></span>

<span data-ttu-id="3e18e-104">.NET Core поддерживается в SLES.</span><span class="sxs-lookup"><span data-stu-id="3e18e-104">.NET Core is supported on SLES.</span></span> <span data-ttu-id="3e18e-105">В этой статье описано, как установить .NET Core в SLES.</span><span class="sxs-lookup"><span data-stu-id="3e18e-105">This article describes how to install .NET Core on SLES.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="supported-distributions"></a><span data-ttu-id="3e18e-106">Поддерживаемые дистрибутивы</span><span class="sxs-lookup"><span data-stu-id="3e18e-106">Supported distributions</span></span>

<span data-ttu-id="3e18e-107">В следующей таблице приведен список выпусков .NET Core, которые сейчас поддерживаются в SLES 12 SP2 и SLES 15.</span><span class="sxs-lookup"><span data-stu-id="3e18e-107">The following table is a list of currently supported .NET Core releases on both SLES 12 SP2 and SLES 15.</span></span> <span data-ttu-id="3e18e-108">Эти версии поддерживаются до тех пор, пока для версии [.NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) или версии SLES не будет прекращена поддержка.</span><span class="sxs-lookup"><span data-stu-id="3e18e-108">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of SLES is no longer supported.</span></span>

- <span data-ttu-id="3e18e-109">Значок ✔️ означает, что версия SLES или .NET Core поддерживается.</span><span class="sxs-lookup"><span data-stu-id="3e18e-109">A ✔️ indicates that the version of SLES or .NET Core is still supported.</span></span>
- <span data-ttu-id="3e18e-110">Значок ❌ означает, что версия SLES или версия .NET Core в таком выпуске SLES не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="3e18e-110">A ❌ indicates that the version of SLES or .NET Core isn't supported on that SLES release.</span></span>
- <span data-ttu-id="3e18e-111">Если значок ✔️ стоит как напротив версии SLES, так и напротив версии .NET Core, это значит, что такое сочетание ОС и .NET поддерживается.</span><span class="sxs-lookup"><span data-stu-id="3e18e-111">When both a version of SLES and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="3e18e-112">SLES</span><span class="sxs-lookup"><span data-stu-id="3e18e-112">SLES</span></span>                   | <span data-ttu-id="3e18e-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="3e18e-113">.NET Core 2.1</span></span> | <span data-ttu-id="3e18e-114">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="3e18e-114">.NET Core 3.1</span></span> | <span data-ttu-id="3e18e-115">Предварительная версия .NET 5 (только установка вручную)</span><span class="sxs-lookup"><span data-stu-id="3e18e-115">.NET 5 Preview (manual install only)</span></span> |
|------------------------|---------------|---------------|----------------|
| <span data-ttu-id="3e18e-116">✔️ [15](#sles-15-)</span><span class="sxs-lookup"><span data-stu-id="3e18e-116">✔️ [15](#sles-15-)</span></span>     | <span data-ttu-id="3e18e-117">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="3e18e-117">✔️ 2.1</span></span>        | <span data-ttu-id="3e18e-118">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="3e18e-118">✔️ 3.1</span></span>        | <span data-ttu-id="3e18e-119">✔️ 5.0 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="3e18e-119">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="3e18e-120">✔️ [12 SP2](#sles-12-)</span><span class="sxs-lookup"><span data-stu-id="3e18e-120">✔️ [12 SP2](#sles-12-)</span></span> | <span data-ttu-id="3e18e-121">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="3e18e-121">✔️ 2.1</span></span>        | <span data-ttu-id="3e18e-122">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="3e18e-122">✔️ 3.1</span></span>        | <span data-ttu-id="3e18e-123">✔️ 5.0 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="3e18e-123">✔️ 5.0 Preview</span></span> |

<span data-ttu-id="3e18e-124">Следующие версии .NET Core больше не поддерживаются</span><span class="sxs-lookup"><span data-stu-id="3e18e-124">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="3e18e-125">(но остаются доступными для скачивания):</span><span class="sxs-lookup"><span data-stu-id="3e18e-125">The downloads for these still remain published:</span></span>

- <span data-ttu-id="3e18e-126">3.0</span><span class="sxs-lookup"><span data-stu-id="3e18e-126">3.0</span></span>
- <span data-ttu-id="3e18e-127">2.2</span><span class="sxs-lookup"><span data-stu-id="3e18e-127">2.2</span></span>
- <span data-ttu-id="3e18e-128">2.0</span><span class="sxs-lookup"><span data-stu-id="3e18e-128">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="3e18e-129">Установка других версий</span><span class="sxs-lookup"><span data-stu-id="3e18e-129">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="sles-15-"></a><span data-ttu-id="3e18e-130">SLES 15 ✔️</span><span class="sxs-lookup"><span data-stu-id="3e18e-130">SLES 15 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/15/packages-microsoft-prod.rpm
```

<span data-ttu-id="3e18e-131">В настоящее время пакет установки репозитория Microsoft SLES 15 устанавливает файл *microsoft-prod.repo* в неправильный каталог, мешая поиску пакетов .NET Core в zypper.</span><span class="sxs-lookup"><span data-stu-id="3e18e-131">Currently, the SLES 15 Microsoft repository setup package installs the *microsoft-prod.repo* file to the wrong directory, preventing zypper from finding the .NET Core packages.</span></span> <span data-ttu-id="3e18e-132">Чтобы устранить эту проблему, создайте символьную ссылку в правильном каталоге.</span><span class="sxs-lookup"><span data-stu-id="3e18e-132">To fix this problem, create a symlink in the correct directory.</span></span>

```bash
sudo ln -s /etc/yum.repos.d/microsoft-prod.repo /etc/zypp/repos.d/microsoft-prod.repo
```

[!INCLUDE [linux-zyp-install-31](includes/linux-install-31-zyp.md)]

## <a name="sles-12-"></a><span data-ttu-id="3e18e-133">SLES 12 ✔️</span><span class="sxs-lookup"><span data-stu-id="3e18e-133">SLES 12 ✔️</span></span>

<span data-ttu-id="3e18e-134">.NET Core требуется как минимум семейство SLES 12 с пакетом обновления 2 (SP2).</span><span class="sxs-lookup"><span data-stu-id="3e18e-134">.NET Core requires SP2 as a minimum for the SLES 12 family.</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/12/packages-microsoft-prod.rpm
```

[!INCLUDE [linux-zyp-install-31](includes/linux-install-31-zyp.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="3e18e-135">Устранение неполадок диспетчера пакетов</span><span class="sxs-lookup"><span data-stu-id="3e18e-135">Troubleshoot the package manager</span></span>

<span data-ttu-id="3e18e-136">В этом разделе описаны распространенные ошибки, которые могут возникнуть при использовании диспетчера пакетов для установки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3e18e-136">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="3e18e-137">Ошибка получения</span><span class="sxs-lookup"><span data-stu-id="3e18e-137">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="dependencies"></a><span data-ttu-id="3e18e-138">Зависимости</span><span class="sxs-lookup"><span data-stu-id="3e18e-138">Dependencies</span></span>

[!INCLUDE [linux-install-dependencies](includes/linux-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="3e18e-139">Установка с помощью скрипта</span><span class="sxs-lookup"><span data-stu-id="3e18e-139">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="3e18e-140">Установка вручную</span><span class="sxs-lookup"><span data-stu-id="3e18e-140">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="3e18e-141">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="3e18e-141">Next steps</span></span>

- [<span data-ttu-id="3e18e-142">Учебник. Создание консольного приложения с помощью пакета SDK для .NET Core в Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="3e18e-142">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
