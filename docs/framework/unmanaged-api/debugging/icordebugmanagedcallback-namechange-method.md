---
title: Метод ICorDebugManagedCallback::NameChange
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.NameChange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::NameChange
helpviewer_keywords:
- ICorDebugManagedCallback::NameChange method [.NET Framework debugging]
- NameChange method [.NET Framework debugging]
ms.assetid: a7018a0e-880e-4b68-b52a-1cd22c7aad62
topic_type:
- apiref
ms.openlocfilehash: 0307ad5794d641833c2da1a1674e455ebff24861
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726526"
---
# <a name="icordebugmanagedcallbacknamechange-method"></a><span data-ttu-id="99926-102">Метод ICorDebugManagedCallback::NameChange</span><span class="sxs-lookup"><span data-stu-id="99926-102">ICorDebugManagedCallback::NameChange Method</span></span>

<span data-ttu-id="99926-103">Уведомляет отладчик о том, что имя домена приложения или потока изменилось.</span><span class="sxs-lookup"><span data-stu-id="99926-103">Notifies the debugger that the name of either an application domain or a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99926-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="99926-104">Syntax</span></span>  
  
```cpp  
HRESULT NameChange (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99926-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="99926-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="99926-106">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, в котором либо было изменено имя, либо содержащий поток, в котором было изменено имя.</span><span class="sxs-lookup"><span data-stu-id="99926-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that either had a name change or that contains the thread that had a name change.</span></span>  
  
 `pThread`  
 <span data-ttu-id="99926-107">окне Указатель на объект ICorDebugThread, представляющий поток, для которого было изменено имя.</span><span class="sxs-lookup"><span data-stu-id="99926-107">[in] A pointer to an ICorDebugThread object that represents the thread that had a name change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99926-108">Требования</span><span class="sxs-lookup"><span data-stu-id="99926-108">Requirements</span></span>  

 <span data-ttu-id="99926-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99926-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99926-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="99926-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="99926-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99926-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99926-112">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99926-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99926-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="99926-113">See also</span></span>

- [<span data-ttu-id="99926-114">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="99926-114">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
