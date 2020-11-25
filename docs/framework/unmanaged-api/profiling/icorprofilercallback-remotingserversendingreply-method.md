---
title: Метод ICorProfilerCallback::RemotingServerSendingReply
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerSendingReply
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerSendingReply
helpviewer_keywords:
- RemotingServerSendingReply method [.NET Framework profiling]
- ICorProfilerCallback::RemotingServerSendingReply method [.NET Framework profiling]
ms.assetid: dfe84a19-2e03-4be2-8b25-f02bad38e4a9
topic_type:
- apiref
ms.openlocfilehash: 1d876644ae35d13a481b01d9e0e5ff0d0764ca18
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713955"
---
# <a name="icorprofilercallbackremotingserversendingreply-method"></a><span data-ttu-id="640fd-102">Метод ICorProfilerCallback::RemotingServerSendingReply</span><span class="sxs-lookup"><span data-stu-id="640fd-102">ICorProfilerCallback::RemotingServerSendingReply Method</span></span>

<span data-ttu-id="640fd-103">Уведомляет профилировщик о том, что процесс завершил обработку запроса удаленного вызова метода и собирается передать ответ через канал.</span><span class="sxs-lookup"><span data-stu-id="640fd-103">Notifies the profiler that the process has finished processing a remote method invocation request and is about to transmit the reply through a channel.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="640fd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="640fd-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingServerSendingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="640fd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="640fd-105">Parameters</span></span>  

 `pCookie`  
 <span data-ttu-id="640fd-106">окне Указатель на идентификатор GUID, который будет соответствовать значению, указанному в параметре [ICorProfilerCallback:: ремотингклиентрецеивингрепли](icorprofilercallback-remotingclientreceivingreply-method.md) в следующих условиях:</span><span class="sxs-lookup"><span data-stu-id="640fd-106">[in] A pointer to a GUID that will correspond with the value provided in [ICorProfilerCallback::RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="640fd-107">Файлы Cookie GUID удаленного взаимодействия активны.</span><span class="sxs-lookup"><span data-stu-id="640fd-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="640fd-108">Канал проходит успешную передачу сообщения.</span><span class="sxs-lookup"><span data-stu-id="640fd-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="640fd-109">Файлы Cookie GUID активны в процессе на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="640fd-109">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="640fd-110">Это позволяет легко связывать вызовы удаленного взаимодействия и создавать логические стеки вызовов.</span><span class="sxs-lookup"><span data-stu-id="640fd-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="640fd-111">окне Значение, равное, `true` Если вызов является асинхронным; в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="640fd-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="640fd-112">Требования</span><span class="sxs-lookup"><span data-stu-id="640fd-112">Requirements</span></span>  

 <span data-ttu-id="640fd-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="640fd-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="640fd-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="640fd-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="640fd-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="640fd-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="640fd-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="640fd-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="640fd-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="640fd-117">See also</span></span>

- [<span data-ttu-id="640fd-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="640fd-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
