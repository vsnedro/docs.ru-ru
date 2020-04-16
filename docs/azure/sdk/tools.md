---
title: Средства Azure для разработчиков .NET и .NET Core
description: Получите средства для работы с библиотеками Azure для .NET в среде Windows, Mac и Linux.
ms.date: 10/01/2018
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: 1c6370e4b3e5e6e901ba6ef56c65d794f3da5abe
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2020
ms.locfileid: "81433166"
---
# <a name="tools-for-net-and-net-core-azure-developers"></a><span data-ttu-id="decc2-103">Средства Azure для разработчиков .NET и .NET Core</span><span class="sxs-lookup"><span data-stu-id="decc2-103">Tools for .NET and .NET Core Azure developers</span></span>

## <a name="sdk-downloads"></a><span data-ttu-id="decc2-104">Загрузки SDK</span><span class="sxs-lookup"><span data-stu-id="decc2-104">SDK downloads</span></span>

<span data-ttu-id="decc2-105">Библиотеки Azure для .NET реализованы в виде [пакетов NuGet.](https://www.nuget.org/packages?q=windowsazureofficial)</span><span class="sxs-lookup"><span data-stu-id="decc2-105">Azure libraries for .NET are implemented as [NuGet packages](https://www.nuget.org/packages?q=windowsazureofficial).</span></span> <span data-ttu-id="decc2-106">Ознакомьтесь с [справкой aPI](/dotnet/api/overview/azure/?view=azure-dotnet) для инструкций по установке, организованных службой Azure.</span><span class="sxs-lookup"><span data-stu-id="decc2-106">See the [API Reference](/dotnet/api/overview/azure/?view=azure-dotnet) for installation instructions organized by Azure service.</span></span>

## <a name="development-tools"></a><span data-ttu-id="decc2-107">Инструменты разработки</span><span class="sxs-lookup"><span data-stu-id="decc2-107">Development tools</span></span>

<span data-ttu-id="decc2-108">Visual Studio имеет инструментарий для многих встроенных служб Azure.</span><span class="sxs-lookup"><span data-stu-id="decc2-108">Visual Studio has tooling for many Azure services built-in.</span></span> <span data-ttu-id="decc2-109">Некоторые службы Azure имеют дополнительные инструменты или эмуляторы, такие как [Azure Storage Explorer.](https://azure.microsoft.com/features/storage-explorer/)</span><span class="sxs-lookup"><span data-stu-id="decc2-109">Some Azure services have additional tools or emulators available, such as [Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/).</span></span> <span data-ttu-id="decc2-110">При необходимости ознакомьтесь с документацией службы Azure для любых дополнительных инструментов.</span><span class="sxs-lookup"><span data-stu-id="decc2-110">See the documentation for your Azure service for any additional tools, if necessary.</span></span>

<span data-ttu-id="decc2-111">Эти инструкции устанавливают рекомендуемую среду начала разработки для вашей операционной системы.</span><span class="sxs-lookup"><span data-stu-id="decc2-111">These instructions install the recommended starting development environment for your operating system.</span></span>

## <a name="windows"></a>[<span data-ttu-id="decc2-112">Windows</span><span class="sxs-lookup"><span data-stu-id="decc2-112">Windows</span></span>](#tab/windows)

<span data-ttu-id="decc2-113">Версии Visual Studio 2017 и позже встроены в разработку Azure.</span><span class="sxs-lookup"><span data-stu-id="decc2-113">Visual Studio versions 2017 and later have built-in support for Azure development.</span></span> <span data-ttu-id="decc2-114">Ниже приведены шаги, описывая предоставление поддержки разработки Azure в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="decc2-114">The below steps describe enabling Azure development support in Visual Studio.</span></span>

<span data-ttu-id="decc2-115">Для Visual Studio 2015 и ранее, <a href="vs2015-install.md">следуйте этим инструкциям</a>.</span><span class="sxs-lookup"><span data-stu-id="decc2-115">For Visual Studio 2015 and earlier, <a href="vs2015-install.md">follow these instructions</a>.</span></span>

### <a name="step-1-download-visual-studio-2019"></a><span data-ttu-id="decc2-116">Шаг 1: Скачать Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="decc2-116">Step 1: Download Visual Studio 2019</span></span>

<span data-ttu-id="decc2-117">Вы можете пропустить этот шаг, если у вас уже есть Visual Studio 2019 установлен.</span><span class="sxs-lookup"><span data-stu-id="decc2-117">You can skip this step if you already have Visual Studio 2019 installed.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="decc2-118">Скачивание Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="decc2-118">Download Visual Studio 2019</span></span>](https://www.visualstudio.com/downloads/)

### <a name="step-2-install-the-two-azure-workloads"></a><span data-ttu-id="decc2-119">Шаг 2. Установка двух рабочих нагрузок Azure</span><span class="sxs-lookup"><span data-stu-id="decc2-119">Step 2: Install the two Azure workloads</span></span>

<span data-ttu-id="decc2-120">В установке Visual Studio установите Visual Studio (или измените существующую установку).</span><span class="sxs-lookup"><span data-stu-id="decc2-120">In the Visual Studio installer, install Visual Studio (or modify an existing installation).</span></span> <span data-ttu-id="decc2-121">Убедитесь, что выбраны рабочие нагрузки разработки и *ASP.NET и веб-разработки* *Azure.*</span><span class="sxs-lookup"><span data-stu-id="decc2-121">Make sure the *Azure development* and *ASP.NET and web development* workloads are selected.</span></span>

### <a name="step-3-develop-with-net-on-azure"></a><span data-ttu-id="decc2-122">Шаг 3. Разработка с помощью .NET в Azure</span><span class="sxs-lookup"><span data-stu-id="decc2-122">Step 3: Develop with .NET on Azure</span></span>

<span data-ttu-id="decc2-123">Начните с [развертывания первого веб-приложения ASP.NET Core в Службе приложений Azure](https://docs.microsoft.com/azure/app-service-web/app-service-web-get-started-dotnet).</span><span class="sxs-lookup"><span data-stu-id="decc2-123">Get started by [deploying your first ASP.NET Core web app on Azure App Service](https://docs.microsoft.com/azure/app-service-web/app-service-web-get-started-dotnet).</span></span>

## <a name="macos"></a>[<span data-ttu-id="decc2-124">macOS</span><span class="sxs-lookup"><span data-stu-id="decc2-124">macOS</span></span>](#tab/macos)

<span data-ttu-id="decc2-125">В Visual Studio для Mac есть все необходимое для разработки в Azure.</span><span class="sxs-lookup"><span data-stu-id="decc2-125">Visual Studio for Mac has everything you need for Azure development.</span></span>

### <a name="step-1-download-visual-studio-for-mac"></a><span data-ttu-id="decc2-126">Шаг 1. Скачивание Visual Studio для Mac</span><span class="sxs-lookup"><span data-stu-id="decc2-126">Step 1: Download Visual Studio for Mac</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="decc2-127">Скачать Visual Studio для Mac</span><span class="sxs-lookup"><span data-stu-id="decc2-127">Download Visual Studio for Mac</span></span>](https://www.visualstudio.com/vs/visual-studio-mac/)

<span data-ttu-id="decc2-128">Во время установки инструменты Azure выбираются по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="decc2-128">During installation, Azure tools are selected by default.</span></span>

## <a name="linux"></a>[<span data-ttu-id="decc2-129">Linux</span><span class="sxs-lookup"><span data-stu-id="decc2-129">Linux</span></span>](#tab/linux)

<span data-ttu-id="decc2-130">В Visual Studio Code есть все необходимое для разработки в Azure в среде Linux.</span><span class="sxs-lookup"><span data-stu-id="decc2-130">Visual Studio Code has everything you need for Azure development on Linux.</span></span>

### <a name="step-1-download-the-net-core-sdk"></a><span data-ttu-id="decc2-131">Шаг 1. Скачивание пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="decc2-131">Step 1: Download the .NET Core SDK</span></span>

<span data-ttu-id="decc2-132">Пакет SDK и средства командной строки для приложений .NET Core.</span><span class="sxs-lookup"><span data-stu-id="decc2-132">The SDK and command-line tools for .NET Core apps.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="decc2-133">Скачать пакет SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="decc2-133">Download .NET Core SDK</span></span>](https://dotnet.microsoft.com/download)

### <a name="step-2-visual-studio-code"></a><span data-ttu-id="decc2-134">Шаг 2. Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="decc2-134">Step 2: Visual Studio Code</span></span>

<span data-ttu-id="decc2-135">Изменение и отладка приложений .NET Core в любой операционной системе: Windows, Mac и Linux.</span><span class="sxs-lookup"><span data-stu-id="decc2-135">Edit and debug .NET Core apps on any operating system: Windows, Mac, and Linux.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="decc2-136">Скачать Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="decc2-136">Download Visual Studio Code</span></span>](https://code.visualstudio.com)

---
