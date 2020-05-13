---
title: Метод ICorDebugManagedCallback::CreateProcess
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.CreateProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::CreateProcess
helpviewer_keywords:
- ICorDebugManagedCallback::CreateProcess method [.NET Framework debugging]
- CreateProcess method, ICorDebugManagedCallback interface [.NET Framework debugging]
ms.assetid: 8e89d5ee-e4e3-4738-8302-0b7d1cf4846e
topic_type:
- apiref
ms.openlocfilehash: 0e9ed8054711297173e880c9eecb12c3f5bd0a68
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207136"
---
# <a name="icordebugmanagedcallbackcreateprocess-method"></a><span data-ttu-id="782a4-102">Метод ICorDebugManagedCallback::CreateProcess</span><span class="sxs-lookup"><span data-stu-id="782a4-102">ICorDebugManagedCallback::CreateProcess Method</span></span>
<span data-ttu-id="782a4-103">Уведомляет отладчик о том, что процесс был присоединен или запущен в первый раз.</span><span class="sxs-lookup"><span data-stu-id="782a4-103">Notifies the debugger when a process has been attached or started for the first time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="782a4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="782a4-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="782a4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="782a4-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="782a4-106">окне Указатель на объект ICorDebugProcess, представляющий процесс, который был присоединен или запущен.</span><span class="sxs-lookup"><span data-stu-id="782a4-106">[in] A pointer to an ICorDebugProcess object that represents the process that has been attached or started.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="782a4-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="782a4-107">Remarks</span></span>  
 <span data-ttu-id="782a4-108">Этот метод не вызывается до тех пор, пока не будет инициализирована среда CLR.</span><span class="sxs-lookup"><span data-stu-id="782a4-108">This method is not called until the common language runtime is initialized.</span></span> <span data-ttu-id="782a4-109">Большая часть методов [ICorDebug](icordebug-interface.md) возвратит CORDBG_E_NOTREADY перед `CreateProcess` обратным вызовом.</span><span class="sxs-lookup"><span data-stu-id="782a4-109">Most of the [ICorDebug](icordebug-interface.md) methods will return CORDBG_E_NOTREADY before the `CreateProcess` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="782a4-110">Требования</span><span class="sxs-lookup"><span data-stu-id="782a4-110">Requirements</span></span>  
 <span data-ttu-id="782a4-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="782a4-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="782a4-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="782a4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="782a4-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="782a4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="782a4-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="782a4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="782a4-115">См. также</span><span class="sxs-lookup"><span data-stu-id="782a4-115">See also</span></span>

- [<span data-ttu-id="782a4-116">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="782a4-116">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
