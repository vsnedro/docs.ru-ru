---
title: 'Конечная точка: количество отброшенных сообщений, передаваемых по надежным каналам, в секунду'
ms.date: 03/30/2017
ms.assetid: ea3c4fc0-1e0f-4863-8879-57bc6c113018
ms.openlocfilehash: b8c0f91b2de5d023232756159a50236574308954
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96290846"
---
# <a name="endpoint-reliable-messaging-messages-dropped-per-second"></a><span data-ttu-id="bf091-102">Конечная точка: количество отброшенных сообщений, передаваемых по надежным каналам, в секунду</span><span class="sxs-lookup"><span data-stu-id="bf091-102">Endpoint: Reliable Messaging Messages Dropped Per Second</span></span>

<span data-ttu-id="bf091-103">Имя счетчика: Reliable Messaging Sessions Dropped Per Second.</span><span class="sxs-lookup"><span data-stu-id="bf091-103">Counter Name: Reliable Messaging Sessions Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="bf091-104">Описание</span><span class="sxs-lookup"><span data-stu-id="bf091-104">Description</span></span>  

 <span data-ttu-id="bf091-105">Общее количество сообщений системы надежного обмена сообщениями, которое было отброшено в данной конечной точке в секунду.</span><span class="sxs-lookup"><span data-stu-id="bf091-105">Total number of reliable messaging messages that have been dropped at this endpoint in a second.</span></span>  
  
 <span data-ttu-id="bf091-106">Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.</span><span class="sxs-lookup"><span data-stu-id="bf091-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="bf091-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="bf091-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
