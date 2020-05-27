---
title: Метод IGCThreadControl::SuspensionStarting
ms.date: 03/30/2017
api_name:
- IGCThreadControl.SuspensionStarting
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SuspensionStarting
helpviewer_keywords:
- IGCThreadControl::SuspensionStarting method [.NET Framework hosting]
- SuspensionStarting method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 0af312af-98e9-415e-b182-42e80a1aee51
topic_type:
- apiref
ms.openlocfilehash: 2acabe66e3b6b5652df20e31a9d2294c2396b54b
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805102"
---
# <a name="igcthreadcontrolsuspensionstarting-method"></a><span data-ttu-id="5bfa1-102">Метод IGCThreadControl::SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="5bfa1-102">IGCThreadControl::SuspensionStarting Method</span></span>
<span data-ttu-id="5bfa1-103">Уведомляет узел о том, что среда выполнения начинает приостановку потока для сборки мусора или другой приостановки.</span><span class="sxs-lookup"><span data-stu-id="5bfa1-103">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bfa1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5bfa1-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionStarting ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="5bfa1-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="5bfa1-105">Remarks</span></span>  
 <span data-ttu-id="5bfa1-106">Не Перепланируйте потоки во время `SuspensionStarting` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="5bfa1-106">Do not reschedule any threads during the `SuspensionStarting` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bfa1-107">Требования</span><span class="sxs-lookup"><span data-stu-id="5bfa1-107">Requirements</span></span>  
 <span data-ttu-id="5bfa1-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5bfa1-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bfa1-109">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5bfa1-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5bfa1-110">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5bfa1-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5bfa1-111">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bfa1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bfa1-112">См. также статью</span><span class="sxs-lookup"><span data-stu-id="5bfa1-112">See also</span></span>

- [<span data-ttu-id="5bfa1-113">Интерфейс IGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="5bfa1-113">IGCThreadControl Interface</span></span>](igcthreadcontrol-interface.md)
