---
title: Проверка установленных версий .NET Core в Windows, Linux и macOS — .NET Core
description: Сведения о том, какие версии .NET установлены на компьютере. Сюда входит среда выполнения .NET Core и пакет SDK для .NET Core.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 3a78acee6cf427085e98f14353fc2c0ac65d3d80
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645339"
---
# <a name="how-to-check-that-net-core-is-already-installed"></a><span data-ttu-id="74d21-104">Проверка того, установлена ли платформа .NET Core</span><span class="sxs-lookup"><span data-stu-id="74d21-104">How to check that .NET Core is already installed</span></span>

<span data-ttu-id="74d21-105">Эта статья описывает, как проверить, какие версии среды выполнения .NET Core и пакета SDK установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="74d21-105">This article teaches you how to check which versions of the .NET Core runtime and SDK are installed on your computer.</span></span> <span data-ttu-id="74d21-106">Возможно, платформа .NET Core уже установлена, если у вас есть интегрированная среда разработки, такая как Visual Studio или Visual Studio для Mac.</span><span class="sxs-lookup"><span data-stu-id="74d21-106">.NET core may have already been installed if you have an integrated development environment, such as Visual Studio or Visual Studio for Mac.</span></span>

<span data-ttu-id="74d21-107">При установке пакета SDK устанавливается и соответствующая среда выполнения.</span><span class="sxs-lookup"><span data-stu-id="74d21-107">Installing an SDK installs the corresponding runtime.</span></span>

<span data-ttu-id="74d21-108">Если любая команда из этой статьи завершается ошибкой, среда выполнения или пакет SDK не установлены.</span><span class="sxs-lookup"><span data-stu-id="74d21-108">If any command in this article fails, you don't have the runtime or SDK installed.</span></span> <span data-ttu-id="74d21-109">Дополнительные сведения см. в статье [Скачивание и установка .NET Core](index.md).</span><span class="sxs-lookup"><span data-stu-id="74d21-109">For more information, see [Download and install .NET Core](index.md).</span></span>

## <a name="check-sdk-versions"></a><span data-ttu-id="74d21-110">Проверка версий пакета SDK</span><span class="sxs-lookup"><span data-stu-id="74d21-110">Check SDK versions</span></span>

<span data-ttu-id="74d21-111">Вы можете узнать, какие версии пакета SDK для .NET Core установлены, с помощью терминала.</span><span class="sxs-lookup"><span data-stu-id="74d21-111">You can see which versions of the .NET Core SDK are currently installed with a terminal.</span></span> <span data-ttu-id="74d21-112">Откройте терминал и выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="74d21-112">Open a terminal and run the following command.</span></span>

```dotnetcli
dotnet --list-sdks
```

<span data-ttu-id="74d21-113">Вы получите результат, аналогичный приведенному ниже.</span><span class="sxs-lookup"><span data-stu-id="74d21-113">You get output similar to the following.</span></span>

::: zone pivot="os-windows"

```console
2.1.500 [C:\program files\dotnet\sdk]
2.1.502 [C:\program files\dotnet\sdk]
2.1.504 [C:\program files\dotnet\sdk]
2.1.600 [C:\program files\dotnet\sdk]
2.1.602 [C:\program files\dotnet\sdk]
2.2.101 [C:\program files\dotnet\sdk]
3.0.100 [C:\program files\dotnet\sdk]
3.1.100 [C:\program files\dotnet\sdk]
```

::: zone-end

::: zone pivot="os-linux"

```bash
2.1.500 [/home/user/dotnet/sdk]
2.1.502 [/home/user/dotnet/sdk]
2.1.504 [/home/user/dotnet/sdk]
2.1.600 [/home/user/dotnet/sdk]
2.1.602 [/home/user/dotnet/sdk]
2.2.101 [/home/user/dotnet/sdk]
3.0.100 [/home/user/dotnet/sdk]
3.1.100 [/home/user/dotnet/sdk]
```

::: zone-end

::: zone pivot="os-macos"

```bash
2.1.500 [/usr/local/share/dotnet/sdk]
2.1.502 [/usr/local/share/dotnet/sdk]
2.1.504 [/usr/local/share/dotnet/sdk]
2.1.600 [/usr/local/share/dotnet/sdk]
2.1.602 [/usr/local/share/dotnet/sdk]
2.2.101 [/usr/local/share/dotnet/sdk]
3.0.100 [/usr/local/share/dotnet/sdk]
3.1.100 [/usr/local/share/dotnet/sdk]
```

::: zone-end

## <a name="check-runtime-versions"></a><span data-ttu-id="74d21-114">Проверка версий среды выполнения</span><span class="sxs-lookup"><span data-stu-id="74d21-114">Check runtime versions</span></span>

