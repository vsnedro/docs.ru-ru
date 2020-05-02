---
title: Установка .NET Core на openSUSE 15 — диспетчер пакетов — .NET Core
description: Используйте диспетчер пакетов для установки пакета SDK для .NET Core и среды выполнения на openSUSE 15.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: fc4c9e30ddb0cfd3e6fe79fa4f78206f4700eeee
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645661"
---
# <a name="opensuse-15-package-manager---install-net-core"></a><span data-ttu-id="c6b94-103">Диспетчер пакетов openSUSE 15 — установка .NET Core</span><span class="sxs-lookup"><span data-stu-id="c6b94-103">openSUSE 15 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="c6b94-104">Эта статья описывает, как использовать диспетчер пакетов для установки .NET Core на openSUSE 15.</span><span class="sxs-lookup"><span data-stu-id="c6b94-104">This article describes how to use a package manager to install .NET Core on openSUSE 15.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="add-microsoft-repository-key-and-feed"></a><span data-ttu-id="c6b94-105">Добавление ключа и веб-канала репозитория Майкрософт</span><span class="sxs-lookup"><span data-stu-id="c6b94-105">Add Microsoft repository key and feed</span></span>

<span data-ttu-id="c6b94-106">Перед установкой .NET нужно сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="c6b94-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="c6b94-107">добавить ключ подписывания пакета Майкрософт в список доверенных ключей;</span><span class="sxs-lookup"><span data-stu-id="c6b94-107">Add the Microsoft package signing key to the list of trusted keys.</span></span>
- <span data-ttu-id="c6b94-108">добавить репозиторий в диспетчер пакетов;</span><span class="sxs-lookup"><span data-stu-id="c6b94-108">Add the repository to the package manager.</span></span>
- <span data-ttu-id="c6b94-109">установить необходимые зависимости.</span><span class="sxs-lookup"><span data-stu-id="c6b94-109">Install required dependencies.</span></span>

<span data-ttu-id="c6b94-110">Данную операцию достаточно выполнить один раз для каждого компьютера.</span><span class="sxs-lookup"><span data-stu-id="c6b94-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="c6b94-111">Откройте терминал и выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="c6b94-111">Open a terminal and run the following commands.</span></span>

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="c6b94-112">Установка пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="c6b94-112">Install the .NET Core SDK</span></span>

<span data-ttu-id="c6b94-113">Обновите продукты, доступные для установки, а затем установите пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c6b94-113">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="c6b94-114">В терминале выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="c6b94-114">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="c6b94-115">Установка среды выполнения ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c6b94-115">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="c6b94-116">Обновите продукты, доступные для установки, а затем установите среду выполнения ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="c6b94-116">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="c6b94-117">В терминале выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="c6b94-117">In your terminal, run the following command.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="c6b94-118">Установка среды выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="c6b94-118">Install the .NET Core runtime</span></span>

<span data-ttu-id="c6b94-119">Обновите продукты, доступные для установки, а затем установите среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c6b94-119">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="c6b94-120">В терминале выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="c6b94-120">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="c6b94-121">Установка других версий</span><span class="sxs-lookup"><span data-stu-id="c6b94-121">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="c6b94-122">Устранение неполадок диспетчера пакетов</span><span class="sxs-lookup"><span data-stu-id="c6b94-122">Troubleshoot the package manager</span></span>

<span data-ttu-id="c6b94-123">В этом разделе описаны распространенные ошибки, которые могут возникнуть при использовании диспетчера пакетов для установки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c6b94-123">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="c6b94-124">Ошибка получения</span><span class="sxs-lookup"><span data-stu-id="c6b94-124">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]
