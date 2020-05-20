---
title: Интерфейс ICLROnEventManager
ms.date: 03/30/2017
api_name:
- ICLROnEventManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager
helpviewer_keywords:
- ICLROnEventManager interface [.NET Framework hosting]
ms.assetid: 9e15a0c1-8ab6-43d0-ae28-6ec7a4edd913
topic_type:
- apiref
ms.openlocfilehash: 30312e6e09535cee2968b1f9e8ac87b461c5ff40
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703518"
---
# <a name="iclroneventmanager-interface"></a><span data-ttu-id="41fbe-102">Интерфейс ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="41fbe-102">ICLROnEventManager Interface</span></span>
<span data-ttu-id="41fbe-103">Предоставляет методы, позволяющие основному приложению регистрировать и отменять регистрацию обратных вызовов для событий среды CLR.</span><span class="sxs-lookup"><span data-stu-id="41fbe-103">Provides methods that allow the host to register and unregister callbacks for common language runtime (CLR) events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="41fbe-104">Методы</span><span class="sxs-lookup"><span data-stu-id="41fbe-104">Methods</span></span>  
  
|<span data-ttu-id="41fbe-105">Метод</span><span class="sxs-lookup"><span data-stu-id="41fbe-105">Method</span></span>|<span data-ttu-id="41fbe-106">Описание</span><span class="sxs-lookup"><span data-stu-id="41fbe-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="41fbe-107">Метод RegisterActionOnEvent</span><span class="sxs-lookup"><span data-stu-id="41fbe-107">RegisterActionOnEvent Method</span></span>](iclroneventmanager-registeractiononevent-method.md)|<span data-ttu-id="41fbe-108">Регистрирует указатель обратного вызова для указанного события.</span><span class="sxs-lookup"><span data-stu-id="41fbe-108">Registers a callback pointer for the specified event.</span></span>|  
|[<span data-ttu-id="41fbe-109">Метод UnregisterActionOnEvent</span><span class="sxs-lookup"><span data-stu-id="41fbe-109">UnregisterActionOnEvent Method</span></span>](iclroneventmanager-unregisteractiononevent-method.md)|<span data-ttu-id="41fbe-110">Отменяет регистрацию ранее зарегистрированного указателя обратного вызова для указанного события.</span><span class="sxs-lookup"><span data-stu-id="41fbe-110">Unregisters a previously registered callback pointer for the specified event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41fbe-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="41fbe-111">Remarks</span></span>  
 <span data-ttu-id="41fbe-112">Для регистрации и отмены регистрации обратных вызовов событий узел получает ссылку на `ICLROnEventManager` , вызывая метод [ICLRControl:: GetCLRManager](iclrcontrol-getclrmanager-method.md) .</span><span class="sxs-lookup"><span data-stu-id="41fbe-112">To register and unregister event callbacks, the host gets a reference to `ICLROnEventManager` by calling the [ICLRControl::GetCLRManager](iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="41fbe-113">События, описанные [еклревент](eclrevent-enumeration.md) , можно инициировать несколько раз и из разных потоков, чтобы сообщить о выгрузке или отключении среды CLR.</span><span class="sxs-lookup"><span data-stu-id="41fbe-113">The events described by [EClrEvent](eclrevent-enumeration.md) can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41fbe-114">Требования</span><span class="sxs-lookup"><span data-stu-id="41fbe-114">Requirements</span></span>  
 <span data-ttu-id="41fbe-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41fbe-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41fbe-116">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="41fbe-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="41fbe-117">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="41fbe-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="41fbe-118">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41fbe-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41fbe-119">См. также статью</span><span class="sxs-lookup"><span data-stu-id="41fbe-119">See also</span></span>

- [<span data-ttu-id="41fbe-120">Перечисление EClrEvent</span><span class="sxs-lookup"><span data-stu-id="41fbe-120">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="41fbe-121">Интерфейс IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="41fbe-121">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)
- [<span data-ttu-id="41fbe-122">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="41fbe-122">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="41fbe-123">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="41fbe-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
