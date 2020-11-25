---
title: Метод ICorDebugStepper::StepOut
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.StepOut
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::StepOut
helpviewer_keywords:
- ICorDebugStepper::StepOut method [.NET Framework debugging]
- StepOut method [.NET Framework debugging]
ms.assetid: aae0f48c-4ede-4256-9251-a7fc85a229dc
topic_type:
- apiref
ms.openlocfilehash: 1396e7a8ca61734a9363a9c852502290675249d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727670"
---
# <a name="icordebugstepperstepout-method"></a><span data-ttu-id="0a1e9-102">Метод ICorDebugStepper::StepOut</span><span class="sxs-lookup"><span data-stu-id="0a1e9-102">ICorDebugStepper::StepOut Method</span></span>

<span data-ttu-id="0a1e9-103">Приводит к тому, что данный ICorDebugStepper пошаговым путем через содержащий его поток и завершается, когда текущий кадр возвращает управление вызывающему кадру.</span><span class="sxs-lookup"><span data-stu-id="0a1e9-103">Causes this ICorDebugStepper to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a1e9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0a1e9-104">Syntax</span></span>  
  
```cpp  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="0a1e9-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="0a1e9-105">Remarks</span></span>  

 <span data-ttu-id="0a1e9-106">`StepOut`Операция будет завершена после возврата в обычном режиме из текущего кадра в вызывающий кадр.</span><span class="sxs-lookup"><span data-stu-id="0a1e9-106">A `StepOut` operation will complete after returning normally from the current frame to the calling frame.</span></span>  
  
 <span data-ttu-id="0a1e9-107">Если `StepOut` вызывается в неуправляемом коде, этот шаг завершается, когда текущий кадр возвращается в управляемый код, вызвавший его.</span><span class="sxs-lookup"><span data-stu-id="0a1e9-107">If `StepOut` is called when in unmanaged code, the step will complete when the current frame returns to the managed code that called it.</span></span>  
  
 <span data-ttu-id="0a1e9-108">В .NET Framework версии 2,0 не используйте `StepOut` с установленным флагом STOP_UNMANAGED, так как он завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="0a1e9-108">In the .NET Framework version 2.0, do not use `StepOut` with the STOP_UNMANAGED flag set because it will fail.</span></span> <span data-ttu-id="0a1e9-109">(Используйте [ICorDebugStepper:: сетунмаппедстопмаск](icordebugstepper-setunmappedstopmask-method.md) для установки флагов для пошагового выполнения.) Отладчики взаимодействия должны выполнять шаг с заходом в собственный код.</span><span class="sxs-lookup"><span data-stu-id="0a1e9-109">(Use [ICorDebugStepper::SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) to set flags for stepping.) Interop debuggers must step out to native code themselves.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a1e9-110">Требования</span><span class="sxs-lookup"><span data-stu-id="0a1e9-110">Requirements</span></span>  

 <span data-ttu-id="0a1e9-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a1e9-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a1e9-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0a1e9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0a1e9-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0a1e9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0a1e9-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a1e9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
