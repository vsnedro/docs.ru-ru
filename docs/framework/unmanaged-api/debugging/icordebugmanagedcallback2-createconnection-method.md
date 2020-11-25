---
title: Метод ICorDebugManagedCallback2::CreateConnection
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.CreateConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::CreateConnection
helpviewer_keywords:
- CreateConnection method [.NET Framework debugging]
- ICorDebugManagedCallback2::CreateConnection method [.NET Framework debugging]
ms.assetid: 49e647be-9d63-4250-9d11-704e2a400d1b
topic_type:
- apiref
ms.openlocfilehash: 5a4ebf65dfaaa487e87f3fd78e54c468c7e24a89
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697250"
---
# <a name="icordebugmanagedcallback2createconnection-method"></a><span data-ttu-id="86158-102">Метод ICorDebugManagedCallback2::CreateConnection</span><span class="sxs-lookup"><span data-stu-id="86158-102">ICorDebugManagedCallback2::CreateConnection Method</span></span>

<span data-ttu-id="86158-103">Уведомляет отладчик о создании нового соединения.</span><span class="sxs-lookup"><span data-stu-id="86158-103">Notifies the debugger that a new connection has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86158-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="86158-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId,  
    [in] WCHAR                *pConnName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86158-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="86158-105">Parameters</span></span>  

 `pProcess`  
 <span data-ttu-id="86158-106">окне Указатель на объект "ICorDebugProcess", представляющий процесс, в котором было создано соединение</span><span class="sxs-lookup"><span data-stu-id="86158-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the connection was created</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="86158-107">окне Идентификатор нового соединения.</span><span class="sxs-lookup"><span data-stu-id="86158-107">[in] The ID of the new connection.</span></span>  
  
 `pConnName`  
 <span data-ttu-id="86158-108">окне Указатель на имя нового соединения.</span><span class="sxs-lookup"><span data-stu-id="86158-108">[in] A pointer to the name of the new connection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86158-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="86158-109">Remarks</span></span>  

 <span data-ttu-id="86158-110">`CreateConnection`Обратный вызов будет срабатывать в одном из следующих случаев.</span><span class="sxs-lookup"><span data-stu-id="86158-110">A `CreateConnection` callback will be fired in either of the following cases:</span></span>  
  
- <span data-ttu-id="86158-111">При присоединении отладчика к процессу, который содержит соединения.</span><span class="sxs-lookup"><span data-stu-id="86158-111">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="86158-112">В этом случае среда выполнения создаст и отправит `CreateConnection` событие и событие [ICorDebugManagedCallback2:: чанжеконнектион](icordebugmanagedcallback2-changeconnection-method.md) для каждого соединения в процессе.</span><span class="sxs-lookup"><span data-stu-id="86158-112">In this case, the runtime will generate and dispatch a `CreateConnection` event and a [ICorDebugManagedCallback2::ChangeConnection](icordebugmanagedcallback2-changeconnection-method.md) event for each connection in the process.</span></span>  
  
- <span data-ttu-id="86158-113">Когда узел вызывает [ICLRDebugManager:: бегинконнектион](../hosting/iclrdebugmanager-beginconnection-method.md) в [API размещения](../hosting/index.md).</span><span class="sxs-lookup"><span data-stu-id="86158-113">When a host calls [ICLRDebugManager::BeginConnection](../hosting/iclrdebugmanager-beginconnection-method.md) in the [Hosting API](../hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86158-114">Требования</span><span class="sxs-lookup"><span data-stu-id="86158-114">Requirements</span></span>  

 <span data-ttu-id="86158-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86158-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86158-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="86158-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="86158-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86158-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86158-118">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86158-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86158-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="86158-119">See also</span></span>

- [<span data-ttu-id="86158-120">Интерфейс ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="86158-120">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="86158-121">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="86158-121">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
