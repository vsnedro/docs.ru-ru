---
title: Установка .NET Core в Alpine — .NET Core
description: Здесь приводятся различные способы установки пакета SDK для .NET Core и среды выполнения .NET Core в Alpine.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 92753933cbcedae28867b66293d1044f700d7baa
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324836"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-alpine"></a><span data-ttu-id="b19a6-103">Установка пакета SDK для .NET Core или среды выполнения .NET Core в Alpine</span><span class="sxs-lookup"><span data-stu-id="b19a6-103">Install .NET Core SDK or .NET Core Runtime on Alpine</span></span>

<span data-ttu-id="b19a6-104">В этой статье описано, как установить .NET Core в Alpine.</span><span class="sxs-lookup"><span data-stu-id="b19a6-104">This article describes how to install .NET Core on Alpine.</span></span> <span data-ttu-id="b19a6-105">Если поддержка какой-либо версии Alpine прекращается, то .NET Core также перестает поддерживать ее.</span><span class="sxs-lookup"><span data-stu-id="b19a6-105">When a Alpine version falls out of support, .NET Core is no longer supported with that version.</span></span> <span data-ttu-id="b19a6-106">Но с помощью этих инструкций вы сможете запустить .NET Core даже в неподдерживаемых версиях.</span><span class="sxs-lookup"><span data-stu-id="b19a6-106">However, these instructions may help you to get .NET Core running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

