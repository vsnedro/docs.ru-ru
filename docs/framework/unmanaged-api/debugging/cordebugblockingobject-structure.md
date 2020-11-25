---
title: Структура CorDebugBlockingObject
ms.date: 03/30/2017
api_name:
- CorDebugBlockingObject Structure
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugBlockingObject
helpviewer_keywords:
- CorDebugBlockingObject structure [.NET Framework debugging]
ms.assetid: 5944edd1-0914-4efa-aba0-d5a277c38b1a
topic_type:
- apiref
ms.openlocfilehash: b16feb1af0d4975411876e78940d21096750d2ae
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726591"
---
# <a name="cordebugblockingobject-structure"></a><span data-ttu-id="3a8d2-102">Структура CorDebugBlockingObject</span><span class="sxs-lookup"><span data-stu-id="3a8d2-102">CorDebugBlockingObject Structure</span></span>

<span data-ttu-id="3a8d2-103">Определяет объект, который блокирует поток и конкретную причину блокировки потока.</span><span class="sxs-lookup"><span data-stu-id="3a8d2-103">Defines an object that is blocking a thread and the specific reason that the thread is blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a8d2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3a8d2-104">Syntax</span></span>  
  
```cpp  
Typedef struct CorDebugBlockingObject  
{  
ICorDebugValue pBlockingObject;  
DWORD dwTimeout;  
CorDebugBlockingReason blockingReason;  
}  CorDebugBlockingObject;  
```  
  
## <a name="members"></a><span data-ttu-id="3a8d2-105">Члены</span><span class="sxs-lookup"><span data-stu-id="3a8d2-105">Members</span></span>  
  
|<span data-ttu-id="3a8d2-106">Член</span><span class="sxs-lookup"><span data-stu-id="3a8d2-106">Member</span></span>|<span data-ttu-id="3a8d2-107">Описание</span><span class="sxs-lookup"><span data-stu-id="3a8d2-107">Description</span></span>|  
|------------|-----------------|  
|`pBlockingObject`|<span data-ttu-id="3a8d2-108">Объект, для которого блокируется поток.</span><span class="sxs-lookup"><span data-stu-id="3a8d2-108">The object on which the thread is blocking.</span></span> <span data-ttu-id="3a8d2-109">Этот объект допустим только в течение текущего синхронизированного состояния.</span><span class="sxs-lookup"><span data-stu-id="3a8d2-109">This object is valid only for the duration of the current synchronized state.</span></span> <span data-ttu-id="3a8d2-110">Если два потока блокируют один и тот же объект в одном и том же синхронизированном состоянии, то, возможно, предполагается, что метод [ICorDebugValue::](icordebugvalue-getaddress-method.md) GetObject возвратит одно и то же значение.</span><span class="sxs-lookup"><span data-stu-id="3a8d2-110">If two threads are blocking on the same object within the same synchronized state, you may expect the [ICorDebugValue::GetAddress](icordebugvalue-getaddress-method.md) method to return the same value.</span></span> <span data-ttu-id="3a8d2-111">Однако интерфейсы могут и не быть эквивалентными указателями.</span><span class="sxs-lookup"><span data-stu-id="3a8d2-111">However, the interfaces may or may not be pointer equivalent.</span></span>|  
|`dwTimeout`|<span data-ttu-id="3a8d2-112">Время ожидания (в миллисекундах), по истечении которого операция блокирования истечет или бесконечное значение, которое указывает, что время ожидания не истечет. Значение времени ожидания указывает общий период времени для блокирующей операции, а не оставшееся время.</span><span class="sxs-lookup"><span data-stu-id="3a8d2-112">The number of milliseconds before the blocking operation will time out, or the value INFINITE, which indicates that it will not time out. The time-out value specifies the total length of time for the blocking operation, not the time that is still remaining.</span></span>|  
|`blockingReason`|<span data-ttu-id="3a8d2-113">Причина, по которой поток блокируется для этого объекта.</span><span class="sxs-lookup"><span data-stu-id="3a8d2-113">The reason that the thread is blocked on this object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a8d2-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="3a8d2-114">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a8d2-115">Требования</span><span class="sxs-lookup"><span data-stu-id="3a8d2-115">Requirements</span></span>  

 <span data-ttu-id="3a8d2-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a8d2-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a8d2-117">**Заголовок:** CorDebug. idl</span><span class="sxs-lookup"><span data-stu-id="3a8d2-117">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="3a8d2-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a8d2-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3a8d2-119">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a8d2-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a8d2-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3a8d2-120">See also</span></span>

- [<span data-ttu-id="3a8d2-121">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="3a8d2-121">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="3a8d2-122">Отладка</span><span class="sxs-lookup"><span data-stu-id="3a8d2-122">Debugging</span></span>](index.md)
