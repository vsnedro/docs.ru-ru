---
title: Метод ICorDebugController::SetAllThreadsDebugState
ms.date: 03/30/2017
api_name:
- ICorDebugController.SetAllThreadsDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::SetAllThreadsDebugState
helpviewer_keywords:
- SetAllThreadsDebugState method [.NET Framework debugging]
- ICorDebugController::SetAllThreadsDebugState method [.NET Framework debugging]
ms.assetid: bdda4bd7-4743-4d58-a22b-8067e967db95
topic_type:
- apiref
ms.openlocfilehash: c2e8aaa2774e3e2699a73c40804391ca245047b1
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976594"
---
# <a name="icordebugcontrollersetallthreadsdebugstate-method"></a><span data-ttu-id="eb886-102">Метод ICorDebugController::SetAllThreadsDebugState</span><span class="sxs-lookup"><span data-stu-id="eb886-102">ICorDebugController::SetAllThreadsDebugState Method</span></span>
<span data-ttu-id="eb886-103">Задает состояние отладки всех управляемых потоков в процессе.</span><span class="sxs-lookup"><span data-stu-id="eb886-103">Sets the debug state of all managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb886-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eb886-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAllThreadsDebugState (  
    [in] CorDebugThreadState  state,  
    [in] ICorDebugThread      *pExceptThisThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb886-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="eb886-105">Parameters</span></span>  
 `state`  
 <span data-ttu-id="eb886-106">окне Значение перечисления "Кордебугсреадстате", указывающее состояние потока для отладки.</span><span class="sxs-lookup"><span data-stu-id="eb886-106">[in] A value of the "CorDebugThreadState" enumeration that specifies the state of the thread for debugging.</span></span>  
  
 `pExceptThisThread`  
 <span data-ttu-id="eb886-107">окне Указатель на объект "ICorDebugThread", представляющий поток, исключаемый из параметра состояния отладки.</span><span class="sxs-lookup"><span data-stu-id="eb886-107">[in] A pointer to an "ICorDebugThread" object that represents a thread to be exempted from the debug state setting.</span></span> <span data-ttu-id="eb886-108">Если это значение равно null, ни один поток не исключен.</span><span class="sxs-lookup"><span data-stu-id="eb886-108">If this value is null, no thread is exempted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eb886-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="eb886-109">Remarks</span></span>  
 <span data-ttu-id="eb886-110">Метод может влиять на потоки, которые не видны через [метод енумератесреадс](icordebugcontroller-enumeratethreads-method.md), поэтому потоки, которые были приостановлены с `SetAllThreadsDebugState` помощью метода, необходимо возобновить с `SetAllThreadsDebugState` помощью метода. `SetAllThreadsDebugState`</span><span class="sxs-lookup"><span data-stu-id="eb886-110">The `SetAllThreadsDebugState` method may affect threads that are not visible via [EnumerateThreads Method](icordebugcontroller-enumeratethreads-method.md), so threads that were suspended with the `SetAllThreadsDebugState` method will need to be resumed with the `SetAllThreadsDebugState` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb886-111">Требования</span><span class="sxs-lookup"><span data-stu-id="eb886-111">Requirements</span></span>  
 <span data-ttu-id="eb886-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb886-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb886-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eb886-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eb886-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb886-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb886-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb886-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb886-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="eb886-116">See also</span></span>
