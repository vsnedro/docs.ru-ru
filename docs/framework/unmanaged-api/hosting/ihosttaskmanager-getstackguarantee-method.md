---
title: Метод IHostTaskManager::GetStackGuarantee
ms.date: 03/30/2017
api_name:
- IHostTaskManager.GetStackGuarantee
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::GetStackGuarantee
helpviewer_keywords:
- GetStackGuarantee method [.NET Framework hosting]
- IHostTaskManager::GetStackGuarantee method [.NET Framework hosting]
ms.assetid: 8176d732-c25c-4520-811d-e3310f339947
topic_type:
- apiref
ms.openlocfilehash: 718e6f3f19a5c368091c8a8aad3bd1f6598228df
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727284"
---
# <a name="ihosttaskmanagergetstackguarantee-method"></a><span data-ttu-id="310d0-102">Метод IHostTaskManager::GetStackGuarantee</span><span class="sxs-lookup"><span data-stu-id="310d0-102">IHostTaskManager::GetStackGuarantee Method</span></span>

<span data-ttu-id="310d0-103">Возвращает объем стекового пространства, который гарантированно будет доступен после завершения операции с стеком, но до закрытия процесса.</span><span class="sxs-lookup"><span data-stu-id="310d0-103">Gets the amount of stack space that is guaranteed to be available after a stack operation completes, but before the closing of a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="310d0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="310d0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackGuarantee(  
    [out] ULONG *pGuarantee  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="310d0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="310d0-105">Parameters</span></span>  

 `pGuarantee`  
 <span data-ttu-id="310d0-106">заполняет Указатель на количество доступных байтов.</span><span class="sxs-lookup"><span data-stu-id="310d0-106">[out] A pointer to the number of bytes that are available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="310d0-107">Требования</span><span class="sxs-lookup"><span data-stu-id="310d0-107">Requirements</span></span>  

 <span data-ttu-id="310d0-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="310d0-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="310d0-109">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="310d0-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="310d0-110">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="310d0-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="310d0-111">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="310d0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="310d0-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="310d0-112">See also</span></span>

- [<span data-ttu-id="310d0-113">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="310d0-113">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
