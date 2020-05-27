---
title: Метод IDebuggerThreadControl::ReleaseAllRuntimeThreads
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.ReleaseAllRuntimeThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ReleaseAllRuntimeThreads
helpviewer_keywords:
- ReleaseAllRuntimeThreads method [.NET Framework hosting]
- IDebuggerThreadControl::ReleaseAllRuntimeThreads method [.NET Framework hosting]
ms.assetid: 1a2995ff-5f02-4b49-84dc-3a5f9cfd7d55
topic_type:
- apiref
ms.openlocfilehash: 50ffb33456f942a71089f9bc44daa07f6b77ab21
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805300"
---
# <a name="idebuggerthreadcontrolreleaseallruntimethreads-method"></a><span data-ttu-id="eb2e2-102">Метод IDebuggerThreadControl::ReleaseAllRuntimeThreads</span><span class="sxs-lookup"><span data-stu-id="eb2e2-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads Method</span></span>
<span data-ttu-id="eb2e2-103">Уведомляет узел о том, что службы отладки собирается освободить все заблокированные потоки.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-103">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb2e2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eb2e2-104">Syntax</span></span>  
  
```cpp  
HRESULT ReleaseAllRuntimeThreads ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="eb2e2-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="eb2e2-105">Remarks</span></span>  
 <span data-ttu-id="eb2e2-106">`ReleaseAllRuntimeThreads`Метод никогда не будет вызываться в потоке среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-106">The `ReleaseAllRuntimeThreads` method will never be called on a runtime thread.</span></span> <span data-ttu-id="eb2e2-107">Если в узле заблокирован поток среды выполнения, он должен освободить его сейчас.</span><span class="sxs-lookup"><span data-stu-id="eb2e2-107">If the host has a runtime thread blocked, it should release it now.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb2e2-108">Требования</span><span class="sxs-lookup"><span data-stu-id="eb2e2-108">Requirements</span></span>  
 <span data-ttu-id="eb2e2-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb2e2-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb2e2-110">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="eb2e2-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="eb2e2-111">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="eb2e2-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eb2e2-112">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb2e2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb2e2-113">См. также статью</span><span class="sxs-lookup"><span data-stu-id="eb2e2-113">See also</span></span>

- [<span data-ttu-id="eb2e2-114">Интерфейс IDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="eb2e2-114">IDebuggerThreadControl Interface</span></span>](idebuggerthreadcontrol-interface.md)
