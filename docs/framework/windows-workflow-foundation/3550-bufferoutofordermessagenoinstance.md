---
title: 3550 - BufferOutOfOrderMessageNoInstance
ms.date: 03/30/2017
ms.assetid: 1299d294-99b8-430e-98b1-55f5f17002f3
ms.openlocfilehash: 61605d666911cce277bcebbb0a2f803e9a5dcfeb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96261310"
---
# <a name="3550---bufferoutofordermessagenoinstance"></a><span data-ttu-id="363b8-102">3550 - BufferOutOfOrderMessageNoInstance</span><span class="sxs-lookup"><span data-stu-id="363b8-102">3550 - BufferOutOfOrderMessageNoInstance</span></span>

## <a name="properties"></a><span data-ttu-id="363b8-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="363b8-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="363b8-104">ID</span><span class="sxs-lookup"><span data-stu-id="363b8-104">ID</span></span>|<span data-ttu-id="363b8-105">3550</span><span class="sxs-lookup"><span data-stu-id="363b8-105">3550</span></span>|  
|<span data-ttu-id="363b8-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="363b8-106">Keywords</span></span>|<span data-ttu-id="363b8-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="363b8-107">WFServices</span></span>|  
|<span data-ttu-id="363b8-108">Level</span><span class="sxs-lookup"><span data-stu-id="363b8-108">Level</span></span>|<span data-ttu-id="363b8-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="363b8-109">Information</span></span>|  
|<span data-ttu-id="363b8-110">Канал</span><span class="sxs-lookup"><span data-stu-id="363b8-110">Channel</span></span>|<span data-ttu-id="363b8-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="363b8-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="363b8-112">Описание</span><span class="sxs-lookup"><span data-stu-id="363b8-112">Description</span></span>  

 <span data-ttu-id="363b8-113">Указывает, что получение через буфер не удалось.</span><span class="sxs-lookup"><span data-stu-id="363b8-113">Indicates a buffered receive has failed.</span></span> <span data-ttu-id="363b8-114">Следующая попытка выполнить операцию будет предпринята, когда экземпляр службы будет готов к обработке именно этой операции.</span><span class="sxs-lookup"><span data-stu-id="363b8-114">The operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="363b8-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="363b8-115">Message</span></span>  

 <span data-ttu-id="363b8-116">Операция «%1» сейчас не может быть выполнена.</span><span class="sxs-lookup"><span data-stu-id="363b8-116">Operation '%1' cannot be performed at this time.</span></span> <span data-ttu-id="363b8-117">Следующая попытка будет предпринята, когда экземпляр службы будет готов к обработке именно этой операции.</span><span class="sxs-lookup"><span data-stu-id="363b8-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="363b8-118">Сведения</span><span class="sxs-lookup"><span data-stu-id="363b8-118">Details</span></span>  
  
|<span data-ttu-id="363b8-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="363b8-119">Data Item Name</span></span>|<span data-ttu-id="363b8-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="363b8-120">Data Item Type</span></span>|<span data-ttu-id="363b8-121">Описание</span><span class="sxs-lookup"><span data-stu-id="363b8-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="363b8-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="363b8-122">OperationName</span></span>|<span data-ttu-id="363b8-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="363b8-123">xs:string</span></span>|<span data-ttu-id="363b8-124">Имя операции.</span><span class="sxs-lookup"><span data-stu-id="363b8-124">The name of the operation.</span></span>|  
|<span data-ttu-id="363b8-125">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="363b8-125">AppDomain</span></span>|<span data-ttu-id="363b8-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="363b8-126">xs:string</span></span>|<span data-ttu-id="363b8-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="363b8-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
