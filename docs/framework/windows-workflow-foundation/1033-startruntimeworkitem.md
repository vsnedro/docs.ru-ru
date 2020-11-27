---
title: 1033 - StartRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 172b5346-9f3b-46ae-bc06-39872022376a
ms.openlocfilehash: 46a3dc8d313ec72ac90abc2e2e333b274dad2e4c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294304"
---
# <a name="1033---startruntimeworkitem"></a><span data-ttu-id="d678b-102">1033 - StartRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="d678b-102">1033 - StartRuntimeWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="d678b-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="d678b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d678b-104">ID</span><span class="sxs-lookup"><span data-stu-id="d678b-104">ID</span></span>|<span data-ttu-id="d678b-105">1033</span><span class="sxs-lookup"><span data-stu-id="d678b-105">1033</span></span>|  
|<span data-ttu-id="d678b-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="d678b-106">Keywords</span></span>|<span data-ttu-id="d678b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="d678b-107">WFRuntime</span></span>|  
|<span data-ttu-id="d678b-108">Level</span><span class="sxs-lookup"><span data-stu-id="d678b-108">Level</span></span>|<span data-ttu-id="d678b-109">Подробный</span><span class="sxs-lookup"><span data-stu-id="d678b-109">Verbose</span></span>|  
|<span data-ttu-id="d678b-110">Канал</span><span class="sxs-lookup"><span data-stu-id="d678b-110">Channel</span></span>|<span data-ttu-id="d678b-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="d678b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d678b-112">Описание</span><span class="sxs-lookup"><span data-stu-id="d678b-112">Description</span></span>  

 <span data-ttu-id="d678b-113">Указывает, что начинается выполнение RuntimeWorkItem.</span><span class="sxs-lookup"><span data-stu-id="d678b-113">Indicates a RuntimeWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d678b-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="d678b-114">Message</span></span>  

 <span data-ttu-id="d678b-115">Начато выполнение рабочего элемента среды выполнения для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="d678b-115">Starting execution of a runtime work item for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d678b-116">Сведения</span><span class="sxs-lookup"><span data-stu-id="d678b-116">Details</span></span>  
  
|<span data-ttu-id="d678b-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="d678b-117">Data Item Name</span></span>|<span data-ttu-id="d678b-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="d678b-118">Data Item Type</span></span>|<span data-ttu-id="d678b-119">Описание</span><span class="sxs-lookup"><span data-stu-id="d678b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d678b-120">Действие</span><span class="sxs-lookup"><span data-stu-id="d678b-120">Activity</span></span>|<span data-ttu-id="d678b-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="d678b-121">xs:string</span></span>|<span data-ttu-id="d678b-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="d678b-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="d678b-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="d678b-123">DisplayName</span></span>|<span data-ttu-id="d678b-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="d678b-124">xs:string</span></span>|<span data-ttu-id="d678b-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="d678b-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="d678b-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="d678b-126">InstanceId</span></span>|<span data-ttu-id="d678b-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="d678b-127">xs:string</span></span>|<span data-ttu-id="d678b-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="d678b-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="d678b-129">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="d678b-129">AppDomain</span></span>|<span data-ttu-id="d678b-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="d678b-130">xs:string</span></span>|<span data-ttu-id="d678b-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="d678b-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
