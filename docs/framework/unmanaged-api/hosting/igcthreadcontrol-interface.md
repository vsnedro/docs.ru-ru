---
title: Интерфейс IGCThreadControl
ms.date: 03/30/2017
api_name:
- IGCThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCThreadControl
helpviewer_keywords:
- IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 3ff04d75-85ac-4df9-886d-dbaa037c0552
topic_type:
- apiref
ms.openlocfilehash: 78e667acf1573769a1a67b4c964d7801f11838fe
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805131"
---
# <a name="igcthreadcontrol-interface"></a><span data-ttu-id="4888b-102">Интерфейс IGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="4888b-102">IGCThreadControl Interface</span></span>
<span data-ttu-id="4888b-103">Предоставляет методы для участия в планировании потоков, которые в противном случае были бы заблокированы для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="4888b-103">Provides methods for participating in the scheduling of threads that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4888b-104">Методы</span><span class="sxs-lookup"><span data-stu-id="4888b-104">Methods</span></span>  
  
|<span data-ttu-id="4888b-105">Метод</span><span class="sxs-lookup"><span data-stu-id="4888b-105">Method</span></span>|<span data-ttu-id="4888b-106">Описание</span><span class="sxs-lookup"><span data-stu-id="4888b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4888b-107">Метод SuspensionEnding</span><span class="sxs-lookup"><span data-stu-id="4888b-107">SuspensionEnding Method</span></span>](igcthreadcontrol-suspensionending-method.md)|<span data-ttu-id="4888b-108">Уведомляет узел о том, что среда выполнения возобновляет потоки после сборки мусора или другой приостановки.</span><span class="sxs-lookup"><span data-stu-id="4888b-108">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="4888b-109">Метод SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="4888b-109">SuspensionStarting Method</span></span>](igcthreadcontrol-suspensionstarting-method.md)|<span data-ttu-id="4888b-110">Уведомляет узел о том, что среда выполнения начинает приостановку потока для сборки мусора или другой приостановки.</span><span class="sxs-lookup"><span data-stu-id="4888b-110">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="4888b-111">Метод ThreadIsBlockingForSuspension</span><span class="sxs-lookup"><span data-stu-id="4888b-111">ThreadIsBlockingForSuspension Method</span></span>](igcthreadcontrol-threadisblockingforsuspension-method.md)|<span data-ttu-id="4888b-112">Уведомляет узел о том, что поток, выполняющий вызов, будет заблокирован, возможно, для сборки мусора или другой приостановки.</span><span class="sxs-lookup"><span data-stu-id="4888b-112">Notifies the host that the thread making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4888b-113">Требования</span><span class="sxs-lookup"><span data-stu-id="4888b-113">Requirements</span></span>  
 <span data-ttu-id="4888b-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4888b-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4888b-115">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4888b-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4888b-116">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4888b-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4888b-117">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4888b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4888b-118">См. также статью</span><span class="sxs-lookup"><span data-stu-id="4888b-118">See also</span></span>

- [<span data-ttu-id="4888b-119">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="4888b-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
