---
title: Службы рабочего процесса
ms.date: 03/30/2017
ms.assetid: 7b05c766-f181-425d-9a3d-2a5e150c85f7
ms.openlocfilehash: c7a5c6245702497fcd75341b3ff7ba08dc190fa5
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600131"
---
# <a name="workflow-services"></a><span data-ttu-id="1c2ad-102">Службы рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="1c2ad-102">Workflow Services</span></span>
[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] <span data-ttu-id="1c2ad-103">позволяет описать службу на основе рабочего процесса полностью декларативно на языке XAML.</span><span class="sxs-lookup"><span data-stu-id="1c2ad-103">allows you to fully describe a workflow-based service declaratively in XAML.</span></span> <span data-ttu-id="1c2ad-104">Рабочий процесс, реализующий службу, и описание конечных точек, предоставляемых службой, можно полностью определить на языке XAML.</span><span class="sxs-lookup"><span data-stu-id="1c2ad-104">You can define a workflow that implements your service and describe endpoints the service exposes, all entirely in XAML.</span></span> <span data-ttu-id="1c2ad-105">Подразделы, содержащиеся в этом разделе, подробно описывают модель программирования, декларативную поддержку создания служб.</span><span class="sxs-lookup"><span data-stu-id="1c2ad-105">The topics in this section describe, in detail, the programming model that supports writing services declaratively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1c2ad-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="1c2ad-106">In This Section</span></span>  
 [<span data-ttu-id="1c2ad-107">Общие сведения о службах рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="1c2ad-107">Workflow Services Overview</span></span>](workflow-services-overview.md)  
 <span data-ttu-id="1c2ad-108">Описывает компоненты, участвующие в создании и размещении службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="1c2ad-108">Describes the components involved in creating and hosting a workflow service.</span></span>  
  
 [<span data-ttu-id="1c2ad-109">Действия обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="1c2ad-109">Messaging Activities</span></span>](messaging-activities.md)  
 <span data-ttu-id="1c2ad-110">Описывает действия, которые позволяют рабочим потокам отправлять или получать сообщения.</span><span class="sxs-lookup"><span data-stu-id="1c2ad-110">Discusses activities that allow workflows to send and receive messages.</span></span>  
  
 [<span data-ttu-id="1c2ad-111">Практическое руководство. Как создать службу рабочего процесса с помощью действий обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="1c2ad-111">How to: Create a Workflow Service with Messaging Activities</span></span>](how-to-create-a-workflow-service-with-messaging-activities.md)  
 <span data-ttu-id="1c2ad-112">Описывает, как использовать действия обмена сообщениями для создания службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="1c2ad-112">Describes how to use messaging activities to create a workflow service.</span></span>  
  
 [<span data-ttu-id="1c2ad-113">Как выполнить: Получить доступ к службе из приложения рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="1c2ad-113">How To: Access a Service From a Workflow Application</span></span>](how-to-access-a-service-from-a-workflow-application.md)  
 <span data-ttu-id="1c2ad-114">Описывает, как вызвать службу из приложения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="1c2ad-114">Discusses how to call a service from a workflow application.</span></span>  
  
 [<span data-ttu-id="1c2ad-115">Correlation</span><span class="sxs-lookup"><span data-stu-id="1c2ad-115">Correlation</span></span>](correlation.md)  
 <span data-ttu-id="1c2ad-116">Описывает, как корреляция сопоставляет сообщения друг с другом и с экземплярами.</span><span class="sxs-lookup"><span data-stu-id="1c2ad-116">Discusses how correlation maps messages to each other and to instances.</span></span>  
  
 [<span data-ttu-id="1c2ad-117">Обработка неупорядоченных сообщений</span><span class="sxs-lookup"><span data-stu-id="1c2ad-117">Out-of-Order Message Processing</span></span>](out-of-order-message-processing.md)  
 <span data-ttu-id="1c2ad-118">Описывает, как настроить службу для принятия несогласованных сообщений.</span><span class="sxs-lookup"><span data-stu-id="1c2ad-118">Describes configuring a service to accept out of order messages.</span></span>  
  
 [<span data-ttu-id="1c2ad-119">Разработка службы рабочих процессов на основе контракта</span><span class="sxs-lookup"><span data-stu-id="1c2ad-119">Contract First Workflow Service Development</span></span>](../../windows-workflow-foundation/contract-first-workflow-service-development.md)  
 <span data-ttu-id="1c2ad-120">Описывает создание службы рабочих процессов на основе существующего контракта службы.</span><span class="sxs-lookup"><span data-stu-id="1c2ad-120">Describes creating a workflow service based on an existing service contract.</span></span>  
  
 [<span data-ttu-id="1c2ad-121">Практическое руководство. Создание службы рабочих процессов, использующей существующий контракт службы</span><span class="sxs-lookup"><span data-stu-id="1c2ad-121">How to: Create a workflow service that consumes an existing service contract</span></span>](../../windows-workflow-foundation/how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)  
 <span data-ttu-id="1c2ad-122">Предоставляет подробный пример создания службы рабочих процессов на основе существующего контракта.</span><span class="sxs-lookup"><span data-stu-id="1c2ad-122">Provides a step-by-step example of creating a workflow service using an existing service contract.</span></span>  
  
 [<span data-ttu-id="1c2ad-123">Общие сведения о размещении служб рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="1c2ad-123">Hosting Workflow Services Overview</span></span>](hosting-workflow-services-overview.md)  
 <span data-ttu-id="1c2ad-124">Описывает различные аспекты размещения службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="1c2ad-124">Describes the different aspects of hosting a workflow service.</span></span>  
  
 [<span data-ttu-id="1c2ad-125">Использование контрактов в рабочих процессах</span><span class="sxs-lookup"><span data-stu-id="1c2ad-125">Using Contracts in Workflow</span></span>](using-contracts-in-workflow.md)  
 <span data-ttu-id="1c2ad-126">Описывает различные типы контрактов и вывод контракта.</span><span class="sxs-lookup"><span data-stu-id="1c2ad-126">Describes the different types of contracts and contract inference.</span></span>
