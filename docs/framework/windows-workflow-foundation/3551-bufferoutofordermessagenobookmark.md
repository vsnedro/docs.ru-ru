---
title: 3551 - BufferOutOfOrderMessageNoBookmark
ms.date: 03/30/2017
ms.assetid: 7930d6c4-c843-4a83-933a-cecd71b80d1e
ms.openlocfilehash: 5e6a5f9d21435fee8309bd222443407e50ec2cee
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263611"
---
# <a name="3551---bufferoutofordermessagenobookmark"></a><span data-ttu-id="4ba12-102">3551 - BufferOutOfOrderMessageNoBookmark</span><span class="sxs-lookup"><span data-stu-id="4ba12-102">3551 - BufferOutOfOrderMessageNoBookmark</span></span>

## <a name="properties"></a><span data-ttu-id="4ba12-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="4ba12-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4ba12-104">ID</span><span class="sxs-lookup"><span data-stu-id="4ba12-104">ID</span></span>|<span data-ttu-id="4ba12-105">3551</span><span class="sxs-lookup"><span data-stu-id="4ba12-105">3551</span></span>|  
|<span data-ttu-id="4ba12-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="4ba12-106">Keywords</span></span>|<span data-ttu-id="4ba12-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="4ba12-107">WFServices</span></span>|  
|<span data-ttu-id="4ba12-108">Level</span><span class="sxs-lookup"><span data-stu-id="4ba12-108">Level</span></span>|<span data-ttu-id="4ba12-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="4ba12-109">Information</span></span>|  
|<span data-ttu-id="4ba12-110">Канал</span><span class="sxs-lookup"><span data-stu-id="4ba12-110">Channel</span></span>|<span data-ttu-id="4ba12-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="4ba12-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4ba12-112">Описание</span><span class="sxs-lookup"><span data-stu-id="4ba12-112">Description</span></span>  

 <span data-ttu-id="4ba12-113">Указывает на сбой возобновления закладки.</span><span class="sxs-lookup"><span data-stu-id="4ba12-113">Indicates a bookmark resumption has failed.</span></span> <span data-ttu-id="4ba12-114">Следующая попытка выполнить операцию получения через буфер будет предпринята, когда экземпляр службы будет готов к обработке именно этой операции.</span><span class="sxs-lookup"><span data-stu-id="4ba12-114">The buffered receive operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4ba12-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="4ba12-115">Message</span></span>  

 <span data-ttu-id="4ba12-116">Операция «%2» в экземпляре службы «%1» не может быть выполнена в данный момент.</span><span class="sxs-lookup"><span data-stu-id="4ba12-116">Operation '%2' on service instance '%1' cannot be performed at this time.</span></span> <span data-ttu-id="4ba12-117">Следующая попытка будет предпринята, когда экземпляр службы будет готов к обработке именно этой операции.</span><span class="sxs-lookup"><span data-stu-id="4ba12-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4ba12-118">Сведения</span><span class="sxs-lookup"><span data-stu-id="4ba12-118">Details</span></span>  
  
|<span data-ttu-id="4ba12-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="4ba12-119">Data Item Name</span></span>|<span data-ttu-id="4ba12-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="4ba12-120">Data Item Type</span></span>|<span data-ttu-id="4ba12-121">Описание</span><span class="sxs-lookup"><span data-stu-id="4ba12-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4ba12-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="4ba12-122">OperationName</span></span>|<span data-ttu-id="4ba12-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="4ba12-123">xs:string</span></span>|<span data-ttu-id="4ba12-124">Имя операции.</span><span class="sxs-lookup"><span data-stu-id="4ba12-124">The name of the operation.</span></span>|  
|<span data-ttu-id="4ba12-125">ServiceInstanceId</span><span class="sxs-lookup"><span data-stu-id="4ba12-125">ServiceInstanceId</span></span>|<span data-ttu-id="4ba12-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="4ba12-126">xs:string</span></span>|<span data-ttu-id="4ba12-127">Идентификатор экземпляра службы.</span><span class="sxs-lookup"><span data-stu-id="4ba12-127">The id of the service instance.</span></span>|  
|<span data-ttu-id="4ba12-128">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="4ba12-128">AppDomain</span></span>|<span data-ttu-id="4ba12-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="4ba12-129">xs:string</span></span>|<span data-ttu-id="4ba12-130">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="4ba12-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
