---
title: Метод ICorDebugManagedCallback::EvalException
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.EvalException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::EvalException
helpviewer_keywords:
- EvalException method [.NET Framework debugging]
- ICorDebugManagedCallback::EvalException method [.NET Framework debugging]
ms.assetid: d6036345-18a3-45c1-a302-b1c6f2dced9b
topic_type:
- apiref
ms.openlocfilehash: 6c59ede004ce02ee3d14a448fc61d1c092bd0d61
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721274"
---
# <a name="icordebugmanagedcallbackevalexception-method"></a><span data-ttu-id="38433-102">Метод ICorDebugManagedCallback::EvalException</span><span class="sxs-lookup"><span data-stu-id="38433-102">ICorDebugManagedCallback::EvalException Method</span></span>

<span data-ttu-id="38433-103">Уведомляет отладчик о том, что вычисление завершено с необработанным исключением.</span><span class="sxs-lookup"><span data-stu-id="38433-103">Notifies the debugger that an evaluation has terminated with an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38433-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="38433-104">Syntax</span></span>  
  
```cpp  
HRESULT EvalException (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38433-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="38433-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="38433-106">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, в котором завершается вычисление.</span><span class="sxs-lookup"><span data-stu-id="38433-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation terminated.</span></span>  
  
 `pThread`  
 <span data-ttu-id="38433-107">окне Указатель на объект ICorDebugThread, представляющий поток, в котором завершено вычисление.</span><span class="sxs-lookup"><span data-stu-id="38433-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation terminated.</span></span>  
  
 `pEval`  
 <span data-ttu-id="38433-108">окне Указатель на объект ICorDebugEval, представляющий код, который выполнил вычисление.</span><span class="sxs-lookup"><span data-stu-id="38433-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38433-109">Требования</span><span class="sxs-lookup"><span data-stu-id="38433-109">Requirements</span></span>  

 <span data-ttu-id="38433-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38433-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38433-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="38433-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="38433-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38433-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38433-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38433-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38433-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="38433-114">See also</span></span>

- [<span data-ttu-id="38433-115">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="38433-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
