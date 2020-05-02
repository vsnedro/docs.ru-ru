---
title: Установка .NET Core на SLES 12 — диспетчер пакетов — .NET Core
description: Используйте диспетчер пакетов для установки пакета SDK для .NET Core и среды выполнения на SLES 12.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: 314688d60fb77e1b569dd037fb1d78c3f1f94dbc
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645648"
---
# <a name="sles-12-package-manager---install-net-core"></a><span data-ttu-id="7bc2b-103">Диспетчер пакетов SLES 12 — установка .NET Core</span><span class="sxs-lookup"><span data-stu-id="7bc2b-103">SLES 12 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="7bc2b-104">Эта статья описывает, как использовать диспетчер пакетов для установки .NET Core на SLES 12.</span><span class="sxs-lookup"><span data-stu-id="7bc2b-104">This article describes how to use a package manager to install .NET Core on SLES 12.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="add-microsoft-repository-key-and-feed"></a><span data-ttu-id="7bc2b-105">Добавление ключа и веб-канала репозитория Майкрософт</span><span class="sxs-lookup"><span data-stu-id="7bc2b-105">Add Microsoft repository key and feed</span></span>

<span data-ttu-id="7bc2b-106">Перед установкой .NET нужно сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="7bc2b-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="7bc2b-107">добавить ключ подписывания пакета Майкрософт в список доверенных ключей;</span><span class="sxs-lookup"><span data-stu-id="7bc2b-107">Add the Microsoft package signing key to the list of trusted keys.</span></span>
- <span data-ttu-id="7bc2b-108">добавить репозиторий в диспетчер пакетов;</span><span class="sxs-lookup"><span data-stu-id="7bc2b-108">Add the repository to the package manager.</span></span>
- <span data-ttu-id="7bc2b-109">установить необходимые зависимости.</span><span class="sxs-lookup"><span data-stu-id="7bc2b-109">Install required dependencies.</span></span>

<span data-ttu-id="7bc2b-110">Данную операцию достаточно выполнить один раз для каждого компьютера.</span><span class="sxs-lookup"><span data-stu-id="7bc2b-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="7bc2b-111">Откройте терминал и выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="7bc2b-111">Open a terminal and run the following command.</span></span>

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/12/packages-microsoft-prod.rpm
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="7bc2b-112">Установка пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="7bc2b-112">Install the .NET Core SDK</span></span>

<span data-ttu-id="7bc2b-113">Обновите продукты, доступные для установки, а затем установите пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7bc2b-113">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="7bc2b-114">В терминале выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="7bc2b-114">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="7bc2b-115">Установка среды выполнения ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7bc2b-115">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="7bc2b-116">Обновите продукты, доступные для установки, а затем установите среду выполнения ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="7bc2b-116">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="7bc2b-117">В терминале выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="7bc2b-117">In your terminal, run the following command.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="7bc2b-118">Установка среды выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="7bc2b-118">Install the .NET Core runtime</span></span>

<span data-ttu-id="7bc2b-119">Обновите продукты, доступные для установки, а затем установите среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7bc2b-119">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="7bc2b-120">В терминале выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="7bc2b-120">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="7bc2b-121">Установка других версий</span><span class="sxs-lookup"><span data-stu-id="7bc2b-121">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="7bc2b-122">Устранение неполадок диспетчера пакетов</span><span class="sxs-lookup"><span data-stu-id="7bc2b-122">Troubleshoot the package manager</span></span>

<span data-ttu-id="7bc2b-123">В этом разделе описаны распространенные ошибки, которые могут возникнуть при использовании диспетчера пакетов для установки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7bc2b-123">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="7bc2b-124">Ошибка получения</span><span class="sxs-lookup"><span data-stu-id="7bc2b-124">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]
