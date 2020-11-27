---
title: Количество отброшенных сообщений, передаваемых по надежным каналам, в секунду
ms.date: 03/30/2017
ms.assetid: a11b0b80-b242-48e1-b0bb-7f756db5486b
ms.openlocfilehash: 1e6db155f21fb2443394bc3a65235d4e9539dab3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276182"
---
# <a name="reliable-messaging-messages-dropped-per-second"></a><span data-ttu-id="715a4-102">Количество отброшенных сообщений, передаваемых по надежным каналам, в секунду</span><span class="sxs-lookup"><span data-stu-id="715a4-102">Reliable Messaging Messages Dropped Per Second</span></span>

<span data-ttu-id="715a4-103">Имя счетчика: Reliable Messaging Sessions Dropped Per Second.</span><span class="sxs-lookup"><span data-stu-id="715a4-103">Counter Name: Reliable Messaging Sessions Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="715a4-104">Описание</span><span class="sxs-lookup"><span data-stu-id="715a4-104">Description</span></span>  

 <span data-ttu-id="715a4-105">Общее количество надежных сообщений, которые были отклонены в данной службе в течение секунды.</span><span class="sxs-lookup"><span data-stu-id="715a4-105">Total number of reliable messaging messages that have been dropped in this service in a second.</span></span>  
  
 <span data-ttu-id="715a4-106">Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.</span><span class="sxs-lookup"><span data-stu-id="715a4-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="715a4-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="715a4-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
