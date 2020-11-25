---
title: Метод ICorDebug::Terminate
ms.date: 03/30/2017
api_name:
- ICorDebug.Terminate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::Terminate
helpviewer_keywords:
- Terminate method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Terminate method [.NET Framework debugging]
ms.assetid: fffe5616-0896-4426-ab5e-21869b514883
topic_type:
- apiref
ms.openlocfilehash: cf9c9d11c4725908fcf7ff4a0c91882b70a80190
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723380"
---
# <a name="icordebugterminate-method"></a><span data-ttu-id="14311-102">Метод ICorDebug::Terminate</span><span class="sxs-lookup"><span data-stu-id="14311-102">ICorDebug::Terminate Method</span></span>

<span data-ttu-id="14311-103">Завершает `ICorDebug` объект.</span><span class="sxs-lookup"><span data-stu-id="14311-103">Terminates the `ICorDebug` object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="14311-104">`Terminate` не следует вызывать, пока не получен обратный вызов [ICorDebugManagedCallback:: ExitProcess](icordebugmanagedcallback-exitprocess-method.md) для всех отлаживаемых процессов.</span><span class="sxs-lookup"><span data-stu-id="14311-104">`Terminate` should not be called until an [ICorDebugManagedCallback::ExitProcess](icordebugmanagedcallback-exitprocess-method.md) callback has been received for all processes being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14311-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="14311-105">Syntax</span></span>  
  
```cpp  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="14311-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="14311-106">Remarks</span></span>  

 <span data-ttu-id="14311-107">`Terminate` должен вызываться, когда `ICorDebug` объект больше не нужен.</span><span class="sxs-lookup"><span data-stu-id="14311-107">`Terminate` must be called when the `ICorDebug` object is no longer needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14311-108">Требования</span><span class="sxs-lookup"><span data-stu-id="14311-108">Requirements</span></span>  

 <span data-ttu-id="14311-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14311-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14311-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="14311-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="14311-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14311-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14311-112">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14311-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14311-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="14311-113">See also</span></span>

- [<span data-ttu-id="14311-114">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="14311-114">ICorDebug Interface</span></span>](icordebug-interface.md)
