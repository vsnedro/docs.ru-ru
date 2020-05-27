---
title: Метод IGCThreadControl::SuspensionEnding
ms.date: 03/30/2017
api_name:
- IGCThreadControl.SuspensionEnding
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SuspensionEnding
helpviewer_keywords:
- IGCThreadControl::SuspensionEnding method [.NET Framework hosting]
- SuspensionEnding method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 70814265-c734-4ddc-9502-fe8b28d2b414
topic_type:
- apiref
ms.openlocfilehash: 8300daf0d39745ceda80f6c56da7e3c459a97468
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805118"
---
# <a name="igcthreadcontrolsuspensionending-method"></a><span data-ttu-id="ad76f-102">Метод IGCThreadControl::SuspensionEnding</span><span class="sxs-lookup"><span data-stu-id="ad76f-102">IGCThreadControl::SuspensionEnding Method</span></span>
<span data-ttu-id="ad76f-103">Уведомляет узел о том, что среда выполнения возобновляет потоки после сборки мусора или другой приостановки.</span><span class="sxs-lookup"><span data-stu-id="ad76f-103">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad76f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ad76f-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionEnding (  
    [in] DWORD Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad76f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ad76f-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="ad76f-106">окне Поколение, на котором была выполнена сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="ad76f-106">[in] The generation on which a garbage collection has been performed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad76f-107">Замечания</span><span class="sxs-lookup"><span data-stu-id="ad76f-107">Remarks</span></span>  
 <span data-ttu-id="ad76f-108">Не Перепланируйте потоки во время `SuspensionEnding` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="ad76f-108">Do not reschedule any threads during the `SuspensionEnding` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad76f-109">Требования</span><span class="sxs-lookup"><span data-stu-id="ad76f-109">Requirements</span></span>  
 <span data-ttu-id="ad76f-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad76f-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad76f-111">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ad76f-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ad76f-112">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ad76f-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ad76f-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad76f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad76f-114">См. также статью</span><span class="sxs-lookup"><span data-stu-id="ad76f-114">See also</span></span>

- [<span data-ttu-id="ad76f-115">Интерфейс IGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="ad76f-115">IGCThreadControl Interface</span></span>](igcthreadcontrol-interface.md)
