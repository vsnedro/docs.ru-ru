---
title: Установка F#
description: 'Узнайте, как установить F # различными способами.'
ms.date: 12/20/2019
ms.openlocfilehash: 302e04f7cf3271516dff88d9d5f18f620b6ede80
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/20/2020
ms.locfileid: "92224283"
---
# <a name="install-f"></a><span data-ttu-id="e56e3-103">Установка F\#</span><span class="sxs-lookup"><span data-stu-id="e56e3-103">Install F\#</span></span>

<span data-ttu-id="e56e3-104">F # можно установить несколькими способами в зависимости от среды.</span><span class="sxs-lookup"><span data-stu-id="e56e3-104">You can install F# in multiple ways, depending on your environment.</span></span>

## <a name="install-f-with-visual-studio"></a><span data-ttu-id="e56e3-105">Установка F # с помощью Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e56e3-105">Install F# with Visual Studio</span></span>

1. <span data-ttu-id="e56e3-106">Если вы скачиваете [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) впервые, сначала будет установлена Visual Studio Installer.</span><span class="sxs-lookup"><span data-stu-id="e56e3-106">If you're downloading [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) for the first time, it will first install Visual Studio Installer.</span></span> <span data-ttu-id="e56e3-107">Установите соответствующий выпуск Visual Studio из установщика.</span><span class="sxs-lookup"><span data-stu-id="e56e3-107">Install the appropriate edition of Visual Studio from the installer.</span></span>

   <span data-ttu-id="e56e3-108">Если у вас уже установлена среда Visual Studio, выберите пункт **изменить** рядом с выпуском, в который нужно добавить F #.</span><span class="sxs-lookup"><span data-stu-id="e56e3-108">If you already have Visual Studio installed, choose **Modify** next to the edition you want to add F# to.</span></span>

2. <span data-ttu-id="e56e3-109">На странице рабочие нагрузки выберите рабочую нагрузку **ASP.NET and Web Development** , которая включает в себя поддержку F # и .NET Core для проектов ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="e56e3-109">On the Workloads page, select the **ASP.NET and web development** workload, which includes F# and .NET Core support for ASP.NET Core projects.</span></span>

3. <span data-ttu-id="e56e3-110">Выберите **изменить** в правом нижнем углу, чтобы установить все, что вы выбрали.</span><span class="sxs-lookup"><span data-stu-id="e56e3-110">Choose **Modify** in the lower right-hand corner to install everything you've selected.</span></span>

   <span data-ttu-id="e56e3-111">Затем можно открыть Visual Studio с помощью F #, выбрав **запустить** в Visual Studio Installer.</span><span class="sxs-lookup"><span data-stu-id="e56e3-111">You can then open Visual Studio with F# by choosing **Launch** in Visual Studio Installer.</span></span>

## <a name="install-f-with-visual-studio-code"></a><span data-ttu-id="e56e3-112">Установка F # с Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="e56e3-112">Install F# with Visual Studio Code</span></span>

1. <span data-ttu-id="e56e3-113">Убедитесь, что на вашем пути установлен и доступен [Git](https://git-scm.com/download) .</span><span class="sxs-lookup"><span data-stu-id="e56e3-113">Ensure you have [git](https://git-scm.com/download) installed and available on your PATH.</span></span> <span data-ttu-id="e56e3-114">Чтобы проверить правильность установки, введите `git --version` в командной строке и нажмите клавишу **Ввод**.</span><span class="sxs-lookup"><span data-stu-id="e56e3-114">You can verify that it's installed correctly by entering `git --version` at a command prompt and pressing **Enter**.</span></span>

2. <span data-ttu-id="e56e3-115">Установите [пакет SDK для .NET Core](https://dotnet.microsoft.com/download) и [Visual Studio Code](https://code.visualstudio.com).</span><span class="sxs-lookup"><span data-stu-id="e56e3-115">Install the [.NET Core SDK](https://dotnet.microsoft.com/download) and [Visual Studio Code](https://code.visualstudio.com).</span></span>

3. <span data-ttu-id="e56e3-116">Щелкните значок расширения и выполните поиск по запросу "Ionide":</span><span class="sxs-lookup"><span data-stu-id="e56e3-116">Select the Extensions icon and search for "Ionide":</span></span>

   <span data-ttu-id="e56e3-117">Единственным подключаемым модулем, необходимым для поддержки F # в Visual Studio Code, является [Ionide-FSharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span><span class="sxs-lookup"><span data-stu-id="e56e3-117">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="e56e3-118">Однако можно также установить [Ionide-ПОДдельные](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) , чтобы получить [поддельную](https://fake.build/) поддержку и [Ionide-пакет](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) , чтобы получить поддержку [пакет](https://fsprojects.github.io/Paket/) .</span><span class="sxs-lookup"><span data-stu-id="e56e3-118">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) to get [FAKE](https://fake.build/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="e56e3-119">Поддельные и пакет — это дополнительные инструменты сообщества F # для создания проектов и управления зависимостями соответственно.</span><span class="sxs-lookup"><span data-stu-id="e56e3-119">FAKE and Paket are additional F# community tools for building projects and managing dependencies, respectively.</span></span>

## <a name="install-f-with-visual-studio-for-mac"></a><span data-ttu-id="e56e3-120">Установка F # с Visual Studio для Mac</span><span class="sxs-lookup"><span data-stu-id="e56e3-120">Install F# with Visual Studio for Mac</span></span>

<span data-ttu-id="e56e3-121">F # устанавливается по умолчанию в [Visual Studio для Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), независимо от выбранной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e56e3-121">F# is installed by default in [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), no matter which configuration you choose.</span></span>

<span data-ttu-id="e56e3-122">После завершения установки нажмите кнопку **запустить Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="e56e3-122">After the install completes, choose **Start Visual Studio**.</span></span> <span data-ttu-id="e56e3-123">Вы также можете открыть Visual Studio с помощью Finder в macOS.</span><span class="sxs-lookup"><span data-stu-id="e56e3-123">You can also open Visual Studio through Finder on macOS.</span></span>

## <a name="install-f-on-a-build-server"></a><span data-ttu-id="e56e3-124">Установка F # на сервере сборки</span><span class="sxs-lookup"><span data-stu-id="e56e3-124">Install F# on a build server</span></span>

<span data-ttu-id="e56e3-125">Если вы используете .NET Core или .NET Framework с помощью пакета SDK для .NET, необходимо просто установить пакет SDK для .NET на сервере сборки.</span><span class="sxs-lookup"><span data-stu-id="e56e3-125">If you're using .NET Core or .NET Framework via the .NET SDK, you simply need to install the .NET SDK on your build server.</span></span> <span data-ttu-id="e56e3-126">Он содержит все необходимое.</span><span class="sxs-lookup"><span data-stu-id="e56e3-126">It has everything you need.</span></span>

<span data-ttu-id="e56e3-127">Если вы используете .NET Framework и вы **не** используете пакет SDK для .NET, необходимо установить [Visual Studio Build Tools SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) на сервере Windows Server.</span><span class="sxs-lookup"><span data-stu-id="e56e3-127">If you're using .NET Framework and you are **not** using the .NET SDK, then you'll need to install the [Visual Studio Build Tools SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) onto your Windows Server.</span></span> <span data-ttu-id="e56e3-128">В установщике выберите **.NET Desktop Build Tools**, а затем выберите компонент **компилятора F #** в правой части меню установщика.</span><span class="sxs-lookup"><span data-stu-id="e56e3-128">In the installer, select **.NET desktop build tools**, and then select the **F# compiler** component on the right-hand side of the installer menu.</span></span>
