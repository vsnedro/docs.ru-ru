---
title: Перечисление EClrEvent
ms.date: 03/30/2017
api_name:
- EClrEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrEvent
helpviewer_keywords:
- EClrEvent enumeration [.NET Framework hosting]
ms.assetid: 7c36a7c2-75a2-4971-bc23-abf54c812154
topic_type:
- apiref
ms.openlocfilehash: 3ecaebb9d943a3cdbb231307012b5dc3aaf000f7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493423"
---
# <a name="eclrevent-enumeration"></a><span data-ttu-id="cc47f-102">Перечисление EClrEvent</span><span class="sxs-lookup"><span data-stu-id="cc47f-102">EClrEvent Enumeration</span></span>
<span data-ttu-id="cc47f-103">Описывает события среды CLR, для которых узел может регистрировать обратные вызовы.</span><span class="sxs-lookup"><span data-stu-id="cc47f-103">Describes the common language runtime (CLR) events for which the host can register callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc47f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cc47f-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    Event_ClrDisabled,  
    Event_DomainUnload,  
    Event_MDAFired,  
    Event_StackOverflow  
} EClrEvent;  
```  
  
## <a name="members"></a><span data-ttu-id="cc47f-105">Участники</span><span class="sxs-lookup"><span data-stu-id="cc47f-105">Members</span></span>  
  
|<span data-ttu-id="cc47f-106">Член</span><span class="sxs-lookup"><span data-stu-id="cc47f-106">Member</span></span>|<span data-ttu-id="cc47f-107">Описание</span><span class="sxs-lookup"><span data-stu-id="cc47f-107">Description</span></span>|  
|------------|-----------------|  
|`Event_ClrDisabled`|<span data-ttu-id="cc47f-108">Указывает неустранимую ошибку среды CLR.</span><span class="sxs-lookup"><span data-stu-id="cc47f-108">Specifies a fatal CLR error.</span></span>|  
|`Event_DomainUnload`|<span data-ttu-id="cc47f-109">Задает выгрузку конкретного объекта <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="cc47f-109">Specifies the unloading of a particular <xref:System.AppDomain>.</span></span>|  
|`Event_MDAFired`|<span data-ttu-id="cc47f-110">Указывает, что создано сообщение помощника по отладке управляемого кода (MDA).</span><span class="sxs-lookup"><span data-stu-id="cc47f-110">Specifies that a Managed Debugging Assistant (MDA) message has been generated.</span></span>|  
|`Event_StackOverflow`|<span data-ttu-id="cc47f-111">Указывает, что произошла ошибка переполнения стека.</span><span class="sxs-lookup"><span data-stu-id="cc47f-111">Specifies that a stack overflow error has occurred.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc47f-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="cc47f-112">Remarks</span></span>  
 <span data-ttu-id="cc47f-113">Узел может регистрировать обратные вызовы для любого из типов событий, описанных путем `EClrEvent` вызова методов интерфейса [ICLROnEventManager](iclroneventmanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="cc47f-113">The host can register callbacks for any of the event types described by `EClrEvent` by calling methods of the [ICLROnEventManager](iclroneventmanager-interface.md) interface.</span></span> <span data-ttu-id="cc47f-114">Узел получает указатель на этот интерфейс путем вызова метода [ICLRControl:: GetCLRManager](iclrcontrol-getclrmanager-method.md) .</span><span class="sxs-lookup"><span data-stu-id="cc47f-114">The host gets a pointer to this interface by calling the [ICLRControl::GetCLRManager](iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
 <span data-ttu-id="cc47f-115">`Event_CLRDisabled`События и `Event_DomainUnload` могут вызываться более одного раза и из разных потоков для сигнализации выгрузки или отключения среды CLR.</span><span class="sxs-lookup"><span data-stu-id="cc47f-115">The `Event_CLRDisabled` and `Event_DomainUnload` events can be raised more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
 <span data-ttu-id="cc47f-116">`Event_MDAFired`Событие вызывает создание экземпляра [мдаинфо](mdainfo-structure.md) , содержащего подробные сведения о сообщении MDA.</span><span class="sxs-lookup"><span data-stu-id="cc47f-116">The `Event_MDAFired` event raises the creation of an [MDAInfo](mdainfo-structure.md) instance that contains the details of the MDA message.</span></span> <span data-ttu-id="cc47f-117">Дополнительные сведения о помощниках MDA см. в разделе [Диагностика ошибок с помощью помощников по отладке управляемого](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)кода.</span><span class="sxs-lookup"><span data-stu-id="cc47f-117">For more information about MDAs, see [Diagnosing Errors with Managed Debugging Assistants](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc47f-118">Требования</span><span class="sxs-lookup"><span data-stu-id="cc47f-118">Requirements</span></span>  
 <span data-ttu-id="cc47f-119">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc47f-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc47f-120">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="cc47f-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cc47f-121">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cc47f-121">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cc47f-122">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc47f-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc47f-123">См. также</span><span class="sxs-lookup"><span data-stu-id="cc47f-123">See also</span></span>

- [<span data-ttu-id="cc47f-124">Интерфейс IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="cc47f-124">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)
- [<span data-ttu-id="cc47f-125">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="cc47f-125">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="cc47f-126">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="cc47f-126">Hosting Enumerations</span></span>](hosting-enumerations.md)
