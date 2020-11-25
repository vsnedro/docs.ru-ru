---
title: Метод IGCThreadControl::ThreadIsBlockingForSuspension
ms.date: 03/30/2017
api_name:
- IGCThreadControl.ThreadIsBlockingForSuspension
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ThreadIsBlockingForSuspension
helpviewer_keywords:
- IGCThreadControl::ThreadIsBlockingForSuspension method [.NET Framework hosting]
- ThreadIsBlockingForSuspension method [.NET Framework hosting]
ms.assetid: ed5b5b58-7db7-46b5-9e2c-278db7159cee
topic_type:
- apiref
ms.openlocfilehash: 39834ba868a21ead3113f2f0d9157cd210d9798c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721651"
---
# <a name="igcthreadcontrolthreadisblockingforsuspension-method"></a><span data-ttu-id="806e7-102">Метод IGCThreadControl::ThreadIsBlockingForSuspension</span><span class="sxs-lookup"><span data-stu-id="806e7-102">IGCThreadControl::ThreadIsBlockingForSuspension Method</span></span>

<span data-ttu-id="806e7-103">Уведомляет узел о том, что поток, выполняющий вызов, будет заблокирован, возможно, для сборки мусора или другой приостановки.</span><span class="sxs-lookup"><span data-stu-id="806e7-103">Notifies the host that the thread that is making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="806e7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="806e7-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadIsBlockingForSuspension ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="806e7-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="806e7-105">Remarks</span></span>  

 <span data-ttu-id="806e7-106">Основное приложение может выбрать в `ThreadIsBlockingForSuspension` обратном вызове, следует ли перепланировать поток.</span><span class="sxs-lookup"><span data-stu-id="806e7-106">The host may choose within the `ThreadIsBlockingForSuspension` callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="806e7-107">Требования</span><span class="sxs-lookup"><span data-stu-id="806e7-107">Requirements</span></span>  

 <span data-ttu-id="806e7-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="806e7-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="806e7-109">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="806e7-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="806e7-110">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="806e7-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="806e7-111">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="806e7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="806e7-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="806e7-112">See also</span></span>

- [<span data-ttu-id="806e7-113">Интерфейс IGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="806e7-113">IGCThreadControl Interface</span></span>](igcthreadcontrol-interface.md)
