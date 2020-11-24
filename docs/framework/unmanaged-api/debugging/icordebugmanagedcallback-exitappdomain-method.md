---
title: Метод ICorDebugManagedCallback::ExitAppDomain
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ExitAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitAppDomain
helpviewer_keywords:
- ICorDebugManagedCallback::ExitAppDomain method [.NET Framework debugging]
- ExitAppDomain method [.NET Framework debugging]
ms.assetid: d815486e-b3bd-4fe8-ba28-02abdb4d67ba
topic_type:
- apiref
ms.openlocfilehash: 51beed47e7187d6fa22e60baed16598a8ad73adb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688995"
---
# <a name="icordebugmanagedcallbackexitappdomain-method"></a><span data-ttu-id="4c973-102">Метод ICorDebugManagedCallback::ExitAppDomain</span><span class="sxs-lookup"><span data-stu-id="4c973-102">ICorDebugManagedCallback::ExitAppDomain Method</span></span>

<span data-ttu-id="4c973-103">Уведомляет отладчик о завершении работы домена приложения.</span><span class="sxs-lookup"><span data-stu-id="4c973-103">Notifies the debugger that an application domain has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c973-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4c973-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c973-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4c973-105">Parameters</span></span>  

 `pProcess`  
 <span data-ttu-id="4c973-106">окне Указатель на объект ICorDebugProcess, представляющий процесс, который содержит заданный домен приложения.</span><span class="sxs-lookup"><span data-stu-id="4c973-106">[in] A pointer to an ICorDebugProcess object that represents the process that contains the given application domain.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="4c973-107">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, который завершил работу.</span><span class="sxs-lookup"><span data-stu-id="4c973-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has exited.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c973-108">Требования</span><span class="sxs-lookup"><span data-stu-id="4c973-108">Requirements</span></span>  

 <span data-ttu-id="4c973-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c973-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c973-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4c973-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4c973-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4c973-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4c973-112">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c973-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c973-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4c973-113">See also</span></span>

- [<span data-ttu-id="4c973-114">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="4c973-114">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
