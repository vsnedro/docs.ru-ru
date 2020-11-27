---
title: 1036 - RuntimeTransactionCompletionRequested
ms.date: 03/30/2017
ms.assetid: d36b9f44-7c0f-4083-9d3a-9034dd2b98de
ms.openlocfilehash: 96ea253fd61652a3719eaf8b1a4d31aa88337eeb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294265"
---
# <a name="1036---runtimetransactioncompletionrequested"></a><span data-ttu-id="aab11-102">1036 - RuntimeTransactionCompletionRequested</span><span class="sxs-lookup"><span data-stu-id="aab11-102">1036 - RuntimeTransactionCompletionRequested</span></span>

## <a name="properties"></a><span data-ttu-id="aab11-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="aab11-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="aab11-104">ID</span><span class="sxs-lookup"><span data-stu-id="aab11-104">ID</span></span>|<span data-ttu-id="aab11-105">1036</span><span class="sxs-lookup"><span data-stu-id="aab11-105">1036</span></span>|  
|<span data-ttu-id="aab11-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="aab11-106">Keywords</span></span>|<span data-ttu-id="aab11-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="aab11-107">WFRuntime</span></span>|  
|<span data-ttu-id="aab11-108">Level</span><span class="sxs-lookup"><span data-stu-id="aab11-108">Level</span></span>|<span data-ttu-id="aab11-109">Подробный</span><span class="sxs-lookup"><span data-stu-id="aab11-109">Verbose</span></span>|  
|<span data-ttu-id="aab11-110">Канал</span><span class="sxs-lookup"><span data-stu-id="aab11-110">Channel</span></span>|<span data-ttu-id="aab11-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="aab11-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="aab11-112">Описание</span><span class="sxs-lookup"><span data-stu-id="aab11-112">Description</span></span>  

 <span data-ttu-id="aab11-113">Указывает, что действие запланировало завершение транзакции среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="aab11-113">Indicates an activity has scheduled the completion of the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="aab11-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="aab11-114">Message</span></span>  

 <span data-ttu-id="aab11-115">Действие «%1», DisplayName «%2», InstanceId «%3» запланировало завершение транзакции времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="aab11-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has scheduled completion of the runtime transaction.</span></span>  
  
## <a name="details"></a><span data-ttu-id="aab11-116">Сведения</span><span class="sxs-lookup"><span data-stu-id="aab11-116">Details</span></span>  
  
|<span data-ttu-id="aab11-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="aab11-117">Data Item Name</span></span>|<span data-ttu-id="aab11-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="aab11-118">Data Item Type</span></span>|<span data-ttu-id="aab11-119">Описание</span><span class="sxs-lookup"><span data-stu-id="aab11-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="aab11-120">Действие</span><span class="sxs-lookup"><span data-stu-id="aab11-120">Activity</span></span>|<span data-ttu-id="aab11-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="aab11-121">xs:string</span></span>|<span data-ttu-id="aab11-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="aab11-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="aab11-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="aab11-123">DisplayName</span></span>|<span data-ttu-id="aab11-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="aab11-124">xs:string</span></span>|<span data-ttu-id="aab11-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="aab11-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="aab11-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="aab11-126">InstanceId</span></span>|<span data-ttu-id="aab11-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="aab11-127">xs:string</span></span>|<span data-ttu-id="aab11-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="aab11-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="aab11-129">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="aab11-129">AppDomain</span></span>|<span data-ttu-id="aab11-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="aab11-130">xs:string</span></span>|<span data-ttu-id="aab11-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="aab11-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
