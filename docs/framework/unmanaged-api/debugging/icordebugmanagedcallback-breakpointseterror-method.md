---
title: Метод ICorDebugManagedCallback::BreakpointSetError
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.BreakpointSetError
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::BreakpointSetError
helpviewer_keywords:
- BreakpointSetError method [.NET Framework debugging]
- ICorDebugManagedCallback::BreakpointSetError method [.NET Framework debugging]
ms.assetid: f2b773a4-c4d0-429c-9717-51d6e2ed86af
topic_type:
- apiref
ms.openlocfilehash: cac8393408de626efe2360999e259780eac29f38
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721339"
---
# <a name="icordebugmanagedcallbackbreakpointseterror-method"></a><span data-ttu-id="15c69-102">Метод ICorDebugManagedCallback::BreakpointSetError</span><span class="sxs-lookup"><span data-stu-id="15c69-102">ICorDebugManagedCallback::BreakpointSetError Method</span></span>

<span data-ttu-id="15c69-103">Уведомляет отладчик о том, что среде CLR не удалось точно привязать точку останова, установленную до JIT-компиляции функции.</span><span class="sxs-lookup"><span data-stu-id="15c69-103">Notifies the debugger that the common language runtime was unable to accurately bind a breakpoint that was set before a function was just-in-time (JIT) compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15c69-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="15c69-104">Syntax</span></span>  
  
```cpp  
HRESULT BreakpointSetError (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint,  
    [in] DWORD                dwError  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15c69-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="15c69-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="15c69-106">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, который содержит несвязанную точку останова.</span><span class="sxs-lookup"><span data-stu-id="15c69-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the unbound breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="15c69-107">окне Указатель на объект ICorDebugThread, представляющий поток, содержащий несвязанную точку останова.</span><span class="sxs-lookup"><span data-stu-id="15c69-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the unbound breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="15c69-108">окне Указатель на объект Икордебугбреакпоинт, представляющий несвязанную точку останова.</span><span class="sxs-lookup"><span data-stu-id="15c69-108">[in] A pointer to an ICorDebugBreakpoint object that represents the unbound breakpoint.</span></span>  
  
 `dwError`  
 <span data-ttu-id="15c69-109">окне Целое число, указывающее на ошибку.</span><span class="sxs-lookup"><span data-stu-id="15c69-109">[in] An integer that indicates the error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15c69-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="15c69-110">Remarks</span></span>  

 <span data-ttu-id="15c69-111">Заданная точка останова никогда не будет достигнута.</span><span class="sxs-lookup"><span data-stu-id="15c69-111">The given breakpoint will never be hit.</span></span> <span data-ttu-id="15c69-112">Отладчик должен деактивироваться и повторно привязывать его.</span><span class="sxs-lookup"><span data-stu-id="15c69-112">The debugger should deactivate and rebind it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15c69-113">Требования</span><span class="sxs-lookup"><span data-stu-id="15c69-113">Requirements</span></span>  

 <span data-ttu-id="15c69-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15c69-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15c69-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="15c69-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="15c69-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15c69-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15c69-117">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15c69-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15c69-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="15c69-118">See also</span></span>

- [<span data-ttu-id="15c69-119">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="15c69-119">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
