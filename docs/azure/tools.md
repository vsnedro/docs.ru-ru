---
title: Средства для разработчиков Azure .NET
description: Получите средства для работы с библиотеками Azure для .NET в среде Windows, Mac и Linux.
ms.date: 06/19/2020
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: fa645b152f15550b25a3542ba0cdbb43799536b9
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174854"
---
# <a name="azure-tools-for-developing-with-net"></a><span data-ttu-id="42ead-103">Средства Azure для разработки с использованием .NET</span><span class="sxs-lookup"><span data-stu-id="42ead-103">Azure tools for developing with .NET</span></span>

## <a name="sdk-downloads"></a><span data-ttu-id="42ead-104">Скачиваемые пакеты SDK</span><span class="sxs-lookup"><span data-stu-id="42ead-104">SDK downloads</span></span>

<span data-ttu-id="42ead-105">Библиотеки Azure для .NET реализуются как [пакеты NuGet](https://www.nuget.org/packages?q=windowsazureofficial).</span><span class="sxs-lookup"><span data-stu-id="42ead-105">Azure libraries for .NET are implemented as [NuGet packages](https://www.nuget.org/packages?q=windowsazureofficial).</span></span> <span data-ttu-id="42ead-106">Справочную документацию, упорядоченную по службам Azure, см. в [справочнике по API](/dotnet/api/overview/azure/?view=azure-dotnet).</span><span class="sxs-lookup"><span data-stu-id="42ead-106">See the [API Reference](/dotnet/api/overview/azure/?view=azure-dotnet) for reference documentation organized by Azure service.</span></span>

## <a name="development-tools"></a><span data-ttu-id="42ead-107">Инструменты разработки</span><span class="sxs-lookup"><span data-stu-id="42ead-107">Development tools</span></span>

<span data-ttu-id="42ead-108">Visual Studio содержит встроенный инструментарий для многих служб Azure.</span><span class="sxs-lookup"><span data-stu-id="42ead-108">Visual Studio has tooling for many Azure services built-in.</span></span> <span data-ttu-id="42ead-109">Для некоторых служб Azure доступны дополнительные средства или эмуляторы, например [Обозреватель службы хранилища Azure](https://azure.microsoft.com/features/storage-explorer/).</span><span class="sxs-lookup"><span data-stu-id="42ead-109">Some Azure services have additional tools or emulators available, such as [Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/).</span></span> <span data-ttu-id="42ead-110">При необходимости ознакомьтесь с документацией по соответствующей службе Azure.</span><span class="sxs-lookup"><span data-stu-id="42ead-110">See the documentation for your Azure service for any additional tools, if necessary.</span></span>

<span data-ttu-id="42ead-111">Выберите предпочитаемую среду разработки ниже.</span><span class="sxs-lookup"><span data-stu-id="42ead-111">Select your preferred development environment below.</span></span>

## <a name="visual-studio-on-windows"></a>[<span data-ttu-id="42ead-112">Visual Studio в Windows</span><span class="sxs-lookup"><span data-stu-id="42ead-112">Visual Studio on Windows</span></span>](#tab/vs)

<span data-ttu-id="42ead-113">В Visual Studio 2017 и более поздних версий есть встроенная поддержка средств разработки для Azure.</span><span class="sxs-lookup"><span data-stu-id="42ead-113">Visual Studio version 2017 and later have built-in support for Azure development.</span></span> <span data-ttu-id="42ead-114">Ниже описано, как включить поддержку средств разработки Azure в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="42ead-114">The below steps describe enabling Azure development support in Visual Studio.</span></span>

<span data-ttu-id="42ead-115">В Visual Studio 2015 и более ранних версий <a href="vs2015-install.md">следуйте этим инструкциям</a>.</span><span class="sxs-lookup"><span data-stu-id="42ead-115">For Visual Studio 2015 and earlier, <a href="vs2015-install.md">follow these instructions</a>.</span></span>

### <a name="step-1-download-visual-studio-2019"></a><span data-ttu-id="42ead-116">Шаг 1. Скачивание Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="42ead-116">Step 1: Download Visual Studio 2019</span></span>

<span data-ttu-id="42ead-117">Вы можете пропустить этот шаг, если уже установили Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="42ead-117">You can skip this step if you already have Visual Studio 2019 installed.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="42ead-118">Скачивание Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="42ead-118">Download Visual Studio 2019</span></span>](https://www.visualstudio.com/downloads/)

### <a name="step-2-install-the-two-azure-workloads"></a><span data-ttu-id="42ead-119">Шаг 2. Установка двух рабочих нагрузок Azure</span><span class="sxs-lookup"><span data-stu-id="42ead-119">Step 2: Install the two Azure workloads</span></span>

<span data-ttu-id="42ead-120">В установщике Visual Studio установите Visual Studio (или измените существующую установку).</span><span class="sxs-lookup"><span data-stu-id="42ead-120">In the Visual Studio installer, install Visual Studio (or modify an existing installation).</span></span> <span data-ttu-id="42ead-121">Убедитесь, что выбраны рабочие нагрузки *Разработка Azure* и *Веб-разработка и разработка ASP.NET*.</span><span class="sxs-lookup"><span data-stu-id="42ead-121">Make sure the *Azure development* and *ASP.NET and web development* workloads are selected.</span></span>

### <a name="step-3-develop-with-net-on-azure"></a><span data-ttu-id="42ead-122">Шаг 3. Разработка с помощью .NET в Azure</span><span class="sxs-lookup"><span data-stu-id="42ead-122">Step 3: Develop with .NET on Azure</span></span>

<span data-ttu-id="42ead-123">Начните с [развертывания первого веб-приложения ASP.NET Core в Службе приложений Azure](/azure/app-service-web/app-service-web-get-started-dotnet).</span><span class="sxs-lookup"><span data-stu-id="42ead-123">Get started by [deploying your first ASP.NET Core web app on Azure App Service](/azure/app-service-web/app-service-web-get-started-dotnet).</span></span>

## <a name="visual-studio-code-cross-platform"></a>[<span data-ttu-id="42ead-124">Visual Studio Code (кроссплатформенная среда)</span><span class="sxs-lookup"><span data-stu-id="42ead-124">Visual Studio Code (cross-platform)</span></span>](#tab/vscode)

<span data-ttu-id="42ead-125">В Visual Studio Code есть все необходимое для кроссплатформенной разработки в Azure.</span><span class="sxs-lookup"><span data-stu-id="42ead-125">Visual Studio Code has everything you need for cross-platform Azure development.</span></span>

### <a name="step-1-download-the-net-core-sdk"></a><span data-ttu-id="42ead-126">Шаг 1. Скачать пакет SDK .NET Core</span><span class="sxs-lookup"><span data-stu-id="42ead-126">Step 1: Download the .NET Core SDK</span></span>

<span data-ttu-id="42ead-127">Пакет SDK и средства командной строки для приложений .NET Core.</span><span class="sxs-lookup"><span data-stu-id="42ead-127">The SDK and command-line tools for .NET Core apps.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="42ead-128">Скачать пакет SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="42ead-128">Download .NET Core SDK</span></span>](https://dotnet.microsoft.com/download)

### <a name="step-2-visual-studio-code"></a><span data-ttu-id="42ead-129">Шаг 2. Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="42ead-129">Step 2: Visual Studio Code</span></span>

<span data-ttu-id="42ead-130">Изменение и отладка приложений .NET Core в любой операционной системе: Windows, Mac и Linux.</span><span class="sxs-lookup"><span data-stu-id="42ead-130">Edit and debug .NET Core apps on any operating system: Windows, Mac, and Linux.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="42ead-131">Скачать Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="42ead-131">Download Visual Studio Code</span></span>](https://code.visualstudio.com)

### <a name="step-3-azure-tools-extension"></a><span data-ttu-id="42ead-132">Шаг 3. Расширение Azure Tools</span><span class="sxs-lookup"><span data-stu-id="42ead-132">Step 3: Azure Tools extension</span></span>

<span data-ttu-id="42ead-133">Установите расширение Azure Tools в Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="42ead-133">Install the Azure Tools extension in Visual Studio Code.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="42ead-134">Установка расширения Azure Tools</span><span class="sxs-lookup"><span data-stu-id="42ead-134">Install Azure Tools extension</span></span>](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-node-azure-pack)

### <a name="step-4-develop-with-net-on-azure"></a><span data-ttu-id="42ead-135">Шаг 4. Разработка с помощью .NET в Azure</span><span class="sxs-lookup"><span data-stu-id="42ead-135">Step 4: Develop with .NET on Azure</span></span>

<span data-ttu-id="42ead-136">Начните с [развертывания первого веб-приложения ASP.NET Core в Службе приложений Azure в Linux](/azure/app-service/containers/quickstart-dotnetcore).</span><span class="sxs-lookup"><span data-stu-id="42ead-136">Get started by [deploying your first ASP.NET Core web app on Azure App Service on Linux](/azure/app-service/containers/quickstart-dotnetcore).</span></span>

---
