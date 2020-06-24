---
title: Установка .NET Core в RHEL — .NET Core
description: Здесь приводятся различные способы установки пакета SDK для .NET Core и среды выполнения .NET Core в RHEL.
author: thraka
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 7ae55f881cd0c877cf1db24be7a4ee23320e21a8
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602798"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-rhel"></a><span data-ttu-id="7b217-103">Установка пакета SDK для .NET Core или среды выполнения .NET Core в RHEL</span><span class="sxs-lookup"><span data-stu-id="7b217-103">Install .NET Core SDK or .NET Core Runtime on RHEL</span></span>

<span data-ttu-id="7b217-104">.NET Core поддерживается в RHEL.</span><span class="sxs-lookup"><span data-stu-id="7b217-104">.NET Core is supported on RHEL.</span></span> <span data-ttu-id="7b217-105">В этой статье описано, как установить .NET Core в RHEL.</span><span class="sxs-lookup"><span data-stu-id="7b217-105">This article describes how to install .NET Core on RHEL.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="7b217-106">Регистрация подписки Red Hat</span><span class="sxs-lookup"><span data-stu-id="7b217-106">Register your Red Hat subscription</span></span>

<span data-ttu-id="7b217-107">Чтобы установить .NET Core из Red Hat на RHEL, сначала нужно зарегистрироваться с помощью диспетчера подписки Red Hat.</span><span class="sxs-lookup"><span data-stu-id="7b217-107">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="7b217-108">Если это еще не сделано в вашей системе либо вы точно не уверены, ознакомьтесь с [документацией по продукту Red Hat для .NET Core](https://access.redhat.com/documentation/net_core/).</span><span class="sxs-lookup"><span data-stu-id="7b217-108">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="supported-distributions"></a><span data-ttu-id="7b217-109">Поддерживаемые дистрибутивы</span><span class="sxs-lookup"><span data-stu-id="7b217-109">Supported distributions</span></span>

<span data-ttu-id="7b217-110">В приведенной ниже таблице содержится список поддерживаемых сейчас выпусков .NET Core в RHEL 7 и RHEL 8.</span><span class="sxs-lookup"><span data-stu-id="7b217-110">The following table is a list of currently supported .NET Core releases on both RHEL 7 and RHEL 8.</span></span> <span data-ttu-id="7b217-111">Эти версии поддерживаются до того же времени, что и версия [.NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) или RHEL.</span><span class="sxs-lookup"><span data-stu-id="7b217-111">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of RHEL is no longer supported.</span></span>

- <span data-ttu-id="7b217-112">Значок ✔️ означает, что версия RHEL или .NET Core поддерживается.</span><span class="sxs-lookup"><span data-stu-id="7b217-112">A ✔️ indicates that the version of RHEL or .NET Core is still supported.</span></span>
- <span data-ttu-id="7b217-113">Значок ❌ означает, что версия RHEL или версия .NET Core в таком выпуске RHEL не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="7b217-113">A ❌ indicates that the version of RHEL or .NET Core isn't supported on that RHEL release.</span></span>
- <span data-ttu-id="7b217-114">Если значок ✔️ стоит как напротив версии RHEL, так и напротив версии .NET Core, это значит, что такое сочетание ОС и .NET поддерживается.</span><span class="sxs-lookup"><span data-stu-id="7b217-114">When both a version of RHEL and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="7b217-115">RHEL</span><span class="sxs-lookup"><span data-stu-id="7b217-115">RHEL</span></span>                   | <span data-ttu-id="7b217-116">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="7b217-116">.NET Core 2.1</span></span> | <span data-ttu-id="7b217-117">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="7b217-117">.NET Core 3.1</span></span> | <span data-ttu-id="7b217-118">Предварительная версия .NET 5 (только установка вручную)</span><span class="sxs-lookup"><span data-stu-id="7b217-118">.NET 5 Preview (manual install only)</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="7b217-119">✔️ [8](#rhel-8-)</span><span class="sxs-lookup"><span data-stu-id="7b217-119">✔️ [8](#rhel-8-)</span></span> | <span data-ttu-id="7b217-120">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="7b217-120">✔️ 2.1</span></span>        | <span data-ttu-id="7b217-121">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="7b217-121">✔️ 3.1</span></span>        | <span data-ttu-id="7b217-122">✔️ 5.0 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="7b217-122">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="7b217-123">✔️ [7](#rhel-7-)</span><span class="sxs-lookup"><span data-stu-id="7b217-123">✔️ [7](#rhel-7-)</span></span> | <span data-ttu-id="7b217-124">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="7b217-124">✔️ 2.1</span></span>        | <span data-ttu-id="7b217-125">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="7b217-125">✔️ 3.1</span></span>        | <span data-ttu-id="7b217-126">✔️ 5.0 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="7b217-126">✔️ 5.0 Preview</span></span> |

<span data-ttu-id="7b217-127">Следующие версии .NET Core больше не поддерживаются</span><span class="sxs-lookup"><span data-stu-id="7b217-127">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="7b217-128">(но остаются доступными для скачивания):</span><span class="sxs-lookup"><span data-stu-id="7b217-128">The downloads for these still remain published:</span></span>

- <span data-ttu-id="7b217-129">3.0</span><span class="sxs-lookup"><span data-stu-id="7b217-129">3.0</span></span>
- <span data-ttu-id="7b217-130">2.2</span><span class="sxs-lookup"><span data-stu-id="7b217-130">2.2</span></span>
- <span data-ttu-id="7b217-131">2.0</span><span class="sxs-lookup"><span data-stu-id="7b217-131">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="7b217-132">Установка других версий</span><span class="sxs-lookup"><span data-stu-id="7b217-132">How to install other versions</span></span>

<span data-ttu-id="7b217-133">Сведения об установке других выпусков .NET Core см. в [документации по Red Hat для .NET Core](https://access.redhat.com/documentation/net_core/).</span><span class="sxs-lookup"><span data-stu-id="7b217-133">Consult the [Red Hat documentation for .NET Core](https://access.redhat.com/documentation/net_core/) on the steps required to install other releases of .NET Core.</span></span>

## <a name="rhel-8-"></a><span data-ttu-id="7b217-134">RHEL 8 ✔️</span><span class="sxs-lookup"><span data-stu-id="7b217-134">RHEL 8 ✔️</span></span>

<span data-ttu-id="7b217-135">Платформа .NET Core включена в репозитории AppStream для RHEL 8.</span><span class="sxs-lookup"><span data-stu-id="7b217-135">.NET Core is included in the AppStream repositories for RHEL 8.</span></span>

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="rhel-7-"></a><span data-ttu-id="7b217-136">RHEL 7 ✔️</span><span class="sxs-lookup"><span data-stu-id="7b217-136">RHEL 7 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

<span data-ttu-id="7b217-137">Следующая команда устанавливает пакет `scl-utils`:</span><span class="sxs-lookup"><span data-stu-id="7b217-137">The following command installs the `scl-utils` package:</span></span>

```bash
sudo yum install scl-utils
```

### <a name="install-the-sdk"></a><span data-ttu-id="7b217-138">Установка пакета SDK</span><span class="sxs-lookup"><span data-stu-id="7b217-138">Install the SDK</span></span>

<span data-ttu-id="7b217-139">Пакет SDK для .NET Core позволяет разрабатывать приложения с помощью .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7b217-139">.NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="7b217-140">При установке пакета SDK для .NET Core не нужно устанавливать соответствующую среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="7b217-140">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="7b217-141">Чтобы установить пакет SDK для .NET Core, выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="7b217-141">To install .NET Core SDK, run the following commands:</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31 -y
scl enable rh-dotnet31 bash
```

<span data-ttu-id="7b217-142">В Red Hat не рекомендуется активировать `rh-dotnet31` на постоянной основе, так как это может повлиять на другие программы.</span><span class="sxs-lookup"><span data-stu-id="7b217-142">Red Hat does not recommend permanently enabling `rh-dotnet31` because it may affect other programs.</span></span> <span data-ttu-id="7b217-143">Например, `rh-dotnet31` включает версию `libcurl`, которая отличается от базовой версии RHEL.</span><span class="sxs-lookup"><span data-stu-id="7b217-143">For example, `rh-dotnet31` includes a version of `libcurl` that differs from the base RHEL version.</span></span> <span data-ttu-id="7b217-144">Это может вызвать проблемы в программах, которые не ожидают другой версии `libcurl`.</span><span class="sxs-lookup"><span data-stu-id="7b217-144">This may lead to issues in programs that do not expect a different version of `libcurl`.</span></span> <span data-ttu-id="7b217-145">Если вы хотите активировать `rh-dotnet` на постоянной основе, добавьте следующую строку в файл _~/.bashrc_.</span><span class="sxs-lookup"><span data-stu-id="7b217-145">If you want to enable `rh-dotnet` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet31
```

### <a name="install-the-runtime"></a><span data-ttu-id="7b217-146">Установка среды выполнения</span><span class="sxs-lookup"><span data-stu-id="7b217-146">Install the runtime</span></span>

<span data-ttu-id="7b217-147">Среда выполнения .NET Core позволяет запускать приложения, созданные с помощью версии .NET Core без поддержки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="7b217-147">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="7b217-148">Приведенные ниже команды позволяют установить среду выполнения ASP.NET Core, которая больше всего совместима с .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7b217-148">The commands below install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="7b217-149">В терминале выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="7b217-149">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-aspnetcore-runtime-3.1 -y
scl enable rh-dotnet31-aspnetcore-runtime-3.1 bash
```

<span data-ttu-id="7b217-150">В Red Hat не рекомендуется активировать `rh-dotnet31-aspnetcore-runtime-3.1` на постоянной основе, так как это может повлиять на другие программы.</span><span class="sxs-lookup"><span data-stu-id="7b217-150">Red Hat does not recommend permanently enabling `rh-dotnet31-aspnetcore-runtime-3.1` because it may affect other programs.</span></span> <span data-ttu-id="7b217-151">Например, `rh-dotnet31-aspnetcore-runtime-3.1` включает версию `libcurl`, которая отличается от базовой версии RHEL.</span><span class="sxs-lookup"><span data-stu-id="7b217-151">For example, `rh-dotnet31-aspnetcore-runtime-3.1` includes a version of `libcurl` that differs from the base RHEL version.</span></span> <span data-ttu-id="7b217-152">Это может вызвать проблемы в программах, которые не ожидают другой версии `libcurl`.</span><span class="sxs-lookup"><span data-stu-id="7b217-152">This may lead to issues in programs that do not expect a different version of `libcurl`.</span></span> <span data-ttu-id="7b217-153">Если вы хотите активировать `rh-dotnet31-aspnetcore-runtime-3.1` на постоянной основе, добавьте следующую строку в файл _~/.bashrc_.</span><span class="sxs-lookup"><span data-stu-id="7b217-153">If you want to enable `rh-dotnet31-aspnetcore-runtime-3.1` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet31-aspnetcore-runtime-3.1
```

<span data-ttu-id="7b217-154">В качестве альтернативы среде выполнения ASP.NET Core вы можете установить среду выполнения .NET Core без поддержки ASP.NET Core. Для этого в приведенной выше команде замените `rh-dotnet31-aspnetcore-runtime-3.1` на `rh-dotnet31-dotnet-runtime-3.1`.</span><span class="sxs-lookup"><span data-stu-id="7b217-154">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime that doesn't include ASP.NET Core support: replace `rh-dotnet31-aspnetcore-runtime-3.1` in the commands above with `rh-dotnet31-dotnet-runtime-3.1`.</span></span>

## <a name="snap"></a><span data-ttu-id="7b217-155">Snap-пакеты</span><span class="sxs-lookup"><span data-stu-id="7b217-155">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="7b217-156">Зависимости</span><span class="sxs-lookup"><span data-stu-id="7b217-156">Dependencies</span></span>

[!INCLUDE [linux-install-dependencies](includes/linux-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="7b217-157">Установка с помощью скрипта</span><span class="sxs-lookup"><span data-stu-id="7b217-157">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="7b217-158">Установка вручную</span><span class="sxs-lookup"><span data-stu-id="7b217-158">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="7b217-159">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="7b217-159">Next steps</span></span>

- [<span data-ttu-id="7b217-160">Учебник. Создание консольного приложения с помощью пакета SDK для .NET Core в Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="7b217-160">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
