---
title: Метод ICorDebugManagedCallback::LoadAssembly
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadAssembly
helpviewer_keywords:
- LoadAssembly method [.NET Framework debugging]
- ICorDebugManagedCallback::LoadAssembly method [.NET Framework debugging]
ms.assetid: 55cb673a-e240-43a6-a406-6912e7c0fe66
topic_type:
- apiref
ms.openlocfilehash: 8cb8699c103f48b42694449a2bb2bbd25c42d3c6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212736"
---
# <a name="icordebugmanagedcallbackloadassembly-method"></a><span data-ttu-id="2467a-102">Метод ICorDebugManagedCallback::LoadAssembly</span><span class="sxs-lookup"><span data-stu-id="2467a-102">ICorDebugManagedCallback::LoadAssembly Method</span></span>
<span data-ttu-id="2467a-103">Уведомляет отладчик о том, что сборка среды CLR была успешно загружена.</span><span class="sxs-lookup"><span data-stu-id="2467a-103">Notifies the debugger that a common language runtime (CLR) assembly has been successfully loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2467a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2467a-104">Syntax</span></span>  
  
```cpp  
HRESULT LoadAssembly (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugAssembly  *pAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2467a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2467a-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="2467a-106">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, в который была загружена сборка.</span><span class="sxs-lookup"><span data-stu-id="2467a-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the assembly has been loaded.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="2467a-107">окне Указатель на объект ICorDebugAssembly, представляющий сборку.</span><span class="sxs-lookup"><span data-stu-id="2467a-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2467a-108">Требования</span><span class="sxs-lookup"><span data-stu-id="2467a-108">Requirements</span></span>  
 <span data-ttu-id="2467a-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2467a-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2467a-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2467a-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2467a-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2467a-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2467a-112">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2467a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2467a-113">См. также</span><span class="sxs-lookup"><span data-stu-id="2467a-113">See also</span></span>

- [<span data-ttu-id="2467a-114">Метод UnloadAssembly</span><span class="sxs-lookup"><span data-stu-id="2467a-114">UnloadAssembly Method</span></span>](icordebugmanagedcallback-unloadassembly-method.md)
- [<span data-ttu-id="2467a-115">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="2467a-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
