---
title: Метод ICorConfiguration::SetDebuggerThreadControl
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetDebuggerThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetDebuggerThreadControl
helpviewer_keywords:
- SetDebuggerThreadControl method [.NET Framework hosting]
- ICorConfiguration::SetDebuggerThreadControl method [.NET Framework hosting]
ms.assetid: 1ded7639-dacb-4db1-961c-d1ceaec01959
topic_type:
- apiref
ms.openlocfilehash: 05df50d80c6b8962b3bdfe2708d5f9d30c58aaea
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723926"
---
# <a name="icorconfigurationsetdebuggerthreadcontrol-method"></a><span data-ttu-id="211af-102">Метод ICorConfiguration::SetDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="211af-102">ICorConfiguration::SetDebuggerThreadControl Method</span></span>

<span data-ttu-id="211af-103">Задает интерфейс обратного вызова, который службы отладки будут вызывать, так как потоки среды CLR блокируются и разблокируются для отладки.</span><span class="sxs-lookup"><span data-stu-id="211af-103">Sets the callback interface that the debugging services will call as common language runtime (CLR) threads are blocked and unblocked for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="211af-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="211af-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDebuggerThreadControl (  
    [in] IDebuggerThreadControl* pDebuggerThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="211af-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="211af-105">Parameters</span></span>  

 `pDebuggerThreadControl`  
 <span data-ttu-id="211af-106">окне Указатель на объект [идебугжерсреадконтрол](idebuggerthreadcontrol-interface.md) , который уведомляет узел о блокировании и разблокировке потоков службами отладки.</span><span class="sxs-lookup"><span data-stu-id="211af-106">[in] A pointer to an [IDebuggerThreadControl](idebuggerthreadcontrol-interface.md) object that notifies the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="211af-107">Требования</span><span class="sxs-lookup"><span data-stu-id="211af-107">Requirements</span></span>  

 <span data-ttu-id="211af-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="211af-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="211af-109">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="211af-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="211af-110">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="211af-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="211af-111">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="211af-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="211af-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="211af-112">See also</span></span>

- [<span data-ttu-id="211af-113">Интерфейс ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="211af-113">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)
