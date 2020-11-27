---
title: 1018 - StartCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 68b4fa1d-eee6-4a2a-8c16-7e9d89f08ab9
ms.openlocfilehash: c1558e19b0de2dc5d22d4356b0f80c35e5b4fbc1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275509"
---
# <a name="1018---startcancelactivityworkitem"></a><span data-ttu-id="147ce-102">1018 - StartCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="147ce-102">1018 - StartCancelActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="147ce-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="147ce-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="147ce-104">ID</span><span class="sxs-lookup"><span data-stu-id="147ce-104">ID</span></span>|<span data-ttu-id="147ce-105">1018</span><span class="sxs-lookup"><span data-stu-id="147ce-105">1018</span></span>|  
|<span data-ttu-id="147ce-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="147ce-106">Keywords</span></span>|<span data-ttu-id="147ce-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="147ce-107">WFRuntime</span></span>|  
|<span data-ttu-id="147ce-108">Level</span><span class="sxs-lookup"><span data-stu-id="147ce-108">Level</span></span>|<span data-ttu-id="147ce-109">Подробный</span><span class="sxs-lookup"><span data-stu-id="147ce-109">Verbose</span></span>|  
|<span data-ttu-id="147ce-110">Канал</span><span class="sxs-lookup"><span data-stu-id="147ce-110">Channel</span></span>|<span data-ttu-id="147ce-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="147ce-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="147ce-112">Описание</span><span class="sxs-lookup"><span data-stu-id="147ce-112">Description</span></span>  

 <span data-ttu-id="147ce-113">Указывает, что CancelActivityWorkItem начинает выполнение.</span><span class="sxs-lookup"><span data-stu-id="147ce-113">Indicates a CancelActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="147ce-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="147ce-114">Message</span></span>  

 <span data-ttu-id="147ce-115">Начато выполнение CancelActivityWorkItem для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="147ce-115">Starting execution of a CancelActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="147ce-116">Сведения</span><span class="sxs-lookup"><span data-stu-id="147ce-116">Details</span></span>  
  
|<span data-ttu-id="147ce-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="147ce-117">Data Item Name</span></span>|<span data-ttu-id="147ce-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="147ce-118">Data Item Type</span></span>|<span data-ttu-id="147ce-119">Описание</span><span class="sxs-lookup"><span data-stu-id="147ce-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="147ce-120">Действие</span><span class="sxs-lookup"><span data-stu-id="147ce-120">Activity</span></span>|<span data-ttu-id="147ce-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="147ce-121">xs:string</span></span>|<span data-ttu-id="147ce-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="147ce-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="147ce-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="147ce-123">DisplayName</span></span>|<span data-ttu-id="147ce-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="147ce-124">xs:string</span></span>|<span data-ttu-id="147ce-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="147ce-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="147ce-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="147ce-126">InstanceId</span></span>|<span data-ttu-id="147ce-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="147ce-127">xs:string</span></span>|<span data-ttu-id="147ce-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="147ce-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="147ce-129">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="147ce-129">AppDomain</span></span>|<span data-ttu-id="147ce-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="147ce-130">xs:string</span></span>|<span data-ttu-id="147ce-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="147ce-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
