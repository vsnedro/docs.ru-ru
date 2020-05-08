---
title: Интерфейс ICorDebugController
ms.date: 03/30/2017
api_name:
- ICorDebugController
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController
helpviewer_keywords:
- ICorDebugController interface [.NET Framework debugging]
ms.assetid: dbb1c4dc-269a-459b-ab1d-6c70788782ce
topic_type:
- apiref
ms.openlocfilehash: e494bbb24e8f2245593e7945625e72e70ae1dde5
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82892772"
---
# <a name="icordebugcontroller-interface"></a><span data-ttu-id="55686-102">Интерфейс ICorDebugController</span><span class="sxs-lookup"><span data-stu-id="55686-102">ICorDebugController Interface</span></span>

<span data-ttu-id="55686-103">Представляет область (<xref:System.Diagnostics.Process> или <xref:System.AppDomain>), в которой можно осуществлять управление контекстом выполнения кода.</span><span class="sxs-lookup"><span data-stu-id="55686-103">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="55686-104">Методы</span><span class="sxs-lookup"><span data-stu-id="55686-104">Methods</span></span>  
  
|<span data-ttu-id="55686-105">Метод</span><span class="sxs-lookup"><span data-stu-id="55686-105">Method</span></span>|<span data-ttu-id="55686-106">Описание</span><span class="sxs-lookup"><span data-stu-id="55686-106">Description</span></span>|  
|------------|-----------------|  
|`ICorDebugController::CanCommitChanges`|<span data-ttu-id="55686-107">Этот метод устарел.</span><span class="sxs-lookup"><span data-stu-id="55686-107">This method is obsolete.</span></span>|  
|`ICorDebugController::CommitChanges`|<span data-ttu-id="55686-108">Этот метод устарел.</span><span class="sxs-lookup"><span data-stu-id="55686-108">This method is obsolete.</span></span>|  
|[<span data-ttu-id="55686-109">Метод Continue</span><span class="sxs-lookup"><span data-stu-id="55686-109">Continue Method</span></span>](icordebugcontroller-continue-method.md)|<span data-ttu-id="55686-110">Возобновляет выполнение управляемых потоков после вызова [ICorDebugController:: останавливаться](icordebugcontroller-stop-method.md).</span><span class="sxs-lookup"><span data-stu-id="55686-110">Resumes execution of managed threads after a call to [ICorDebugController::Stop](icordebugcontroller-stop-method.md).</span></span>|  
|[<span data-ttu-id="55686-111">Метод Detach</span><span class="sxs-lookup"><span data-stu-id="55686-111">Detach Method</span></span>](icordebugcontroller-detach-method.md)|<span data-ttu-id="55686-112">Отсоединяет отладчик от процесса или домена приложения.</span><span class="sxs-lookup"><span data-stu-id="55686-112">Detaches the debugger from the process or application domain.</span></span>|  
|[<span data-ttu-id="55686-113">Метод EnumerateThreads</span><span class="sxs-lookup"><span data-stu-id="55686-113">EnumerateThreads Method</span></span>](icordebugcontroller-enumeratethreads-method.md)|<span data-ttu-id="55686-114">Возвращает перечислитель для активных управляемых потоков в процессе.</span><span class="sxs-lookup"><span data-stu-id="55686-114">Gets an enumerator for the active managed threads in the process.</span></span>|  
|[<span data-ttu-id="55686-115">Метод HasQueuedCallbacks</span><span class="sxs-lookup"><span data-stu-id="55686-115">HasQueuedCallbacks Method</span></span>](icordebugcontroller-hasqueuedcallbacks-method.md)|<span data-ttu-id="55686-116">Возвращает значение, указывающее, находятся ли в очереди управляемые обратные вызовы для указанного потока.</span><span class="sxs-lookup"><span data-stu-id="55686-116">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>|  
|[<span data-ttu-id="55686-117">Метод IsRunning</span><span class="sxs-lookup"><span data-stu-id="55686-117">IsRunning Method</span></span>](icordebugcontroller-isrunning-method.md)|<span data-ttu-id="55686-118">Возвращает значение, указывающее, выполняются ли в настоящий момент потоки в процессе.</span><span class="sxs-lookup"><span data-stu-id="55686-118">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>|  
|[<span data-ttu-id="55686-119">Метод SetAllThreadsDebugState</span><span class="sxs-lookup"><span data-stu-id="55686-119">SetAllThreadsDebugState Method</span></span>](icordebugcontroller-setallthreadsdebugstate-method.md)|<span data-ttu-id="55686-120">Задает состояние отладки всех управляемых потоков в процессе.</span><span class="sxs-lookup"><span data-stu-id="55686-120">Sets the debug state of all managed threads in the process.</span></span>|  
|[<span data-ttu-id="55686-121">Метод Stop</span><span class="sxs-lookup"><span data-stu-id="55686-121">Stop Method</span></span>](icordebugcontroller-stop-method.md)|<span data-ttu-id="55686-122">Выполняет совместную работу во всех потоках, где выполняется управляемый код в процессе.</span><span class="sxs-lookup"><span data-stu-id="55686-122">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>|  
|[<span data-ttu-id="55686-123">Метод Terminate</span><span class="sxs-lookup"><span data-stu-id="55686-123">Terminate Method</span></span>](icordebugcontroller-terminate-method.md)|<span data-ttu-id="55686-124">Завершает процесс с указанным кодом выхода.</span><span class="sxs-lookup"><span data-stu-id="55686-124">Terminates the process with the specified exit code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55686-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="55686-125">Remarks</span></span>  
 <span data-ttu-id="55686-126">Если `ICorDebugController` управляет процессом, область включает все потоки процесса.</span><span class="sxs-lookup"><span data-stu-id="55686-126">If `ICorDebugController` is controlling a process, the scope includes all threads of the process.</span></span> <span data-ttu-id="55686-127">Если `ICorDebugController` управляет доменом приложения, область включает только потоки этого конкретного домена приложения.</span><span class="sxs-lookup"><span data-stu-id="55686-127">If `ICorDebugController` is controlling an application domain, the scope includes only the threads of that particular application domain.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="55686-128">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="55686-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55686-129">Требования</span><span class="sxs-lookup"><span data-stu-id="55686-129">Requirements</span></span>  
 <span data-ttu-id="55686-130">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55686-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55686-131">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="55686-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="55686-132">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55686-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55686-133">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55686-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55686-134">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="55686-134">See also</span></span>

- [<span data-ttu-id="55686-135">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="55686-135">Debugging Interfaces</span></span>](debugging-interfaces.md)
