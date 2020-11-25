---
title: Метод ICorThreadpool::CorGetAvailableThreads
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorGetAvailableThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorGetAvailableThreads
helpviewer_keywords:
- CorGetAvailableThreads method [.NET Framework hosting]
- ICorThreadpool::CorGetAvailableThreads method [.NET Framework hosting]
ms.assetid: 0b09b750-0b86-4ba4-9621-041857cfe8ba
topic_type:
- apiref
ms.openlocfilehash: 09b1f56600c05bf8e6028328adb80083b03ccc13
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725785"
---
# <a name="icorthreadpoolcorgetavailablethreads-method"></a><span data-ttu-id="32dc1-102">Метод ICorThreadpool::CorGetAvailableThreads</span><span class="sxs-lookup"><span data-stu-id="32dc1-102">ICorThreadpool::CorGetAvailableThreads Method</span></span>

<span data-ttu-id="32dc1-103">Этот метод поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="32dc1-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32dc1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="32dc1-104">Syntax</span></span>  
  
```cpp  
HRESULT CorGetAvailableThreads (  
    [out] DWORD *AvailableWorkerThreads,  
    [out] DWORD *AvailableIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="32dc1-105">Требования</span><span class="sxs-lookup"><span data-stu-id="32dc1-105">Requirements</span></span>  

 <span data-ttu-id="32dc1-106">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32dc1-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32dc1-107">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="32dc1-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="32dc1-108">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="32dc1-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="32dc1-109">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32dc1-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32dc1-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="32dc1-110">See also</span></span>

- [<span data-ttu-id="32dc1-111">Интерфейс ICorThreadpool</span><span class="sxs-lookup"><span data-stu-id="32dc1-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
