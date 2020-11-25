---
title: Метод ICorDebugStepper::Step
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.Step
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::Step
helpviewer_keywords:
- Step method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::Step method [.NET Framework debugging]
ms.assetid: 38c1940b-ada1-40ba-8295-4c0833744e1e
topic_type:
- apiref
ms.openlocfilehash: 234705e4495a1a582f3801ad1e645f923cd6f4b2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727696"
---
# <a name="icordebugstepperstep-method"></a><span data-ttu-id="86e07-102">Метод ICorDebugStepper::Step</span><span class="sxs-lookup"><span data-stu-id="86e07-102">ICorDebugStepper::Step Method</span></span>

<span data-ttu-id="86e07-103">Приводит к тому, что данный ICorDebugStepper пошаговым путем через содержащий его поток, и, при необходимости, для продолжения пошагового выполнения функций, которые вызываются в потоке.</span><span class="sxs-lookup"><span data-stu-id="86e07-103">Causes this ICorDebugStepper to single-step through its containing thread, and optionally, to continue single-stepping through functions that are called within the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86e07-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="86e07-104">Syntax</span></span>  
  
```cpp  
HRESULT Step (  
    [in] BOOL   bStepIn  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86e07-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="86e07-105">Parameters</span></span>  

 `bStepIn`  
 <span data-ttu-id="86e07-106">окне Задайте для значение, чтобы `true` выполнить шаг с заходом в функцию, которая вызывается в потоке.</span><span class="sxs-lookup"><span data-stu-id="86e07-106">[in] Set to `true` to step into a function that is called within the thread.</span></span> <span data-ttu-id="86e07-107">Задайте для значение `false` , чтобы выполнить шаг с обходом функции.</span><span class="sxs-lookup"><span data-stu-id="86e07-107">Set to `false` to step over the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86e07-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="86e07-108">Remarks</span></span>  

 <span data-ttu-id="86e07-109">Шаг завершается, когда среда CLR выполняет следующую управляемую инструкцию в кадре этого средства.</span><span class="sxs-lookup"><span data-stu-id="86e07-109">The step completes when the common language runtime performs the next managed instruction in this stepper's frame.</span></span> <span data-ttu-id="86e07-110">Если `Step` метод вызывается в пошаговом процессе, который не находится в управляемом коде, шаг будет выполнен, когда поток выполняет следующую инструкцию управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="86e07-110">If `Step` is called on a stepper, which is not in managed code, the step will complete when the next managed code instruction is executed by the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86e07-111">Требования</span><span class="sxs-lookup"><span data-stu-id="86e07-111">Requirements</span></span>  

 <span data-ttu-id="86e07-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86e07-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86e07-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="86e07-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="86e07-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86e07-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86e07-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86e07-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
