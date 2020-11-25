---
title: Метод ICorThreadpool::CorUnregisterWait
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorUnregisterWait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorUnregisterWait
helpviewer_keywords:
- CorUnregisterWait method [.NET Framework hosting]
- ICorThreadpool::CorUnregisterWait method [.NET Framework hosting]
ms.assetid: 42c933f1-30a8-4011-bdea-e117f3c3265e
topic_type:
- apiref
ms.openlocfilehash: 38b3655da75750ffc3ea1c7983ce3b549d76f087
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733976"
---
# <a name="icorthreadpoolcorunregisterwait-method"></a><span data-ttu-id="df2f0-102">Метод ICorThreadpool::CorUnregisterWait</span><span class="sxs-lookup"><span data-stu-id="df2f0-102">ICorThreadpool::CorUnregisterWait Method</span></span>

<span data-ttu-id="df2f0-103">Этот метод поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="df2f0-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df2f0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="df2f0-104">Syntax</span></span>  
  
```cpp  
HRESULT CorUnregisterWait (  
    [in] HANDLE hWaitObject,  
    [in] HANDLE CompletionEvent,  
    [out] BOOL* result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="df2f0-105">Требования</span><span class="sxs-lookup"><span data-stu-id="df2f0-105">Requirements</span></span>  

 <span data-ttu-id="df2f0-106">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df2f0-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df2f0-107">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="df2f0-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="df2f0-108">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="df2f0-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="df2f0-109">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df2f0-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df2f0-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="df2f0-110">See also</span></span>

- [<span data-ttu-id="df2f0-111">Интерфейс ICorThreadpool</span><span class="sxs-lookup"><span data-stu-id="df2f0-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
