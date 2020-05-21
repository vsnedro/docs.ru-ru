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
ms.openlocfilehash: 7f972bcfedd028d85debbbd60968a57c4d64ee0c
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83760353"
---
# <a name="icorthreadpoolcorsetmaxthreads-method"></a><span data-ttu-id="2a889-102">Метод ICorThreadpool::CorSetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="2a889-102">ICorThreadpool::CorSetMaxThreads Method</span></span>
<span data-ttu-id="2a889-103">Этот метод поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="2a889-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a889-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2a889-104">Syntax</span></span>  
  
```cpp  
HRESULT CorSetMaxThreads (  
    [in] DWORD MaxWorkerThreads,  
    [in] DWORD MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="2a889-105">Требования</span><span class="sxs-lookup"><span data-stu-id="2a889-105">Requirements</span></span>  
 <span data-ttu-id="2a889-106">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a889-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a889-107">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2a889-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2a889-108">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2a889-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2a889-109">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a889-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a889-110">См. также</span><span class="sxs-lookup"><span data-stu-id="2a889-110">See also</span></span>

- [<span data-ttu-id="2a889-111">Интерфейс ICorThreadpool</span><span class="sxs-lookup"><span data-stu-id="2a889-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
