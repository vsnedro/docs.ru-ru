---
title: Жизненный цикл контейнерного приложения Docker на основе платформы и средств Майкрософт
description: Общий обзор процесса разработки и развертывания контейнерных приложений с помощью Docker, а также платформы и средств Microsoft.
ms.date: 07/30/2020
ms.openlocfilehash: d8055315b25f73d7b0b355026ab6b2c4767f9d89
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2020
ms.locfileid: "87915152"
---
# <a name="containerized-docker-application-lifecycle-with-microsoft-platform-and-tools"></a><span data-ttu-id="40af4-103">Жизненный цикл контейнерного приложения Docker на основе платформы и средств Майкрософт</span><span class="sxs-lookup"><span data-stu-id="40af4-103">Containerized Docker Application Lifecycle with Microsoft Platform and Tools</span></span>

![Обложка книги](./media/devops-book-cover-large-we.png)

<span data-ttu-id="40af4-105">**ВЫПУСК 3.1** — обновлен до ASP.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="40af4-105">**EDITION v3.1** - Updated to ASP.NET Core 3.1</span></span>

<span data-ttu-id="40af4-106">В этом руководстве приводится общее описание процесса разработки и развертывания контейнерных приложений ASP.NET Core с помощью Docker с использованием платформы и средств Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="40af4-106">This guide is a general overview for developing and deploying containerized ASP.NET Core applications with Docker, using the Microsoft platform and tools.</span></span> <span data-ttu-id="40af4-107">В этом руководстве представлено общее описание Azure DevOps для реализации конвейеров CI/CD, а также реестра контейнеров Azure (ACR) и Службы Azure Kubernetes (AKS) для развертывания.</span><span class="sxs-lookup"><span data-stu-id="40af4-107">The guide includes a high-level introduction to Azure DevOps, for implementing CI/CD pipelines, as well as Azure Container Registry (ACR), and Azure Kubernetes Services AKS for deployment.</span></span>

