---
title: Метод ICorDebugManagedCallback::ExitProcess
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ExitProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitProcess
helpviewer_keywords:
- ExitProcess method, ICorDebugManagedCallback interface [.NET Framework debugging]
- ICorDebugManagedCallback::ExitProcess method [.NET Framework debugging]
ms.assetid: 63a7d47a-0d54-4e29-9767-9f09feaa38b7
topic_type:
- apiref
ms.openlocfilehash: 7a49bd6626518179c9b5ef008fca28d304537cc8
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205262"
---
# <a name="icordebugmanagedcallbackexitprocess-method"></a><span data-ttu-id="cf4c3-102">Метод ICorDebugManagedCallback::ExitProcess</span><span class="sxs-lookup"><span data-stu-id="cf4c3-102">ICorDebugManagedCallback::ExitProcess Method</span></span>
<span data-ttu-id="cf4c3-103">Уведомляет отладчик о завершении процесса.</span><span class="sxs-lookup"><span data-stu-id="cf4c3-103">Notifies the debugger that a process has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf4c3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cf4c3-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf4c3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cf4c3-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="cf4c3-106">окне Указатель на объект ICorDebugProcess, представляющий процесс.</span><span class="sxs-lookup"><span data-stu-id="cf4c3-106">[in] A pointer to an ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf4c3-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="cf4c3-107">Remarks</span></span>  
 <span data-ttu-id="cf4c3-108">Невозможно продолжить выполнение `ExitProcess` события.</span><span class="sxs-lookup"><span data-stu-id="cf4c3-108">You cannot continue from an `ExitProcess` event.</span></span> <span data-ttu-id="cf4c3-109">Это событие может вызываться асинхронно для других событий, пока процесс остановлен.</span><span class="sxs-lookup"><span data-stu-id="cf4c3-109">This event may fire asynchronously to other events while the process appears to be stopped.</span></span> <span data-ttu-id="cf4c3-110">Это может произойти, если процесс завершается при остановке, обычно из-за некоторой внешней силы.</span><span class="sxs-lookup"><span data-stu-id="cf4c3-110">This can occur if the process terminates while stopped, usually due to some external force.</span></span>  
  
 <span data-ttu-id="cf4c3-111">Если общеязыковая среда выполнения (CLR) уже передает управляемый обратный вызов, это событие будет отложено до тех пор, пока этот обратный вызов не вернется.</span><span class="sxs-lookup"><span data-stu-id="cf4c3-111">If the common language runtime (CLR) is already dispatching a managed callback, this event will be delayed until after that callback has returned.</span></span>  
  
 <span data-ttu-id="cf4c3-112">`ExitProcess`Событие является единственным событием Exit/unload, которое гарантированно вызывается при завершении работы.</span><span class="sxs-lookup"><span data-stu-id="cf4c3-112">The `ExitProcess` event is the only exit/unload event that is guaranteed to get called on shutdown.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf4c3-113">Требования</span><span class="sxs-lookup"><span data-stu-id="cf4c3-113">Requirements</span></span>  
 <span data-ttu-id="cf4c3-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf4c3-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf4c3-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cf4c3-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cf4c3-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf4c3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf4c3-117">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf4c3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf4c3-118">См. также</span><span class="sxs-lookup"><span data-stu-id="cf4c3-118">See also</span></span>

- [<span data-ttu-id="cf4c3-119">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="cf4c3-119">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
