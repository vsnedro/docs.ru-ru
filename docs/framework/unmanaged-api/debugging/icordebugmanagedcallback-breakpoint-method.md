---
title: Метод ICorDebugManagedCallback::Breakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.Breakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Breakpoint
helpviewer_keywords:
- ICorDebugManagedCallback::Breakpoint method [.NET Framework debugging]
- Breakpoint method [.NET Framework debugging]
ms.assetid: 60b279b0-a726-46d2-8c53-76986a007ebb
topic_type:
- apiref
ms.openlocfilehash: d7cf966f407572cc681f641b63791906a5c015f3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731869"
---
# <a name="icordebugmanagedcallbackbreakpoint-method"></a><span data-ttu-id="2c569-102">Метод ICorDebugManagedCallback::Breakpoint</span><span class="sxs-lookup"><span data-stu-id="2c569-102">ICorDebugManagedCallback::Breakpoint Method</span></span>

<span data-ttu-id="2c569-103">Уведомляет отладчик об обнаружении точки останова.</span><span class="sxs-lookup"><span data-stu-id="2c569-103">Notifies the debugger when a breakpoint is encountered.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c569-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2c569-104">Syntax</span></span>  
  
```cpp  
HRESULT Breakpoint (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c569-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2c569-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="2c569-106">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, содержащий точку останова.</span><span class="sxs-lookup"><span data-stu-id="2c569-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="2c569-107">окне Указатель на объект ICorDebugThread, представляющий поток, содержащий точку останова.</span><span class="sxs-lookup"><span data-stu-id="2c569-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="2c569-108">окне Указатель на объект Икордебугбреакпоинт, представляющий точку останова.</span><span class="sxs-lookup"><span data-stu-id="2c569-108">[in] A pointer to an ICorDebugBreakpoint object that represents the breakpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c569-109">Требования</span><span class="sxs-lookup"><span data-stu-id="2c569-109">Requirements</span></span>  

 <span data-ttu-id="2c569-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c569-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c569-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2c569-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c569-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c569-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c569-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c569-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c569-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2c569-114">See also</span></span>

- [<span data-ttu-id="2c569-115">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="2c569-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
