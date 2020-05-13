---
title: Метод ICorDebugManagedCallback::EditAndContinueRemap
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.EditAndContinueRemap
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::EditAndContinueRemap
helpviewer_keywords:
- EditAndContinueRemap method [.NET Framework debugging]
- ICorDebugManagedCallback::EditAndContinueRemap method [.NET Framework debugging]
ms.assetid: 24a8fcce-317e-48ff-aefc-d86123ada935
topic_type:
- apiref
ms.openlocfilehash: 78b87b5c566b0d760a205757430123665fb2fcd3
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213716"
---
# <a name="icordebugmanagedcallbackeditandcontinueremap-method"></a><span data-ttu-id="c96aa-102">Метод ICorDebugManagedCallback::EditAndContinueRemap</span><span class="sxs-lookup"><span data-stu-id="c96aa-102">ICorDebugManagedCallback::EditAndContinueRemap Method</span></span>
<span data-ttu-id="c96aa-103">Этот метод использовать не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="c96aa-103">This method has been deprecated.</span></span> <span data-ttu-id="c96aa-104">Он уведомляет отладчик о том, что событие повторного сопоставления было отправлено в интегрированную среду разработки (IDE).</span><span class="sxs-lookup"><span data-stu-id="c96aa-104">It notifies the debugger that a remap event has been sent to the integrated development environment (IDE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c96aa-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c96aa-105">Syntax</span></span>  
  
```cpp  
HRESULT EditAndContinueRemap (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread *pThread,  
    [in] ICorDebugFunction *pFunction,  
    [in] BOOL fAccurate  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="c96aa-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="c96aa-106">Remarks</span></span>  
 <span data-ttu-id="c96aa-107">`EditAndContinueRemap`Метод вызывается при попыток выполнения кода в старой версии обновленной функции.</span><span class="sxs-lookup"><span data-stu-id="c96aa-107">The `EditAndContinueRemap` method is called when the execution of the code in an old version of an updated function has been attempted.</span></span> <span data-ttu-id="c96aa-108">Среда CLR вызывает `EditAndContinueRemap` метод для отправки события повторного сопоставления в интегрированную среду разработки.</span><span class="sxs-lookup"><span data-stu-id="c96aa-108">The common language runtime calls the `EditAndContinueRemap` method to send a remap event to the IDE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c96aa-109">Требования</span><span class="sxs-lookup"><span data-stu-id="c96aa-109">Requirements</span></span>  
 <span data-ttu-id="c96aa-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c96aa-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c96aa-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c96aa-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c96aa-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c96aa-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c96aa-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c96aa-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c96aa-114">См. также</span><span class="sxs-lookup"><span data-stu-id="c96aa-114">See also</span></span>

- [<span data-ttu-id="c96aa-115">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="c96aa-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
