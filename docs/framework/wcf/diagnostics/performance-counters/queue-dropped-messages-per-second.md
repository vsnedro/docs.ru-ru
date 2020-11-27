---
title: Количество удаленных из очереди сообщений в секунду
ms.date: 03/30/2017
ms.assetid: 74540f52-8762-4147-b5ba-e171180515a3
ms.openlocfilehash: 81ba15965676ba7ffe5ca2aaac5e1d0e94e27962
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266042"
---
# <a name="queue-dropped-messages-per-second"></a><span data-ttu-id="d129e-102">Количество удаленных из очереди сообщений в секунду</span><span class="sxs-lookup"><span data-stu-id="d129e-102">Queue Dropped Messages Per Second</span></span>

<span data-ttu-id="d129e-103">Имя счетчика: Queued Messages Dropped Per Second.</span><span class="sxs-lookup"><span data-stu-id="d129e-103">Counter Name: Queued Messages Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="d129e-104">Описание</span><span class="sxs-lookup"><span data-stu-id="d129e-104">Description</span></span>  

 <span data-ttu-id="d129e-105">Количество сообщений, отброшенных транспортом очередей этой службы за секунду.</span><span class="sxs-lookup"><span data-stu-id="d129e-105">Number of messages that are dropped by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="d129e-106">Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.</span><span class="sxs-lookup"><span data-stu-id="d129e-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="d129e-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="d129e-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
