---
title: Учебник. Начало работы с Windows Communication Foundation приложениями
description: В этих руководствах содержатся общие сведения о создании приложений WCF.
ms.date: 01/25/2019
helpviewer_keywords:
- WCF [WCF], get started
- Windows Communication Foundation [WCF], get started
- get started [WCF]
ms.assetid: df939177-73cb-4440-bd95-092a421516a1
ms.openlocfilehash: 620a83260f01e27a19b19227165695a621c88e5e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238240"
---
# <a name="tutorial-get-started-with-windows-communication-foundation-applications"></a><span data-ttu-id="0ebc0-103">Учебник. Начало работы с Windows Communication Foundation приложениями</span><span class="sxs-lookup"><span data-stu-id="0ebc0-103">Tutorial: Get started with Windows Communication Foundation applications</span></span>

<span data-ttu-id="0ebc0-104">В приведенной ниже серии руководств представлены инструкции по программированию Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="0ebc0-104">The following series of tutorials introduce you to the Windows Communication Foundation (WCF) programming experience.</span></span> <span data-ttu-id="0ebc0-105">При работе с этими учебниками вы получите вводные сведения о шагах, необходимых для создания приложений WCF.</span><span class="sxs-lookup"><span data-stu-id="0ebc0-105">Working through these tutorials in order will give you an introductory understanding of the steps required to create WCF applications.</span></span> <span data-ttu-id="0ebc0-106">После завершения работы у вас будет работающая служба WCF и клиент WCF, который вызывает службу.</span><span class="sxs-lookup"><span data-stu-id="0ebc0-106">After you finish, you'll have a running WCF service and a WCF client that calls the service.</span></span>

<span data-ttu-id="0ebc0-107">В учебнике предполагается, что вы используете Visual Studio в качестве среды разработки.</span><span class="sxs-lookup"><span data-stu-id="0ebc0-107">The tutorial assumes you're using Visual Studio as the development environment.</span></span> <span data-ttu-id="0ebc0-108">Если вы используете другую среду разработки, пропустите инструкции, относящиеся к Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0ebc0-108">If you're using another development environment, ignore the Visual Studio-specific instructions.</span></span>