<span data-ttu-id="74d21-115">Вы можете узнать, какие версии среды выполнения .NET Core установлены, с помощью приведенной ниже команды.</span><span class="sxs-lookup"><span data-stu-id="74d21-115">You can see which versions of the .NET Core runtime are currently installed with the following command.</span></span>

```dotnetcli
dotnet --list-runtimes
```

<span data-ttu-id="74d21-116">Вы получите результат, аналогичный приведенному ниже.</span><span class="sxs-lookup"><span data-stu-id="74d21-116">You get output similar to the following.</span></span>

::: zone pivot="os-windows"

```console
Microsoft.AspNetCore.All 2.1.7 [c:\program files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.13 [c:\program files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.0 [c:\program files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.3 [c:\program files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.7 [c:\program files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.6 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.7 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.13 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.2.0 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.2.7 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.0.0 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.1.0 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.NETCore.App 2.1.7 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.13 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.0 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.3 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.7 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 3.0.0 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 3.1.0 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.WindowsDesktop.App 3.0.0 [c:\program files\dotnet\shared\Microsoft.WindowsDesktop.App]
Microsoft.WindowsDesktop.App 3.1.0 [c:\program files\dotnet\shared\Microsoft.WindowsDesktop.App]
```

::: zone-end

::: zone pivot="os-linux"

```bash
Microsoft.AspNetCore.All 2.1.7 [/home/user/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.13 [/home/user/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.0 [/home/user/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.3 [/home/user/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.7 [/home/user/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.6 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.7 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.13 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.2.0 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.2.7 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.0.0 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.1.0 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 2.1.7 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.13 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.0 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.3 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.7 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 3.0.0 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 3.1.0 [/home/user/dotnet/shared/Microsoft.NETCore.App]
```

::: zone-end

::: zone pivot="os-macos"

```bash
Microsoft.AspNetCore.All 2.1.7 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.13 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.3 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.7 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.6 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.7 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.13 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.2.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.2.7 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.0.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.1.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 2.1.7 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.13 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.3 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.7 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 3.0.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 3.1.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
```

::: zone-end

## <a name="check-for-install-folders"></a><span data-ttu-id="74d21-117">Проверка папок установки</span><span class="sxs-lookup"><span data-stu-id="74d21-117">Check for install folders</span></span>

<span data-ttu-id="74d21-118">Возможно, платформа .NET Core установлена, но не добавлена в переменную `PATH` для профиля операционной системы или пользователя.</span><span class="sxs-lookup"><span data-stu-id="74d21-118">It's possible that .NET Core is installed but not added to the `PATH` variable for your operating system or user profile.</span></span> <span data-ttu-id="74d21-119">Выполнение команд из предыдущих разделов может не работать.</span><span class="sxs-lookup"><span data-stu-id="74d21-119">Running the commands from the previous sections may not work.</span></span> <span data-ttu-id="74d21-120">В качестве альтернативы можно проверить существование папок установки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="74d21-120">As an alternative, you can check that the .NET Core install folders exist.</span></span>

<span data-ttu-id="74d21-121">При установке с помощью установщика или сценария .NET Core устанавливается в стандартную папку.</span><span class="sxs-lookup"><span data-stu-id="74d21-121">When you install .NET Core from an installer or script, it's installed to a standard folder.</span></span> <span data-ttu-id="74d21-122">В большинстве случаев установщик или сценарий, который вы используете для установки .NET Core, предоставляет возможность установки в другую папку.</span><span class="sxs-lookup"><span data-stu-id="74d21-122">Much of the time the installer or script you're using to install .NET Core gives you an option to install to a different folder.</span></span> <span data-ttu-id="74d21-123">Если вы решили выполнить установить в другую папку, измените начало пути к папке.</span><span class="sxs-lookup"><span data-stu-id="74d21-123">If you choose to install to a different folder, adjust the start of the folder path.</span></span>

::: zone pivot="os-windows"

- <span data-ttu-id="74d21-124">**Исполняемый файл dotnet**</span><span class="sxs-lookup"><span data-stu-id="74d21-124">**dotnet executable**</span></span>\
<span data-ttu-id="74d21-125">_C:\\program files\\dotnet\\dotnet.exe_</span><span class="sxs-lookup"><span data-stu-id="74d21-125">_C:\\program files\\dotnet\\dotnet.exe_</span></span>

- <span data-ttu-id="74d21-126">**Пакет SDK для .NET**</span><span class="sxs-lookup"><span data-stu-id="74d21-126">**.NET SDK**</span></span>\
<span data-ttu-id="74d21-127">_C:\\program files\\dotnet\\sdk\\{версия}\\_</span><span class="sxs-lookup"><span data-stu-id="74d21-127">_C:\\program files\\dotnet\\sdk\\{version}\\_</span></span>

