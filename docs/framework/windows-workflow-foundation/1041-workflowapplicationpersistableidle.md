---
title: 1041 - WorkflowApplicationPersistableIdle
ms.date: 03/30/2017
ms.assetid: 966adf2f-e21d-44df-a3ec-a8e285e0a316
ms.openlocfilehash: 9995823753fc78ca3f278cd635fcf6c7d2b84325
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238942"
---
# <a name="1041---workflowapplicationpersistableidle"></a><span data-ttu-id="337fb-102">1041 - WorkflowApplicationPersistableIdle</span><span class="sxs-lookup"><span data-stu-id="337fb-102">1041 - WorkflowApplicationPersistableIdle</span></span>

## <a name="properties"></a><span data-ttu-id="337fb-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="337fb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="337fb-104">ID</span><span class="sxs-lookup"><span data-stu-id="337fb-104">ID</span></span>|<span data-ttu-id="337fb-105">1041</span><span class="sxs-lookup"><span data-stu-id="337fb-105">1041</span></span>|  
|<span data-ttu-id="337fb-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="337fb-106">Keywords</span></span>|<span data-ttu-id="337fb-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="337fb-107">WFRuntime</span></span>|  
|<span data-ttu-id="337fb-108">Level</span><span class="sxs-lookup"><span data-stu-id="337fb-108">Level</span></span>|<span data-ttu-id="337fb-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="337fb-109">Information</span></span>|  
|<span data-ttu-id="337fb-110">Канал</span><span class="sxs-lookup"><span data-stu-id="337fb-110">Channel</span></span>|<span data-ttu-id="337fb-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="337fb-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="337fb-112">Описание</span><span class="sxs-lookup"><span data-stu-id="337fb-112">Description</span></span>  

 <span data-ttu-id="337fb-113">Указывает, что приложение рабочего процесса бездействует и является сохраняемым.</span><span class="sxs-lookup"><span data-stu-id="337fb-113">Indicates that a workflow application is idle and persistable.</span></span> <span data-ttu-id="337fb-114">Приложение рабочего процесса будет бездействующим или сохраняемым.</span><span class="sxs-lookup"><span data-stu-id="337fb-114">The workflow application will be idled or persisted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="337fb-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="337fb-115">Message</span></span>  

 <span data-ttu-id="337fb-116">Идентификатор WorkflowApplication: "%1" находится в состоянии бездействия и является сохраняемым.</span><span class="sxs-lookup"><span data-stu-id="337fb-116">WorkflowApplication Id: '%1' is idle and persistable.</span></span>  <span data-ttu-id="337fb-117">Будет выполнено следующее действие: %2.</span><span class="sxs-lookup"><span data-stu-id="337fb-117">The following action will be taken: %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="337fb-118">Сведения</span><span class="sxs-lookup"><span data-stu-id="337fb-118">Details</span></span>  
  
|<span data-ttu-id="337fb-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="337fb-119">Data Item Name</span></span>|<span data-ttu-id="337fb-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="337fb-120">Data Item Type</span></span>|<span data-ttu-id="337fb-121">Описание</span><span class="sxs-lookup"><span data-stu-id="337fb-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="337fb-122">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="337fb-122">WorkflowApplicationId</span></span>|<span data-ttu-id="337fb-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="337fb-123">xs:string</span></span>|<span data-ttu-id="337fb-124">Идентификатор приложения рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="337fb-124">The workflow application id</span></span>|  
|<span data-ttu-id="337fb-125">ActionTaken</span><span class="sxs-lookup"><span data-stu-id="337fb-125">ActionTaken</span></span>|<span data-ttu-id="337fb-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="337fb-126">xs:string</span></span>|<span data-ttu-id="337fb-127">Действие, которое будет выполняться в приложении рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="337fb-127">The action that will be taken on the workflow application.</span></span>|  
|<span data-ttu-id="337fb-128">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="337fb-128">AppDomain</span></span>|<span data-ttu-id="337fb-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="337fb-129">xs:string</span></span>|<span data-ttu-id="337fb-130">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="337fb-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
