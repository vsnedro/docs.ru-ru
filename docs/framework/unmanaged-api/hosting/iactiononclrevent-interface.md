---
title: Интерфейс IActionOnCLREvent
ms.date: 03/30/2017
api_name:
- IActionOnCLREvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IActionOnCLREvent
helpviewer_keywords:
- IActionOnCLREvent interface [.NET Framework hosting]
ms.assetid: b5f9b41e-7301-429c-911f-21d5422292b3
topic_type:
- apiref
ms.openlocfilehash: 8ca4bb1fe35451f95f752a4e71f5f0b541b55e58
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721781"
---
# <a name="iactiononclrevent-interface"></a><span data-ttu-id="b3f28-102">Интерфейс IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="b3f28-102">IActionOnCLREvent Interface</span></span>

<span data-ttu-id="b3f28-103">Предоставляет метод [иактиононклревент:: oneven](iactiononclrevent-onevent-method.md) , который выполняет обратные вызовы для событий, зарегистрированных с помощью вызова метода [ICLROnEventManager:: регистерактиононевент](iclroneventmanager-registeractiononevent-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b3f28-103">Provides the [IActionOnCLREvent::OnEvent](iactiononclrevent-onevent-method.md) method, which performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b3f28-104">Методы</span><span class="sxs-lookup"><span data-stu-id="b3f28-104">Methods</span></span>  
  
|<span data-ttu-id="b3f28-105">Метод</span><span class="sxs-lookup"><span data-stu-id="b3f28-105">Method</span></span>|<span data-ttu-id="b3f28-106">Описание</span><span class="sxs-lookup"><span data-stu-id="b3f28-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b3f28-107">Метод OnEvent</span><span class="sxs-lookup"><span data-stu-id="b3f28-107">OnEvent Method</span></span>](iactiononclrevent-onevent-method.md)|<span data-ttu-id="b3f28-108">Выполняет обратный вызов для зарегистрированного события.</span><span class="sxs-lookup"><span data-stu-id="b3f28-108">Performs a callback for a registered event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b3f28-109">Требования</span><span class="sxs-lookup"><span data-stu-id="b3f28-109">Requirements</span></span>  

 <span data-ttu-id="b3f28-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3f28-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3f28-111">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b3f28-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b3f28-112">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b3f28-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b3f28-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3f28-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3f28-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b3f28-114">See also</span></span>

- [<span data-ttu-id="b3f28-115">Перечисление EClrEvent</span><span class="sxs-lookup"><span data-stu-id="b3f28-115">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="b3f28-116">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="b3f28-116">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="b3f28-117">Интерфейс ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="b3f28-117">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
- [<span data-ttu-id="b3f28-118">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="b3f28-118">Hosting Interfaces</span></span>](hosting-interfaces.md)
