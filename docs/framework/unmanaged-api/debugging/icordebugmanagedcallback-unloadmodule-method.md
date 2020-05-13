---
title: Метод ICorDebugManagedCallback::UnloadModule
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadModule
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadModule method [.NET Framework debugging]
- UnloadModule method [.NET Framework debugging]
ms.assetid: b12bfcd9-1e29-48bf-9a3d-44bfae5df5e8
topic_type:
- apiref
ms.openlocfilehash: 4b44a16d143c1daea1ea6c36eb096ab9a937b272
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210050"
---
# <a name="icordebugmanagedcallbackunloadmodule-method"></a><span data-ttu-id="08dc8-102">Метод ICorDebugManagedCallback::UnloadModule</span><span class="sxs-lookup"><span data-stu-id="08dc8-102">ICorDebugManagedCallback::UnloadModule Method</span></span>
<span data-ttu-id="08dc8-103">Уведомляет отладчик о выгрузке модуля общеязыковой среды выполнения (DLL).</span><span class="sxs-lookup"><span data-stu-id="08dc8-103">Notifies the debugger that a common language runtime module (DLL) has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08dc8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="08dc8-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadModule (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugModule     *pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08dc8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="08dc8-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="08dc8-106">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, в котором содержится модуль.</span><span class="sxs-lookup"><span data-stu-id="08dc8-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the module.</span></span>  
  
 `pModule`  
 <span data-ttu-id="08dc8-107">окне Указатель на объект ICorDebugModule, представляющий модуль.</span><span class="sxs-lookup"><span data-stu-id="08dc8-107">[in] A pointer to an ICorDebugModule object that represents the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08dc8-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="08dc8-108">Remarks</span></span>  
 <span data-ttu-id="08dc8-109">Модуль не должен использоваться после этого вызова.</span><span class="sxs-lookup"><span data-stu-id="08dc8-109">The module should not be used after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08dc8-110">Требования</span><span class="sxs-lookup"><span data-stu-id="08dc8-110">Requirements</span></span>  
 <span data-ttu-id="08dc8-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08dc8-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08dc8-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="08dc8-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="08dc8-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08dc8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08dc8-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08dc8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08dc8-115">См. также</span><span class="sxs-lookup"><span data-stu-id="08dc8-115">See also</span></span>

- [<span data-ttu-id="08dc8-116">Метод LoadModule</span><span class="sxs-lookup"><span data-stu-id="08dc8-116">LoadModule Method</span></span>](icordebugmanagedcallback-loadmodule-method.md)
- [<span data-ttu-id="08dc8-117">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="08dc8-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
