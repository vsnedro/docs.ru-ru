---
title: 1006 - WorkflowApplicationUnhandledException
ms.date: 03/30/2017
ms.assetid: dfe0f316-e03b-47fb-b6a3-622c56bfd753
ms.openlocfilehash: 4bb76a93ec7a07a735def1f1d5dc79decb7792ad
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239839"
---
# <a name="1006---workflowapplicationunhandledexception"></a><span data-ttu-id="fc1f5-102">1006 - WorkflowApplicationUnhandledException</span><span class="sxs-lookup"><span data-stu-id="fc1f5-102">1006 - WorkflowApplicationUnhandledException</span></span>

## <a name="properties"></a><span data-ttu-id="fc1f5-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="fc1f5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fc1f5-104">ID</span><span class="sxs-lookup"><span data-stu-id="fc1f5-104">ID</span></span>|<span data-ttu-id="fc1f5-105">1006</span><span class="sxs-lookup"><span data-stu-id="fc1f5-105">1006</span></span>|  
|<span data-ttu-id="fc1f5-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="fc1f5-106">Keywords</span></span>|<span data-ttu-id="fc1f5-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="fc1f5-107">WFRuntime</span></span>|  
|<span data-ttu-id="fc1f5-108">Level</span><span class="sxs-lookup"><span data-stu-id="fc1f5-108">Level</span></span>|<span data-ttu-id="fc1f5-109">Ошибка</span><span class="sxs-lookup"><span data-stu-id="fc1f5-109">Error</span></span>|  
|<span data-ttu-id="fc1f5-110">Канал</span><span class="sxs-lookup"><span data-stu-id="fc1f5-110">Channel</span></span>|<span data-ttu-id="fc1f5-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="fc1f5-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fc1f5-112">Описание</span><span class="sxs-lookup"><span data-stu-id="fc1f5-112">Description</span></span>  

 <span data-ttu-id="fc1f5-113">Указывает, что приложение рабочего процесса обнаружило необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="fc1f5-113">Indicates a workflow application has encountered an unhandled exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fc1f5-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="fc1f5-114">Message</span></span>  

 <span data-ttu-id="fc1f5-115">Элемент WorkflowInstance с идентификатором "%1" обнаружил необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="fc1f5-115">WorkflowInstance Id: '%1' has encountered an unhandled exception.</span></span>  <span data-ttu-id="fc1f5-116">Исключение произошло из действия "%2", DisplayName: "%3".</span><span class="sxs-lookup"><span data-stu-id="fc1f5-116">The exception originated from Activity '%2', DisplayName: '%3'.</span></span>  <span data-ttu-id="fc1f5-117">Будет выполнено следующее действие: %4.</span><span class="sxs-lookup"><span data-stu-id="fc1f5-117">The following action will be taken: %4.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fc1f5-118">Сведения</span><span class="sxs-lookup"><span data-stu-id="fc1f5-118">Details</span></span>  
  
|<span data-ttu-id="fc1f5-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="fc1f5-119">Data Item Name</span></span>|<span data-ttu-id="fc1f5-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="fc1f5-120">Data Item Type</span></span>|<span data-ttu-id="fc1f5-121">Описание</span><span class="sxs-lookup"><span data-stu-id="fc1f5-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fc1f5-122">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="fc1f5-122">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="fc1f5-123">Идентификатор экземпляра для рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="fc1f5-123">The instance id for the workflow</span></span>|  
|<span data-ttu-id="fc1f5-124">Исключение</span><span class="sxs-lookup"><span data-stu-id="fc1f5-124">Exception</span></span>|`xs:string`|<span data-ttu-id="fc1f5-125">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="fc1f5-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="fc1f5-126">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="fc1f5-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="fc1f5-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="fc1f5-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
