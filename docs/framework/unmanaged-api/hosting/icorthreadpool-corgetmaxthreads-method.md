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
ms.openlocfilehash: 46ffdb21c1f3b501cc28afffc224349887af5644
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762756"
---
# <a name="icorthreadpoolcorgetmaxthreads-method"></a><span data-ttu-id="1b2c0-102">Метод ICorThreadpool::CorGetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="1b2c0-102">ICorThreadpool::CorGetMaxThreads Method</span></span>
<span data-ttu-id="1b2c0-103">Этот метод поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="1b2c0-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b2c0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1b2c0-104">Syntax</span></span>  
  
```cpp  
HRESULT CorGetMaxThreads (  
    [out] DWORD *MaxWorkerThreads,  
    [out] DWORD *MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="1b2c0-105">Требования</span><span class="sxs-lookup"><span data-stu-id="1b2c0-105">Requirements</span></span>  
 <span data-ttu-id="1b2c0-106">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b2c0-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b2c0-107">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1b2c0-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1b2c0-108">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1b2c0-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1b2c0-109">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b2c0-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b2c0-110">См. также</span><span class="sxs-lookup"><span data-stu-id="1b2c0-110">See also</span></span>

- [<span data-ttu-id="1b2c0-111">Интерфейс ICorThreadpool</span><span class="sxs-lookup"><span data-stu-id="1b2c0-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
