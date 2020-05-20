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
ms.openlocfilehash: 4e72cd8bee2cb4f35155d7b99cfe8d9cf63f463a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616077"
---
# <a name="iactiononclrevent-interface"></a><span data-ttu-id="cfa90-102">Интерфейс IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="cfa90-102">IActionOnCLREvent Interface</span></span>
<span data-ttu-id="cfa90-103">Предоставляет метод [иактиононклревент:: oneven](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) , который выполняет обратные вызовы для событий, зарегистрированных с помощью вызова метода [ICLROnEventManager:: регистерактиононевент](iclroneventmanager-registeractiononevent-method.md) .</span><span class="sxs-lookup"><span data-stu-id="cfa90-103">Provides the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method, which performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cfa90-104">Методы</span><span class="sxs-lookup"><span data-stu-id="cfa90-104">Methods</span></span>  
  
|<span data-ttu-id="cfa90-105">Метод</span><span class="sxs-lookup"><span data-stu-id="cfa90-105">Method</span></span>|<span data-ttu-id="cfa90-106">Описание</span><span class="sxs-lookup"><span data-stu-id="cfa90-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cfa90-107">Метод OnEvent</span><span class="sxs-lookup"><span data-stu-id="cfa90-107">OnEvent Method</span></span>](iactiononclrevent-onevent-method.md)|<span data-ttu-id="cfa90-108">Выполняет обратный вызов для зарегистрированного события.</span><span class="sxs-lookup"><span data-stu-id="cfa90-108">Performs a callback for a registered event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cfa90-109">Требования</span><span class="sxs-lookup"><span data-stu-id="cfa90-109">Requirements</span></span>  
 <span data-ttu-id="cfa90-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cfa90-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfa90-111">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="cfa90-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cfa90-112">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cfa90-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cfa90-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfa90-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfa90-114">См. также статью</span><span class="sxs-lookup"><span data-stu-id="cfa90-114">See also</span></span>

- [<span data-ttu-id="cfa90-115">Перечисление EClrEvent</span><span class="sxs-lookup"><span data-stu-id="cfa90-115">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="cfa90-116">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="cfa90-116">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="cfa90-117">Интерфейс ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="cfa90-117">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
- [<span data-ttu-id="cfa90-118">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="cfa90-118">Hosting Interfaces</span></span>](hosting-interfaces.md)
