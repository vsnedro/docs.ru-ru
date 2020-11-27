---
title: Количество подозрительных сообщений из очереди в секунду
ms.date: 03/30/2017
ms.assetid: d193fdd1-02f1-44a0-906e-f632a8f574c3
ms.openlocfilehash: 1e515a81580bd9773841bee4230288d8c7d12216
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276234"
---
# <a name="queued-poison-messages-per-second"></a><span data-ttu-id="525a7-102">Количество подозрительных сообщений из очереди в секунду</span><span class="sxs-lookup"><span data-stu-id="525a7-102">Queued Poison Messages Per Second</span></span>

<span data-ttu-id="525a7-103">Имя счетчика: Queued Poison Messages Per Second.</span><span class="sxs-lookup"><span data-stu-id="525a7-103">Counter Name: Queued Poison Messages Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="525a7-104">Описание</span><span class="sxs-lookup"><span data-stu-id="525a7-104">Description</span></span>  

 <span data-ttu-id="525a7-105">Количество сообщений, отмеченных как подозрительные транспортом очередей в этой службе в секунду.</span><span class="sxs-lookup"><span data-stu-id="525a7-105">Number of messages that are marked poisoned by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="525a7-106">Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.</span><span class="sxs-lookup"><span data-stu-id="525a7-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="525a7-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="525a7-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