- <span data-ttu-id="74d21-128">**Среда выполнения .NET**</span><span class="sxs-lookup"><span data-stu-id="74d21-128">**.NET Runtime**</span></span>\
<span data-ttu-id="74d21-129">_C:\\program files\\dotnet\\shared\\{тип среды выполнения}\\{версия}\\_</span><span class="sxs-lookup"><span data-stu-id="74d21-129">_C:\\program files\\dotnet\\shared\\{runtime-type}\\{version}\\_</span></span>

::: zone-end

::: zone pivot="os-linux"

- <span data-ttu-id="74d21-130">**Исполняемый файл dotnet**</span><span class="sxs-lookup"><span data-stu-id="74d21-130">**dotnet executable**</span></span>\
<span data-ttu-id="74d21-131">_/home/user/share/dotnet/dotnet_</span><span class="sxs-lookup"><span data-stu-id="74d21-131">_/home/user/share/dotnet/dotnet_</span></span>

- <span data-ttu-id="74d21-132">**Пакет SDK для .NET**</span><span class="sxs-lookup"><span data-stu-id="74d21-132">**.NET SDK**</span></span>\
<span data-ttu-id="74d21-133">_/home/user/share/dotnet/sdk/{version}/_</span><span class="sxs-lookup"><span data-stu-id="74d21-133">_/home/user/share/dotnet/sdk/{version}/_</span></span>

- <span data-ttu-id="74d21-134">**Среда выполнения .NET**</span><span class="sxs-lookup"><span data-stu-id="74d21-134">**.NET Runtime**</span></span>\
<span data-ttu-id="74d21-135">_/home/user/share/dotnet/shared/{тип среды выполнения}/{версия}/_</span><span class="sxs-lookup"><span data-stu-id="74d21-135">_/home/user/share/dotnet/shared/{runtime-type}/{version}/_</span></span>

::: zone-end

::: zone pivot="os-macos"

- <span data-ttu-id="74d21-136">**Исполняемый файл dotnet**</span><span class="sxs-lookup"><span data-stu-id="74d21-136">**dotnet executable**</span></span>\
<span data-ttu-id="74d21-137">_/usr/local/share/dotnet/dotnet_</span><span class="sxs-lookup"><span data-stu-id="74d21-137">_/usr/local/share/dotnet/dotnet_</span></span>

- <span data-ttu-id="74d21-138">**Пакет SDK для .NET**</span><span class="sxs-lookup"><span data-stu-id="74d21-138">**.NET SDK**</span></span>\
<span data-ttu-id="74d21-139">_/usr/local/share/dotnet/sdk/{версия}/_</span><span class="sxs-lookup"><span data-stu-id="74d21-139">_/usr/local/share/dotnet/sdk/{version}/_</span></span>

- <span data-ttu-id="74d21-140">**Среда выполнения .NET**</span><span class="sxs-lookup"><span data-stu-id="74d21-140">**.NET Runtime**</span></span>\
<span data-ttu-id="74d21-141">_/usr/local/share/dotnet/shared/{тип среды выполнения}/{версия}/_</span><span class="sxs-lookup"><span data-stu-id="74d21-141">_/usr/local/share/dotnet/shared/{runtime-type}/{version}/_</span></span>

::: zone-end

## <a name="more-information"></a><span data-ttu-id="74d21-142">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="74d21-142">More information</span></span>

<span data-ttu-id="74d21-143">Версии пакета SDK и среды выполнения можно просмотреть с помощью команды `dotnet --info`.</span><span class="sxs-lookup"><span data-stu-id="74d21-143">You can see both the SDK versions and runtime versions with the command `dotnet --info`.</span></span> <span data-ttu-id="74d21-144">Вы также получите другие сведения о среде, такие как версия операционной системы и идентификатор среды выполнения (RID).</span><span class="sxs-lookup"><span data-stu-id="74d21-144">You'll also get other environmental related information, such as the operating system version and runtime identifier (RID).</span></span>

## <a name="next-steps"></a><span data-ttu-id="74d21-145">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="74d21-145">Next steps</span></span>

- <span data-ttu-id="74d21-146">[Установка среды выполнения .NET Core](runtime.md).</span><span class="sxs-lookup"><span data-stu-id="74d21-146">[Install the .NET Core Runtime](runtime.md).</span></span>
- <span data-ttu-id="74d21-147">[Установка пакета SDK для .NET Core](sdk.md).</span><span class="sxs-lookup"><span data-stu-id="74d21-147">[Install the .NET Core SDK](sdk.md).</span></span>
