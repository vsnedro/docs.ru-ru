---
title: Метод ICorDebugStepper::SetInterceptMask
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetInterceptMask
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetInterceptMask
helpviewer_keywords:
- SetInterceptMask method [.NET Framework debugging]
- ICorDebugStepper::SetInterceptMask method [.NET Framework debugging]
ms.assetid: 6245e2ae-5cc2-43ff-8cc1-71953d12113a
topic_type:
- apiref
ms.openlocfilehash: aaba751a58e5b23b98b1d0629ea3cc9e1e7a83a9
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379004"
---
# <a name="icordebugsteppersetinterceptmask-method"></a><span data-ttu-id="ff55a-102">Метод ICorDebugStepper::SetInterceptMask</span><span class="sxs-lookup"><span data-stu-id="ff55a-102">ICorDebugStepper::SetInterceptMask Method</span></span>
<span data-ttu-id="ff55a-103">Задает значение, указывающее типы кода, в который выполняется пошаговое выполнение.</span><span class="sxs-lookup"><span data-stu-id="ff55a-103">Sets a value that specifies the types of code that are stepped into.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff55a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ff55a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff55a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ff55a-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="ff55a-106">окне Сочетание значений перечисления CorDebugIntercept, определяющих типы кода.</span><span class="sxs-lookup"><span data-stu-id="ff55a-106">[in] A combination of values of the CorDebugIntercept enumeration that specifies the types of code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff55a-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="ff55a-107">Remarks</span></span>  
 <span data-ttu-id="ff55a-108">Если задан бит для перехватчика, средство пошагового выполнения будет выполнено при обнаружении заданного типа перехвата кода.</span><span class="sxs-lookup"><span data-stu-id="ff55a-108">If the bit for an interceptor is set, the stepper will complete when the given type of intercepting code is encountered.</span></span> <span data-ttu-id="ff55a-109">Если бит сброшен, перехват кода будет пропущен.</span><span class="sxs-lookup"><span data-stu-id="ff55a-109">If the bit is cleared, the intercepting code will be skipped.</span></span>  
  
 <span data-ttu-id="ff55a-110">`SetInterceptMask`Метод может иметь непредвиденные взаимодействия с [ICorDebugStepper:: сетунмаппедстопмаск](icordebugstepper-setunmappedstopmask-method.md) (от точки зрения пользователя).</span><span class="sxs-lookup"><span data-stu-id="ff55a-110">The `SetInterceptMask` method may have unforeseen interactions with [ICorDebugStepper::SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) (from the user's point of view).</span></span> <span data-ttu-id="ff55a-111">Например, если единственная видимая (т. е. не внутренняя) часть кода инициализации класса не имеет сведений о сопоставлении и STOP_NO_MAPPING_INFO не задана (см. метод [ICorDebugStepper:: сетунмаппедстопмаск](icordebugstepper-setunmappedstopmask-method.md) и перечисление кордебугунмаппедстоп), средство организации пошаговое руководство будет пройдет инициализацию класса.</span><span class="sxs-lookup"><span data-stu-id="ff55a-111">For example, if the only visible (that is, non-internal) portion of class initialization code lacks mapping information and STOP_NO_MAPPING_INFO isn't set (see the [ICorDebugStepper::SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) method and the CorDebugUnmappedStop enumeration), the stepper will step over the class initialization.</span></span> <span data-ttu-id="ff55a-112">По умолчанию будет использоваться только значение INTERCEPT_NONE `CorDebugIntercept` перечисления.</span><span class="sxs-lookup"><span data-stu-id="ff55a-112">By default, only the INTERCEPT_NONE value of the `CorDebugIntercept` enumeration will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff55a-113">Требования</span><span class="sxs-lookup"><span data-stu-id="ff55a-113">Requirements</span></span>  
 <span data-ttu-id="ff55a-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff55a-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff55a-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ff55a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ff55a-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff55a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff55a-117">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff55a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
