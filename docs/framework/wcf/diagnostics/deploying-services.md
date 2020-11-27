---
title: Развертывание служб
ms.date: 03/30/2017
ms.assetid: ac361bfb-017d-4da9-a2d7-fc0fb72d65bb
ms.openlocfilehash: 07bd2a3938f238336dc00fa2e0826a28a9363a4a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294811"
---
# <a name="deploying-services"></a><span data-ttu-id="5edf8-102">Развертывание служб</span><span class="sxs-lookup"><span data-stu-id="5edf8-102">Deploying Services</span></span>

<span data-ttu-id="5edf8-103">В этом разделе описывается, как можно развернуть приложение Windows Communication Foundation (WCF) в среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="5edf8-103">This topic describes how you can deploy a Windows Communication Foundation (WCF) application to a run-time environment.</span></span>  
  
## <a name="choosing-the-hosting-environment-for-your-application"></a><span data-ttu-id="5edf8-104">Выбор среды размещения для приложения</span><span class="sxs-lookup"><span data-stu-id="5edf8-104">Choosing the Hosting Environment for Your Application</span></span>  

 <span data-ttu-id="5edf8-105">Службы WCF предназначены для работы в любом процессе Windows, который поддерживает управляемый код.</span><span class="sxs-lookup"><span data-stu-id="5edf8-105">WCF services are designed to run in any Windows process that supports managed code.</span></span> <span data-ttu-id="5edf8-106">Для активации службы ее необходимо разместить в среде выполнения, которая создает эту службу и управляет ее контекстом и временем существования.</span><span class="sxs-lookup"><span data-stu-id="5edf8-106">To become active, a service must be hosted within a run-time environment that creates it and controls its context and lifetime.</span></span> <span data-ttu-id="5edf8-107">Варианты размещения могут быть самыми различными - от выполнения внутри простейшего консольного приложения до работы в серверных средах (таких как службы Windows, службы IIS) или внутри рабочего процесса, управляемого службой активации Windows (WAS).</span><span class="sxs-lookup"><span data-stu-id="5edf8-107">Hosting options range from running inside the simplest console application to server environments like a Windows service, Internet Information Services (IIS), or within a worker process managed by the Windows Activation Service (WAS).</span></span> <span data-ttu-id="5edf8-108">Чтобы просмотреть различные варианты размещения для приложения WCF, см. раздел [службы хостинга](../hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="5edf8-108">To review the different hosting options for your WCF application, see [Hosting Services](../hosting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5edf8-109">См. также</span><span class="sxs-lookup"><span data-stu-id="5edf8-109">See also</span></span>

- [<span data-ttu-id="5edf8-110">Размещение</span><span class="sxs-lookup"><span data-stu-id="5edf8-110">Hosting</span></span>](../feature-details/hosting.md)
- [<span data-ttu-id="5edf8-111">Размещение служб</span><span class="sxs-lookup"><span data-stu-id="5edf8-111">Hosting Services</span></span>](../hosting-services.md)
