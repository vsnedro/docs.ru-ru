---
title: Интерфейс ICorDebugProcess
ms.date: 03/30/2017
api_name:
- ICorDebugProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess
helpviewer_keywords:
- ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: be86f4b5-418a-4c5c-a67c-97148c65ed8c
topic_type:
- apiref
ms.openlocfilehash: ab48efccc88787f099a182627777db95304cdc3e
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212078"
---
# <a name="icordebugprocess-interface"></a><span data-ttu-id="08f53-102">Интерфейс ICorDebugProcess</span><span class="sxs-lookup"><span data-stu-id="08f53-102">ICorDebugProcess Interface</span></span>
<span data-ttu-id="08f53-103">Представляет процесс, выполняющий управляемый код.</span><span class="sxs-lookup"><span data-stu-id="08f53-103">Represents a process that is executing managed code.</span></span> <span data-ttu-id="08f53-104">Этот интерфейс является подклассом ICorDebugController.</span><span class="sxs-lookup"><span data-stu-id="08f53-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="08f53-105">Методы</span><span class="sxs-lookup"><span data-stu-id="08f53-105">Methods</span></span>  
  
|<span data-ttu-id="08f53-106">Метод</span><span class="sxs-lookup"><span data-stu-id="08f53-106">Method</span></span>|<span data-ttu-id="08f53-107">Описание</span><span class="sxs-lookup"><span data-stu-id="08f53-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="08f53-108">Метод ClearCurrentException</span><span class="sxs-lookup"><span data-stu-id="08f53-108">ClearCurrentException Method</span></span>](icordebugprocess-clearcurrentexception-method.md)|<span data-ttu-id="08f53-109">Очищает текущее неуправляемое исключение для данного потока.</span><span class="sxs-lookup"><span data-stu-id="08f53-109">Clears the current unmanaged exception on the given thread.</span></span>|  
|[<span data-ttu-id="08f53-110">Метод EnableLogMessages</span><span class="sxs-lookup"><span data-stu-id="08f53-110">EnableLogMessages Method</span></span>](icordebugprocess-enablelogmessages-method.md)|<span data-ttu-id="08f53-111">Включает и отключает отправку сообщений журнала отладчику.</span><span class="sxs-lookup"><span data-stu-id="08f53-111">Enables and disables the sending of log messages to the debugger.</span></span>|  
|[<span data-ttu-id="08f53-112">Метод EnumerateAppDomains</span><span class="sxs-lookup"><span data-stu-id="08f53-112">EnumerateAppDomains Method</span></span>](icordebugprocess-enumerateappdomains-method.md)|<span data-ttu-id="08f53-113">Перечисляет все домены приложений в процессе.</span><span class="sxs-lookup"><span data-stu-id="08f53-113">Enumerates all of the application domains in the process.</span></span>|  
|[<span data-ttu-id="08f53-114">Метод EnumerateObjects</span><span class="sxs-lookup"><span data-stu-id="08f53-114">EnumerateObjects Method</span></span>](icordebugprocess-enumerateobjects-method.md)|<span data-ttu-id="08f53-115">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="08f53-115">Not implemented.</span></span>|  
|[<span data-ttu-id="08f53-116">Метод GetHandle</span><span class="sxs-lookup"><span data-stu-id="08f53-116">GetHandle Method</span></span>](icordebugprocess-gethandle-method.md)|<span data-ttu-id="08f53-117">Возвращает маркер процесса.</span><span class="sxs-lookup"><span data-stu-id="08f53-117">Gets a handle to the process.</span></span>|  
|[<span data-ttu-id="08f53-118">Метод GetHelperThreadID</span><span class="sxs-lookup"><span data-stu-id="08f53-118">GetHelperThreadID Method</span></span>](icordebugprocess-gethelperthreadid-method.md)|<span data-ttu-id="08f53-119">Возвращает идентификатор потока операционной системы (ОС) для внутреннего вспомогательного потока отладчика.</span><span class="sxs-lookup"><span data-stu-id="08f53-119">Gets the operating system (OS) thread ID for the debugger's internal helper thread.</span></span>|  
|[<span data-ttu-id="08f53-120">Метод GetID</span><span class="sxs-lookup"><span data-stu-id="08f53-120">GetID Method</span></span>](icordebugprocess-getid-method.md)|<span data-ttu-id="08f53-121">Возвращает идентификатор операционной системы (ОС) процесса.</span><span class="sxs-lookup"><span data-stu-id="08f53-121">Gets the operating system (OS) ID of the process.</span></span>|  
|[<span data-ttu-id="08f53-122">Метод GetObject</span><span class="sxs-lookup"><span data-stu-id="08f53-122">GetObject Method</span></span>](icordebugprocess-getobject-method.md)|<span data-ttu-id="08f53-123">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="08f53-123">Not implemented.</span></span>|  
|[<span data-ttu-id="08f53-124">Метод GetThread</span><span class="sxs-lookup"><span data-stu-id="08f53-124">GetThread Method</span></span>](icordebugprocess-getthread-method.md)|<span data-ttu-id="08f53-125">Возвращает экземпляр ICorDebugThread с указанным ИДЕНТИФИКАТОРом потока ОС.</span><span class="sxs-lookup"><span data-stu-id="08f53-125">Gets the ICorDebugThread instance that has the specified OS thread ID.</span></span>|  
|[<span data-ttu-id="08f53-126">Метод GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="08f53-126">GetThreadContext Method</span></span>](icordebugprocess-getthreadcontext-method.md)|<span data-ttu-id="08f53-127">Возвращает контекст для заданного потока.</span><span class="sxs-lookup"><span data-stu-id="08f53-127">Gets the context for the given thread.</span></span>|  
|[<span data-ttu-id="08f53-128">Метод IsOSSuspended</span><span class="sxs-lookup"><span data-stu-id="08f53-128">IsOSSuspended Method</span></span>](icordebugprocess-isossuspended-method.md)|<span data-ttu-id="08f53-129">Определяет, был ли поток приостановлен в результате остановки процесса отладчиком.</span><span class="sxs-lookup"><span data-stu-id="08f53-129">Determines whether the thread has been suspended as a result of the debugger stopping the process.</span></span>|  
|[<span data-ttu-id="08f53-130">Метод IsTransitionStub</span><span class="sxs-lookup"><span data-stu-id="08f53-130">IsTransitionStub Method</span></span>](icordebugprocess-istransitionstub-method.md)|<span data-ttu-id="08f53-131">Определяет, находится ли адрес в заглушке, что приведет к переходу в управляемый код.</span><span class="sxs-lookup"><span data-stu-id="08f53-131">Determines whether an address is inside a stub that will cause a transition to managed code.</span></span>|  
|[<span data-ttu-id="08f53-132">Метод ModifyLogSwitch</span><span class="sxs-lookup"><span data-stu-id="08f53-132">ModifyLogSwitch Method</span></span>](icordebugprocess-modifylogswitch-method.md)|<span data-ttu-id="08f53-133">Задает уровень серьезности указанного переключателя журнала.</span><span class="sxs-lookup"><span data-stu-id="08f53-133">Sets the severity level of the specified log switch.</span></span>|  
|[<span data-ttu-id="08f53-134">Метод ReadMemory</span><span class="sxs-lookup"><span data-stu-id="08f53-134">ReadMemory Method</span></span>](icordebugprocess-readmemory-method.md)|<span data-ttu-id="08f53-135">Считывает память из процесса.</span><span class="sxs-lookup"><span data-stu-id="08f53-135">Reads memory from the process.</span></span>|  
|[<span data-ttu-id="08f53-136">Метод SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="08f53-136">SetThreadContext Method</span></span>](icordebugprocess-setthreadcontext-method.md)|<span data-ttu-id="08f53-137">Задает контекст для заданного потока.</span><span class="sxs-lookup"><span data-stu-id="08f53-137">Sets the context for the given thread.</span></span>|  
|[<span data-ttu-id="08f53-138">Метод ThreadForFiberCookie</span><span class="sxs-lookup"><span data-stu-id="08f53-138">ThreadForFiberCookie Method</span></span>](icordebugprocess-threadforfibercookie-method.md)|<span data-ttu-id="08f53-139">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="08f53-139">Deprecated.</span></span>|  
|[<span data-ttu-id="08f53-140">Метод WriteMemory</span><span class="sxs-lookup"><span data-stu-id="08f53-140">WriteMemory Method</span></span>](icordebugprocess-writememory-method.md)|<span data-ttu-id="08f53-141">Записывает данные в область памяти в процессе.</span><span class="sxs-lookup"><span data-stu-id="08f53-141">Writes data to an area of memory in the process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08f53-142">Remarks</span><span class="sxs-lookup"><span data-stu-id="08f53-142">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="08f53-143">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="08f53-143">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08f53-144">Требования</span><span class="sxs-lookup"><span data-stu-id="08f53-144">Requirements</span></span>  
 <span data-ttu-id="08f53-145">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08f53-145">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08f53-146">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="08f53-146">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="08f53-147">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08f53-147">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08f53-148">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08f53-148">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08f53-149">См. также</span><span class="sxs-lookup"><span data-stu-id="08f53-149">See also</span></span>

- [<span data-ttu-id="08f53-150">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="08f53-150">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="08f53-151">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="08f53-151">Debugging Interfaces</span></span>](debugging-interfaces.md)
