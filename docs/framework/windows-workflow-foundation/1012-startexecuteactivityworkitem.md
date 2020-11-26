---
title: 1012 - StartExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 29e9b1c6-c5d7-4b58-b59d-a06a923d3c80
ms.openlocfilehash: b9cfceb12d56f93c0f9726849e34f4333f1399ac
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239644"
---
# <a name="1012---startexecuteactivityworkitem"></a><span data-ttu-id="4d14e-102">1012 - StartExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="4d14e-102">1012 - StartExecuteActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="4d14e-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="4d14e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4d14e-104">ID</span><span class="sxs-lookup"><span data-stu-id="4d14e-104">ID</span></span>|<span data-ttu-id="4d14e-105">1012</span><span class="sxs-lookup"><span data-stu-id="4d14e-105">1012</span></span>|  
|<span data-ttu-id="4d14e-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="4d14e-106">Keywords</span></span>|<span data-ttu-id="4d14e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="4d14e-107">WFRuntime</span></span>|  
|<span data-ttu-id="4d14e-108">Level</span><span class="sxs-lookup"><span data-stu-id="4d14e-108">Level</span></span>|<span data-ttu-id="4d14e-109">Подробный</span><span class="sxs-lookup"><span data-stu-id="4d14e-109">Verbose</span></span>|  
|<span data-ttu-id="4d14e-110">Канал</span><span class="sxs-lookup"><span data-stu-id="4d14e-110">Channel</span></span>|<span data-ttu-id="4d14e-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="4d14e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4d14e-112">Описание</span><span class="sxs-lookup"><span data-stu-id="4d14e-112">Description</span></span>  

 <span data-ttu-id="4d14e-113">Указывает на начало выполнения элемента ExecuteActivityWorkItem.</span><span class="sxs-lookup"><span data-stu-id="4d14e-113">Indicates an ExecuteActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4d14e-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="4d14e-114">Message</span></span>  

 <span data-ttu-id="4d14e-115">Начато выполнение ExecuteActivityWorkItem для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="4d14e-115">Starting execution of an ExecuteActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4d14e-116">Сведения</span><span class="sxs-lookup"><span data-stu-id="4d14e-116">Details</span></span>  
  
|<span data-ttu-id="4d14e-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="4d14e-117">Data Item Name</span></span>|<span data-ttu-id="4d14e-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="4d14e-118">Data Item Type</span></span>|<span data-ttu-id="4d14e-119">Описание</span><span class="sxs-lookup"><span data-stu-id="4d14e-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4d14e-120">Действие</span><span class="sxs-lookup"><span data-stu-id="4d14e-120">Activity</span></span>|<span data-ttu-id="4d14e-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="4d14e-121">xs:string</span></span>|<span data-ttu-id="4d14e-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="4d14e-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="4d14e-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="4d14e-123">DisplayName</span></span>|<span data-ttu-id="4d14e-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="4d14e-124">xs:string</span></span>|<span data-ttu-id="4d14e-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="4d14e-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="4d14e-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="4d14e-126">InstanceId</span></span>|<span data-ttu-id="4d14e-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="4d14e-127">xs:string</span></span>|<span data-ttu-id="4d14e-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="4d14e-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="4d14e-129">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="4d14e-129">AppDomain</span></span>|<span data-ttu-id="4d14e-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="4d14e-130">xs:string</span></span>|<span data-ttu-id="4d14e-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="4d14e-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
