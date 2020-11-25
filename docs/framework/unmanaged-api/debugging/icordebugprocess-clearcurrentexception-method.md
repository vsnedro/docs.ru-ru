---
title: Метод ICorDebugProcess::ClearCurrentException
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ClearCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ClearCurrentException
helpviewer_keywords:
- ClearCurrentException method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::ClearCurrentException method [.NET Framework debugging]
ms.assetid: 9e02ee1a-e495-4578-bfb5-b946274bede7
topic_type:
- apiref
ms.openlocfilehash: 0d36390a905561b64b3ca6ca95722f82158450be
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695222"
---
# <a name="icordebugprocessclearcurrentexception-method"></a><span data-ttu-id="43e32-102">Метод ICorDebugProcess::ClearCurrentException</span><span class="sxs-lookup"><span data-stu-id="43e32-102">ICorDebugProcess::ClearCurrentException Method</span></span>

<span data-ttu-id="43e32-103">Очищает текущее неуправляемое исключение для данного потока.</span><span class="sxs-lookup"><span data-stu-id="43e32-103">Clears the current unmanaged exception on the given thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43e32-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="43e32-104">Syntax</span></span>  
  
```cpp  
HRESULT ClearCurrentException([in] DWORD threadID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43e32-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="43e32-105">Parameters</span></span>  

 `threadID`  
 <span data-ttu-id="43e32-106">окне Идентификатор потока, в котором будет очищаться текущее неуправляемое исключение.</span><span class="sxs-lookup"><span data-stu-id="43e32-106">[in] The ID of the thread on which the current unmanaged exception will be cleared.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43e32-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="43e32-107">Remarks</span></span>  

 <span data-ttu-id="43e32-108">Вызывайте этот метод перед вызовом [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) , когда поток сообщил о неуправляемом исключении, которое должно игнорироваться отлаживаемым объектом.</span><span class="sxs-lookup"><span data-stu-id="43e32-108">Call this method before calling [ICorDebugController::Continue](icordebugcontroller-continue-method.md) when a thread has reported an unmanaged exception that should be ignored by the debuggee.</span></span> <span data-ttu-id="43e32-109">Это приведет к удалению необработанных внутренних () и нестандартных событий (OOB) для данного потока.</span><span class="sxs-lookup"><span data-stu-id="43e32-109">This will clear both the outstanding in-band (IB) and out-of-band (OOB) events on the given thread.</span></span> <span data-ttu-id="43e32-110">Все точки останова OOB и одношаговые исключения автоматически очищаются.</span><span class="sxs-lookup"><span data-stu-id="43e32-110">All OOB breakpoints and single-step exceptions are automatically cleared.</span></span>  
  
 <span data-ttu-id="43e32-111">Используйте [ICorDebugThread2:: интерцепткуррентексцептион](icordebugthread2-interceptcurrentexception-method.md) для перехвата текущего управляемого исключения в потоке.</span><span class="sxs-lookup"><span data-stu-id="43e32-111">Use [ICorDebugThread2::InterceptCurrentException](icordebugthread2-interceptcurrentexception-method.md) to intercept the current managed exception on a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43e32-112">Требования</span><span class="sxs-lookup"><span data-stu-id="43e32-112">Requirements</span></span>  

 <span data-ttu-id="43e32-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43e32-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43e32-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="43e32-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43e32-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43e32-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43e32-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43e32-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
