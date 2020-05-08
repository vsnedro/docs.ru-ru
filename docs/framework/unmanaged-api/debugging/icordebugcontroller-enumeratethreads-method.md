---
title: Метод ICorDebugController::EnumerateThreads
ms.date: 03/30/2017
api_name:
- ICorDebugController.EnumerateThreads
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::EnumerateThreads
helpviewer_keywords:
- ICorDebugController::EnumerateThreads method [.NET Framework debugging]
- EnumerateThreads method [.NET Framework debugging]
ms.assetid: 73f536f6-4668-4a4a-b3e4-ac7df862d5be
topic_type:
- apiref
ms.openlocfilehash: 4d69f13d4716b43c815148ff0fe4aa087b57c6e5
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82892758"
---
# <a name="icordebugcontrollerenumeratethreads-method"></a><span data-ttu-id="407b7-102">Метод ICorDebugController::EnumerateThreads</span><span class="sxs-lookup"><span data-stu-id="407b7-102">ICorDebugController::EnumerateThreads Method</span></span>
<span data-ttu-id="407b7-103">Возвращает перечислитель для активных управляемых потоков в процессе.</span><span class="sxs-lookup"><span data-stu-id="407b7-103">Gets an enumerator for the active managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="407b7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="407b7-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="407b7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="407b7-105">Parameters</span></span>  
 `ppThreads`  
 <span data-ttu-id="407b7-106">заполняет Указатель на адрес объекта "Икордебугсреаденум", который представляет перечислитель для всех управляемых потоков, активных в процессе.</span><span class="sxs-lookup"><span data-stu-id="407b7-106">[out] A pointer to the address of an "ICorDebugThreadEnum" object that represents an enumerator for all managed threads that are active in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="407b7-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="407b7-107">Remarks</span></span>  
 <span data-ttu-id="407b7-108">Поток считается активным после отправки обратного вызова [ICorDebugManagedCallback:: CreateThread](icordebugmanagedcallback-createthread-method.md) и перед отправкой обратного вызова [ICorDebugManagedCallback:: ExitThread](icordebugmanagedcallback-exitthread-method.md) .</span><span class="sxs-lookup"><span data-stu-id="407b7-108">A thread is considered active after the [ICorDebugManagedCallback::CreateThread](icordebugmanagedcallback-createthread-method.md) callback has been dispatched and before the [ICorDebugManagedCallback::ExitThread](icordebugmanagedcallback-exitthread-method.md) callback has been dispatched.</span></span> <span data-ttu-id="407b7-109">Управляемый поток может не обязательно содержать управляемые фреймы в своем стеке.</span><span class="sxs-lookup"><span data-stu-id="407b7-109">A managed thread may not necessarily have any managed frames on its stack.</span></span> <span data-ttu-id="407b7-110">Потоки можно перечислить даже перед обратным вызовом [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="407b7-110">Threads can be enumerated even before the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="407b7-111">Перечисление естественным образом будет пустым.</span><span class="sxs-lookup"><span data-stu-id="407b7-111">The enumeration will naturally be empty.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="407b7-112">Требования</span><span class="sxs-lookup"><span data-stu-id="407b7-112">Requirements</span></span>  
 <span data-ttu-id="407b7-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="407b7-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="407b7-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="407b7-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="407b7-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="407b7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="407b7-116">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="407b7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="407b7-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="407b7-117">See also</span></span>
