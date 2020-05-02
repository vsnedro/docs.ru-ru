---
title: Установка .NET Core на CentOS 7 — диспетчер пакетов — .NET Core
description: Используйте диспетчер пакетов для установки пакета SDK для .NET Core и среды выполнения на CentOS 7.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: f8c4115b9d85edc36809f0daed5f6825149c8411
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645400"
---
# <a name="centos-7-package-manager---install-net-core"></a><span data-ttu-id="c1145-103">Диспетчер пакетов CentOS 7 — установка .NET Core</span><span class="sxs-lookup"><span data-stu-id="c1145-103">CentOS 7 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="c1145-104">Эта статья описывает, как использовать диспетчер пакетов для установки .NET Core на CentOS 7.</span><span class="sxs-lookup"><span data-stu-id="c1145-104">This article describes how to use a package manager to install .NET Core on CentOS 7.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="add-microsoft-repository-key-and-feed"></a><span data-ttu-id="c1145-105">Добавление ключа и веб-канала репозитория Майкрософт</span><span class="sxs-lookup"><span data-stu-id="c1145-105">Add Microsoft repository key and feed</span></span>

<span data-ttu-id="c1145-106">Перед установкой .NET нужно сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="c1145-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="c1145-107">добавить ключ подписывания пакета Майкрософт в список доверенных ключей;</span><span class="sxs-lookup"><span data-stu-id="c1145-107">Add the Microsoft package signing key to the list of trusted keys.</span></span>
- <span data-ttu-id="c1145-108">добавить репозиторий в диспетчер пакетов;</span><span class="sxs-lookup"><span data-stu-id="c1145-108">Add the repository to the package manager.</span></span>
- <span data-ttu-id="c1145-109">установить необходимые зависимости.</span><span class="sxs-lookup"><span data-stu-id="c1145-109">Install required dependencies.</span></span>

<span data-ttu-id="c1145-110">Данную операцию достаточно выполнить один раз для каждого компьютера.</span><span class="sxs-lookup"><span data-stu-id="c1145-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="c1145-111">Откройте терминал и выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="c1145-111">Open a terminal and run the following command.</span></span>

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/centos/7/packages-microsoft-prod.rpm
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="c1145-112">Установка пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="c1145-112">Install the .NET Core SDK</span></span>

<span data-ttu-id="c1145-113">Обновите продукты, доступные для установки, а затем установите пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c1145-113">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="c1145-114">В терминале выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="c1145-114">In your terminal, run the following command.</span></span>

```bash
sudo yum install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="c1145-115">Установка среды выполнения ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c1145-115">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="c1145-116">Обновите продукты, доступные для установки, а затем установите среду выполнения ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="c1145-116">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="c1145-117">В терминале выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="c1145-117">In your terminal, run the following command.</span></span>

```bash
sudo yum install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="c1145-118">Установка среды выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="c1145-118">Install the .NET Core runtime</span></span>

<span data-ttu-id="c1145-119">Обновите продукты, доступные для установки, а затем установите среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c1145-119">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="c1145-120">В терминале выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="c1145-120">In your terminal, run the following command.</span></span>

```bash
sudo yum install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="c1145-121">Установка других версий</span><span class="sxs-lookup"><span data-stu-id="c1145-121">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="c1145-122">Устранение неполадок диспетчера пакетов</span><span class="sxs-lookup"><span data-stu-id="c1145-122">Troubleshoot the package manager</span></span>

<span data-ttu-id="c1145-123">В этом разделе описаны распространенные ошибки, которые могут возникнуть при использовании диспетчера пакетов для установки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c1145-123">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="c1145-124">Ошибка получения</span><span class="sxs-lookup"><span data-stu-id="c1145-124">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]
