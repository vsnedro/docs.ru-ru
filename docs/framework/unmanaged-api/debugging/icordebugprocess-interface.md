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
ms.openlocfilehash: 7f9d4ac99234545ef75d9b91e6e84f79a133ffef
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95694923"
---
# <a name="icordebugprocess-interface"></a><span data-ttu-id="81feb-102">Интерфейс ICorDebugProcess</span><span class="sxs-lookup"><span data-stu-id="81feb-102">ICorDebugProcess Interface</span></span>

<span data-ttu-id="81feb-103">Представляет процесс, выполняющий управляемый код.</span><span class="sxs-lookup"><span data-stu-id="81feb-103">Represents a process that is executing managed code.</span></span> <span data-ttu-id="81feb-104">Этот интерфейс является подклассом ICorDebugController.</span><span class="sxs-lookup"><span data-stu-id="81feb-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="81feb-105">Методы</span><span class="sxs-lookup"><span data-stu-id="81feb-105">Methods</span></span>  
  
|<span data-ttu-id="81feb-106">Метод</span><span class="sxs-lookup"><span data-stu-id="81feb-106">Method</span></span>|<span data-ttu-id="81feb-107">Описание</span><span class="sxs-lookup"><span data-stu-id="81feb-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="81feb-108">Метод ClearCurrentException</span><span class="sxs-lookup"><span data-stu-id="81feb-108">ClearCurrentException Method</span></span>](icordebugprocess-clearcurrentexception-method.md)|<span data-ttu-id="81feb-109">Очищает текущее неуправляемое исключение для данного потока.</span><span class="sxs-lookup"><span data-stu-id="81feb-109">Clears the current unmanaged exception on the given thread.</span></span>|  
|[<span data-ttu-id="81feb-110">Метод EnableLogMessages</span><span class="sxs-lookup"><span data-stu-id="81feb-110">EnableLogMessages Method</span></span>](icordebugprocess-enablelogmessages-method.md)|<span data-ttu-id="81feb-111">Включает и отключает отправку сообщений журнала отладчику.</span><span class="sxs-lookup"><span data-stu-id="81feb-111">Enables and disables the sending of log messages to the debugger.</span></span>|  
|[<span data-ttu-id="81feb-112">Метод EnumerateAppDomains</span><span class="sxs-lookup"><span data-stu-id="81feb-112">EnumerateAppDomains Method</span></span>](icordebugprocess-enumerateappdomains-method.md)|<span data-ttu-id="81feb-113">Перечисляет все домены приложений в процессе.</span><span class="sxs-lookup"><span data-stu-id="81feb-113">Enumerates all of the application domains in the process.</span></span>|  
|[<span data-ttu-id="81feb-114">Метод EnumerateObjects</span><span class="sxs-lookup"><span data-stu-id="81feb-114">EnumerateObjects Method</span></span>](icordebugprocess-enumerateobjects-method.md)|<span data-ttu-id="81feb-115">Не реализован.</span><span class="sxs-lookup"><span data-stu-id="81feb-115">Not implemented.</span></span>|  
|[<span data-ttu-id="81feb-116">Метод GetHandle</span><span class="sxs-lookup"><span data-stu-id="81feb-116">GetHandle Method</span></span>](icordebugprocess-gethandle-method.md)|<span data-ttu-id="81feb-117">Возвращает маркер процесса.</span><span class="sxs-lookup"><span data-stu-id="81feb-117">Gets a handle to the process.</span></span>|  
|[<span data-ttu-id="81feb-118">Метод GetHelperThreadID</span><span class="sxs-lookup"><span data-stu-id="81feb-118">GetHelperThreadID Method</span></span>](icordebugprocess-gethelperthreadid-method.md)|<span data-ttu-id="81feb-119">Возвращает идентификатор потока операционной системы (ОС) для внутреннего вспомогательного потока отладчика.</span><span class="sxs-lookup"><span data-stu-id="81feb-119">Gets the operating system (OS) thread ID for the debugger's internal helper thread.</span></span>|  
|[<span data-ttu-id="81feb-120">Метод GetID</span><span class="sxs-lookup"><span data-stu-id="81feb-120">GetID Method</span></span>](icordebugprocess-getid-method.md)|<span data-ttu-id="81feb-121">Возвращает идентификатор операционной системы (ОС) процесса.</span><span class="sxs-lookup"><span data-stu-id="81feb-121">Gets the operating system (OS) ID of the process.</span></span>|  
|[<span data-ttu-id="81feb-122">Метод GetObject</span><span class="sxs-lookup"><span data-stu-id="81feb-122">GetObject Method</span></span>](icordebugprocess-getobject-method.md)|<span data-ttu-id="81feb-123">Не реализован.</span><span class="sxs-lookup"><span data-stu-id="81feb-123">Not implemented.</span></span>|  
|[<span data-ttu-id="81feb-124">Метод GetThread</span><span class="sxs-lookup"><span data-stu-id="81feb-124">GetThread Method</span></span>](icordebugprocess-getthread-method.md)|<span data-ttu-id="81feb-125">Возвращает экземпляр ICorDebugThread с указанным ИДЕНТИФИКАТОРом потока ОС.</span><span class="sxs-lookup"><span data-stu-id="81feb-125">Gets the ICorDebugThread instance that has the specified OS thread ID.</span></span>|  
|[<span data-ttu-id="81feb-126">Метод GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="81feb-126">GetThreadContext Method</span></span>](icordebugprocess-getthreadcontext-method.md)|<span data-ttu-id="81feb-127">Возвращает контекст для заданного потока.</span><span class="sxs-lookup"><span data-stu-id="81feb-127">Gets the context for the given thread.</span></span>|  
|[<span data-ttu-id="81feb-128">Метод IsOSSuspended</span><span class="sxs-lookup"><span data-stu-id="81feb-128">IsOSSuspended Method</span></span>](icordebugprocess-isossuspended-method.md)|<span data-ttu-id="81feb-129">Определяет, был ли поток приостановлен в результате остановки процесса отладчиком.</span><span class="sxs-lookup"><span data-stu-id="81feb-129">Determines whether the thread has been suspended as a result of the debugger stopping the process.</span></span>|  
|[<span data-ttu-id="81feb-130">Метод IsTransitionStub</span><span class="sxs-lookup"><span data-stu-id="81feb-130">IsTransitionStub Method</span></span>](icordebugprocess-istransitionstub-method.md)|<span data-ttu-id="81feb-131">Определяет, находится ли адрес в заглушке, что приведет к переходу в управляемый код.</span><span class="sxs-lookup"><span data-stu-id="81feb-131">Determines whether an address is inside a stub that will cause a transition to managed code.</span></span>|  
|[<span data-ttu-id="81feb-132">Метод ModifyLogSwitch</span><span class="sxs-lookup"><span data-stu-id="81feb-132">ModifyLogSwitch Method</span></span>](icordebugprocess-modifylogswitch-method.md)|<span data-ttu-id="81feb-133">Задает уровень серьезности указанного переключателя журнала.</span><span class="sxs-lookup"><span data-stu-id="81feb-133">Sets the severity level of the specified log switch.</span></span>|  
|[<span data-ttu-id="81feb-134">Метод ReadMemory</span><span class="sxs-lookup"><span data-stu-id="81feb-134">ReadMemory Method</span></span>](icordebugprocess-readmemory-method.md)|<span data-ttu-id="81feb-135">Считывает память из процесса.</span><span class="sxs-lookup"><span data-stu-id="81feb-135">Reads memory from the process.</span></span>|  
|[<span data-ttu-id="81feb-136">Метод SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="81feb-136">SetThreadContext Method</span></span>](icordebugprocess-setthreadcontext-method.md)|<span data-ttu-id="81feb-137">Задает контекст для заданного потока.</span><span class="sxs-lookup"><span data-stu-id="81feb-137">Sets the context for the given thread.</span></span>|  
|[<span data-ttu-id="81feb-138">Метод ThreadForFiberCookie</span><span class="sxs-lookup"><span data-stu-id="81feb-138">ThreadForFiberCookie Method</span></span>](icordebugprocess-threadforfibercookie-method.md)|<span data-ttu-id="81feb-139">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="81feb-139">Deprecated.</span></span>|  
|[<span data-ttu-id="81feb-140">Метод WriteMemory</span><span class="sxs-lookup"><span data-stu-id="81feb-140">WriteMemory Method</span></span>](icordebugprocess-writememory-method.md)|<span data-ttu-id="81feb-141">Записывает данные в область памяти в процессе.</span><span class="sxs-lookup"><span data-stu-id="81feb-141">Writes data to an area of memory in the process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81feb-142">Комментарии</span><span class="sxs-lookup"><span data-stu-id="81feb-142">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="81feb-143">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="81feb-143">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81feb-144">Требования</span><span class="sxs-lookup"><span data-stu-id="81feb-144">Requirements</span></span>  

 <span data-ttu-id="81feb-145">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81feb-145">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81feb-146">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="81feb-146">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="81feb-147">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81feb-147">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81feb-148">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81feb-148">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81feb-149">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="81feb-149">See also</span></span>

- [<span data-ttu-id="81feb-150">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="81feb-150">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="81feb-151">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="81feb-151">Debugging Interfaces</span></span>](debugging-interfaces.md)
