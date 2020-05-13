---
title: Метод ICorDebugStepper::Deactivate
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.Deactivate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::Deactivate
helpviewer_keywords:
- Deactivate method [.NET Framework debugging]
- ICorDebugStepper::Deactivate method [.NET Framework debugging]
ms.assetid: 855f4199-b62d-40ce-998e-1eb4a1772142
topic_type:
- apiref
ms.openlocfilehash: 760f69baf311cf320e9c358ba1c45c942934f1a5
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379395"
---
# <a name="icordebugstepperdeactivate-method"></a><span data-ttu-id="7a161-102">Метод ICorDebugStepper::Deactivate</span><span class="sxs-lookup"><span data-stu-id="7a161-102">ICorDebugStepper::Deactivate Method</span></span>
<span data-ttu-id="7a161-103">Заставляет этот объект ICorDebugStepper отменить последнюю полученную команду шага.</span><span class="sxs-lookup"><span data-stu-id="7a161-103">Causes this ICorDebugStepper to cancel the last step command that it received.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a161-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7a161-104">Syntax</span></span>  
  
```cpp  
HRESULT Deactivate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="7a161-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="7a161-105">Remarks</span></span>  
 <span data-ttu-id="7a161-106">Новая команда пошагового выполнения может быть выдана после отмены последней полученной команды Step.</span><span class="sxs-lookup"><span data-stu-id="7a161-106">A new stepping command may be issued after the most recently received step command has been canceled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a161-107">Требования</span><span class="sxs-lookup"><span data-stu-id="7a161-107">Requirements</span></span>  
 <span data-ttu-id="7a161-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a161-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a161-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7a161-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7a161-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a161-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a161-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a161-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
