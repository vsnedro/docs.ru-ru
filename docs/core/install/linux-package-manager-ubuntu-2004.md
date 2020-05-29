---
title: Установка .NET Core с помощью диспетчера пакетов Ubuntu 20.04 — .NET Core
description: Используйте диспетчер пакетов для установки пакета SDK для .NET Core и среды выполнения на Ubuntu 20.04.
author: thraka
ms.author: adegeo
ms.date: 05/13/2020
ms.openlocfilehash: 4d7d7ee9117314ef360097fee929f24943c7a7f2
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83618873"
---
# <a name="ubuntu-2004-package-manager---install-net-core"></a><span data-ttu-id="c68a0-103">Диспетчер пакетов Ubuntu 20.04 — установка .NET Core</span><span class="sxs-lookup"><span data-stu-id="c68a0-103">Ubuntu 20.04 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="c68a0-104">В этой статье описывается, как использовать диспетчер пакетов для установки .NET Core в Ubuntu 20.04.</span><span class="sxs-lookup"><span data-stu-id="c68a0-104">This article describes how to use a package manager to install .NET Core on Ubuntu 20.04.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="add-microsoft-repository-key-and-feed"></a><span data-ttu-id="c68a0-105">Добавление ключа и веб-канала репозитория Майкрософт</span><span class="sxs-lookup"><span data-stu-id="c68a0-105">Add Microsoft repository key and feed</span></span>

<span data-ttu-id="c68a0-106">Перед установкой .NET нужно сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="c68a0-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="c68a0-107">добавить ключ подписывания пакета Майкрософт в список доверенных ключей;</span><span class="sxs-lookup"><span data-stu-id="c68a0-107">Add the Microsoft package signing key to the list of trusted keys.</span></span>
- <span data-ttu-id="c68a0-108">добавить репозиторий в диспетчер пакетов;</span><span class="sxs-lookup"><span data-stu-id="c68a0-108">Add the repository to the package manager.</span></span>
- <span data-ttu-id="c68a0-109">установить необходимые зависимости.</span><span class="sxs-lookup"><span data-stu-id="c68a0-109">Install required dependencies.</span></span>

<span data-ttu-id="c68a0-110">Данную операцию достаточно выполнить один раз для каждого компьютера.</span><span class="sxs-lookup"><span data-stu-id="c68a0-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="c68a0-111">Откройте терминал и выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="c68a0-111">Open a terminal and run the following commands.</span></span>

```bash
wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="c68a0-112">Установка пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="c68a0-112">Install the .NET Core SDK</span></span>

<span data-ttu-id="c68a0-113">Обновите продукты, доступные для установки, а затем установите пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c68a0-113">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="c68a0-114">В терминале выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="c68a0-114">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-sdk-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="c68a0-115">Если появляется сообщение об ошибке, похожее на **Unable to locate package dotnet-sdk-3.1** (Не удалось найти пакет dotnet-sdk-3.1), см. раздел [Устранение неполадок диспетчера пакетов](#troubleshoot-the-package-manager).</span><span class="sxs-lookup"><span data-stu-id="c68a0-115">If you receive an error message similar to **Unable to locate package dotnet-sdk-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="c68a0-116">Установка среды выполнения ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c68a0-116">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="c68a0-117">Обновите продукты, доступные для установки, а затем установите среду выполнения ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="c68a0-117">Update the products available for installation, then install the ASP.NET Core runtime.</span></span> <span data-ttu-id="c68a0-118">В терминале выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="c68a0-118">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install aspnetcore-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="c68a0-119">Если появляется сообщение об ошибке, похожее на **Unable to locate package aspnetcore-runtime-3.1** (Не удалось найти пакет aspnetcore-runtime-3.1), см. раздел [Устранение неполадок диспетчера пакетов](#troubleshoot-the-package-manager).</span><span class="sxs-lookup"><span data-stu-id="c68a0-119">If you receive an error message similar to **Unable to locate package aspnetcore-runtime-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="c68a0-120">Установка среды выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="c68a0-120">Install the .NET Core runtime</span></span>

<span data-ttu-id="c68a0-121">Обновите продукты, доступные для установки, а затем установите среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c68a0-121">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="c68a0-122">В терминале выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="c68a0-122">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="c68a0-123">Если появляется сообщение об ошибке, похожее на **Unable to locate package dotnet-runtime-3.1** (Не удалось найти пакет dotnet-runtime-3.1), см. раздел [Устранение неполадок диспетчера пакетов](#troubleshoot-the-package-manager).</span><span class="sxs-lookup"><span data-stu-id="c68a0-123">If you receive an error message similar to **Unable to locate package dotnet-runtime-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="c68a0-124">Установка других версий</span><span class="sxs-lookup"><span data-stu-id="c68a0-124">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="c68a0-125">Устранение неполадок диспетчера пакетов</span><span class="sxs-lookup"><span data-stu-id="c68a0-125">Troubleshoot the package manager</span></span>

<span data-ttu-id="c68a0-126">В этом разделе описаны распространенные ошибки, которые могут возникнуть при использовании диспетчера пакетов для установки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c68a0-126">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="unable-to-locate"></a><span data-ttu-id="c68a0-127">Ошибка обнаружения</span><span class="sxs-lookup"><span data-stu-id="c68a0-127">Unable to locate</span></span>

<span data-ttu-id="c68a0-128">Если появляется сообщение об ошибке, похожее на **Unable to locate package {the .NET Core package}** (Не удалось найти пакет {пакет .NET Core}), выполните проведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="c68a0-128">If you receive an error message similar to **Unable to locate package {the .NET Core package}**, run the following commands.</span></span>

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
sudo apt-get install {the .NET Core package}
```

<span data-ttu-id="c68a0-129">Если проблема не решена, можно выполнить установку вручную с помощью приведенных ниже команд.</span><span class="sxs-lookup"><span data-stu-id="c68a0-129">If that doesn't work, you can run a manual install with the following commands.</span></span>

```bash
sudo apt-get install -y gpg
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor -o microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/ubuntu/20.04/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
sudo apt-get install -y apt-transport-https
sudo apt-get update
sudo apt-get install {the .NET Core package}
```

### <a name="failed-to-fetch"></a><span data-ttu-id="c68a0-130">Ошибка получения</span><span class="sxs-lookup"><span data-stu-id="c68a0-130">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]
