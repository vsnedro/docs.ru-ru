---
title: Метод ICorDebugThread::SetDebugState
ms.date: 03/30/2017
api_name:
- ICorDebugThread.SetDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::SetDebugState
helpviewer_keywords:
- ICorDebugThread::SetDebugState method [.NET Framework debugging]
- SetDebugState method [.NET Framework debugging]
ms.assetid: 6382bdf6-d488-4952-b653-cb09b6e1c6c2
topic_type:
- apiref
ms.openlocfilehash: 05ae2791ee7f8bd31be38ec4d2117ddc3c2ea2bc
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83377947"
---
# <a name="icordebugthreadsetdebugstate-method"></a><span data-ttu-id="04ff7-102">Метод ICorDebugThread::SetDebugState</span><span class="sxs-lookup"><span data-stu-id="04ff7-102">ICorDebugThread::SetDebugState Method</span></span>
<span data-ttu-id="04ff7-103">Устанавливает флаги, описывающие состояние отладки этого ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="04ff7-103">Sets flags that describe the debugging state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04ff7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="04ff7-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDebugState (  
    [in] CorDebugThreadState state  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04ff7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="04ff7-105">Parameters</span></span>  
 `state`  
 <span data-ttu-id="04ff7-106">окне Побитовое сочетание значений перечисления Кордебугсреадстате, определяющих состояние отладки этого потока.</span><span class="sxs-lookup"><span data-stu-id="04ff7-106">[in] A bitwise combination of CorDebugThreadState enumeration values that specify the debugging state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04ff7-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="04ff7-107">Remarks</span></span>  
 <span data-ttu-id="04ff7-108">`SetDebugState`Задает текущее состояние отладки потока.</span><span class="sxs-lookup"><span data-stu-id="04ff7-108">`SetDebugState` sets the current debug state of the thread.</span></span> <span data-ttu-id="04ff7-109">("Текущее состояние отладки" представляет состояние отладки, если процесс должен быть продолжен, а не фактическое текущее состояние.) Нормальное значение для этого параметра — THREAD_RUN.</span><span class="sxs-lookup"><span data-stu-id="04ff7-109">(The "current debug state" represents the debug state if the process were to be continued, not the actual current state.) The normal value for this is THREAD_RUN.</span></span> <span data-ttu-id="04ff7-110">Только отладчик может повлиять на состояние отладки потока.</span><span class="sxs-lookup"><span data-stu-id="04ff7-110">Only the debugger can affect the debug state of a thread.</span></span> <span data-ttu-id="04ff7-111">Состояния отладки проявляются последними, поэтому, если вы хотите, чтобы поток THREAD_SUSPENDed более одного раза, можно установить его один раз, а затем не беспокоиться о нем.</span><span class="sxs-lookup"><span data-stu-id="04ff7-111">Debug states do last across continues, so if you want to keep a thread THREAD_SUSPENDed over multiple continues, you can set it once and thereafter not have to worry about it.</span></span> <span data-ttu-id="04ff7-112">Приостановка потоков и возобновление процесса могут привести к взаимоблокировке, хотя обычно маловероятно.</span><span class="sxs-lookup"><span data-stu-id="04ff7-112">Suspending threads and resuming the process can cause deadlocks, though it's usually unlikely.</span></span> <span data-ttu-id="04ff7-113">Это встроенное качество потоков и процессов, а именно-проектирование.</span><span class="sxs-lookup"><span data-stu-id="04ff7-113">This is an intrinsic quality of threads and processes and is by-design.</span></span> <span data-ttu-id="04ff7-114">Отладчик может асинхронно приостанавливать и возобновлять потоки, чтобы нарушить взаимоблокировку.</span><span class="sxs-lookup"><span data-stu-id="04ff7-114">A debugger can asynchronously break and resume the threads to break the deadlock.</span></span> <span data-ttu-id="04ff7-115">Если пользовательское состояние потока включает USER_UNSAFE_POINT, поток может блокировать сборку мусора (GC).</span><span class="sxs-lookup"><span data-stu-id="04ff7-115">If the thread's user state includes USER_UNSAFE_POINT, then the thread may block a garbage collection (GC).</span></span> <span data-ttu-id="04ff7-116">Это означает, что приостановленный поток имеет намного более высокий шанс возникновения взаимоблокировки.</span><span class="sxs-lookup"><span data-stu-id="04ff7-116">This means the suspended thread has a much higher chance of causing a deadlock.</span></span> <span data-ttu-id="04ff7-117">Это может не влиять на события отладки, уже поставленные в очередь.</span><span class="sxs-lookup"><span data-stu-id="04ff7-117">This may not affect debug events already queued.</span></span> <span data-ttu-id="04ff7-118">Таким образом, отладчик должен очистить всю очередь событий (вызвав [ICorDebugController:: хаскуеуедкаллбаккс](icordebugcontroller-hasqueuedcallbacks-method.md)) перед приостановкой или возобновлением потоков.</span><span class="sxs-lookup"><span data-stu-id="04ff7-118">Thus a debugger should drain the entire event queue (by calling [ICorDebugController::HasQueuedCallbacks](icordebugcontroller-hasqueuedcallbacks-method.md)) before suspending or resuming threads.</span></span> <span data-ttu-id="04ff7-119">В противном случае он может получить события в потоке, который предположительно уже приостановлен.</span><span class="sxs-lookup"><span data-stu-id="04ff7-119">Else it may get events on a thread that it believes it has already suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04ff7-120">Требования</span><span class="sxs-lookup"><span data-stu-id="04ff7-120">Requirements</span></span>  
 <span data-ttu-id="04ff7-121">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04ff7-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04ff7-122">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="04ff7-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="04ff7-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04ff7-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04ff7-124">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04ff7-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
