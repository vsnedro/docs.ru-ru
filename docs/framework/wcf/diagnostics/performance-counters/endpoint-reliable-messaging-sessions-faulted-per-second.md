---
title: 'Конечная точка: количество надежных сеансов обмена сообщениями, в которых произошел сбой, в секунду'
ms.date: 03/30/2017
ms.assetid: e9ae808a-7e1f-46b0-9560-d5a866be6d6e
ms.openlocfilehash: b9aa0e62aaf3a7e44f90c37a8611733321969ded
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96290833"
---
# <a name="endpoint-reliable-messaging-sessions-faulted-per-second"></a><span data-ttu-id="ee7f7-102">Конечная точка: количество надежных сеансов обмена сообщениями, в которых произошел сбой, в секунду</span><span class="sxs-lookup"><span data-stu-id="ee7f7-102">Endpoint: Reliable Messaging Sessions Faulted Per Second</span></span>

<span data-ttu-id="ee7f7-103">Имя счетчика: Reliable Messaging Sessions Faulted Per Second.</span><span class="sxs-lookup"><span data-stu-id="ee7f7-103">Counter Name: Reliable Messaging Sessions Faulted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ee7f7-104">Описание</span><span class="sxs-lookup"><span data-stu-id="ee7f7-104">Description</span></span>  

 <span data-ttu-id="ee7f7-105">Количество сеансов надежного обмена сообщениями, в которых произошел сбой на этой конечной точке в течение секунды.</span><span class="sxs-lookup"><span data-stu-id="ee7f7-105">Number of reliable messaging sessions that are faulted at this endpoint in a second.</span></span>  
  
 <span data-ttu-id="ee7f7-106">Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.</span><span class="sxs-lookup"><span data-stu-id="ee7f7-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="ee7f7-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="ee7f7-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
