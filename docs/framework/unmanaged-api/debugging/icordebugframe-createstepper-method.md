---
title: Метод ICorDebugFrame::CreateStepper
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::CreateStepper
helpviewer_keywords:
- ICorDebugFrame::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 689e7f28-20c1-4d5c-9baa-17441cd63a88
topic_type:
- apiref
ms.openlocfilehash: 5dfb64d0c440cbd2c8a8a65b2c18d78f02a7615e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679719"
---
# <a name="icordebugframecreatestepper-method"></a><span data-ttu-id="66228-102">Метод ICorDebugFrame::CreateStepper</span><span class="sxs-lookup"><span data-stu-id="66228-102">ICorDebugFrame::CreateStepper Method</span></span>

<span data-ttu-id="66228-103">Возвращает средство, позволяющее отладчику выполнять операции пошагового выполнения по отношению к этому ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="66228-103">Gets a stepper that allows the debugger to perform stepping operations relative to this ICorDebugFrame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66228-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="66228-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper   **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66228-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="66228-105">Parameters</span></span>  

 `ppStepper`  
 <span data-ttu-id="66228-106">заполняет Указатель на адрес объекта ICorDebugStepper, который позволяет отладчику выполнять операции пошагового выполнения по отношению к текущему кадру.</span><span class="sxs-lookup"><span data-stu-id="66228-106">[out] A pointer to the address of an ICorDebugStepper object that allows the debugger to perform stepping operations relative to the current frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66228-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="66228-107">Remarks</span></span>  

 <span data-ttu-id="66228-108">Если кадр неактивен, объект средства Организации, как правило, должен вернуться к кадру до завершения этого шага.</span><span class="sxs-lookup"><span data-stu-id="66228-108">If the frame is not active, the stepper object will typically have to return to the frame before the step is completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66228-109">Требования</span><span class="sxs-lookup"><span data-stu-id="66228-109">Requirements</span></span>  

 <span data-ttu-id="66228-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66228-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66228-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="66228-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="66228-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66228-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66228-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66228-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
