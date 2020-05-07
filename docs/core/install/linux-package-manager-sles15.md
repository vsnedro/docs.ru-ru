---
title: Установка .NET Core на SLES 15 — диспетчер пакетов — .NET Core
description: Используйте диспетчер пакетов для установки пакета SDK для .NET Core и среды выполнения на SLES 15.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: be5a21db8c3942bfe8827dfbce41bcf88aec342a
ms.sourcegitcommit: d7666f6e49c57a769612602ea7857b927294ce47
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2020
ms.locfileid: "82595665"
---
# <a name="sles-15-package-manager---install-net-core"></a><span data-ttu-id="ef9cf-103">Диспетчер пакетов SLES 15 — установка .NET Core</span><span class="sxs-lookup"><span data-stu-id="ef9cf-103">SLES 15 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="ef9cf-104">Эта статья описывает, как использовать диспетчер пакетов для установки .NET Core на SLES 15.</span><span class="sxs-lookup"><span data-stu-id="ef9cf-104">This article describes how to use a package manager to install .NET Core on SLES 15.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="add-microsoft-repository-key-and-feed"></a><span data-ttu-id="ef9cf-105">Добавление ключа и веб-канала репозитория Майкрософт</span><span class="sxs-lookup"><span data-stu-id="ef9cf-105">Add Microsoft repository key and feed</span></span>

<span data-ttu-id="ef9cf-106">Перед установкой .NET нужно сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="ef9cf-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="ef9cf-107">добавить ключ подписывания пакета Майкрософт в список доверенных ключей;</span><span class="sxs-lookup"><span data-stu-id="ef9cf-107">Add the Microsoft package signing key to the list of trusted keys.</span></span>
- <span data-ttu-id="ef9cf-108">добавить репозиторий в диспетчер пакетов;</span><span class="sxs-lookup"><span data-stu-id="ef9cf-108">Add the repository to the package manager.</span></span>
- <span data-ttu-id="ef9cf-109">установить необходимые зависимости.</span><span class="sxs-lookup"><span data-stu-id="ef9cf-109">Install required dependencies.</span></span>

<span data-ttu-id="ef9cf-110">Данную операцию достаточно выполнить один раз для каждого компьютера.</span><span class="sxs-lookup"><span data-stu-id="ef9cf-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="ef9cf-111">Откройте терминал и выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="ef9cf-111">Open a terminal and run the following command.</span></span>

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/15/packages-microsoft-prod.rpm
```

<span data-ttu-id="ef9cf-112">В настоящее время пакет установки репозитория Microsoft SLES 15 устанавливает файл *microsoft-prod.repo* в неправильный каталог, мешая поиску пакетов .NET Core в zypper.</span><span class="sxs-lookup"><span data-stu-id="ef9cf-112">Currently, the SLES 15 Microsoft repository setup package installs the *microsoft-prod.repo* file to the wrong directory, preventing zypper from finding the .NET Core packages.</span></span> <span data-ttu-id="ef9cf-113">Чтобы устранить эту проблему, создайте символьную ссылку в правильном каталоге.</span><span class="sxs-lookup"><span data-stu-id="ef9cf-113">To fix this problem, create a symlink in the correct directory.</span></span>

```bash
sudo ln -s /etc/yum.repos.d/microsoft-prod.repo /etc/zypp/repos.d/microsoft-prod.repo
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="ef9cf-114">Установка пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="ef9cf-114">Install the .NET Core SDK</span></span>

<span data-ttu-id="ef9cf-115">Обновите продукты, доступные для установки, а затем установите пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ef9cf-115">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="ef9cf-116">В терминале выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="ef9cf-116">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="ef9cf-117">Установка среды выполнения ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ef9cf-117">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="ef9cf-118">Обновите продукты, доступные для установки, а затем установите среду выполнения ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="ef9cf-118">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="ef9cf-119">В терминале выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="ef9cf-119">In your terminal, run the following command.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="ef9cf-120">Установка среды выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="ef9cf-120">Install the .NET Core runtime</span></span>

<span data-ttu-id="ef9cf-121">Обновите продукты, доступные для установки, а затем установите среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ef9cf-121">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="ef9cf-122">В терминале выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="ef9cf-122">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="ef9cf-123">Установка других версий</span><span class="sxs-lookup"><span data-stu-id="ef9cf-123">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="ef9cf-124">Устранение неполадок диспетчера пакетов</span><span class="sxs-lookup"><span data-stu-id="ef9cf-124">Troubleshoot the package manager</span></span>

<span data-ttu-id="ef9cf-125">В этом разделе описаны распространенные ошибки, которые могут возникнуть при использовании диспетчера пакетов для установки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ef9cf-125">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="ef9cf-126">Ошибка получения</span><span class="sxs-lookup"><span data-stu-id="ef9cf-126">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-rpm.md)]
