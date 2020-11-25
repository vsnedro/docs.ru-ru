---
title: Метод ICorProfilerCallback::RemotingClientReceivingReply
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientReceivingReply
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientReceivingReply
helpviewer_keywords:
- ICorProfilerCallback::RemotingClientReceivingReply method [.NET Framework profiling]
- RemotingClientReceivingReply method [.NET Framework profiling]
ms.assetid: 15cfc300-8231-4ecb-9a04-19851c3eb484
topic_type:
- apiref
ms.openlocfilehash: 058c66af85da6c902e3d628e1b1479bb88c4fa85
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704855"
---
# <a name="icorprofilercallbackremotingclientreceivingreply-method"></a><span data-ttu-id="beba4-102">Метод ICorProfilerCallback::RemotingClientReceivingReply</span><span class="sxs-lookup"><span data-stu-id="beba4-102">ICorProfilerCallback::RemotingClientReceivingReply Method</span></span>

<span data-ttu-id="beba4-103">Уведомляет профилировщик о завершении серверной части удаленного вызова, а также о получении и обработке ответа клиентом.</span><span class="sxs-lookup"><span data-stu-id="beba4-103">Notifies the profiler that the server-side portion of a remoting call has completed and the client is now receiving and about to process the reply.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="beba4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="beba4-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientReceivingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);
```  
  
## <a name="parameters"></a><span data-ttu-id="beba4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="beba4-105">Parameters</span></span>  

 `pCookie`  
 <span data-ttu-id="beba4-106">окне Значение, которое будет соответствовать значению, указанному в параметре [ICorProfilerCallback:: RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md) в следующих условиях:</span><span class="sxs-lookup"><span data-stu-id="beba4-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="beba4-107">Файлы Cookie GUID удаленного взаимодействия активны.</span><span class="sxs-lookup"><span data-stu-id="beba4-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="beba4-108">Канал проходит успешную передачу сообщения.</span><span class="sxs-lookup"><span data-stu-id="beba4-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="beba4-109">Файлы Cookie GUID активны в процессе на стороне сервера.</span><span class="sxs-lookup"><span data-stu-id="beba4-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="beba4-110">Это позволяет легко связывать вызовы удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="beba4-110">This allows easy pairing of remoting calls.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="beba4-111">окне Значение, равное, `true` Если вызов является асинхронным; в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="beba4-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="beba4-112">Требования</span><span class="sxs-lookup"><span data-stu-id="beba4-112">Requirements</span></span>  

 <span data-ttu-id="beba4-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="beba4-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="beba4-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="beba4-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="beba4-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="beba4-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="beba4-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="beba4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="beba4-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="beba4-117">See also</span></span>

- [<span data-ttu-id="beba4-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="beba4-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
