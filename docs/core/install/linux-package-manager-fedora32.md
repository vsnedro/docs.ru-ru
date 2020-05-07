---
title: Установка .NET Core на Fedora 32 — диспетчер пакетов — .NET Core
description: Используйте диспетчер пакетов для установки пакета SDK для .NET Core и среды выполнения на Fedora 32.
author: thraka
ms.author: adegeo
ms.date: 04/28/2020
ms.openlocfilehash: e5a69bf00e7e2969143e044aea4c9938fd5a610d
ms.sourcegitcommit: e09dbff13f0b21b569a101f3b3c5efa174aec204
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/01/2020
ms.locfileid: "82624954"
---
# <a name="fedora-32-package-manager---install-net-core"></a><span data-ttu-id="a16e9-103">Диспетчер пакетов Fedora 32 — установка .NET Core</span><span class="sxs-lookup"><span data-stu-id="a16e9-103">Fedora 32 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="a16e9-104">В этой статье описывается, как использовать диспетчер пакетов для установки .NET Core на Fedora 32.</span><span class="sxs-lookup"><span data-stu-id="a16e9-104">This article describes how to use a package manager to install .NET Core on Fedora 32.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

<span data-ttu-id="a16e9-105">Начиная с Fedora 32 .NET Core 3.1 доступен в репозиториях пакетов по умолчанию в Fedora.</span><span class="sxs-lookup"><span data-stu-id="a16e9-105">Starting with Fedora 32, .NET Core 3.1 is available in the default package repositories in Fedora.</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="a16e9-106">Установка пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="a16e9-106">Install the .NET Core SDK</span></span>

<span data-ttu-id="a16e9-107">Установите пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a16e9-107">Install the .NET Core SDK.</span></span> <span data-ttu-id="a16e9-108">В терминале выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="a16e9-108">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="a16e9-109">Установка среды выполнения ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a16e9-109">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="a16e9-110">Установите среду выполнения ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a16e9-110">Install the ASP.NET runtime.</span></span> <span data-ttu-id="a16e9-111">В терминале выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="a16e9-111">In your terminal, run the following command.</span></span>

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="a16e9-112">Установка среды выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="a16e9-112">Install the .NET Core runtime</span></span>

<span data-ttu-id="a16e9-113">Установите среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a16e9-113">Install the .NET Core runtime.</span></span> <span data-ttu-id="a16e9-114">В терминале выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="a16e9-114">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="a16e9-115">Установка других версий</span><span class="sxs-lookup"><span data-stu-id="a16e9-115">How to install other versions</span></span>

<span data-ttu-id="a16e9-116">Чтобы установить другие версии .NET Core, вручную установите [пакет SDK для .NET Core](sdk.md?pivots=os-linux#download-and-manually-install) или [среду выполнения .NET Core](runtime.md?pivots=os-linux#download-and-manually-install).</span><span class="sxs-lookup"><span data-stu-id="a16e9-116">To install other versions of .NET Core, manually install [the .NET Core SDK](sdk.md?pivots=os-linux#download-and-manually-install) or [the .NET Core Runtime](runtime.md?pivots=os-linux#download-and-manually-install).</span></span>
