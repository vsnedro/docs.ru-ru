---
title: Метод ICorDebugManagedCallback::StepComplete
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.StepComplete
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::StepComplete
helpviewer_keywords:
- StepComplete method [.NET Framework debugging]
- ICorDebugManagedCallback::StepComplete method [.NET Framework debugging]
ms.assetid: 5e1f2c47-81df-4530-826d-96489cd68719
topic_type:
- apiref
ms.openlocfilehash: 89b010706222ad44bccabd94191c42a888584944
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212663"
---
# <a name="icordebugmanagedcallbackstepcomplete-method"></a><span data-ttu-id="43c3b-102">Метод ICorDebugManagedCallback::StepComplete</span><span class="sxs-lookup"><span data-stu-id="43c3b-102">ICorDebugManagedCallback::StepComplete Method</span></span>
<span data-ttu-id="43c3b-103">Уведомляет отладчик о завершении шага.</span><span class="sxs-lookup"><span data-stu-id="43c3b-103">Notifies the debugger that a step has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43c3b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="43c3b-104">Syntax</span></span>  
  
```cpp  
HRESULT StepComplete (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugStepper    *pStepper,  
    [in] CorDebugStepReason   reason  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43c3b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="43c3b-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="43c3b-106">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, содержащий поток, в котором выполнен шаг.</span><span class="sxs-lookup"><span data-stu-id="43c3b-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread in which the step has completed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="43c3b-107">окне Указатель на объект ICorDebugThread, представляющий поток, в котором выполнен шаг.</span><span class="sxs-lookup"><span data-stu-id="43c3b-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the step has completed.</span></span>  
  
 `pStepper`  
 <span data-ttu-id="43c3b-108">окне Указатель на объект ICorDebugStepper, представляющий шаг при выполнении кода.</span><span class="sxs-lookup"><span data-stu-id="43c3b-108">[in] A pointer to an ICorDebugStepper object that represents the step in code execution.</span></span>  
  
 `reason`  
 <span data-ttu-id="43c3b-109">окне Значение перечисления Кордебугстепреасон, указывающее результат отдельного шага.</span><span class="sxs-lookup"><span data-stu-id="43c3b-109">[in] A value of the CorDebugStepReason enumeration that indicates the outcome of an individual step.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43c3b-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="43c3b-110">Remarks</span></span>  
 <span data-ttu-id="43c3b-111">Средство организации пошагового режима можно использовать для продолжения пошагового выполнения, если отладка не будет завершена.</span><span class="sxs-lookup"><span data-stu-id="43c3b-111">The stepper may be used to continue stepping if desired, unless the debugging is terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43c3b-112">Требования</span><span class="sxs-lookup"><span data-stu-id="43c3b-112">Requirements</span></span>  
 <span data-ttu-id="43c3b-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43c3b-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43c3b-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="43c3b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43c3b-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43c3b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43c3b-116">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43c3b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43c3b-117">См. также</span><span class="sxs-lookup"><span data-stu-id="43c3b-117">See also</span></span>

- [<span data-ttu-id="43c3b-118">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="43c3b-118">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
