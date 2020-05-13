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
ms.openlocfilehash: 9f6962f987079da1ccb04ea368307d7c119910a6
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379505"
---
# <a name="icordebugstepperstepout-method"></a><span data-ttu-id="7716e-102">Метод ICorDebugStepper::StepOut</span><span class="sxs-lookup"><span data-stu-id="7716e-102">ICorDebugStepper::StepOut Method</span></span>
<span data-ttu-id="7716e-103">Приводит к тому, что данный ICorDebugStepper пошаговым путем через содержащий его поток и завершается, когда текущий кадр возвращает управление вызывающему кадру.</span><span class="sxs-lookup"><span data-stu-id="7716e-103">Causes this ICorDebugStepper to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7716e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7716e-104">Syntax</span></span>  
  
```cpp  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="7716e-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="7716e-105">Remarks</span></span>  
 <span data-ttu-id="7716e-106">`StepOut`Операция будет завершена после возврата в обычном режиме из текущего кадра в вызывающий кадр.</span><span class="sxs-lookup"><span data-stu-id="7716e-106">A `StepOut` operation will complete after returning normally from the current frame to the calling frame.</span></span>  
  
 <span data-ttu-id="7716e-107">Если `StepOut` вызывается в неуправляемом коде, этот шаг завершается, когда текущий кадр возвращается в управляемый код, вызвавший его.</span><span class="sxs-lookup"><span data-stu-id="7716e-107">If `StepOut` is called when in unmanaged code, the step will complete when the current frame returns to the managed code that called it.</span></span>  
  
 <span data-ttu-id="7716e-108">В .NET Framework версии 2,0 не используйте `StepOut` с установленным флагом STOP_UNMANAGED, так как он завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="7716e-108">In the .NET Framework version 2.0, do not use `StepOut` with the STOP_UNMANAGED flag set because it will fail.</span></span> <span data-ttu-id="7716e-109">(Используйте [ICorDebugStepper:: сетунмаппедстопмаск](icordebugstepper-setunmappedstopmask-method.md) для установки флагов для пошагового выполнения.) Отладчики взаимодействия должны выполнять шаг с заходом в собственный код.</span><span class="sxs-lookup"><span data-stu-id="7716e-109">(Use [ICorDebugStepper::SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) to set flags for stepping.) Interop debuggers must step out to native code themselves.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7716e-110">Требования</span><span class="sxs-lookup"><span data-stu-id="7716e-110">Requirements</span></span>  
 <span data-ttu-id="7716e-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7716e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7716e-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7716e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7716e-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7716e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7716e-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7716e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
