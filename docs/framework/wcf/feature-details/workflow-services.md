---
title: Службы рабочего процесса
ms.date: 03/30/2017
ms.assetid: 7b05c766-f181-425d-9a3d-2a5e150c85f7
ms.openlocfilehash: ff73055d41531ef8188681d0b95748f62fde8011
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263247"
---
# <a name="workflow-services"></a><span data-ttu-id="af299-102">Службы рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="af299-102">Workflow Services</span></span>

[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] <span data-ttu-id="af299-103">позволяет описать службу на основе рабочего процесса полностью декларативно на языке XAML.</span><span class="sxs-lookup"><span data-stu-id="af299-103">allows you to fully describe a workflow-based service declaratively in XAML.</span></span> <span data-ttu-id="af299-104">Рабочий процесс, реализующий службу, и описание конечных точек, предоставляемых службой, можно полностью определить на языке XAML.</span><span class="sxs-lookup"><span data-stu-id="af299-104">You can define a workflow that implements your service and describe endpoints the service exposes, all entirely in XAML.</span></span> <span data-ttu-id="af299-105">Подразделы, содержащиеся в этом разделе, подробно описывают модель программирования, декларативную поддержку создания служб.</span><span class="sxs-lookup"><span data-stu-id="af299-105">The topics in this section describe, in detail, the programming model that supports writing services declaratively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="af299-106">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="af299-106">In This Section</span></span>  

 [<span data-ttu-id="af299-107">Общие сведения о службах рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="af299-107">Workflow Services Overview</span></span>](workflow-services-overview.md)  
 <span data-ttu-id="af299-108">Описывает компоненты, участвующие в создании и размещении службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="af299-108">Describes the components involved in creating and hosting a workflow service.</span></span>  
  
 [<span data-ttu-id="af299-109">Действия обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="af299-109">Messaging Activities</span></span>](messaging-activities.md)  
 <span data-ttu-id="af299-110">Описывает действия, которые позволяют рабочим потокам отправлять или получать сообщения.</span><span class="sxs-lookup"><span data-stu-id="af299-110">Discusses activities that allow workflows to send and receive messages.</span></span>  
  
 [<span data-ttu-id="af299-111">Практическое руководство. Как создать службу рабочего процесса с помощью действий обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="af299-111">How to: Create a Workflow Service with Messaging Activities</span></span>](how-to-create-a-workflow-service-with-messaging-activities.md)  
 <span data-ttu-id="af299-112">Описывает, как использовать действия обмена сообщениями для создания службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="af299-112">Describes how to use messaging activities to create a workflow service.</span></span>  
  
 [<span data-ttu-id="af299-113">Как выполнить: Получить доступ к службе из приложения рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="af299-113">How To: Access a Service From a Workflow Application</span></span>](how-to-access-a-service-from-a-workflow-application.md)  
 <span data-ttu-id="af299-114">Описывает, как вызвать службу из приложения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="af299-114">Discusses how to call a service from a workflow application.</span></span>  
  
 <span data-ttu-id="af299-115">[Correlation](correlation.md) (корреляция).</span><span class="sxs-lookup"><span data-stu-id="af299-115">[Correlation](correlation.md)</span></span>  
 <span data-ttu-id="af299-116">Описывает, как корреляция сопоставляет сообщения друг с другом и с экземплярами.</span><span class="sxs-lookup"><span data-stu-id="af299-116">Discusses how correlation maps messages to each other and to instances.</span></span>  
  
 [<span data-ttu-id="af299-117">Обработка неупорядоченных сообщений</span><span class="sxs-lookup"><span data-stu-id="af299-117">Out-of-Order Message Processing</span></span>](out-of-order-message-processing.md)  
 <span data-ttu-id="af299-118">Описывает, как настроить службу для принятия несогласованных сообщений.</span><span class="sxs-lookup"><span data-stu-id="af299-118">Describes configuring a service to accept out of order messages.</span></span>  
  
 [<span data-ttu-id="af299-119">Разработка службы рабочих процессов на основе контракта</span><span class="sxs-lookup"><span data-stu-id="af299-119">Contract First Workflow Service Development</span></span>](../../windows-workflow-foundation/contract-first-workflow-service-development.md)  
 <span data-ttu-id="af299-120">Описывает создание службы рабочих процессов на основе существующего контракта службы.</span><span class="sxs-lookup"><span data-stu-id="af299-120">Describes creating a workflow service based on an existing service contract.</span></span>  
  
 [<span data-ttu-id="af299-121">Практическое руководство. Создание службы рабочих процессов, использующей существующий контракт службы</span><span class="sxs-lookup"><span data-stu-id="af299-121">How to: Create a workflow service that consumes an existing service contract</span></span>](../../windows-workflow-foundation/how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)  
 <span data-ttu-id="af299-122">Предоставляет подробный пример создания службы рабочих процессов на основе существующего контракта.</span><span class="sxs-lookup"><span data-stu-id="af299-122">Provides a step-by-step example of creating a workflow service using an existing service contract.</span></span>  
  
 [<span data-ttu-id="af299-123">Общие сведения о размещении служб рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="af299-123">Hosting Workflow Services Overview</span></span>](hosting-workflow-services-overview.md)  
 <span data-ttu-id="af299-124">Описывает различные аспекты размещения службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="af299-124">Describes the different aspects of hosting a workflow service.</span></span>  
  
 [<span data-ttu-id="af299-125">Использование контрактов в рабочих процессах</span><span class="sxs-lookup"><span data-stu-id="af299-125">Using Contracts in Workflow</span></span>](using-contracts-in-workflow.md)  
 <span data-ttu-id="af299-126">Описывает различные типы контрактов и вывод контракта.</span><span class="sxs-lookup"><span data-stu-id="af299-126">Describes the different types of contracts and contract inference.</span></span>
