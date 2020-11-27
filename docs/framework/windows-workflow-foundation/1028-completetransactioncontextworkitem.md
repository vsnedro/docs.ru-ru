---
title: 1028 - CompleteTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 95423f9d-d29a-460e-bcd8-096e80af5bd0
ms.openlocfilehash: 2fc509dac7e13f30f74c24d8b98cba55ed5f8e1d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275119"
---
# <a name="1028---completetransactioncontextworkitem"></a><span data-ttu-id="0b0cb-102">1028 - CompleteTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="0b0cb-102">1028 - CompleteTransactionContextWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="0b0cb-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="0b0cb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0b0cb-104">ID</span><span class="sxs-lookup"><span data-stu-id="0b0cb-104">ID</span></span>|<span data-ttu-id="0b0cb-105">1028</span><span class="sxs-lookup"><span data-stu-id="0b0cb-105">1028</span></span>|  
|<span data-ttu-id="0b0cb-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="0b0cb-106">Keywords</span></span>|<span data-ttu-id="0b0cb-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0b0cb-107">WFRuntime</span></span>|  
|<span data-ttu-id="0b0cb-108">Level</span><span class="sxs-lookup"><span data-stu-id="0b0cb-108">Level</span></span>|<span data-ttu-id="0b0cb-109">Подробный</span><span class="sxs-lookup"><span data-stu-id="0b0cb-109">Verbose</span></span>|  
|<span data-ttu-id="0b0cb-110">Канал</span><span class="sxs-lookup"><span data-stu-id="0b0cb-110">Channel</span></span>|<span data-ttu-id="0b0cb-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="0b0cb-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0b0cb-112">Описание</span><span class="sxs-lookup"><span data-stu-id="0b0cb-112">Description</span></span>  

 <span data-ttu-id="0b0cb-113">Указывает на завершение TransactionContextWorkItem.</span><span class="sxs-lookup"><span data-stu-id="0b0cb-113">Indicates a TransactionContextWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0b0cb-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="0b0cb-114">Message</span></span>  

 <span data-ttu-id="0b0cb-115">TransactionContextWorkItem завершен для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="0b0cb-115">A TransactionContextWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0b0cb-116">Сведения</span><span class="sxs-lookup"><span data-stu-id="0b0cb-116">Details</span></span>  
  
|<span data-ttu-id="0b0cb-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="0b0cb-117">Data Item Name</span></span>|<span data-ttu-id="0b0cb-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="0b0cb-118">Data Item Type</span></span>|<span data-ttu-id="0b0cb-119">Описание</span><span class="sxs-lookup"><span data-stu-id="0b0cb-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0b0cb-120">Действие</span><span class="sxs-lookup"><span data-stu-id="0b0cb-120">Activity</span></span>|<span data-ttu-id="0b0cb-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="0b0cb-121">xs:string</span></span>|<span data-ttu-id="0b0cb-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="0b0cb-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="0b0cb-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="0b0cb-123">DisplayName</span></span>|<span data-ttu-id="0b0cb-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="0b0cb-124">xs:string</span></span>|<span data-ttu-id="0b0cb-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="0b0cb-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="0b0cb-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="0b0cb-126">InstanceId</span></span>|<span data-ttu-id="0b0cb-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="0b0cb-127">xs:string</span></span>|<span data-ttu-id="0b0cb-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="0b0cb-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="0b0cb-129">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="0b0cb-129">AppDomain</span></span>|<span data-ttu-id="0b0cb-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="0b0cb-130">xs:string</span></span>|<span data-ttu-id="0b0cb-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="0b0cb-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
