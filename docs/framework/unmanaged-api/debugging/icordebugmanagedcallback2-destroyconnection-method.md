---
title: Метод ICorDebugManagedCallback2::DestroyConnection
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.DestroyConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::DestroyConnection
helpviewer_keywords:
- DestroyConnection method [.NET Framework debugging]
- ICorDebugManagedCallback2::DestroyConnection method [.NET Framework debugging]
ms.assetid: cf7940e9-4558-4319-925c-09f6c98c8fcd
topic_type:
- apiref
ms.openlocfilehash: c5527f3bd0b04857a1ebc520016b81ddbe3c23f8
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208929"
---
# <a name="icordebugmanagedcallback2destroyconnection-method"></a><span data-ttu-id="5cece-102">Метод ICorDebugManagedCallback2::DestroyConnection</span><span class="sxs-lookup"><span data-stu-id="5cece-102">ICorDebugManagedCallback2::DestroyConnection Method</span></span>
<span data-ttu-id="5cece-103">Уведомляет отладчик о завершении указанного соединения.</span><span class="sxs-lookup"><span data-stu-id="5cece-103">Notifies the debugger that the specified connection has been terminated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cece-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5cece-104">Syntax</span></span>  
  
```cpp  
HRESULT DestroyConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5cece-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5cece-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="5cece-106">окне Указатель на объект ICorDebugProcess, представляющий процесс, содержащий удаленное соединение.</span><span class="sxs-lookup"><span data-stu-id="5cece-106">[in] A pointer to an ICorDebugProcess object that represents the process containing the connection that was destroyed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="5cece-107">окне Идентификатор уничтоженного соединения.</span><span class="sxs-lookup"><span data-stu-id="5cece-107">[in] The ID of the connection that was destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5cece-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="5cece-108">Remarks</span></span>  
 <span data-ttu-id="5cece-109">`DestroyConnection`Обратный вызов будет срабатывать, когда узел вызывает [ICLRDebugManager:: ЕНДКОННЕКТИОН](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md) в [API размещения](../hosting/index.md).</span><span class="sxs-lookup"><span data-stu-id="5cece-109">A `DestroyConnection` callback will be fired when a host calls [ICLRDebugManager::EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md) in the [Hosting API](../hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cece-110">Требования</span><span class="sxs-lookup"><span data-stu-id="5cece-110">Requirements</span></span>  
 <span data-ttu-id="5cece-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5cece-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cece-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5cece-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5cece-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5cece-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5cece-114">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5cece-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cece-115">См. также</span><span class="sxs-lookup"><span data-stu-id="5cece-115">See also</span></span>

- [<span data-ttu-id="5cece-116">Интерфейс ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="5cece-116">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="5cece-117">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="5cece-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
