---
title: Метод ICorProfilerCallback::RemotingServerReceivingMessage
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerReceivingMessage
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage
helpviewer_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage method [.NET Framework profiling]
- RemotingServerReceivingMessage method [.NET Framework profiling]
ms.assetid: 5604d21f-e6b7-490e-b469-42122a7568e1
topic_type:
- apiref
ms.openlocfilehash: 0fc84a15d3250d5103c1dbc6486960f0ea780a2b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676820"
---
# <a name="icorprofilercallbackremotingserverreceivingmessage-method"></a><span data-ttu-id="1aabe-102">Метод ICorProfilerCallback::RemotingServerReceivingMessage</span><span class="sxs-lookup"><span data-stu-id="1aabe-102">ICorProfilerCallback::RemotingServerReceivingMessage Method</span></span>

<span data-ttu-id="1aabe-103">Уведомляет профилировщик о том, что процесс получил удаленный вызов метода или запрос на активацию.</span><span class="sxs-lookup"><span data-stu-id="1aabe-103">Notifies the profiler that the process has received a remote method invocation or activation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1aabe-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1aabe-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1aabe-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1aabe-105">Parameters</span></span>  

 `pCookie`  
 <span data-ttu-id="1aabe-106">окне Значение, которое будет соответствовать значению, указанному в параметре [ICorProfilerCallback:: RemotingClientSendingMessage](icorprofilercallback-remotingclientsendingmessage-method.md) в следующих условиях:</span><span class="sxs-lookup"><span data-stu-id="1aabe-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingClientSendingMessage](icorprofilercallback-remotingclientsendingmessage-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="1aabe-107">Файлы Cookie GUID удаленного взаимодействия активны.</span><span class="sxs-lookup"><span data-stu-id="1aabe-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="1aabe-108">Канал проходит успешную передачу сообщения.</span><span class="sxs-lookup"><span data-stu-id="1aabe-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="1aabe-109">Файлы Cookie GUID активны в процессе на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="1aabe-109">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="1aabe-110">Это позволяет легко связывать вызовы удаленного взаимодействия и создавать логические стеки вызовов.</span><span class="sxs-lookup"><span data-stu-id="1aabe-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="1aabe-111">окне Значение, равное, `true` Если вызов является асинхронным; в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="1aabe-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1aabe-112">Комментарии</span><span class="sxs-lookup"><span data-stu-id="1aabe-112">Remarks</span></span>  

 <span data-ttu-id="1aabe-113">Если запрос сообщения является асинхронным, запрос может обслуживаться любым произвольным потоком.</span><span class="sxs-lookup"><span data-stu-id="1aabe-113">If the message request is asynchronous, the request can be serviced by any arbitrary thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1aabe-114">Требования</span><span class="sxs-lookup"><span data-stu-id="1aabe-114">Requirements</span></span>  

 <span data-ttu-id="1aabe-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1aabe-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1aabe-116">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1aabe-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1aabe-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1aabe-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1aabe-118">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1aabe-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1aabe-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1aabe-119">See also</span></span>

- [<span data-ttu-id="1aabe-120">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="1aabe-120">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
