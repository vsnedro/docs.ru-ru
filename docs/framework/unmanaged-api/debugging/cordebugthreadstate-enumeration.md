---
title: Перечисление CorDebugThreadState
ms.date: 03/30/2017
api_name:
- CorDebugThreadState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugThreadState
helpviewer_keywords:
- CorDebugThreadState enumeration [.NET Framework debugging]
ms.assetid: a3ccdf18-4ec6-494d-9024-48e5c8c724f5
topic_type:
- apiref
ms.openlocfilehash: 5eee2aee5873fe512136bc5407e395acdc31af29
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722613"
---
# <a name="cordebugthreadstate-enumeration"></a><span data-ttu-id="d5de6-102">Перечисление CorDebugThreadState</span><span class="sxs-lookup"><span data-stu-id="d5de6-102">CorDebugThreadState Enumeration</span></span>

<span data-ttu-id="d5de6-103">Указывает состояние потока для отладки.</span><span class="sxs-lookup"><span data-stu-id="d5de6-103">Specifies the state of a thread for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5de6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d5de6-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugThreadState {  
    THREAD_RUN,  
    THREAD_SUSPEND  
} CorDebugThreadState;  
```  
  
## <a name="members"></a><span data-ttu-id="d5de6-105">Члены</span><span class="sxs-lookup"><span data-stu-id="d5de6-105">Members</span></span>  
  
|<span data-ttu-id="d5de6-106">Член</span><span class="sxs-lookup"><span data-stu-id="d5de6-106">Member</span></span>|<span data-ttu-id="d5de6-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d5de6-107">Description</span></span>|  
|------------|-----------------|  
|`THREAD_RUN`|<span data-ttu-id="d5de6-108">Поток выполняется свободно, если не происходит событие отладки.</span><span class="sxs-lookup"><span data-stu-id="d5de6-108">The thread runs freely, unless a debug event occurs.</span></span>|  
|`THREAD_SUSPEND`|<span data-ttu-id="d5de6-109">Поток не может быть запущен.</span><span class="sxs-lookup"><span data-stu-id="d5de6-109">The thread cannot run.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5de6-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="d5de6-110">Remarks</span></span>  

 <span data-ttu-id="d5de6-111">Отладчик использует `CorDebugThreadState` перечисление для управления выполнением потока.</span><span class="sxs-lookup"><span data-stu-id="d5de6-111">The debugger uses the `CorDebugThreadState` enumeration to control a thread's execution.</span></span> <span data-ttu-id="d5de6-112">Состояние потока можно задать с помощью метода [ICorDebugThread:: SetDebugState](icordebugthread-setdebugstate-method.md) или [ICorDebugController:: SetAllThreadsDebugState](icordebugcontroller-setallthreadsdebugstate-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d5de6-112">The state of a thread can be set by using the [ICorDebugThread::SetDebugState](icordebugthread-setdebugstate-method.md) or [ICorDebugController::SetAllThreadsDebugState](icordebugcontroller-setallthreadsdebugstate-method.md) method.</span></span>  
  
 <span data-ttu-id="d5de6-113">Обратный вызов, предоставленный [API размещения](../hosting/index.md) , позволяет передавать сообщения, поэтому прерывание состояния не требуется.</span><span class="sxs-lookup"><span data-stu-id="d5de6-113">A callback provided to the [hosting API](../hosting/index.md) enables message pumping, so an interrupted state is not needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5de6-114">Требования</span><span class="sxs-lookup"><span data-stu-id="d5de6-114">Requirements</span></span>  

 <span data-ttu-id="d5de6-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5de6-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5de6-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d5de6-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d5de6-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5de6-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5de6-118">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5de6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5de6-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d5de6-119">See also</span></span>

- [<span data-ttu-id="d5de6-120">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="d5de6-120">Debugging Enumerations</span></span>](debugging-enumerations.md)