<span data-ttu-id="0ebc0-109">Примеры приложений WCF, которые можно скачать и запустить, см. в разделе [Windows Communication Foundation Samples](samples/index.md).</span><span class="sxs-lookup"><span data-stu-id="0ebc0-109">For sample WCF applications that you can download and run, see [Windows Communication Foundation samples](samples/index.md).</span></span> <span data-ttu-id="0ebc0-110">Общие сведения о примерах см. в статье [Приступая к работе](samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="0ebc0-110">For an introduction to the samples, see [Getting started sample](samples/getting-started-sample.md).</span></span>

<span data-ttu-id="0ebc0-111">Более подробные сведения о создании служб и клиентов см. в разделе [Базовая программирование WCF](basic-wcf-programming.md).</span><span class="sxs-lookup"><span data-stu-id="0ebc0-111">For more in-depth information about creating services and clients, see [Basic WCF programming](basic-wcf-programming.md).</span></span>

## <a name="wcf-tutorials"></a><span data-ttu-id="0ebc0-112">Учебники по WCF</span><span class="sxs-lookup"><span data-stu-id="0ebc0-112">WCF tutorials</span></span>

<span data-ttu-id="0ebc0-113">В первых трех руководствах описывается, как определить контракт службы WCF, как его реализовать и как разместить его.</span><span class="sxs-lookup"><span data-stu-id="0ebc0-113">The first three tutorials describe how to define a WCF service contract, how to implement it, and how to host it.</span></span> <span data-ttu-id="0ebc0-114">Создаваемая служба является саморазмещенной в консольном приложении.</span><span class="sxs-lookup"><span data-stu-id="0ebc0-114">The service that you create is self-hosted within a console application.</span></span> <span data-ttu-id="0ebc0-115">Службы также можно размещать в Microsoft службы IIS (IIS).</span><span class="sxs-lookup"><span data-stu-id="0ebc0-115">You can also host services under Microsoft Internet Information Services (IIS).</span></span> <span data-ttu-id="0ebc0-116">Дополнительные сведения см. в разделе [инструкции. размещение службы WCF в IIS](feature-details/how-to-host-a-wcf-service-in-iis.md).</span><span class="sxs-lookup"><span data-stu-id="0ebc0-116">For more information, see [How to: Host a WCF Service in IIS](feature-details/how-to-host-a-wcf-service-in-iis.md).</span></span> <span data-ttu-id="0ebc0-117">Хотя для настройки службы в этом учебнике используется код, можно также [настроить службы в файле конфигурации](configuring-services-using-configuration-files.md).</span><span class="sxs-lookup"><span data-stu-id="0ebc0-117">Although you use code to configure the service in the tutorial, you can also [configure services within a configuration file](configuring-services-using-configuration-files.md).</span></span>

- [<span data-ttu-id="0ebc0-118">Учебник. определение контракта службы</span><span class="sxs-lookup"><span data-stu-id="0ebc0-118">Tutorial: Define a service contract</span></span>](how-to-define-a-wcf-service-contract.md)

    <span data-ttu-id="0ebc0-119">Вы создаете контракт WCF с определяемым пользователем интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="0ebc0-119">You create a WCF contract with a user-defined interface.</span></span> <span data-ttu-id="0ebc0-120">Этот контракт определяет функциональные возможности, предоставляемые службой.</span><span class="sxs-lookup"><span data-stu-id="0ebc0-120">This contract defines the functionality that the service exposes.</span></span>

- [<span data-ttu-id="0ebc0-121">Учебник. Реализация контракта службы</span><span class="sxs-lookup"><span data-stu-id="0ebc0-121">Tutorial: Implement a service contract</span></span>](how-to-implement-a-wcf-contract.md)

    <span data-ttu-id="0ebc0-122">После определения контракта его необходимо реализовать с помощью класса службы.</span><span class="sxs-lookup"><span data-stu-id="0ebc0-122">After you define a contract, you must implement it with a service class.</span></span>

- [<span data-ttu-id="0ebc0-123">Учебник. размещение и запуск базовой службы</span><span class="sxs-lookup"><span data-stu-id="0ebc0-123">Tutorial: Host and run a basic service</span></span>](how-to-host-and-run-a-basic-wcf-service.md)

    <span data-ttu-id="0ebc0-124">Настройте конечную точку для службы и разместите ее в консольном приложении.</span><span class="sxs-lookup"><span data-stu-id="0ebc0-124">Configure an endpoint for the service and host the service in a console application.</span></span> <span data-ttu-id="0ebc0-125">Чтобы служба стала активной, ее необходимо настроить и разместить в среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="0ebc0-125">For a service to become active, you must configure it and host it within a run-time environment.</span></span> <span data-ttu-id="0ebc0-126">Эта среда времени выполнения создает службу и управляет ее контекстом и временем существования.</span><span class="sxs-lookup"><span data-stu-id="0ebc0-126">This run-time environment creates the service and controls its context and lifetime.</span></span>

<span data-ttu-id="0ebc0-127">В следующих двух учебниках описывается создание, Настройка и использование клиентского приложения для вызова операций, предоставляемых службой.</span><span class="sxs-lookup"><span data-stu-id="0ebc0-127">The next two tutorials describe how to create, configure, and use a client application to call the operations the service exposes.</span></span> <span data-ttu-id="0ebc0-128">Службы публикуют доступные метаданные, определяющие сведения, необходимые клиентским приложениям для взаимодействия со службой.</span><span class="sxs-lookup"><span data-stu-id="0ebc0-128">Services publish metadata that define the information a client application needs to communicate with the service.</span></span> <span data-ttu-id="0ebc0-129">Visual Studio автоматизирует процесс доступа к этим метаданным и использует его для создания клиентского приложения для службы.</span><span class="sxs-lookup"><span data-stu-id="0ebc0-129">Visual Studio automates the process of accessing this metadata and uses it to construct the client application for the service.</span></span> <span data-ttu-id="0ebc0-130">Если вы решили не использовать Visual Studio, вместо этого можно использовать [средство служебной программы метаданных ServiceModel (*Svcutil.exe*)](servicemodel-metadata-utility-tool-svcutil-exe.md) .</span><span class="sxs-lookup"><span data-stu-id="0ebc0-130">If you decide not to use Visual Studio, you can use the [ServiceModel Metadata Utility tool (*Svcutil.exe*)](servicemodel-metadata-utility-tool-svcutil-exe.md) instead.</span></span>

- [<span data-ttu-id="0ebc0-131">Учебник. Создание клиента</span><span class="sxs-lookup"><span data-stu-id="0ebc0-131">Tutorial: Create a client</span></span>](how-to-create-a-wcf-client.md)

    <span data-ttu-id="0ebc0-132">Получите метаданные для создания прокси клиента WCF из службы WCF.</span><span class="sxs-lookup"><span data-stu-id="0ebc0-132">Retrieve metadata for creating a WCF client proxy from a WCF service.</span></span> <span data-ttu-id="0ebc0-133">Метаданные извлекаются с помощью Visual Studio для добавления ссылки на службу или можно использовать средство служебной программы метаданных ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="0ebc0-133">You retrieve metadata by using Visual Studio to add a service reference or you can use the ServiceModel Metadata Utility tool.</span></span> <span data-ttu-id="0ebc0-134">Укажите конечную точку, которую клиент использует для доступа к службе.</span><span class="sxs-lookup"><span data-stu-id="0ebc0-134">You specify the endpoint that the client uses to access the service.</span></span>

- [<span data-ttu-id="0ebc0-135">Учебник. Использование клиента</span><span class="sxs-lookup"><span data-stu-id="0ebc0-135">Tutorial: Use a client</span></span>](how-to-use-a-wcf-client.md)

    <span data-ttu-id="0ebc0-136">Используйте прокси клиента WCF для вызова операций службы.</span><span class="sxs-lookup"><span data-stu-id="0ebc0-136">Use the WCF client proxy to call the service operations.</span></span>

## <a name="reference"></a><span data-ttu-id="0ebc0-137">Справочник</span><span class="sxs-lookup"><span data-stu-id="0ebc0-137">Reference</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>

## <a name="see-also"></a><span data-ttu-id="0ebc0-138">См. также</span><span class="sxs-lookup"><span data-stu-id="0ebc0-138">See also</span></span>

- [<span data-ttu-id="0ebc0-139">Обзор концепции</span><span class="sxs-lookup"><span data-stu-id="0ebc0-139">Conceptual overview</span></span>](conceptual-overview.md)
- [<span data-ttu-id="0ebc0-140">Руководство по документации</span><span class="sxs-lookup"><span data-stu-id="0ebc0-140">Guide to the documentation</span></span>](guide-to-the-documentation.md)
- [<span data-ttu-id="0ebc0-141">Что такое Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="0ebc0-141">What is Windows Communication Foundation</span></span>](whats-wcf.md)
- [<span data-ttu-id="0ebc0-142">Подробные сведения о возможностях WCF</span><span class="sxs-lookup"><span data-stu-id="0ebc0-142">WCF feature details</span></span>](feature-details/index.md)
- [<span data-ttu-id="0ebc0-143">Базовый жизненный цикл программирования</span><span class="sxs-lookup"><span data-stu-id="0ebc0-143">Basic programming lifecycle</span></span>](basic-programming-lifecycle.md)
- [<span data-ttu-id="0ebc0-144">Создание клиентов</span><span class="sxs-lookup"><span data-stu-id="0ebc0-144">Building clients</span></span>](building-clients.md)
- [<span data-ttu-id="0ebc0-145">Базовое программирование WCF</span><span class="sxs-lookup"><span data-stu-id="0ebc0-145">Basic WCF programming</span></span>](basic-wcf-programming.md)
- [<span data-ttu-id="0ebc0-146">Как создать дуплексный контракт</span><span class="sxs-lookup"><span data-stu-id="0ebc0-146">How to: Create a duplex contract</span></span>](feature-details/how-to-create-a-duplex-contract.md)
- [<span data-ttu-id="0ebc0-147">Руководство. доступ к службам с помощью дуплексного контракта</span><span class="sxs-lookup"><span data-stu-id="0ebc0-147">How to: Access services with a duplex contract</span></span>](feature-details/how-to-access-services-with-a-duplex-contract.md)
- [<span data-ttu-id="0ebc0-148">Средство служебной программы метаданных ServiceModel (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="0ebc0-148">ServiceModel Metadata Utility tool (Svcutil.exe)</span></span>](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="0ebc0-149">Как использовать Svcutil.exe для скачивания документов метаданных</span><span class="sxs-lookup"><span data-stu-id="0ebc0-149">How to: Use Svcutil.exe to download metadata documents</span></span>](feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)
- [<span data-ttu-id="0ebc0-150">Инструкции. Публикация метаданных для службы с помощью файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="0ebc0-150">How to: Publish metadata for a service using a configuration file</span></span>](feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="0ebc0-151">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="0ebc0-151">Using bindings to configure services and clients</span></span>](using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="0ebc0-152">Пример Приступая к работе</span><span class="sxs-lookup"><span data-stu-id="0ebc0-152">Getting started sample</span></span>](samples/getting-started-sample.md)
- [<span data-ttu-id="0ebc0-153">Примеры Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="0ebc0-153">Windows Communication Foundation samples</span></span>](samples/index.md)
- [<span data-ttu-id="0ebc0-154">Резидентное размещение</span><span class="sxs-lookup"><span data-stu-id="0ebc0-154">Self-Host</span></span>](samples/self-host.md)
