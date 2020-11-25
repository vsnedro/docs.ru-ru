---
title: Метод IGCHostControl::RequestVirtualMemLimit
ms.date: 03/30/2017
api_name:
- IGCHostControl.RequestVirtualMemLimit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- RequestVirtualMemLimit
helpviewer_keywords:
- IGCHostControl::RequestVirtualMemLimit method [.NET Framework hosting]
- RequestVirtualMemLimit method [.NET Framework hosting]
ms.assetid: f4984a8c-4c0e-4460-9aa1-d022b3621228
topic_type:
- apiref
ms.openlocfilehash: bbcabdec45945b969230a40b85a62e24e323ccc4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733936"
---
# <a name="igchostcontrolrequestvirtualmemlimit-method"></a><span data-ttu-id="4861e-102">Метод IGCHostControl::RequestVirtualMemLimit</span><span class="sxs-lookup"><span data-stu-id="4861e-102">IGCHostControl::RequestVirtualMemLimit Method</span></span>

<span data-ttu-id="4861e-103">Запрашивает у узла изменение ограничений виртуальной памяти.</span><span class="sxs-lookup"><span data-stu-id="4861e-103">Requests the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4861e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4861e-104">Syntax</span></span>  
  
```cpp  
HRESULT RequestVirtualMemLimit (  
    [in] SIZE_T       sztMaxVirtualMemMB,  
    [in, out] SIZE_T* psztNewMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4861e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4861e-105">Parameters</span></span>  

 `sztMaxVirtualMemMB`  
 <span data-ttu-id="4861e-106">окне Запрошенный размер выделенной памяти.</span><span class="sxs-lookup"><span data-stu-id="4861e-106">[in] The requested size of memory to be allocated.</span></span>  
  
 `psztNewMaxVirtualMemMB`  
 <span data-ttu-id="4861e-107">[вход, выход] Указатель на фактический размер выделенной памяти.</span><span class="sxs-lookup"><span data-stu-id="4861e-107">[in, out] A pointer to the actual size of memory allocated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4861e-108">Требования</span><span class="sxs-lookup"><span data-stu-id="4861e-108">Requirements</span></span>  

 <span data-ttu-id="4861e-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4861e-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4861e-110">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4861e-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4861e-111">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4861e-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4861e-112">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4861e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4861e-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4861e-113">See also</span></span>

- [<span data-ttu-id="4861e-114">Интерфейс IGCHostControl</span><span class="sxs-lookup"><span data-stu-id="4861e-114">IGCHostControl Interface</span></span>](igchostcontrol-interface.md)
