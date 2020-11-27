---
title: 1026 - ScheduleTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 0d5f86ba-ec21-4129-a726-5432e425384c
ms.openlocfilehash: 7ba2ada1fbd5217592b4e4e3cffd813ffbe978ac
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275249"
---
# <a name="1026---scheduletransactioncontextworkitem"></a><span data-ttu-id="5b76a-102">1026 - ScheduleTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="5b76a-102">1026 - ScheduleTransactionContextWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="5b76a-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="5b76a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5b76a-104">ID</span><span class="sxs-lookup"><span data-stu-id="5b76a-104">ID</span></span>|<span data-ttu-id="5b76a-105">1026</span><span class="sxs-lookup"><span data-stu-id="5b76a-105">1026</span></span>|  
|<span data-ttu-id="5b76a-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="5b76a-106">Keywords</span></span>|<span data-ttu-id="5b76a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="5b76a-107">WFRuntime</span></span>|  
|<span data-ttu-id="5b76a-108">Level</span><span class="sxs-lookup"><span data-stu-id="5b76a-108">Level</span></span>|<span data-ttu-id="5b76a-109">Подробный</span><span class="sxs-lookup"><span data-stu-id="5b76a-109">Verbose</span></span>|  
|<span data-ttu-id="5b76a-110">Канал</span><span class="sxs-lookup"><span data-stu-id="5b76a-110">Channel</span></span>|<span data-ttu-id="5b76a-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="5b76a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5b76a-112">Описание</span><span class="sxs-lookup"><span data-stu-id="5b76a-112">Description</span></span>  

 <span data-ttu-id="5b76a-113">Указывает, что TransactionContextWorkItem было запланировано.</span><span class="sxs-lookup"><span data-stu-id="5b76a-113">Indicates a TransactionContextWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5b76a-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="5b76a-114">Message</span></span>  

 <span data-ttu-id="5b76a-115">TransactionContextWorkItem запланирован для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="5b76a-115">A TransactionContextWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5b76a-116">Сведения</span><span class="sxs-lookup"><span data-stu-id="5b76a-116">Details</span></span>  
  
|<span data-ttu-id="5b76a-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="5b76a-117">Data Item Name</span></span>|<span data-ttu-id="5b76a-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="5b76a-118">Data Item Type</span></span>|<span data-ttu-id="5b76a-119">Описание</span><span class="sxs-lookup"><span data-stu-id="5b76a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5b76a-120">Действие</span><span class="sxs-lookup"><span data-stu-id="5b76a-120">Activity</span></span>|<span data-ttu-id="5b76a-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="5b76a-121">xs:string</span></span>|<span data-ttu-id="5b76a-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="5b76a-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="5b76a-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="5b76a-123">DisplayName</span></span>|<span data-ttu-id="5b76a-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="5b76a-124">xs:string</span></span>|<span data-ttu-id="5b76a-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="5b76a-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="5b76a-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="5b76a-126">InstanceId</span></span>|<span data-ttu-id="5b76a-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="5b76a-127">xs:string</span></span>|<span data-ttu-id="5b76a-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="5b76a-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="5b76a-129">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="5b76a-129">AppDomain</span></span>|<span data-ttu-id="5b76a-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="5b76a-130">xs:string</span></span>|<span data-ttu-id="5b76a-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="5b76a-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