<span data-ttu-id="b19a6-107">Установщиков для Alpine не существует.</span><span class="sxs-lookup"><span data-stu-id="b19a6-107">There are no installers for Alpine.</span></span> <span data-ttu-id="b19a6-108">Необходимо либо использовать [сценарий установки](#scripted-install), либо следовать инструкциям по [установке вручную](#manual-install).</span><span class="sxs-lookup"><span data-stu-id="b19a6-108">You must either use the [install script](#scripted-install) or follow the [manual install](#manual-install) instructions.</span></span>

## <a name="supported-distributions"></a><span data-ttu-id="b19a6-109">Поддерживаемые дистрибутивы</span><span class="sxs-lookup"><span data-stu-id="b19a6-109">Supported distributions</span></span>

<span data-ttu-id="b19a6-110">В приведенной ниже таблице содержится список поддерживаемых сейчас выпусков .NET Core и версий Alpine, в которых они поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="b19a6-110">The following table is a list of currently supported .NET Core releases and the versions of Alpine they're supported on.</span></span> <span data-ttu-id="b19a6-111">Эти версии поддерживаются до того же времени, что и версия [.NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) или [Alpine](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases).</span><span class="sxs-lookup"><span data-stu-id="b19a6-111">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Alpine reaches end-of-life](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases).</span></span>

- <span data-ttu-id="b19a6-112">Значок ✔️ означает, что версия Alpine или .NET Core поддерживается.</span><span class="sxs-lookup"><span data-stu-id="b19a6-112">A ✔️ indicates that the version of Alpine or .NET Core is still supported.</span></span>
- <span data-ttu-id="b19a6-113">Значок ❌ означает, что версия Alpine или версия .NET Core в таком выпуске Alpine не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="b19a6-113">A ❌ indicates that the version of Alpine or .NET Core isn't supported on that Alpine release.</span></span>
- <span data-ttu-id="b19a6-114">Если значок ✔️ стоит как напротив версии Alpine, так и напротив версии .NET Core, это значит, что такое сочетание ОС и .NET поддерживается.</span><span class="sxs-lookup"><span data-stu-id="b19a6-114">When both a version of Alpine and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="b19a6-115">Alpine</span><span class="sxs-lookup"><span data-stu-id="b19a6-115">Alpine</span></span>                   | <span data-ttu-id="b19a6-116">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="b19a6-116">.NET Core 2.1</span></span> | <span data-ttu-id="b19a6-117">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="b19a6-117">.NET Core 3.1</span></span> | <span data-ttu-id="b19a6-118">Предварительная версия .NET 5</span><span class="sxs-lookup"><span data-stu-id="b19a6-118">.NET 5 Preview</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="b19a6-119">✔️ 3.12</span><span class="sxs-lookup"><span data-stu-id="b19a6-119">✔️ 3.12</span></span>  | <span data-ttu-id="b19a6-120">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="b19a6-120">✔️ 2.1</span></span>        | <span data-ttu-id="b19a6-121">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="b19a6-121">✔️ 3.1</span></span>        | <span data-ttu-id="b19a6-122">✔️ 5.0 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="b19a6-122">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="b19a6-123">✔️ 3.11</span><span class="sxs-lookup"><span data-stu-id="b19a6-123">✔️ 3.11</span></span>  | <span data-ttu-id="b19a6-124">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="b19a6-124">✔️ 2.1</span></span>        | <span data-ttu-id="b19a6-125">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="b19a6-125">✔️ 3.1</span></span>        | <span data-ttu-id="b19a6-126">✔️ 5.0 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="b19a6-126">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="b19a6-127">✔️ 3.10</span><span class="sxs-lookup"><span data-stu-id="b19a6-127">✔️ 3.10</span></span>  | <span data-ttu-id="b19a6-128">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="b19a6-128">✔️ 2.1</span></span>        | <span data-ttu-id="b19a6-129">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="b19a6-129">✔️ 3.1</span></span>        | <span data-ttu-id="b19a6-130">✔️ 5.0 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="b19a6-130">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="b19a6-131">✔️ 3.9</span><span class="sxs-lookup"><span data-stu-id="b19a6-131">✔️ 3.9</span></span>   | <span data-ttu-id="b19a6-132">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="b19a6-132">✔️ 2.1</span></span>        | <span data-ttu-id="b19a6-133">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="b19a6-133">✔️ 3.1</span></span>        | <span data-ttu-id="b19a6-134">✔️ 5.0 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="b19a6-134">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="b19a6-135">❌ 3.8</span><span class="sxs-lookup"><span data-stu-id="b19a6-135">❌ 3.8</span></span>   | <span data-ttu-id="b19a6-136">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="b19a6-136">✔️ 2.1</span></span>        | <span data-ttu-id="b19a6-137">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="b19a6-137">❌ 3.1</span></span>        | <span data-ttu-id="b19a6-138">❌ 5.0 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="b19a6-138">❌ 5.0 Preview</span></span> |

<span data-ttu-id="b19a6-139">Следующие версии .NET Core больше не поддерживаются,</span><span class="sxs-lookup"><span data-stu-id="b19a6-139">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="b19a6-140">(но остаются доступными для скачивания):</span><span class="sxs-lookup"><span data-stu-id="b19a6-140">The downloads for these still remain published:</span></span>

- <span data-ttu-id="b19a6-141">3.0</span><span class="sxs-lookup"><span data-stu-id="b19a6-141">3.0</span></span>
- <span data-ttu-id="b19a6-142">2.2</span><span class="sxs-lookup"><span data-stu-id="b19a6-142">2.2</span></span>
- <span data-ttu-id="b19a6-143">2.0</span><span class="sxs-lookup"><span data-stu-id="b19a6-143">2.0</span></span>

## <a name="dependencies"></a><span data-ttu-id="b19a6-144">Зависимости</span><span class="sxs-lookup"><span data-stu-id="b19a6-144">Dependencies</span></span>

<span data-ttu-id="b19a6-145">Для .NET Core в Alpine Linux необходимо установить следующие зависимости:</span><span class="sxs-lookup"><span data-stu-id="b19a6-145">.NET Core on Alpine Linux requires the following dependencies installed:</span></span>

- <span data-ttu-id="b19a6-146">icu-libs</span><span class="sxs-lookup"><span data-stu-id="b19a6-146">icu-libs</span></span>
- <span data-ttu-id="b19a6-147">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="b19a6-147">krb5-libs</span></span>
- <span data-ttu-id="b19a6-148">libintl</span><span class="sxs-lookup"><span data-stu-id="b19a6-148">libintl</span></span>
- <span data-ttu-id="b19a6-149">libssl 1.1 (Alpine версии 3.9 или более поздней)</span><span class="sxs-lookup"><span data-stu-id="b19a6-149">libssl1.1 (Alpine v3.9 or greater)</span></span>
- <span data-ttu-id="b19a6-150">libssl 1.0 (Alpine версии 3.8)</span><span class="sxs-lookup"><span data-stu-id="b19a6-150">libssl1.0 (Alpine v3.8)</span></span>
- <span data-ttu-id="b19a6-151">libstdc++</span><span class="sxs-lookup"><span data-stu-id="b19a6-151">libstdc++</span></span>
- <span data-ttu-id="b19a6-152">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="b19a6-152">lttng-ust</span></span>
- <span data-ttu-id="b19a6-153">numactl (необязательно)</span><span class="sxs-lookup"><span data-stu-id="b19a6-153">numactl (optional)</span></span>
- <span data-ttu-id="b19a6-154">zlib</span><span class="sxs-lookup"><span data-stu-id="b19a6-154">zlib</span></span>

## <a name="scripted-install"></a><span data-ttu-id="b19a6-155">Установка с помощью сценария</span><span class="sxs-lookup"><span data-stu-id="b19a6-155">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="b19a6-156">Установка вручную</span><span class="sxs-lookup"><span data-stu-id="b19a6-156">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="b19a6-157">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="b19a6-157">Next steps</span></span>

- [<span data-ttu-id="b19a6-158">Учебник. Создание консольного приложения с помощью пакета SDK для .NET Core в Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="b19a6-158">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
