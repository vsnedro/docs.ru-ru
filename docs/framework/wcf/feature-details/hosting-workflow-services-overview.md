---
title: Общие сведения о размещении служб рабочих процессов
ms.date: 03/30/2017
ms.assetid: 19f3704f-06bf-4eeb-8724-5224e02d7ead
ms.openlocfilehash: 150cb98ab3cef8231489219a16709344cbd19bd5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242972"
---
# <a name="hosting-workflow-services-overview"></a><span data-ttu-id="18ad4-102">Общие сведения о размещении служб рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="18ad4-102">Hosting Workflow Services Overview</span></span>

<span data-ttu-id="18ad4-103">Для выполнения служб рабочего процесса они должны быть размещены.</span><span class="sxs-lookup"><span data-stu-id="18ad4-103">Workflow services must be hosted to execute.</span></span> <span data-ttu-id="18ad4-104">Класс <xref:System.ServiceModel.WorkflowServiceHost> представляет собой готовый узел размещения рабочих процессов, поддерживающий использование нескольких экземпляров, настройку и обмен сообщениями WCF (хотя от размещаемых рабочих процессов и не требуется обмена сообщениями).</span><span class="sxs-lookup"><span data-stu-id="18ad4-104">The <xref:System.ServiceModel.WorkflowServiceHost> is the out-of-the-box workflow host that supports multiple instances, configuration, and WCF messaging (although the workflows aren’t required to use messaging in order to be hosted).</span></span>  <span data-ttu-id="18ad4-105">Он также реализует сохраняемость, отслеживание и контроль за экземплярами через набор поведений службы.</span><span class="sxs-lookup"><span data-stu-id="18ad4-105">It also integrates with persistence, tracking, and instance control through a set of service behaviors.</span></span>  <span data-ttu-id="18ad4-106">Как и класс WCF <xref:System.ServiceModel.ServiceHost>, класс <xref:System.ServiceModel.WorkflowServiceHost> может быть резидентным в любом управляемом приложении .NET или размещаться на веб-сервере IIS / WAS (в виде файла XAMLX).</span><span class="sxs-lookup"><span data-stu-id="18ad4-106">Just like WCF’s <xref:System.ServiceModel.ServiceHost>, the <xref:System.ServiceModel.WorkflowServiceHost> can be self-hosted in any managed .NET application, or web-hosted (as a .xamlx file) in IIS / WAS.</span></span>  <span data-ttu-id="18ad4-107">В этом разделе описано размещение службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="18ad4-107">Topics in this section describe how to host a workflow service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="18ad4-108">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="18ad4-108">In This Section</span></span>  

 [<span data-ttu-id="18ad4-109">Размещение службы рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="18ad4-109">Hosting Workflow Services</span></span>](hosting-workflow-services.md)  
 <span data-ttu-id="18ad4-110">Описывает размещение служб рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="18ad4-110">Describes hosting workflow services.</span></span>  
  
 [<span data-ttu-id="18ad4-111">Внутренние особенности размещения службы рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="18ad4-111">Workflow Service Host Internals</span></span>](workflow-service-host-internals.md)  
 <span data-ttu-id="18ad4-112">Описывает, как объект <xref:System.ServiceModel.WorkflowServiceHost> обрабатывает входящие сообщения.</span><span class="sxs-lookup"><span data-stu-id="18ad4-112">Describes how <xref:System.ServiceModel.WorkflowServiceHost> processes incoming messages.</span></span>  
  
 [<span data-ttu-id="18ad4-113">Расширяемость узла службы рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="18ad4-113">Workflow Service Host Extensibility</span></span>](workflow-service-host-extensibility.md)  
 <span data-ttu-id="18ad4-114">Описывает способы расширения функциональности узла службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="18ad4-114">Describes how to extend the functionality of the workflow service host.</span></span>  
  
 [<span data-ttu-id="18ad4-115">Конечная точка элемента управления рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="18ad4-115">Workflow Control Endpoint</span></span>](workflow-control-endpoint.md)  
 <span data-ttu-id="18ad4-116">Описывает, как определить конечную точку, позволяющую создавать экземпляры рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="18ad4-116">Describes how to define an endpoint that allows you to create workflow instances.</span></span>
  
 [<span data-ttu-id="18ad4-117">Практическое руководство. Как разместить службу рабочего процесса с помощью Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="18ad4-117">How to: Host a Workflow Service with Windows Server App Fabric</span></span>](how-to-host-a-workflow-service-with-windows-server-app-fabric.md)  
 <span data-ttu-id="18ad4-118">Демонстрирует размещение существующей службы рабочего процесса в фабрике приложений Windows Server.</span><span class="sxs-lookup"><span data-stu-id="18ad4-118">Demonstrates how to host an existing workflow service in Windows Server App Fabric.</span></span>  
  
 [<span data-ttu-id="18ad4-119">Настройка WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="18ad4-119">Configuring WorkflowServiceHost</span></span>](configuring-workflowservicehost.md)  
 <span data-ttu-id="18ad4-120">Описывает управление сохраняемостью, отслеживанием, простоем и поведением необработанных исключений.</span><span class="sxs-lookup"><span data-stu-id="18ad4-120">Describes how to control persistence, tracking, idle, and unhandled exception behavior.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="18ad4-121">Справочник</span><span class="sxs-lookup"><span data-stu-id="18ad4-121">Reference</span></span>  

 <xref:System.ServiceModel.Activities.WorkflowServiceHost>  
  
 <xref:System.ServiceModel.Activities.WorkflowService>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactory>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactoryBase>  
  
 <xref:System.ServiceModel.Activation.WorkflowServiceHostFactory>  
  
## <a name="related-sections"></a><span data-ttu-id="18ad4-122">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="18ad4-122">Related Sections</span></span>  

 [<span data-ttu-id="18ad4-123">Службы рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="18ad4-123">Workflow Services</span></span>](workflow-services.md)
