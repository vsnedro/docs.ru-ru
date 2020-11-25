---
title: Метод ICorThreadpool::CorSetMaxThreads
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorSetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSetMaxThreads
helpviewer_keywords:
- ICorThreadpool::CorSetMaxThreads method [.NET Framework hosting]
- CorSetMaxThreads method [.NET Framework hosting]
ms.assetid: 4a846238-df4e-4060-ba3b-5173f6a51e85
topic_type:
- apiref
ms.openlocfilehash: f7d9d3d059abcf58fe0f4b35ce41046efb9c2400
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733988"
---
# <a name="icorthreadpoolcorsetmaxthreads-method"></a><span data-ttu-id="c49c5-102">Метод ICorThreadpool::CorSetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="c49c5-102">ICorThreadpool::CorSetMaxThreads Method</span></span>

<span data-ttu-id="c49c5-103">Этот метод поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="c49c5-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c49c5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c49c5-104">Syntax</span></span>  
  
```cpp  
HRESULT CorSetMaxThreads (  
    [in] DWORD MaxWorkerThreads,  
    [in] DWORD MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="c49c5-105">Требования</span><span class="sxs-lookup"><span data-stu-id="c49c5-105">Requirements</span></span>  

 <span data-ttu-id="c49c5-106">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c49c5-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c49c5-107">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c49c5-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c49c5-108">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c49c5-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c49c5-109">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c49c5-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c49c5-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c49c5-110">See also</span></span>

- [<span data-ttu-id="c49c5-111">Интерфейс ICorThreadpool</span><span class="sxs-lookup"><span data-stu-id="c49c5-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
