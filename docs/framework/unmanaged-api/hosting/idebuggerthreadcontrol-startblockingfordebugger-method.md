---
title: Метод IDebuggerThreadControl::StartBlockingForDebugger
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.StartBlockingForDebugger
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StartBlockingForDebugger
helpviewer_keywords:
- IDebuggerThreadControl::StartBlockingForDebugger method [.NET Framework hosting]
- StartBlockingForDebugger method [.NET Framework hosting]
ms.assetid: 5c8f11b4-35d3-4c39-9bbd-58b896ba5ba6
topic_type:
- apiref
ms.openlocfilehash: 1e0cb52a6b9f03209256e5398415b4ec632fb5e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705512"
---
# <a name="idebuggerthreadcontrolstartblockingfordebugger-method"></a><span data-ttu-id="9419b-102">Метод IDebuggerThreadControl::StartBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="9419b-102">IDebuggerThreadControl::StartBlockingForDebugger Method</span></span>

<span data-ttu-id="9419b-103">Уведомляет узел о том, что служба отладки собирается начать блокирование всех потоков.</span><span class="sxs-lookup"><span data-stu-id="9419b-103">Notifies the host that the debugging services are about to start blocking all threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9419b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9419b-104">Syntax</span></span>  
  
```cpp  
HRESULT StartBlockingForDebugger (  
    [in] DWORD dwUnused  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9419b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9419b-105">Parameters</span></span>  

 `dwUnused`  
 <span data-ttu-id="9419b-106">[in] Зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="9419b-106">[in] Reserved for future use.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9419b-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="9419b-107">Remarks</span></span>  

 <span data-ttu-id="9419b-108">`StartBlockingForDebugger`Метод может быть вызван в потоке среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="9419b-108">The `StartBlockingForDebugger` method could be called on a runtime thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9419b-109">Требования</span><span class="sxs-lookup"><span data-stu-id="9419b-109">Requirements</span></span>  

 <span data-ttu-id="9419b-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9419b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9419b-111">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9419b-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9419b-112">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9419b-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9419b-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9419b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9419b-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9419b-114">See also</span></span>

- [<span data-ttu-id="9419b-115">Интерфейс IDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="9419b-115">IDebuggerThreadControl Interface</span></span>](idebuggerthreadcontrol-interface.md)
