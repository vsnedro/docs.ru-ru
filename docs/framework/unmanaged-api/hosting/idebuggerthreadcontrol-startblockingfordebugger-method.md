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
ms.openlocfilehash: 878dba37728734a777d2f95226b60bfbe9aae16a
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805270"
---
# <a name="idebuggerthreadcontrolstartblockingfordebugger-method"></a><span data-ttu-id="c089f-102">Метод IDebuggerThreadControl::StartBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="c089f-102">IDebuggerThreadControl::StartBlockingForDebugger Method</span></span>
<span data-ttu-id="c089f-103">Уведомляет узел о том, что служба отладки собирается начать блокирование всех потоков.</span><span class="sxs-lookup"><span data-stu-id="c089f-103">Notifies the host that the debugging services are about to start blocking all threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c089f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c089f-104">Syntax</span></span>  
  
```cpp  
HRESULT StartBlockingForDebugger (  
    [in] DWORD dwUnused  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c089f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c089f-105">Parameters</span></span>  
 `dwUnused`  
 <span data-ttu-id="c089f-106">[in] Зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="c089f-106">[in] Reserved for future use.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c089f-107">Замечания</span><span class="sxs-lookup"><span data-stu-id="c089f-107">Remarks</span></span>  
 <span data-ttu-id="c089f-108">`StartBlockingForDebugger`Метод может быть вызван в потоке среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="c089f-108">The `StartBlockingForDebugger` method could be called on a runtime thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c089f-109">Требования</span><span class="sxs-lookup"><span data-stu-id="c089f-109">Requirements</span></span>  
 <span data-ttu-id="c089f-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c089f-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c089f-111">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c089f-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c089f-112">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c089f-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c089f-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c089f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c089f-114">См. также статью</span><span class="sxs-lookup"><span data-stu-id="c089f-114">See also</span></span>

- [<span data-ttu-id="c089f-115">Интерфейс IDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="c089f-115">IDebuggerThreadControl Interface</span></span>](idebuggerthreadcontrol-interface.md)
