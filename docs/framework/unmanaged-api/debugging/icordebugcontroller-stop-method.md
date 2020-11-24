---
title: Метод ICorDebugController::Stop
ms.date: 03/30/2017
api_name:
- ICorDebugController.Stop
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Stop
helpviewer_keywords:
- Stop method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Stop method [.NET Framework debugging]
ms.assetid: c34e79be-a7fb-479e-8dec-d126a4c330e5
topic_type:
- apiref
ms.openlocfilehash: 11cc6e4108a2064a8a9fcefa760bf3c3411d63fb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679862"
---
# <a name="icordebugcontrollerstop-method"></a><span data-ttu-id="ced48-102">Метод ICorDebugController::Stop</span><span class="sxs-lookup"><span data-stu-id="ced48-102">ICorDebugController::Stop Method</span></span>

<span data-ttu-id="ced48-103">Выполняет совместную работу во всех потоках, где выполняется управляемый код в процессе.</span><span class="sxs-lookup"><span data-stu-id="ced48-103">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ced48-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ced48-104">Syntax</span></span>  
  
```cpp  
HRESULT Stop (  
    [in] DWORD dwTimeoutIgnored  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ced48-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ced48-105">Parameters</span></span>  

 `dwTimeoutIgnored`  
 <span data-ttu-id="ced48-106">Не используется.</span><span class="sxs-lookup"><span data-stu-id="ced48-106">Not used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ced48-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="ced48-107">Remarks</span></span>  

 <span data-ttu-id="ced48-108">`Stop` выполняет совместную работу всех потоков, выполняющих управляемый код в процессе.</span><span class="sxs-lookup"><span data-stu-id="ced48-108">`Stop` performs a cooperative stop on all threads running managed code in the process.</span></span> <span data-ttu-id="ced48-109">Во время сеанса отладки, доступного только для управляемого кода, неуправляемые потоки могут продолжать выполняться (но будут заблокированы при попытке вызвать управляемый код).</span><span class="sxs-lookup"><span data-stu-id="ced48-109">During a managed-only debugging session, unmanaged threads may continue to run (but will be blocked when trying to call managed code).</span></span> <span data-ttu-id="ced48-110">Во время сеанса отладки взаимодействия неуправляемые потоки также будут остановлены.</span><span class="sxs-lookup"><span data-stu-id="ced48-110">During an interop debugging session, unmanaged threads will also be stopped.</span></span> <span data-ttu-id="ced48-111">`dwTimeoutIgnored`Значение в настоящее время игнорируется и обрабатывается как БЕСконечное (-1).</span><span class="sxs-lookup"><span data-stu-id="ced48-111">The `dwTimeoutIgnored` value is currently ignored and treated as INFINITE (-1).</span></span> <span data-ttu-id="ced48-112">Если совместная остановка завершается сбоем из-за взаимоблокировки, все потоки приостанавливаются и возвращается E_TIMEOUT.</span><span class="sxs-lookup"><span data-stu-id="ced48-112">If the cooperative stop fails due to a deadlock, all threads are suspended and E_TIMEOUT is returned.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ced48-113">`Stop` — единственный синхронный метод в API отладки.</span><span class="sxs-lookup"><span data-stu-id="ced48-113">`Stop` is the only synchronous method in the debugging API.</span></span> <span data-ttu-id="ced48-114">Когда `Stop` функция возвращает S_OK, процесс останавливается.</span><span class="sxs-lookup"><span data-stu-id="ced48-114">When `Stop` returns S_OK, the process is stopped.</span></span> <span data-ttu-id="ced48-115">Обратный вызов не предоставляется для уведомления прослушивателей об ошибке.</span><span class="sxs-lookup"><span data-stu-id="ced48-115">No callback is given to notify listeners of the stop.</span></span> <span data-ttu-id="ced48-116">Отладчик должен вызвать [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) , чтобы разрешить возобновление процесса.</span><span class="sxs-lookup"><span data-stu-id="ced48-116">The debugger must call [ICorDebugController::Continue](icordebugcontroller-continue-method.md) to allow the process to resume.</span></span>  
  
 <span data-ttu-id="ced48-117">Отладчик поддерживает счетчик "останавливается".</span><span class="sxs-lookup"><span data-stu-id="ced48-117">The debugger maintains a stop counter.</span></span> <span data-ttu-id="ced48-118">Когда счетчик переходит в нулевое значение, контроллер возобновляется.</span><span class="sxs-lookup"><span data-stu-id="ced48-118">When the counter goes to zero, the controller is resumed.</span></span> <span data-ttu-id="ced48-119">Каждый вызов `Stop` или каждый отправленный обратный вызов увеличивает счетчик.</span><span class="sxs-lookup"><span data-stu-id="ced48-119">Each call to `Stop` or each dispatched callback increments the counter.</span></span> <span data-ttu-id="ced48-120">Каждый вызов `ICorDebugController::Continue` уменьшает значение счетчика.</span><span class="sxs-lookup"><span data-stu-id="ced48-120">Each call to `ICorDebugController::Continue` decrements the counter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ced48-121">Требования</span><span class="sxs-lookup"><span data-stu-id="ced48-121">Requirements</span></span>  

 <span data-ttu-id="ced48-122">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ced48-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ced48-123">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ced48-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ced48-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ced48-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ced48-125">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ced48-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ced48-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ced48-126">See also</span></span>