<span data-ttu-id="40af4-108">Подробные сведения о разработке см. в руководстве [Микрослужбы .NET: архитектура для контейнерных приложений .NET](https://docs.microsoft.com/dotnet/architecture/microservices/) и связанном с ним примере приложения [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers).</span><span class="sxs-lookup"><span data-stu-id="40af4-108">For low-level, development-related details you can see the [.NET Microservices: Architecture for Containerized .NET Applications](https://docs.microsoft.com/dotnet/architecture/microservices/) guide and it related reference application [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers).</span></span>

## <a name="send-us-your-feedback"></a><span data-ttu-id="40af4-109">Отправьте нам свой отзыв.</span><span class="sxs-lookup"><span data-stu-id="40af4-109">Send us your feedback!</span></span>

<span data-ttu-id="40af4-110">Мы создали это руководство, чтобы помочь вам разобраться в архитектуре контейнерных приложений и микрослужб в .NET.</span><span class="sxs-lookup"><span data-stu-id="40af4-110">We wrote this guide to help you understand the architecture of containerized applications and microservices in .NET.</span></span> <span data-ttu-id="40af4-111">Руководство и связанный с ним пример приложения будут развиваться, поэтому мы будем рады вашим отзывам!</span><span class="sxs-lookup"><span data-stu-id="40af4-111">The guide and related reference application will be evolving, so we welcome your feedback!</span></span> <span data-ttu-id="40af4-112">Если у вас есть замечания касательно того, как можно улучшить это руководство, направляйте ваши отзывы по адресу <https://aka.ms/ebookfeedback>.</span><span class="sxs-lookup"><span data-stu-id="40af4-112">If you have comments about how this guide can be improved, submit feedback at <https://aka.ms/ebookfeedback>.</span></span>

## <a name="credits"></a><span data-ttu-id="40af4-113">Благодарности</span><span class="sxs-lookup"><span data-stu-id="40af4-113">Credits</span></span>

<span data-ttu-id="40af4-114">Автор:</span><span class="sxs-lookup"><span data-stu-id="40af4-114">Author:</span></span>

> <span data-ttu-id="40af4-115">**Сезар де ла Торре (Cesar de la Torre)** , старший руководитель проекта, команда разработки .NET, корпорация Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="40af4-115">**Cesar de la Torre**, Sr. PM, .NET product team, Microsoft Corp.</span></span>

<span data-ttu-id="40af4-116">Редактор по приобретениям:</span><span class="sxs-lookup"><span data-stu-id="40af4-116">Acquisitions Editor:</span></span>

> <span data-ttu-id="40af4-117">**Джанин Патрик (Janine Patrick)**</span><span class="sxs-lookup"><span data-stu-id="40af4-117">**Janine Patrick**</span></span>

<span data-ttu-id="40af4-118">Редактор по разработкам:</span><span class="sxs-lookup"><span data-stu-id="40af4-118">Developmental Editor:</span></span>

> <span data-ttu-id="40af4-119">**Боб Рассел (Bob Russell)** , специалист по решениям в корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="40af4-119">**Bob Russell**, Solutions Professional at Microsoft</span></span>
>
> [<span data-ttu-id="40af4-120">**Octal Publishing, Inc.** </span><span class="sxs-lookup"><span data-stu-id="40af4-120">**Octal Publishing, Inc.**</span></span>](http://www.octalpub.com/)

<span data-ttu-id="40af4-121">Редакционная колонка:</span><span class="sxs-lookup"><span data-stu-id="40af4-121">Editorial Production:</span></span>

> [<span data-ttu-id="40af4-122">Дайэнн Рассел (Dianne Russell)</span><span class="sxs-lookup"><span data-stu-id="40af4-122">Dianne Russell</span></span>](http://www.octalpub.com/)
>
> <span data-ttu-id="40af4-123">**Octal Publishing, Inc.**</span><span class="sxs-lookup"><span data-stu-id="40af4-123">**Octal Publishing, Inc.**</span></span>

<span data-ttu-id="40af4-124">Выпускающий редактор:</span><span class="sxs-lookup"><span data-stu-id="40af4-124">Copyeditor:</span></span>

> <span data-ttu-id="40af4-125">**Боб Рассел (Bob Russell)** , специалист по решениям в корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="40af4-125">**Bob Russell**, Solutions Professional at Microsoft</span></span>

<span data-ttu-id="40af4-126">Участники и рецензенты:</span><span class="sxs-lookup"><span data-stu-id="40af4-126">Participants and reviewers:</span></span>

> <span data-ttu-id="40af4-127">**Ниш Анил (Nish Anil)** , старший менеджер программ, команда .NET, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="40af4-127">**Nish Anil**, Sr. Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="40af4-128">**Мигель Велосо** (Miguel Veloso), инженер по разработке программного обеспечения в Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="40af4-128">**Miguel Veloso**, Software Development Engineer at Plain Concepts</span></span>
>
> <span data-ttu-id="40af4-129">**Самит Гош (Sumit Ghosh)** , главный консультант в Neudesic</span><span class="sxs-lookup"><span data-stu-id="40af4-129">**Sumit Ghosh**, Principal Consultant at Neudesic</span></span>

## <a name="copyright"></a><span data-ttu-id="40af4-130">Copyright</span><span class="sxs-lookup"><span data-stu-id="40af4-130">Copyright</span></span>

<span data-ttu-id="40af4-131">ИЗДАТЕЛЬ</span><span class="sxs-lookup"><span data-stu-id="40af4-131">PUBLISHED BY</span></span>

<span data-ttu-id="40af4-132">Подразделение Microsoft Developer Division, команды разработки .NET и Visual Studio</span><span class="sxs-lookup"><span data-stu-id="40af4-132">Microsoft Developer Division, .NET and Visual Studio product teams</span></span>

<span data-ttu-id="40af4-133">Подразделение корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="40af4-133">A division of Microsoft Corporation</span></span>

<span data-ttu-id="40af4-134">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="40af4-134">One Microsoft Way</span></span>

<span data-ttu-id="40af4-135">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="40af4-135">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="40af4-136">&copy; Корпорация Майкрософт (Microsoft Corporation), 2020.</span><span class="sxs-lookup"><span data-stu-id="40af4-136">Copyright &copy; 2020 by Microsoft Corporation</span></span>

<span data-ttu-id="40af4-137">Все права защищены.</span><span class="sxs-lookup"><span data-stu-id="40af4-137">All rights reserved.</span></span> <span data-ttu-id="40af4-138">Запрещается полное или частичное воспроизведение или передача настоящей книги в любом виде или любыми средствами без письменного разрешения издателя.</span><span class="sxs-lookup"><span data-stu-id="40af4-138">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="40af4-139">Эта книга предоставляется на условиях "как есть" и выражает взгляды и мнения автора.</span><span class="sxs-lookup"><span data-stu-id="40af4-139">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="40af4-140">Взгляды, мнения и сведения, содержащиеся в этой книге, включая URL-адреса и другие ссылки на веб-сайты, могут изменяться без уведомления.</span><span class="sxs-lookup"><span data-stu-id="40af4-140">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="40af4-141">Некоторые приведенные в книге примеры служат только для иллюстрации и являются вымышленными.</span><span class="sxs-lookup"><span data-stu-id="40af4-141">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="40af4-142">Все совпадения с реальными наименованиями, людьми и любыми другими предметами являются непреднамеренными и случайными.</span><span class="sxs-lookup"><span data-stu-id="40af4-142">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="40af4-143">Microsoft и товарные знаки, перечисленные на странице "Товарные знаки" на сайте <https://www.microsoft.com>, являются товарными знаками группы компаний Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="40af4-143">Microsoft and the trademarks listed at <https://www.microsoft.com> on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="40af4-144">Mac и macOS являются товарными знаками Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="40af4-144">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="40af4-145">Логотип Docker с изображением кита является зарегистрированным товарным знаком Docker, Inc. Используется с разрешения.</span><span class="sxs-lookup"><span data-stu-id="40af4-145">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="40af4-146">Все другие наименования и логотипы являются собственностью своих законных владельцев.</span><span class="sxs-lookup"><span data-stu-id="40af4-146">All other marks and logos are property of their respective owners.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="40af4-147">Вперед</span><span class="sxs-lookup"><span data-stu-id="40af4-147">Next</span></span>](introduction-to-containers-and-docker.md)
