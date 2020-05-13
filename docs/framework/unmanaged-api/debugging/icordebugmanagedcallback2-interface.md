---
title: Интерфейс ICorDebugManagedCallback2
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2
helpviewer_keywords:
- ICorDebugManagedCallback2 interface [.NET Framework debugging]
ms.assetid: cf7b7cfa-1c4b-4d8c-be70-4f9ed15a788b
topic_type:
- apiref
ms.openlocfilehash: b00be90316598e458f01f6cd440d0ad0a2e79c50
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212364"
---
# <a name="icordebugmanagedcallback2-interface"></a><span data-ttu-id="9ca23-102">Интерфейс ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="9ca23-102">ICorDebugManagedCallback2 Interface</span></span>
<span data-ttu-id="9ca23-103">Предоставляет методы для поддержки обработки исключений отладчика и управляемых помощников по отладке (MDA).</span><span class="sxs-lookup"><span data-stu-id="9ca23-103">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> <span data-ttu-id="9ca23-104">`ICorDebugManagedCallback2`является логическим расширением интерфейса [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="9ca23-104">`ICorDebugManagedCallback2` is a logical extension of the [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9ca23-105">Методы</span><span class="sxs-lookup"><span data-stu-id="9ca23-105">Methods</span></span>  
  
|<span data-ttu-id="9ca23-106">Метод</span><span class="sxs-lookup"><span data-stu-id="9ca23-106">Method</span></span>|<span data-ttu-id="9ca23-107">Описание</span><span class="sxs-lookup"><span data-stu-id="9ca23-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9ca23-108">Метод ChangeConnection</span><span class="sxs-lookup"><span data-stu-id="9ca23-108">ChangeConnection Method</span></span>](icordebugmanagedcallback2-changeconnection-method.md)|<span data-ttu-id="9ca23-109">Уведомляет отладчик о том, что набор задач, связанных с указанным соединением, изменился.</span><span class="sxs-lookup"><span data-stu-id="9ca23-109">Notifies the debugger that the set of tasks associated with the specified connection has changed.</span></span>|  
|[<span data-ttu-id="9ca23-110">Метод CreateConnection</span><span class="sxs-lookup"><span data-stu-id="9ca23-110">CreateConnection Method</span></span>](icordebugmanagedcallback2-createconnection-method.md)|<span data-ttu-id="9ca23-111">Уведомляет отладчик о создании нового соединения.</span><span class="sxs-lookup"><span data-stu-id="9ca23-111">Notifies the debugger that a new connection has been created.</span></span>|  
|[<span data-ttu-id="9ca23-112">Метод DestroyConnection</span><span class="sxs-lookup"><span data-stu-id="9ca23-112">DestroyConnection Method</span></span>](icordebugmanagedcallback2-destroyconnection-method.md)|<span data-ttu-id="9ca23-113">Уведомляет отладчик о завершении указанного соединения.</span><span class="sxs-lookup"><span data-stu-id="9ca23-113">Notifies the debugger that the specified connection has been terminated.</span></span>|  
|[<span data-ttu-id="9ca23-114">Метод Exception</span><span class="sxs-lookup"><span data-stu-id="9ca23-114">Exception Method</span></span>](icordebugmanagedcallback2-exception-method.md)|<span data-ttu-id="9ca23-115">Уведомляет отладчик о запуске поиска обработчика исключений.</span><span class="sxs-lookup"><span data-stu-id="9ca23-115">Notifies the debugger that a search for an exception handler has started.</span></span>|  
|[<span data-ttu-id="9ca23-116">Метод ExceptionUnwind</span><span class="sxs-lookup"><span data-stu-id="9ca23-116">ExceptionUnwind Method</span></span>](icordebugmanagedcallback2-exceptionunwind-method.md)|<span data-ttu-id="9ca23-117">Предоставляет уведомление о состоянии во время процесса очистки исключения.</span><span class="sxs-lookup"><span data-stu-id="9ca23-117">Provides a status notification during the exception unwinding process.</span></span>|  
|[<span data-ttu-id="9ca23-118">Метод FunctionRemapComplete</span><span class="sxs-lookup"><span data-stu-id="9ca23-118">FunctionRemapComplete Method</span></span>](icordebugmanagedcallback2-functionremapcomplete-method.md)|<span data-ttu-id="9ca23-119">Уведомляет отладчик о том, что выполнение кода переключено на новую версию измененной функции.</span><span class="sxs-lookup"><span data-stu-id="9ca23-119">Notifies the debugger that code execution has switched to a new version of an edited function.</span></span>|  
|[<span data-ttu-id="9ca23-120">Метод FunctionRemapOpportunity</span><span class="sxs-lookup"><span data-stu-id="9ca23-120">FunctionRemapOpportunity Method</span></span>](icordebugmanagedcallback2-functionremapopportunity-method.md)|<span data-ttu-id="9ca23-121">Уведомляет отладчик о том, что выполнение кода достигло точки последовательности в более ранней версии измененной функции.</span><span class="sxs-lookup"><span data-stu-id="9ca23-121">Notifies the debugger that code execution has reached a sequence point in an older version of an edited function.</span></span>|  
|[<span data-ttu-id="9ca23-122">Метод MDANotification</span><span class="sxs-lookup"><span data-stu-id="9ca23-122">MDANotification Method</span></span>](icordebugmanagedcallback2-mdanotification-method.md)|<span data-ttu-id="9ca23-123">Предоставляет уведомление о том, что при выполнении кода было обнаружено сообщение MDA.</span><span class="sxs-lookup"><span data-stu-id="9ca23-123">Provides notification that code execution has encountered a managed debugging assistant (MDA) message.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ca23-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="9ca23-124">Remarks</span></span>  
 <span data-ttu-id="9ca23-125">`ICorDebugManagedCallback2`Интерфейс расширяет `ICorDebugManagedCallback` интерфейс для поддержки новых событий отладки, появившихся в .NET Framework версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="9ca23-125">The `ICorDebugManagedCallback2` interface extends the `ICorDebugManagedCallback` interface to handle new debug events introduced in the .NET Framework version 2.0.</span></span>  
  
 <span data-ttu-id="9ca23-126">`ICorDebugManagedCallback2`При отладке приложений .NET Framework 2,0 в отладчике должен быть реализован.</span><span class="sxs-lookup"><span data-stu-id="9ca23-126">A debugger must implement `ICorDebugManagedCallback2` if it is debugging .NET Framework 2.0 applications.</span></span> <span data-ttu-id="9ca23-127">Экземпляр `ICorDebugManagedCallback` или `ICorDebugManagedCallback2` передается как объект обратного вызова в [ICorDebug:: SetManagedHandler](icordebug-setmanagedhandler-method.md).</span><span class="sxs-lookup"><span data-stu-id="9ca23-127">An instance of `ICorDebugManagedCallback` or `ICorDebugManagedCallback2` is passed as the callback object to [ICorDebug::SetManagedHandler](icordebug-setmanagedhandler-method.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9ca23-128">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="9ca23-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ca23-129">Требования</span><span class="sxs-lookup"><span data-stu-id="9ca23-129">Requirements</span></span>  
 <span data-ttu-id="9ca23-130">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ca23-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ca23-131">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9ca23-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ca23-132">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ca23-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ca23-133">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ca23-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ca23-134">См. также</span><span class="sxs-lookup"><span data-stu-id="9ca23-134">See also</span></span>

- [<span data-ttu-id="9ca23-135">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="9ca23-135">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="9ca23-136">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="9ca23-136">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="9ca23-137">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="9ca23-137">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
