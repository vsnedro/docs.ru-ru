---
title: 3552 – MaxPendingMessagesPerChannelExceeded
ms.date: 03/30/2017
ms.assetid: fc8309d9-eb3a-4636-a6f0-dd0018c1361d
ms.openlocfilehash: bd3e7539922e6c430c4ffe5bd96ef1ac7dbd098f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96261167"
---
# <a name="3552---maxpendingmessagesperchannelexceeded"></a><span data-ttu-id="c2af0-102">3552 – MaxPendingMessagesPerChannelExceeded</span><span class="sxs-lookup"><span data-stu-id="c2af0-102">3552 - MaxPendingMessagesPerChannelExceeded</span></span>

## <a name="properties"></a><span data-ttu-id="c2af0-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="c2af0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c2af0-104">ID</span><span class="sxs-lookup"><span data-stu-id="c2af0-104">ID</span></span>|<span data-ttu-id="c2af0-105">3552</span><span class="sxs-lookup"><span data-stu-id="c2af0-105">3552</span></span>|  
|<span data-ttu-id="c2af0-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="c2af0-106">Keywords</span></span>|<span data-ttu-id="c2af0-107">Quota, WFServices</span><span class="sxs-lookup"><span data-stu-id="c2af0-107">Quota, WFServices</span></span>|  
|<span data-ttu-id="c2af0-108">Level</span><span class="sxs-lookup"><span data-stu-id="c2af0-108">Level</span></span>|<span data-ttu-id="c2af0-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="c2af0-109">Warning</span></span>|  
|<span data-ttu-id="c2af0-110">Канал</span><span class="sxs-lookup"><span data-stu-id="c2af0-110">Channel</span></span>|<span data-ttu-id="c2af0-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="c2af0-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c2af0-112">Описание</span><span class="sxs-lookup"><span data-stu-id="c2af0-112">Description</span></span>  

 <span data-ttu-id="c2af0-113">Указывает, что был достигнут предел регулирования «MaxPendingMessagesPerChannel».</span><span class="sxs-lookup"><span data-stu-id="c2af0-113">Indicates the throttle 'MaxPendingMessagesPerChannel' limit was hit.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c2af0-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="c2af0-114">Message</span></span>  

 <span data-ttu-id="c2af0-115">Был достигнут предел регулирования «MaxPendingMessagesPerChannel» для «%1».</span><span class="sxs-lookup"><span data-stu-id="c2af0-115">The throttle 'MaxPendingMessagesPerChannel' limit of  '%1' was hit.</span></span> <span data-ttu-id="c2af0-116">Для увеличения этого предела настройте свойство MaxPendingMessagesPerChannel для поведения BufferedReceiveServiceBehavior.</span><span class="sxs-lookup"><span data-stu-id="c2af0-116">To increase this limit, adjust the MaxPendingMessagesPerChannel property on BufferedReceiveServiceBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c2af0-117">Сведения</span><span class="sxs-lookup"><span data-stu-id="c2af0-117">Details</span></span>  
  
|<span data-ttu-id="c2af0-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="c2af0-118">Data Item Name</span></span>|<span data-ttu-id="c2af0-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="c2af0-119">Data Item Type</span></span>|<span data-ttu-id="c2af0-120">Описание</span><span class="sxs-lookup"><span data-stu-id="c2af0-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c2af0-121">Ограничение</span><span class="sxs-lookup"><span data-stu-id="c2af0-121">Limit</span></span>|<span data-ttu-id="c2af0-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="c2af0-122">xs:string</span></span>|<span data-ttu-id="c2af0-123">Был достигнут предел регулирования «MaxPendingMessagesPerChannel».</span><span class="sxs-lookup"><span data-stu-id="c2af0-123">The limit of the MaxPendingMessagesPerChannel throttle.</span></span>|  
|<span data-ttu-id="c2af0-124">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="c2af0-124">AppDomain</span></span>|<span data-ttu-id="c2af0-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="c2af0-125">xs:string</span></span>|<span data-ttu-id="c2af0-126">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="c2af0-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
