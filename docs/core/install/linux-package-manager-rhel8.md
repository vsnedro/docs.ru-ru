---
title: Установка .NET Core на Linux RHEL 8 — диспетчер пакетов — .NET Core
description: Используйте диспетчер пакетов для установки пакета SDK для .NET Core и среды выполнения на RHEL 8.
author: thraka
ms.author: adegeo
ms.date: 05/01/2020
ms.openlocfilehash: 8829e842e920e6abd4184b5140f80bb016acace2
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728230"
---
# <a name="rhel-8-package-manager---install-net-core"></a><span data-ttu-id="64e1e-103">Диспетчер пакетов RHEL 8 — установка .NET Core</span><span class="sxs-lookup"><span data-stu-id="64e1e-103">RHEL 8 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="64e1e-104">Эта статья описывает, как использовать диспетчер пакетов для установки .NET Core на Red Hat Enterprise Linux (RHEL) 8.</span><span class="sxs-lookup"><span data-stu-id="64e1e-104">This article describes how to use a package manager to install .NET Core on Red Hat Enterprise Linux (RHEL) 8.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="64e1e-105">Регистрация подписки Red Hat</span><span class="sxs-lookup"><span data-stu-id="64e1e-105">Register your Red Hat subscription</span></span>

<span data-ttu-id="64e1e-106">Чтобы установить .NET Core из Red Hat на RHEL, сначала нужно зарегистрироваться с помощью диспетчера подписки Red Hat.</span><span class="sxs-lookup"><span data-stu-id="64e1e-106">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="64e1e-107">Если это еще не сделано в вашей системе либо вы точно не уверены, ознакомьтесь с [документацией по продукту Red Hat для .NET Core](https://access.redhat.com/documentation/net_core/).</span><span class="sxs-lookup"><span data-stu-id="64e1e-107">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="64e1e-108">Установка пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="64e1e-108">Install the .NET Core SDK</span></span>

<span data-ttu-id="64e1e-109">После регистрации в диспетчере подписки вы можете установить и включить пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="64e1e-109">After registering with the Subscription Manager, you're ready to install and enable the .NET Core SDK.</span></span> <span data-ttu-id="64e1e-110">В терминале выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="64e1e-110">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="64e1e-111">Установка среды выполнения ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="64e1e-111">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="64e1e-112">После регистрации в диспетчере подписки вы можете установить и включить среду выполнения ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="64e1e-112">After registering with the Subscription Manager, you're ready to install and enable the ASP.NET Core Runtime.</span></span> <span data-ttu-id="64e1e-113">В терминале выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="64e1e-113">In your terminal, run the following command.</span></span>

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="64e1e-114">Установка среды выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="64e1e-114">Install the .NET Core Runtime</span></span>

<span data-ttu-id="64e1e-115">После регистрации в диспетчере подписки вы можете установить и включить среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="64e1e-115">After registering with the Subscription Manager, you're ready to install and enable the .NET Core Runtime.</span></span> <span data-ttu-id="64e1e-116">В терминале выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="64e1e-116">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="64e1e-117">Установка других версий</span><span class="sxs-lookup"><span data-stu-id="64e1e-117">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="see-also"></a><span data-ttu-id="64e1e-118">См. также</span><span class="sxs-lookup"><span data-stu-id="64e1e-118">See also</span></span>

- [<span data-ttu-id="64e1e-119">Использование .NET Core 3.1 на Red Hat Enterprise Linux 8</span><span class="sxs-lookup"><span data-stu-id="64e1e-119">Using .NET Core 3.1 on Red Hat Enterprise Linux 8</span></span>](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/8/html/developing_.net_applications_in_rhel_8/index)
