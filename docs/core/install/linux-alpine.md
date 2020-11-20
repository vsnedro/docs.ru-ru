---
title: Установка .NET в Alpine — .NET
description: Здесь приводятся различные способы установки пакета SDK для .NET и среды выполнения .NET в Alpine.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 29901cc24ddd4bbe8200a36765ddd29f501394c0
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506835"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-alpine"></a><span data-ttu-id="91984-103">Установка пакета SDK для .NET или среды выполнения .NET в Alpine</span><span class="sxs-lookup"><span data-stu-id="91984-103">Install the .NET SDK or the .NET Runtime on Alpine</span></span>

<span data-ttu-id="91984-104">В этой статье описано, как установить .NET в Alpine.</span><span class="sxs-lookup"><span data-stu-id="91984-104">This article describes how to install .NET on Alpine.</span></span> <span data-ttu-id="91984-105">Если поддержка какой-либо версии Alpine прекращается, то .NET также перестает поддерживать ее.</span><span class="sxs-lookup"><span data-stu-id="91984-105">When an Alpine version falls out of support, .NET is no longer supported with that version.</span></span> <span data-ttu-id="91984-106">Но с помощью этих инструкций вы сможете запустить .NET даже в неподдерживаемых версиях.</span><span class="sxs-lookup"><span data-stu-id="91984-106">However, these instructions may help you to get .NET running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

