---
title: 1003 - WorkflowInstanceCanceled
ms.date: 03/30/2017
ms.assetid: 64754dc2-c160-4bf3-869a-13d56694e2dc
ms.openlocfilehash: bd8abf173ab6588d4a35ba59c6cd14fb53445e9f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239904"
---
# <a name="1003---workflowinstancecanceled"></a><span data-ttu-id="12f91-102">1003 - WorkflowInstanceCanceled</span><span class="sxs-lookup"><span data-stu-id="12f91-102">1003 - WorkflowInstanceCanceled</span></span>

## <a name="properties"></a><span data-ttu-id="12f91-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="12f91-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="12f91-104">ID</span><span class="sxs-lookup"><span data-stu-id="12f91-104">ID</span></span>|<span data-ttu-id="12f91-105">1003</span><span class="sxs-lookup"><span data-stu-id="12f91-105">1003</span></span>|  
|<span data-ttu-id="12f91-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="12f91-106">Keywords</span></span>|<span data-ttu-id="12f91-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="12f91-107">WFRuntime</span></span>|  
|<span data-ttu-id="12f91-108">Level</span><span class="sxs-lookup"><span data-stu-id="12f91-108">Level</span></span>|<span data-ttu-id="12f91-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="12f91-109">Information</span></span>|  
|<span data-ttu-id="12f91-110">Канал</span><span class="sxs-lookup"><span data-stu-id="12f91-110">Channel</span></span>|<span data-ttu-id="12f91-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="12f91-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="12f91-112">Описание</span><span class="sxs-lookup"><span data-stu-id="12f91-112">Description</span></span>  

 <span data-ttu-id="12f91-113">Указывает, что экземпляр рабочего процесса завершено в состоянии Canceled.</span><span class="sxs-lookup"><span data-stu-id="12f91-113">Indicates a workflow instance has completed in the Canceled state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="12f91-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="12f91-114">Message</span></span>  

 <span data-ttu-id="12f91-115">Элемент WorkflowInstance с идентификатором «%1» завершил работу в состоянии Canceled.</span><span class="sxs-lookup"><span data-stu-id="12f91-115">WorkflowInstance Id: '%1' has completed in the Canceled state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="12f91-116">Сведения</span><span class="sxs-lookup"><span data-stu-id="12f91-116">Details</span></span>  
  
|<span data-ttu-id="12f91-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="12f91-117">Data Item Name</span></span>|<span data-ttu-id="12f91-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="12f91-118">Data Item Type</span></span>|<span data-ttu-id="12f91-119">Описание</span><span class="sxs-lookup"><span data-stu-id="12f91-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="12f91-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="12f91-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="12f91-121">Идентификатор экземпляра для рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="12f91-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="12f91-122">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="12f91-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="12f91-123">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="12f91-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
