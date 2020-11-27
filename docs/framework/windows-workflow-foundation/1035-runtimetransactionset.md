---
title: 1035 - RuntimeTransactionSet
ms.date: 03/30/2017
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
ms.openlocfilehash: b8bf8431c4e2b82c6aac95820eb45de2a404e976
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294278"
---
# <a name="1035---runtimetransactionset"></a><span data-ttu-id="2ba3e-102">1035 - RuntimeTransactionSet</span><span class="sxs-lookup"><span data-stu-id="2ba3e-102">1035 - RuntimeTransactionSet</span></span>

## <a name="properties"></a><span data-ttu-id="2ba3e-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="2ba3e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2ba3e-104">ID</span><span class="sxs-lookup"><span data-stu-id="2ba3e-104">ID</span></span>|<span data-ttu-id="2ba3e-105">1035</span><span class="sxs-lookup"><span data-stu-id="2ba3e-105">1035</span></span>|  
|<span data-ttu-id="2ba3e-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="2ba3e-106">Keywords</span></span>|<span data-ttu-id="2ba3e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="2ba3e-107">WFRuntime</span></span>|  
|<span data-ttu-id="2ba3e-108">Level</span><span class="sxs-lookup"><span data-stu-id="2ba3e-108">Level</span></span>|<span data-ttu-id="2ba3e-109">Подробный</span><span class="sxs-lookup"><span data-stu-id="2ba3e-109">Verbose</span></span>|  
|<span data-ttu-id="2ba3e-110">Канал</span><span class="sxs-lookup"><span data-stu-id="2ba3e-110">Channel</span></span>|<span data-ttu-id="2ba3e-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="2ba3e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2ba3e-112">Описание</span><span class="sxs-lookup"><span data-stu-id="2ba3e-112">Description</span></span>  

 <span data-ttu-id="2ba3e-113">Указывает, что действие задало транзакцию среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="2ba3e-113">Indicates an activity has set the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2ba3e-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="2ba3e-114">Message</span></span>  

 <span data-ttu-id="2ba3e-115">Транзакция среды выполнения была задана действием "%1", DisplayName: "%2", InstanceId: "%3".</span><span class="sxs-lookup"><span data-stu-id="2ba3e-115">The runtime transaction has been set by Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="2ba3e-116">Выполнение изолировано с действием "%4", DisplayName: "%5", InstanceId: "%6".</span><span class="sxs-lookup"><span data-stu-id="2ba3e-116">Execution isolated to Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2ba3e-117">Сведения</span><span class="sxs-lookup"><span data-stu-id="2ba3e-117">Details</span></span>  
  
|<span data-ttu-id="2ba3e-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="2ba3e-118">Data Item Name</span></span>|<span data-ttu-id="2ba3e-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="2ba3e-119">Data Item Type</span></span>|<span data-ttu-id="2ba3e-120">Описание</span><span class="sxs-lookup"><span data-stu-id="2ba3e-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2ba3e-121">Действие</span><span class="sxs-lookup"><span data-stu-id="2ba3e-121">Activity</span></span>|<span data-ttu-id="2ba3e-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="2ba3e-122">xs:string</span></span>|<span data-ttu-id="2ba3e-123">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="2ba3e-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="2ba3e-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="2ba3e-124">DisplayName</span></span>|<span data-ttu-id="2ba3e-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="2ba3e-125">xs:string</span></span>|<span data-ttu-id="2ba3e-126">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="2ba3e-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="2ba3e-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="2ba3e-127">InstanceId</span></span>|<span data-ttu-id="2ba3e-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="2ba3e-128">xs:string</span></span>|<span data-ttu-id="2ba3e-129">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="2ba3e-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="2ba3e-130">IsolatedActivity</span><span class="sxs-lookup"><span data-stu-id="2ba3e-130">IsolatedActivity</span></span>|<span data-ttu-id="2ba3e-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="2ba3e-131">xs:string</span></span>|<span data-ttu-id="2ba3e-132">Имя типа для действия, в котором изолирована транзакция.</span><span class="sxs-lookup"><span data-stu-id="2ba3e-132">The type name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="2ba3e-133">IsolatedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="2ba3e-133">IsolatedActivityDisplayName</span></span>|<span data-ttu-id="2ba3e-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="2ba3e-134">xs:string</span></span>|<span data-ttu-id="2ba3e-135">Имя отображаемого имени действия, в котором изолирована транзакция.</span><span class="sxs-lookup"><span data-stu-id="2ba3e-135">The display name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="2ba3e-136">IsolatedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="2ba3e-136">IsolatedActivityInstanceId</span></span>|<span data-ttu-id="2ba3e-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="2ba3e-137">xs:string</span></span>|<span data-ttu-id="2ba3e-138">Идентификатор экземпляра действия, в котором изолирована транзакция.</span><span class="sxs-lookup"><span data-stu-id="2ba3e-138">The instance id of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="2ba3e-139">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="2ba3e-139">AppDomain</span></span>|<span data-ttu-id="2ba3e-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="2ba3e-140">xs:string</span></span>|<span data-ttu-id="2ba3e-141">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="2ba3e-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