<span data-ttu-id="91984-107">Установщиков для Alpine не существует.</span><span class="sxs-lookup"><span data-stu-id="91984-107">There are no installers for Alpine.</span></span> <span data-ttu-id="91984-108">Необходимо либо использовать [сценарий установки](#scripted-install), либо следовать инструкциям по [установке вручную](#manual-install).</span><span class="sxs-lookup"><span data-stu-id="91984-108">You must either use the [install script](#scripted-install) or follow the [manual install](#manual-install) instructions.</span></span>

## <a name="supported-distributions"></a><span data-ttu-id="91984-109">Поддерживаемые дистрибутивы</span><span class="sxs-lookup"><span data-stu-id="91984-109">Supported distributions</span></span>

<span data-ttu-id="91984-110">В приведенной ниже таблице содержится список поддерживаемых сейчас выпусков .NET и версий Alpine, в которых они поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="91984-110">The following table is a list of currently supported .NET releases and the versions of Alpine they're supported on.</span></span> <span data-ttu-id="91984-111">Эти версии поддерживаются до окончания поддержки версии [.NET](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) либо до окончания жизненного цикла версии [Alpine](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases).</span><span class="sxs-lookup"><span data-stu-id="91984-111">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Alpine reaches end-of-life](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases).</span></span>

- <span data-ttu-id="91984-112">Значок ✔️ означает, что версия Alpine или .NET поддерживается.</span><span class="sxs-lookup"><span data-stu-id="91984-112">A ✔️ indicates that the version of Alpine or .NET is still supported.</span></span>
- <span data-ttu-id="91984-113">Значок ❌ означает, что версия Alpine или версия .NET в таком выпуске Alpine не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="91984-113">A ❌ indicates that the version of Alpine or .NET isn't supported on that Alpine release.</span></span>
- <span data-ttu-id="91984-114">Если значок ✔️ стоит как напротив версии Alpine, так и напротив версии .NET, это значит, что такое сочетание ОС и .NET поддерживается.</span><span class="sxs-lookup"><span data-stu-id="91984-114">When both a version of Alpine and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="91984-115">Alpine</span><span class="sxs-lookup"><span data-stu-id="91984-115">Alpine</span></span>  | <span data-ttu-id="91984-116">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="91984-116">.NET Core 2.1</span></span> | <span data-ttu-id="91984-117">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="91984-117">.NET Core 3.1</span></span> | <span data-ttu-id="91984-118">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="91984-118">.NET 5.0</span></span> |
|-------- |---------------|---------------|----------------|
| <span data-ttu-id="91984-119">✔️ 3.12</span><span class="sxs-lookup"><span data-stu-id="91984-119">✔️ 3.12</span></span> | <span data-ttu-id="91984-120">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="91984-120">✔️ 2.1</span></span>        | <span data-ttu-id="91984-121">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="91984-121">✔️ 3.1</span></span>        | <span data-ttu-id="91984-122">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="91984-122">✔️ 5.0</span></span> |
| <span data-ttu-id="91984-123">✔️ 3.11</span><span class="sxs-lookup"><span data-stu-id="91984-123">✔️ 3.11</span></span> | <span data-ttu-id="91984-124">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="91984-124">✔️ 2.1</span></span>        | <span data-ttu-id="91984-125">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="91984-125">✔️ 3.1</span></span>        | <span data-ttu-id="91984-126">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="91984-126">✔️ 5.0</span></span> |
| <span data-ttu-id="91984-127">✔️ 3.10</span><span class="sxs-lookup"><span data-stu-id="91984-127">✔️ 3.10</span></span> | <span data-ttu-id="91984-128">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="91984-128">✔️ 2.1</span></span>        | <span data-ttu-id="91984-129">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="91984-129">✔️ 3.1</span></span>        | <span data-ttu-id="91984-130">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="91984-130">❌ 5.0</span></span> |
| <span data-ttu-id="91984-131">❌ 3.9</span><span class="sxs-lookup"><span data-stu-id="91984-131">❌ 3.9</span></span>  | <span data-ttu-id="91984-132">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="91984-132">✔️ 2.1</span></span>        | <span data-ttu-id="91984-133">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="91984-133">✔️ 3.1</span></span>        | <span data-ttu-id="91984-134">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="91984-134">❌ 5.0</span></span> |
| <span data-ttu-id="91984-135">❌ 3.8</span><span class="sxs-lookup"><span data-stu-id="91984-135">❌ 3.8</span></span>  | <span data-ttu-id="91984-136">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="91984-136">✔️ 2.1</span></span>        | <span data-ttu-id="91984-137">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="91984-137">✔️ 3.1</span></span>        | <span data-ttu-id="91984-138">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="91984-138">❌ 5.0</span></span> |

<span data-ttu-id="91984-139">Следующие версии .NET больше не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="91984-139">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="91984-140">(но остаются доступными для скачивания):</span><span class="sxs-lookup"><span data-stu-id="91984-140">The downloads for these still remain published:</span></span>

- <span data-ttu-id="91984-141">3.0</span><span class="sxs-lookup"><span data-stu-id="91984-141">3.0</span></span>
- <span data-ttu-id="91984-142">2.2</span><span class="sxs-lookup"><span data-stu-id="91984-142">2.2</span></span>
- <span data-ttu-id="91984-143">2.0</span><span class="sxs-lookup"><span data-stu-id="91984-143">2.0</span></span>

## <a name="dependencies"></a><span data-ttu-id="91984-144">Зависимости</span><span class="sxs-lookup"><span data-stu-id="91984-144">Dependencies</span></span>

<span data-ttu-id="91984-145">Для .NET в Alpine Linux необходимо установить следующие зависимости:</span><span class="sxs-lookup"><span data-stu-id="91984-145">.NET on Alpine Linux requires the following dependencies installed:</span></span>

- <span data-ttu-id="91984-146">icu-libs</span><span class="sxs-lookup"><span data-stu-id="91984-146">icu-libs</span></span>
- <span data-ttu-id="91984-147">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="91984-147">krb5-libs</span></span>
- <span data-ttu-id="91984-148">libgcc</span><span class="sxs-lookup"><span data-stu-id="91984-148">libgcc</span></span>
- <span data-ttu-id="91984-149">libintl</span><span class="sxs-lookup"><span data-stu-id="91984-149">libintl</span></span>
- <span data-ttu-id="91984-150">libssl 1.1 (Alpine версии 3.9 или более поздней)</span><span class="sxs-lookup"><span data-stu-id="91984-150">libssl1.1 (Alpine v3.9 or greater)</span></span>
- <span data-ttu-id="91984-151">libssl1.0 (Alpine версии 3.8 или более ранней)</span><span class="sxs-lookup"><span data-stu-id="91984-151">libssl1.0 (Alpine v3.8 or lower)</span></span>
- <span data-ttu-id="91984-152">libstdc++</span><span class="sxs-lookup"><span data-stu-id="91984-152">libstdc++</span></span>
- <span data-ttu-id="91984-153">zlib</span><span class="sxs-lookup"><span data-stu-id="91984-153">zlib</span></span>

## <a name="scripted-install"></a><span data-ttu-id="91984-154">Установка с помощью сценария</span><span class="sxs-lookup"><span data-stu-id="91984-154">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="91984-155">Установка вручную</span><span class="sxs-lookup"><span data-stu-id="91984-155">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="91984-156">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="91984-156">Next steps</span></span>

- [<span data-ttu-id="91984-157">Учебник. Создание консольного приложения с помощью пакета SDK для .NET в Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="91984-157">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
