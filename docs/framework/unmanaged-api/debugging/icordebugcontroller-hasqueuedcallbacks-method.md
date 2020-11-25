---
title: Метод ICorDebugController::HasQueuedCallbacks
ms.date: 03/30/2017
api_name:
- ICorDebugController.HasQueuedCallbacks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::HasQueuedCallbacks
helpviewer_keywords:
- HasQueuedCallbacks method [.NET Framework debugging]
- ICorDebugController::HasQueuedCallbacks method [.NET Framework debugging]
ms.assetid: 0d6a1cd9-370b-4462-adbf-e3980e897ea7
topic_type:
- apiref
ms.openlocfilehash: bd623f8bee2feafebe80c0c7513bcfb33d6ad367
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707923"
---
# <a name="icordebugcontrollerhasqueuedcallbacks-method"></a><span data-ttu-id="a667f-102">Метод ICorDebugController::HasQueuedCallbacks</span><span class="sxs-lookup"><span data-stu-id="a667f-102">ICorDebugController::HasQueuedCallbacks Method</span></span>

<span data-ttu-id="a667f-103">Возвращает значение, указывающее, находятся ли в очереди управляемые обратные вызовы для указанного потока.</span><span class="sxs-lookup"><span data-stu-id="a667f-103">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a667f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a667f-104">Syntax</span></span>  
  
```cpp  
HRESULT HasQueuedCallbacks (  
    [in] ICorDebugThread *pThread,  
    [out] BOOL           *pbQueued  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a667f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a667f-105">Parameters</span></span>  

 `pThread`  
 <span data-ttu-id="a667f-106">окне Указатель на объект "ICorDebugThread", представляющий поток.</span><span class="sxs-lookup"><span data-stu-id="a667f-106">[in] A pointer to an "ICorDebugThread" object that represents the thread.</span></span>  
  
 `pbQueued`  
 <span data-ttu-id="a667f-107">заполняет Указатель на значение, равное, `true` Если какие-либо управляемые обратные вызовы в настоящий момент поставлены в очередь для указанного потока; в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="a667f-107">[out] A pointer to a value that is `true` if any managed callbacks are currently queued for the specified thread; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="a667f-108">Если для параметра задано значение NULL `pThread` , `HasQueuedCallbacks` функция возвратит, если в `true` настоящий момент в очереди есть управляемые обратные вызовы для любого потока.</span><span class="sxs-lookup"><span data-stu-id="a667f-108">If null is specified for the `pThread` parameter, `HasQueuedCallbacks` will return `true` if there are currently managed callbacks queued for any thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a667f-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="a667f-109">Remarks</span></span>  

 <span data-ttu-id="a667f-110">Обратные вызовы будут отправлены по одному, каждый раз, когда вызывается [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a667f-110">Callbacks will be dispatched one at a time, each time [ICorDebugController::Continue](icordebugcontroller-continue-method.md) is called.</span></span> <span data-ttu-id="a667f-111">Отладчик может проверить этот флаг, если он хочет сообщить о нескольких событиях отладки, происходящих одновременно.</span><span class="sxs-lookup"><span data-stu-id="a667f-111">The debugger can check this flag if it wants to report multiple debugging events that occur simultaneously.</span></span>  
  
 <span data-ttu-id="a667f-112">Когда события отладки помещаются в очередь, они уже были выполнены, поэтому отладчик должен очистить всю очередь, чтобы убедиться в состоянии отлаживаемой программы.</span><span class="sxs-lookup"><span data-stu-id="a667f-112">When debugging events are queued, they have already occurred, so the debugger must drain the entire queue to be sure of the state of the debuggee.</span></span> <span data-ttu-id="a667f-113">(Вызов `ICorDebugController::Continue` для очистки очереди.) Например, если очередь содержит два события отладки в потоке *x*, а отладчик приостанавливает поток *x* после первого события отладки и затем вызывает `ICorDebugController::Continue` , второе событие отладки для потока *x* будет отправлено, хотя поток был приостановлен.</span><span class="sxs-lookup"><span data-stu-id="a667f-113">(Call `ICorDebugController::Continue` to drain the queue.) For example, if the queue contains two debugging events on thread *X*, and the debugger suspends thread *X* after the first debugging event and then calls `ICorDebugController::Continue`, the second debugging event for thread *X* will be dispatched although the thread has been suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a667f-114">Требования</span><span class="sxs-lookup"><span data-stu-id="a667f-114">Requirements</span></span>  

 <span data-ttu-id="a667f-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a667f-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a667f-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a667f-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a667f-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a667f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a667f-118">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a667f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a667f-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a667f-119">See also</span></span>
