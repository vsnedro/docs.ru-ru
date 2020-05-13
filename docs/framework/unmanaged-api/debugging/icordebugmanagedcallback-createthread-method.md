---
title: Метод ICorDebugManagedCallback::CreateThread
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.CreateThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::CreateThread method
helpviewer_keywords:
- ICorDebugManagedCallback::CreateThread method [.NET Framework debugging]
- CreateThread method [.NET Framework debugging]
ms.assetid: 6b961728-21c4-4e8d-ae81-197458be62f4
topic_type:
- apiref
ms.openlocfilehash: 5fa3bafd35912a7729833896f7e6f0bb2ff9b121
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212390"
---
# <a name="icordebugmanagedcallbackcreatethread-method"></a><span data-ttu-id="e9945-102">Метод ICorDebugManagedCallback::CreateThread</span><span class="sxs-lookup"><span data-stu-id="e9945-102">ICorDebugManagedCallback::CreateThread Method</span></span>
<span data-ttu-id="e9945-103">Уведомляет отладчик о том, что поток начал выполнение управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="e9945-103">Notifies the debugger that a thread has started executing managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9945-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e9945-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9945-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e9945-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="e9945-106">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, содержащий поток.</span><span class="sxs-lookup"><span data-stu-id="e9945-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="e9945-107">окне Указатель на объект ICorDebugThread, представляющий поток.</span><span class="sxs-lookup"><span data-stu-id="e9945-107">[in] A pointer to an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9945-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="e9945-108">Remarks</span></span>  
 <span data-ttu-id="e9945-109">Поток будет размещен в первой выполняемой инструкции управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="e9945-109">The thread will be positioned at the first managed code instruction to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9945-110">Требования</span><span class="sxs-lookup"><span data-stu-id="e9945-110">Requirements</span></span>  
 <span data-ttu-id="e9945-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9945-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9945-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e9945-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e9945-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9945-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9945-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9945-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9945-115">См. также</span><span class="sxs-lookup"><span data-stu-id="e9945-115">See also</span></span>

- [<span data-ttu-id="e9945-116">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="e9945-116">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
