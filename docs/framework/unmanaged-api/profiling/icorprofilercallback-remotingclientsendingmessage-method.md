---
title: Метод ICorProfilerCallback::RemotingClientSendingMessage
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientSendingMessage
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientSendingMessage
helpviewer_keywords:
- RemotingClientSendingMessage method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientSendingMessage method [.NET Framework profiling]
ms.assetid: 54d9a5a5-3877-49c1-a503-ce7c7943bc2a
topic_type:
- apiref
ms.openlocfilehash: 2ef8f066831df1437bd0b6a6f155dd459cae1eb2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676846"
---
# <a name="icorprofilercallbackremotingclientsendingmessage-method"></a><span data-ttu-id="50174-102">Метод ICorProfilerCallback::RemotingClientSendingMessage</span><span class="sxs-lookup"><span data-stu-id="50174-102">ICorProfilerCallback::RemotingClientSendingMessage Method</span></span>

<span data-ttu-id="50174-103">Уведомляет профилировщик о том, что клиент отправляет запрос на сервер.</span><span class="sxs-lookup"><span data-stu-id="50174-103">Notifies the profiler that the client is sending a request to the server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50174-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="50174-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50174-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="50174-105">Parameters</span></span>  

 `pCookie`  
 <span data-ttu-id="50174-106">окне Значение, которое соответствует значению, указанному в параметре [ICorProfilerCallback:: RemotingServerReceivingMessage](icorprofilercallback-remotingserverreceivingmessage-method.md) в следующих условиях:</span><span class="sxs-lookup"><span data-stu-id="50174-106">[in] A value that corresponds with the value provided in [ICorProfilerCallback::RemotingServerReceivingMessage](icorprofilercallback-remotingserverreceivingmessage-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="50174-107">Файлы Cookie GUID удаленного взаимодействия активны.</span><span class="sxs-lookup"><span data-stu-id="50174-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="50174-108">Канал проходит успешную передачу сообщения.</span><span class="sxs-lookup"><span data-stu-id="50174-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="50174-109">Файлы Cookie GUID активны в процессе на стороне сервера.</span><span class="sxs-lookup"><span data-stu-id="50174-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="50174-110">Это позволяет легко связывать вызовы удаленного взаимодействия и создавать логические стеки вызовов.</span><span class="sxs-lookup"><span data-stu-id="50174-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="50174-111">окне Значение, равное, `true` Если вызов является асинхронным; в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="50174-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50174-112">Требования</span><span class="sxs-lookup"><span data-stu-id="50174-112">Requirements</span></span>  

 <span data-ttu-id="50174-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50174-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50174-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="50174-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="50174-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50174-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50174-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50174-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50174-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="50174-117">See also</span></span>

- [<span data-ttu-id="50174-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="50174-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
