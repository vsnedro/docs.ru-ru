---
title: Интерфейс IDebuggerThreadControl
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IDebuggerThreadControl
helpviewer_keywords:
- IDebuggerThreadControl interface [.NET Framework hosting]
ms.assetid: 0a270c42-a7d1-45f1-a64d-fa3e84d14532
topic_type:
- apiref
ms.openlocfilehash: 82c6113f4df3334500128df22f7e9ce8d4bf151f
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805279"
---
# <a name="idebuggerthreadcontrol-interface"></a><span data-ttu-id="9cc09-102">Интерфейс IDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="9cc09-102">IDebuggerThreadControl Interface</span></span>
<span data-ttu-id="9cc09-103">Предоставляет методы для уведомления узла о блокировке и разблокировке потоков службами отладки.</span><span class="sxs-lookup"><span data-stu-id="9cc09-103">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9cc09-104">Методы</span><span class="sxs-lookup"><span data-stu-id="9cc09-104">Methods</span></span>  
  
|<span data-ttu-id="9cc09-105">Метод</span><span class="sxs-lookup"><span data-stu-id="9cc09-105">Method</span></span>|<span data-ttu-id="9cc09-106">Описание</span><span class="sxs-lookup"><span data-stu-id="9cc09-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9cc09-107">Метод ThreadIsBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="9cc09-107">ThreadIsBlockingForDebugger Method</span></span>](idebuggerthreadcontrol-threadisblockingfordebugger-method.md)|<span data-ttu-id="9cc09-108">Уведомляет узел о том, что поток, отправляющий этот обратный вызов, будет заблокирован в службах отладки.</span><span class="sxs-lookup"><span data-stu-id="9cc09-108">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>|  
|[<span data-ttu-id="9cc09-109">Метод ReleaseAllRuntimeThreads</span><span class="sxs-lookup"><span data-stu-id="9cc09-109">ReleaseAllRuntimeThreads Method</span></span>](idebuggerthreadcontrol-releaseallruntimethreads-method.md)|<span data-ttu-id="9cc09-110">Уведомляет узел о том, что службы отладки собирается освободить все заблокированные потоки.</span><span class="sxs-lookup"><span data-stu-id="9cc09-110">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>|  
|[<span data-ttu-id="9cc09-111">Метод StartBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="9cc09-111">StartBlockingForDebugger Method</span></span>](idebuggerthreadcontrol-startblockingfordebugger-method.md)|<span data-ttu-id="9cc09-112">Уведомляет узел о том, что служба отладки собирается начать блокирование всех потоков.</span><span class="sxs-lookup"><span data-stu-id="9cc09-112">Notifies the host that the debugging services are about to start blocking all threads.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9cc09-113">Требования</span><span class="sxs-lookup"><span data-stu-id="9cc09-113">Requirements</span></span>  
 <span data-ttu-id="9cc09-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9cc09-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cc09-115">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9cc09-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9cc09-116">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9cc09-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9cc09-117">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cc09-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cc09-118">См. также статью</span><span class="sxs-lookup"><span data-stu-id="9cc09-118">See also</span></span>

- [<span data-ttu-id="9cc09-119">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="9cc09-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
