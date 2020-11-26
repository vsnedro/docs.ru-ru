---
title: 1101 - WorkflowActivityStart
ms.date: 03/30/2017
ms.assetid: 831cd386-b9b5-47a9-9690-aff6292ff348
ms.openlocfilehash: 6e43b0ab1e2d35657bae43e7239a677643154fa9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238734"
---
# <a name="1101---workflowactivitystart"></a><span data-ttu-id="fbde4-102">1101 - WorkflowActivityStart</span><span class="sxs-lookup"><span data-stu-id="fbde4-102">1101 - WorkflowActivityStart</span></span>

## <a name="properties"></a><span data-ttu-id="fbde4-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="fbde4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fbde4-104">ID</span><span class="sxs-lookup"><span data-stu-id="fbde4-104">ID</span></span>|<span data-ttu-id="fbde4-105">1101</span><span class="sxs-lookup"><span data-stu-id="fbde4-105">1101</span></span>|  
|<span data-ttu-id="fbde4-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="fbde4-106">Keywords</span></span>|<span data-ttu-id="fbde4-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="fbde4-107">WFRuntime</span></span>|  
|<span data-ttu-id="fbde4-108">Level</span><span class="sxs-lookup"><span data-stu-id="fbde4-108">Level</span></span>|<span data-ttu-id="fbde4-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="fbde4-109">Information</span></span>|  
|<span data-ttu-id="fbde4-110">Канал</span><span class="sxs-lookup"><span data-stu-id="fbde4-110">Channel</span></span>|<span data-ttu-id="fbde4-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="fbde4-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fbde4-112">Описание</span><span class="sxs-lookup"><span data-stu-id="fbde4-112">Description</span></span>  

 <span data-ttu-id="fbde4-113">Указывает, что началось действие рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="fbde4-113">Indicates a workflow activity has started.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fbde4-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="fbde4-114">Message</span></span>  

 <span data-ttu-id="fbde4-115">Элемент WorkflowInstance с идентификатором «%1», действие E2E</span><span class="sxs-lookup"><span data-stu-id="fbde4-115">WorkflowInstance Id: '%1' E2E Activity</span></span>  
  
## <a name="details"></a><span data-ttu-id="fbde4-116">Сведения</span><span class="sxs-lookup"><span data-stu-id="fbde4-116">Details</span></span>  
  
|<span data-ttu-id="fbde4-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="fbde4-117">Data Item Name</span></span>|<span data-ttu-id="fbde4-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="fbde4-118">Data Item Type</span></span>|<span data-ttu-id="fbde4-119">Описание</span><span class="sxs-lookup"><span data-stu-id="fbde4-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fbde4-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="fbde4-120">WorkflowInstanceId</span></span>|<span data-ttu-id="fbde4-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="fbde4-121">xs:string</span></span>|<span data-ttu-id="fbde4-122">Идентификатор экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="fbde4-122">The workflow instance id.</span></span>|  
|<span data-ttu-id="fbde4-123">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="fbde4-123">AppDomain</span></span>|<span data-ttu-id="fbde4-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="fbde4-124">xs:string</span></span>|<span data-ttu-id="fbde4-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="fbde4-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
