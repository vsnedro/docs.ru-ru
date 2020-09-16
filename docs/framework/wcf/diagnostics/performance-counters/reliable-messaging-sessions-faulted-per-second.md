---
title: Количество надежных сеансов обмена сообщениями, в которых произошел сбой, в секунду
ms.date: 03/30/2017
ms.assetid: 8f8ca2eb-1be4-4b6a-aa78-fcd3ee145fe8
ms.openlocfilehash: 2d32f4224f3692cd4fc4f99a58bf54f49811e8ec
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90542930"
---
# <a name="reliable-messaging-sessions-faulted-per-second"></a><span data-ttu-id="adcbd-102">Количество надежных сеансов обмена сообщениями, в которых произошел сбой, в секунду</span><span class="sxs-lookup"><span data-stu-id="adcbd-102">Reliable Messaging Sessions Faulted Per Second</span></span>
<span data-ttu-id="adcbd-103">Имя счетчика: Reliable Messaging Sessions Faulted Per Second.</span><span class="sxs-lookup"><span data-stu-id="adcbd-103">Counter Name: Reliable Messaging Sessions Faulted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="adcbd-104">Описание</span><span class="sxs-lookup"><span data-stu-id="adcbd-104">Description</span></span>  
 <span data-ttu-id="adcbd-105">Количество надежных сессий обмена сообщениями этой службы, в которых произошел сбой в течение секунды.</span><span class="sxs-lookup"><span data-stu-id="adcbd-105">Number of reliable messaging sessions that are faulted in this service in a second.</span></span>  
  
 <span data-ttu-id="adcbd-106">Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.</span><span class="sxs-lookup"><span data-stu-id="adcbd-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="adcbd-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="adcbd-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
