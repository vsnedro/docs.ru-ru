---
title: Метод ICorThreadpool::CorGetMaxThreads
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorGetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorGetMaxThreads
helpviewer_keywords:
- CorGetMaxThreads method [.NET Framework hosting]
- ICorThreadpool::CorGetMaxThreads method [.NET Framework hosting]
ms.assetid: 2861533a-cda0-47b3-b716-0d363505289b
topic_type:
- apiref
ms.openlocfilehash: 511b6e463bcd0d975cf7be96f870baefe27fc77b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720520"
---
# <a name="icorthreadpoolcorgetmaxthreads-method"></a><span data-ttu-id="b963f-102">Метод ICorThreadpool::CorGetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="b963f-102">ICorThreadpool::CorGetMaxThreads Method</span></span>

<span data-ttu-id="b963f-103">Этот метод поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="b963f-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b963f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b963f-104">Syntax</span></span>  
  
```cpp  
HRESULT CorGetMaxThreads (  
    [out] DWORD *MaxWorkerThreads,  
    [out] DWORD *MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="b963f-105">Требования</span><span class="sxs-lookup"><span data-stu-id="b963f-105">Requirements</span></span>  

 <span data-ttu-id="b963f-106">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b963f-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b963f-107">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b963f-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b963f-108">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b963f-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b963f-109">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b963f-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b963f-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b963f-110">See also</span></span>

- [<span data-ttu-id="b963f-111">Интерфейс ICorThreadpool</span><span class="sxs-lookup"><span data-stu-id="b963f-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
