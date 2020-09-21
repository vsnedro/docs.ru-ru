---
title: Введение в .NET Core
description: .NET Core — это модульная высокопроизводительная реализация .NET для создания приложений Windows, Linux и macOS. Для начала получите дополнительную информацию о .NET Core.
author: richlander
ms.date: 03/26/2020
ms.custom: updateeachrelease
ms.openlocfilehash: 350fd50bee3403a05d1c19c9a692535613b17498
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538280"
---
# <a name="introduction-to-net-core"></a><span data-ttu-id="ed13d-104">Введение в .NET Core</span><span class="sxs-lookup"><span data-stu-id="ed13d-104">Introduction to .NET Core</span></span>

<span data-ttu-id="ed13d-105">[.NET Core](about.md) — это платформа разработки общего назначения с [открытым кодом](https://github.com/dotnet/runtime/blob/master/LICENSE.TXT), предназначенная для создания кроссплатформенных приложений.</span><span class="sxs-lookup"><span data-stu-id="ed13d-105">[.NET Core](about.md) is an [open-source](https://github.com/dotnet/runtime/blob/master/LICENSE.TXT), general-purpose development platform.</span></span> <span data-ttu-id="ed13d-106">Вы можете создавать приложения .NET Core для Windows, macOS и Linux с поддержкой процессоров x64, x86, ARM32 и ARM64, используя несколько языков программирования.</span><span class="sxs-lookup"><span data-stu-id="ed13d-106">You can create .NET Core apps for Windows, macOS, and Linux for x64, x86, ARM32, and ARM64 processors using multiple programming languages.</span></span> <span data-ttu-id="ed13d-107">Вам доступны платформы и API-интерфейсы для создания [облачных](/aspnet/core/) приложений, приложений для [Интернета вещей](/archive/msdn-magazine/2019/august/net-core-cross-platform-iot-programming-with-net-core-3-0), использования [клиентского интерфейса](../desktop-wpf/overview/index.md) и [машинного обучения](../machine-learning/index.yml).</span><span class="sxs-lookup"><span data-stu-id="ed13d-107">Frameworks and APIs are provided for [cloud](/aspnet/core/), [IoT](/archive/msdn-magazine/2019/august/net-core-cross-platform-iot-programming-with-net-core-3-0), [client UI](../desktop-wpf/overview/index.md), and [machine learning](../machine-learning/index.yml).</span></span>

<span data-ttu-id="ed13d-108">Скачайте [пакет SDK для .NET Core](https://dotnet.microsoft.com/download), чтобы поработать с .NET Core на компьютере.</span><span class="sxs-lookup"><span data-stu-id="ed13d-108">[Download the .NET Core SDK](https://dotnet.microsoft.com/download) to try .NET Core on your machine.</span></span> <span data-ttu-id="ed13d-109">[.NET Core 3.1](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/) является последней версией.</span><span class="sxs-lookup"><span data-stu-id="ed13d-109">The latest version is [.NET Core 3.1](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/).</span></span>

## <a name="download-net-core"></a><span data-ttu-id="ed13d-110">Скачать .NET Core</span><span class="sxs-lookup"><span data-stu-id="ed13d-110">Download .NET Core</span></span>

<span data-ttu-id="ed13d-111">.NET Core можно получить следующими способами.</span><span class="sxs-lookup"><span data-stu-id="ed13d-111">You can get .NET Core in the following ways:</span></span>

* [<span data-ttu-id="ed13d-112">Установщики для Windows и macOS</span><span class="sxs-lookup"><span data-stu-id="ed13d-112">Installers for Windows and macOS</span></span>](https://dotnet.microsoft.com/download)
* [<span data-ttu-id="ed13d-113">Пакеты Linux</span><span class="sxs-lookup"><span data-stu-id="ed13d-113">Linux packages</span></span>](./install/linux.md)
* [<span data-ttu-id="ed13d-114">Контейнеры Docker</span><span class="sxs-lookup"><span data-stu-id="ed13d-114">Docker containers</span></span>](https://hub.docker.com/_/microsoft-dotnet-core/)
* [<span data-ttu-id="ed13d-115">ZIP- и TAR-архивы</span><span class="sxs-lookup"><span data-stu-id="ed13d-115">Zips and tarballs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* [<span data-ttu-id="ed13d-116">Скрипты установки</span><span class="sxs-lookup"><span data-stu-id="ed13d-116">Install scripts</span></span>](https://dotnet.microsoft.com/download/dotnet-core/scripts)
* [<span data-ttu-id="ed13d-117">Заметки о выпуске</span><span class="sxs-lookup"><span data-stu-id="ed13d-117">Release notes</span></span>](https://github.com/dotnet/core/tree/master/release-notes)

## <a name="create-your-first-application"></a><span data-ttu-id="ed13d-118">Создание первого приложения</span><span class="sxs-lookup"><span data-stu-id="ed13d-118">Create your first application</span></span>

<span data-ttu-id="ed13d-119">После установки пакета SDK для .NET Core откройте командную строку.</span><span class="sxs-lookup"><span data-stu-id="ed13d-119">After installing the .NET Core SDK, open a command prompt.</span></span> <span data-ttu-id="ed13d-120">Для создания и запуска приложения используйте следующие команды.</span><span class="sxs-lookup"><span data-stu-id="ed13d-120">Use the following commands to create and run an application:</span></span>

```dotnetcli
dotnet new console
dotnet run
```

<span data-ttu-id="ed13d-121">Должны выводиться следующие данные:</span><span class="sxs-lookup"><span data-stu-id="ed13d-121">You should see the following output:</span></span>

```output
Hello World!
```

## <a name="contribute"></a><span data-ttu-id="ed13d-122">Участие</span><span class="sxs-lookup"><span data-stu-id="ed13d-122">Contribute</span></span>

<span data-ttu-id="ed13d-123">.NET Core является открытой платформа.</span><span class="sxs-lookup"><span data-stu-id="ed13d-123">.NET Core is an open platform.</span></span> <span data-ttu-id="ed13d-124">Участвовать в разработке может любой желающий.</span><span class="sxs-lookup"><span data-stu-id="ed13d-124">Everyone is welcome to participate.</span></span>

* <span data-ttu-id="ed13d-125">Проблемы и вопросы можно размещать в [Сообществе разработчиков](https://developercommunity.visualstudio.com/spaces/61/index.html).</span><span class="sxs-lookup"><span data-stu-id="ed13d-125">File product issues and questions at [Developer Community](https://developercommunity.visualstudio.com/spaces/61/index.html).</span></span>
* <span data-ttu-id="ed13d-126">Дополнения по продуктам следует вносить в один из репозиториев проекта, например [dotnet/runtime](https://github.com/dotnet/runtime), [dotnet/sdk](https://github.com/dotnet/sdk), [dotnet/rosyln](https://github.com/dotnet/roslyn) или [aspnetcore](https://github.com/dotnet/aspnetcore).</span><span class="sxs-lookup"><span data-stu-id="ed13d-126">Product contributions should be made on one of the project repositories, such as [dotnet/runtime](https://github.com/dotnet/runtime), [dotnet/sdk](https://github.com/dotnet/sdk), [dotnet/rosyln](https://github.com/dotnet/roslyn), or [aspnetcore](https://github.com/dotnet/aspnetcore).</span></span> <span data-ttu-id="ed13d-127">Дополнительные сведения см. в статье [Репозитории .NET Core](https://github.com/dotnet/core/blob/master/Documentation/core-repos.md).</span><span class="sxs-lookup"><span data-stu-id="ed13d-127">For more information, see [.NET Core repos](https://github.com/dotnet/core/blob/master/Documentation/core-repos.md).</span></span>

## <a name="support"></a><span data-ttu-id="ed13d-128">Поддержка</span><span class="sxs-lookup"><span data-stu-id="ed13d-128">Support</span></span>

<span data-ttu-id="ed13d-129">Корпорация Майкрософт обеспечивает поддержку .NET Core в Windows, macOS, Linux, а компания Red Hat — в Red Hat Enterprise Linux.</span><span class="sxs-lookup"><span data-stu-id="ed13d-129">.NET Core is supported by Microsoft on Windows, macOS, and Linux and by Red Hat on Red Hat Enterprise Linux.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ed13d-130">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="ed13d-130">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ed13d-131">Учебники по .NET Core</span><span class="sxs-lookup"><span data-stu-id="ed13d-131">.NET Core tutorials</span></span>](tutorials/index.md)

> [!div class="nextstepaction"]
> [<span data-ttu-id="ed13d-132">Работа с .NET Core в браузере</span><span class="sxs-lookup"><span data-stu-id="ed13d-132">Try .NET Core in your browser</span></span>](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml)
