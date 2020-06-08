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
ms.openlocfilehash: f577e9252d97ec188ff1076fd8340336b16c8257
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504333"
---
# <a name="iactiononclrevent-interface"></a><span data-ttu-id="453c2-102">Интерфейс IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="453c2-102">IActionOnCLREvent Interface</span></span>
<span data-ttu-id="453c2-103">Предоставляет метод [иактиононклревент:: oneven](iactiononclrevent-onevent-method.md) , который выполняет обратные вызовы для событий, зарегистрированных с помощью вызова метода [ICLROnEventManager:: регистерактиононевент](iclroneventmanager-registeractiononevent-method.md) .</span><span class="sxs-lookup"><span data-stu-id="453c2-103">Provides the [IActionOnCLREvent::OnEvent](iactiononclrevent-onevent-method.md) method, which performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="453c2-104">Методы</span><span class="sxs-lookup"><span data-stu-id="453c2-104">Methods</span></span>  
  
|<span data-ttu-id="453c2-105">Метод</span><span class="sxs-lookup"><span data-stu-id="453c2-105">Method</span></span>|<span data-ttu-id="453c2-106">Описание</span><span class="sxs-lookup"><span data-stu-id="453c2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="453c2-107">Метод OnEvent</span><span class="sxs-lookup"><span data-stu-id="453c2-107">OnEvent Method</span></span>](iactiononclrevent-onevent-method.md)|<span data-ttu-id="453c2-108">Выполняет обратный вызов для зарегистрированного события.</span><span class="sxs-lookup"><span data-stu-id="453c2-108">Performs a callback for a registered event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="453c2-109">Требования</span><span class="sxs-lookup"><span data-stu-id="453c2-109">Requirements</span></span>  
 <span data-ttu-id="453c2-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="453c2-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="453c2-111">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="453c2-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="453c2-112">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="453c2-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="453c2-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="453c2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="453c2-114">См. также</span><span class="sxs-lookup"><span data-stu-id="453c2-114">See also</span></span>

- [<span data-ttu-id="453c2-115">Перечисление EClrEvent</span><span class="sxs-lookup"><span data-stu-id="453c2-115">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="453c2-116">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="453c2-116">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="453c2-117">Интерфейс ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="453c2-117">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
- [<span data-ttu-id="453c2-118">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="453c2-118">Hosting Interfaces</span></span>](hosting-interfaces.md)
