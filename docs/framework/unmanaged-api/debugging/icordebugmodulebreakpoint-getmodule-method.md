---
title: Метод ICorDebugModuleBreakpoint::GetModule
ms.date: 03/30/2017
api_name:
- ICorDebugModuleBreakpoint.GetModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleBreakpoint::GetModule
helpviewer_keywords:
- ICorDebugModuleBreakpoint::GetModule method [.NET Framework debugging]
- GetModule method, ICorDebugModuleBreakpoint interface [.NET Framework debugging]
ms.assetid: ffd5d9ec-4564-4200-b625-b306eec0ebd7
topic_type:
- apiref
ms.openlocfilehash: 714819504099ea978ed31d471b4ceb9fc17a6552
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212299"
---
# <a name="icordebugmodulebreakpointgetmodule-method"></a><span data-ttu-id="bc9c3-102">Метод ICorDebugModuleBreakpoint::GetModule</span><span class="sxs-lookup"><span data-stu-id="bc9c3-102">ICorDebugModuleBreakpoint::GetModule Method</span></span>
<span data-ttu-id="bc9c3-103">Возвращает указатель интерфейса на "ICorDebugModule", ссылающийся на модуль, в котором задана эта точка останова.</span><span class="sxs-lookup"><span data-stu-id="bc9c3-103">Gets an interface pointer to an "ICorDebugModule" that references the module in which this breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc9c3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bc9c3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule (  
    [out] ICorDebugModule   **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc9c3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bc9c3-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="bc9c3-106">заполняет Указатель на адрес `ICorDebugModule` интерфейса, который ссылается на модуль, в котором задана точка останова.</span><span class="sxs-lookup"><span data-stu-id="bc9c3-106">[out] A pointer to the address of an `ICorDebugModule` interface that references the module in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc9c3-107">Требования</span><span class="sxs-lookup"><span data-stu-id="bc9c3-107">Requirements</span></span>  
 <span data-ttu-id="bc9c3-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc9c3-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc9c3-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bc9c3-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bc9c3-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc9c3-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc9c3-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc9c3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc9c3-112">См. также</span><span class="sxs-lookup"><span data-stu-id="bc9c3-112">See also</span></span>
