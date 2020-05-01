---
title: Средства Azure для разработчиков .NET и .NET Core
description: Получите средства для работы с библиотеками Azure для .NET в среде Windows, Mac и Linux.
ms.date: 10/01/2018
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: 1c6370e4b3e5e6e901ba6ef56c65d794f3da5abe
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2020
ms.locfileid: "81433166"
---
# <a name="tools-for-net-and-net-core-azure-developers"></a><span data-ttu-id="d1f9d-103">Средства Azure для разработчиков .NET и .NET Core</span><span class="sxs-lookup"><span data-stu-id="d1f9d-103">Tools for .NET and .NET Core Azure developers</span></span>

## <a name="sdk-downloads"></a><span data-ttu-id="d1f9d-104">Скачиваемые пакеты SDK</span><span class="sxs-lookup"><span data-stu-id="d1f9d-104">SDK downloads</span></span>

<span data-ttu-id="d1f9d-105">Библиотеки Azure для .NET реализуются как [пакеты NuGet](https://www.nuget.org/packages?q=windowsazureofficial).</span><span class="sxs-lookup"><span data-stu-id="d1f9d-105">Azure libraries for .NET are implemented as [NuGet packages](https://www.nuget.org/packages?q=windowsazureofficial).</span></span> <span data-ttu-id="d1f9d-106">См. инструкции по установке, упорядоченные по службам Azure, в справочнике по [API](/dotnet/api/overview/azure/?view=azure-dotnet).</span><span class="sxs-lookup"><span data-stu-id="d1f9d-106">See the [API Reference](/dotnet/api/overview/azure/?view=azure-dotnet) for installation instructions organized by Azure service.</span></span>

## <a name="development-tools"></a><span data-ttu-id="d1f9d-107">Инструменты разработки</span><span class="sxs-lookup"><span data-stu-id="d1f9d-107">Development tools</span></span>

<span data-ttu-id="d1f9d-108">Visual Studio содержит встроенный инструментарий для многих служб Azure.</span><span class="sxs-lookup"><span data-stu-id="d1f9d-108">Visual Studio has tooling for many Azure services built-in.</span></span> <span data-ttu-id="d1f9d-109">Для некоторых служб Azure доступны дополнительные средства или эмуляторы, например [Обозреватель службы хранилища Azure](https://azure.microsoft.com/features/storage-explorer/).</span><span class="sxs-lookup"><span data-stu-id="d1f9d-109">Some Azure services have additional tools or emulators available, such as [Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/).</span></span> <span data-ttu-id="d1f9d-110">При необходимости ознакомьтесь с документацией по соответствующей службе Azure.</span><span class="sxs-lookup"><span data-stu-id="d1f9d-110">See the documentation for your Azure service for any additional tools, if necessary.</span></span>

<span data-ttu-id="d1f9d-111">Эти инструкции устанавливают рекомендуемую начальную среду разработки для операционной системы.</span><span class="sxs-lookup"><span data-stu-id="d1f9d-111">These instructions install the recommended starting development environment for your operating system.</span></span>

## <a name="windows"></a>[<span data-ttu-id="d1f9d-112">Windows</span><span class="sxs-lookup"><span data-stu-id="d1f9d-112">Windows</span></span>](#tab/windows)

<span data-ttu-id="d1f9d-113">В Visual Studio 2017 и более поздних версий есть встроенная поддержка средств разработки для Azure.</span><span class="sxs-lookup"><span data-stu-id="d1f9d-113">Visual Studio versions 2017 and later have built-in support for Azure development.</span></span> <span data-ttu-id="d1f9d-114">Ниже описано, как включить поддержку средств разработки Azure в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d1f9d-114">The below steps describe enabling Azure development support in Visual Studio.</span></span>

<span data-ttu-id="d1f9d-115">В Visual Studio 2015 и более ранних версий <a href="vs2015-install.md">следуйте этим инструкциям</a>.</span><span class="sxs-lookup"><span data-stu-id="d1f9d-115">For Visual Studio 2015 and earlier, <a href="vs2015-install.md">follow these instructions</a>.</span></span>

### <a name="step-1-download-visual-studio-2019"></a><span data-ttu-id="d1f9d-116">Шаг 1. Скачивание Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="d1f9d-116">Step 1: Download Visual Studio 2019</span></span>

<span data-ttu-id="d1f9d-117">Вы можете пропустить этот шаг, если уже установили Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="d1f9d-117">You can skip this step if you already have Visual Studio 2019 installed.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d1f9d-118">Скачивание Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="d1f9d-118">Download Visual Studio 2019</span></span>](https://www.visualstudio.com/downloads/)

### <a name="step-2-install-the-two-azure-workloads"></a><span data-ttu-id="d1f9d-119">Шаг 2. Установка двух рабочих нагрузок Azure</span><span class="sxs-lookup"><span data-stu-id="d1f9d-119">Step 2: Install the two Azure workloads</span></span>

<span data-ttu-id="d1f9d-120">В установщике Visual Studio установите Visual Studio (или измените существующую установку).</span><span class="sxs-lookup"><span data-stu-id="d1f9d-120">In the Visual Studio installer, install Visual Studio (or modify an existing installation).</span></span> <span data-ttu-id="d1f9d-121">Убедитесь, что выбраны рабочие нагрузки *Разработка Azure* и *Веб-разработка и разработка ASP.NET*.</span><span class="sxs-lookup"><span data-stu-id="d1f9d-121">Make sure the *Azure development* and *ASP.NET and web development* workloads are selected.</span></span>

### <a name="step-3-develop-with-net-on-azure"></a><span data-ttu-id="d1f9d-122">Шаг 3. Разработка с помощью .NET в Azure</span><span class="sxs-lookup"><span data-stu-id="d1f9d-122">Step 3: Develop with .NET on Azure</span></span>

<span data-ttu-id="d1f9d-123">Начните с [развертывания первого веб-приложения ASP.NET Core в Службе приложений Azure](https://docs.microsoft.com/azure/app-service-web/app-service-web-get-started-dotnet).</span><span class="sxs-lookup"><span data-stu-id="d1f9d-123">Get started by [deploying your first ASP.NET Core web app on Azure App Service](https://docs.microsoft.com/azure/app-service-web/app-service-web-get-started-dotnet).</span></span>

## <a name="macos"></a>[<span data-ttu-id="d1f9d-124">macOS</span><span class="sxs-lookup"><span data-stu-id="d1f9d-124">macOS</span></span>](#tab/macos)

<span data-ttu-id="d1f9d-125">В Visual Studio для Mac есть все необходимое для разработки в Azure.</span><span class="sxs-lookup"><span data-stu-id="d1f9d-125">Visual Studio for Mac has everything you need for Azure development.</span></span>

### <a name="step-1-download-visual-studio-for-mac"></a><span data-ttu-id="d1f9d-126">Шаг 1. Скачать Visual Studio для Mac</span><span class="sxs-lookup"><span data-stu-id="d1f9d-126">Step 1: Download Visual Studio for Mac</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d1f9d-127">Скачайте Visual Studio для Mac</span><span class="sxs-lookup"><span data-stu-id="d1f9d-127">Download Visual Studio for Mac</span></span>](https://www.visualstudio.com/vs/visual-studio-mac/)

<span data-ttu-id="d1f9d-128">Во время установки средства Azure выбираются по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d1f9d-128">During installation, Azure tools are selected by default.</span></span>

## <a name="linux"></a>[<span data-ttu-id="d1f9d-129">Linux</span><span class="sxs-lookup"><span data-stu-id="d1f9d-129">Linux</span></span>](#tab/linux)

<span data-ttu-id="d1f9d-130">В Visual Studio Code есть все необходимое для разработки в Azure в среде Linux.</span><span class="sxs-lookup"><span data-stu-id="d1f9d-130">Visual Studio Code has everything you need for Azure development on Linux.</span></span>

### <a name="step-1-download-the-net-core-sdk"></a><span data-ttu-id="d1f9d-131">Шаг 1. Скачать пакет SDK .NET Core</span><span class="sxs-lookup"><span data-stu-id="d1f9d-131">Step 1: Download the .NET Core SDK</span></span>

<span data-ttu-id="d1f9d-132">Пакет SDK и средства командной строки для приложений .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d1f9d-132">The SDK and command-line tools for .NET Core apps.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d1f9d-133">Скачать пакет SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="d1f9d-133">Download .NET Core SDK</span></span>](https://dotnet.microsoft.com/download)

### <a name="step-2-visual-studio-code"></a><span data-ttu-id="d1f9d-134">Шаг 2. Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="d1f9d-134">Step 2: Visual Studio Code</span></span>

<span data-ttu-id="d1f9d-135">Изменение и отладка приложений .NET Core в любой операционной системе: Windows, Mac и Linux.</span><span class="sxs-lookup"><span data-stu-id="d1f9d-135">Edit and debug .NET Core apps on any operating system: Windows, Mac, and Linux.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d1f9d-136">Скачать Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="d1f9d-136">Download Visual Studio Code</span></span>](https://code.visualstudio.com)

---
