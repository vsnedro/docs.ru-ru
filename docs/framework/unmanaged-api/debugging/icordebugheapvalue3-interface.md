---
title: Интерфейс ICorDebugHeapValue3
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3
helpviewer_keywords:
- ICorDebugHeapValue3 interface [.NET Framework debugging]
ms.assetid: 9c421bb0-e647-4b2d-a986-f3d578cc7f20
topic_type:
- apiref
ms.openlocfilehash: a1f4964c89aa3b658c57946d4b5a0327797118f1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728710"
---
# <a name="icordebugheapvalue3-interface"></a><span data-ttu-id="ada58-102">Интерфейс ICorDebugHeapValue3</span><span class="sxs-lookup"><span data-stu-id="ada58-102">ICorDebugHeapValue3 Interface</span></span>

<span data-ttu-id="ada58-103">Предоставляет свойства блокировки монитора объектов.</span><span class="sxs-lookup"><span data-stu-id="ada58-103">Exposes the monitor lock properties of objects.</span></span> <span data-ttu-id="ada58-104">Этот интерфейс расширяет интерфейсы ICorDebugHeapValue и ICorDebugHeapValue2.</span><span class="sxs-lookup"><span data-stu-id="ada58-104">This interface extends the ICorDebugHeapValue and ICorDebugHeapValue2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ada58-105">Методы</span><span class="sxs-lookup"><span data-stu-id="ada58-105">Methods</span></span>  
  
|<span data-ttu-id="ada58-106">Метод</span><span class="sxs-lookup"><span data-stu-id="ada58-106">Method</span></span>|<span data-ttu-id="ada58-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ada58-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ada58-108">Метод GetThreadOwningMonitorLock</span><span class="sxs-lookup"><span data-stu-id="ada58-108">GetThreadOwningMonitorLock Method</span></span>](icordebugheapvalue3-getthreadowningmonitorlock-method.md)|<span data-ttu-id="ada58-109">Возвращает управляемый поток, которому принадлежит блокировка монитора для этого объекта.</span><span class="sxs-lookup"><span data-stu-id="ada58-109">Returns the managed thread that owns the monitor lock on this object.</span></span>|  
|[<span data-ttu-id="ada58-110">Метод GetMonitorEventWaitList</span><span class="sxs-lookup"><span data-stu-id="ada58-110">GetMonitorEventWaitList Method</span></span>](icordebugheapvalue3-getmonitoreventwaitlist-method.md)|<span data-ttu-id="ada58-111">Предоставляет упорядоченный список потоков, поставленных в очередь на событие, связанное с блокировкой монитора.</span><span class="sxs-lookup"><span data-stu-id="ada58-111">Provides an ordered list of threads that are queued on the event that is associated with a monitor lock.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ada58-112">Комментарии</span><span class="sxs-lookup"><span data-stu-id="ada58-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ada58-113">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="ada58-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ada58-114">Требования</span><span class="sxs-lookup"><span data-stu-id="ada58-114">Requirements</span></span>  

 <span data-ttu-id="ada58-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ada58-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ada58-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ada58-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ada58-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ada58-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ada58-118">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ada58-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ada58-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ada58-119">See also</span></span>

- [<span data-ttu-id="ada58-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="ada58-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="ada58-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="ada58-121">Debugging</span></span>](index.md)
