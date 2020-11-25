---
title: Метод ICorProfilerCallback::RemotingClientInvocationStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientInvocationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientInvocationStarted
helpviewer_keywords:
- RemotingClientInvocationStarted method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientInvocationStarted method [.NET Framework profiling]
ms.assetid: 796b63f3-c809-47f1-89cc-b23ad8eb5e79
topic_type:
- apiref
ms.openlocfilehash: 22b9970556dd9d8b5070f38a7712462aa5a4aae2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720169"
---
# <a name="icorprofilercallbackremotingclientinvocationstarted-method"></a><span data-ttu-id="48ba8-102">Метод ICorProfilerCallback::RemotingClientInvocationStarted</span><span class="sxs-lookup"><span data-stu-id="48ba8-102">ICorProfilerCallback::RemotingClientInvocationStarted Method</span></span>

<span data-ttu-id="48ba8-103">Уведомляет профилировщик о начале удаленного вызова.</span><span class="sxs-lookup"><span data-stu-id="48ba8-103">Notifies the profiler that a remoting call has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48ba8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="48ba8-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientInvocationStarted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="48ba8-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="48ba8-105">Remarks</span></span>  

 <span data-ttu-id="48ba8-106">Это событие одинаково для синхронных и асинхронных вызовов.</span><span class="sxs-lookup"><span data-stu-id="48ba8-106">This event is the same for synchronous and asynchronous calls.</span></span>  
  
 <span data-ttu-id="48ba8-107">Каждая из следующих пар обратных вызовов будет выполняться в одном потоке:</span><span class="sxs-lookup"><span data-stu-id="48ba8-107">Each of the following pairs of callbacks will occur on the same thread:</span></span>  
  
- <span data-ttu-id="48ba8-108">`RemotingClientInvocationStarted` и [ICorProfilerCallback:: RemotingClientSendingMessage](icorprofilercallback-remotingclientsendingmessage-method.md)</span><span class="sxs-lookup"><span data-stu-id="48ba8-108">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](icorprofilercallback-remotingclientsendingmessage-method.md)</span></span>  
  
- <span data-ttu-id="48ba8-109">[ICorProfilerCallback:: ремотингклиентрецеивингрепли](icorprofilercallback-remotingclientreceivingreply-method.md) и [ICorProfilerCallback:: ремотингклиентинвокатионфинишед](icorprofilercallback-remotingclientinvocationfinished-method.md)</span><span class="sxs-lookup"><span data-stu-id="48ba8-109">[ICorProfilerCallback::RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](icorprofilercallback-remotingclientinvocationfinished-method.md)</span></span>  
  
- <span data-ttu-id="48ba8-110">[ICorProfilerCallback:: RemotingServerInvocationReturned](icorprofilercallback-remotingserverinvocationreturned-method.md) и [ICorProfilerCallback:: RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md)</span><span class="sxs-lookup"><span data-stu-id="48ba8-110">[ICorProfilerCallback::RemotingServerInvocationReturned](icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md)</span></span>  
  
 <span data-ttu-id="48ba8-111">При использовании обратных вызовов удаленного взаимодействия следует учитывать следующие моменты.</span><span class="sxs-lookup"><span data-stu-id="48ba8-111">You should be aware of the following issues with the remoting callbacks:</span></span>  
  
- <span data-ttu-id="48ba8-112">Выполнение функции удаленного взаимодействия не отражается API-интерфейсом профилировщика, поэтому уведомления для функций, которые вызываются из клиента и выполняются на сервере, не получаются должным образом.</span><span class="sxs-lookup"><span data-stu-id="48ba8-112">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span></span> <span data-ttu-id="48ba8-113">Фактический вызов происходит через прокси-объект; для профилировщика отображается, что определенные функции JIT-скомпилированы, но никогда не используются.</span><span class="sxs-lookup"><span data-stu-id="48ba8-113">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span></span>  
  
- <span data-ttu-id="48ba8-114">Профилировщик не получает точные уведомления о событиях асинхронного удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="48ba8-114">The profiler does not receive accurate notifications for asynchronous remoting events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48ba8-115">Требования</span><span class="sxs-lookup"><span data-stu-id="48ba8-115">Requirements</span></span>  

 <span data-ttu-id="48ba8-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48ba8-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48ba8-117">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="48ba8-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="48ba8-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48ba8-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48ba8-119">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48ba8-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48ba8-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="48ba8-120">See also</span></span>

- [<span data-ttu-id="48ba8-121">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="48ba8-121">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
