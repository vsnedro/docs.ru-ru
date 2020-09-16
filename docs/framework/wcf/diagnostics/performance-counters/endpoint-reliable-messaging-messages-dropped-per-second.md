---
title: 'Конечная точка: количество отброшенных сообщений, передаваемых по надежным каналам, в секунду'
ms.date: 03/30/2017
ms.assetid: ea3c4fc0-1e0f-4863-8879-57bc6c113018
ms.openlocfilehash: 06259ba0d60d9f1cec7717364f2e014bb123ee40
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90550271"
---
# <a name="endpoint-reliable-messaging-messages-dropped-per-second"></a><span data-ttu-id="e05c3-102">Конечная точка: количество отброшенных сообщений, передаваемых по надежным каналам, в секунду</span><span class="sxs-lookup"><span data-stu-id="e05c3-102">Endpoint: Reliable Messaging Messages Dropped Per Second</span></span>
<span data-ttu-id="e05c3-103">Имя счетчика: Reliable Messaging Sessions Dropped Per Second.</span><span class="sxs-lookup"><span data-stu-id="e05c3-103">Counter Name: Reliable Messaging Sessions Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="e05c3-104">Описание</span><span class="sxs-lookup"><span data-stu-id="e05c3-104">Description</span></span>  
 <span data-ttu-id="e05c3-105">Общее количество сообщений системы надежного обмена сообщениями, которое было отброшено в данной конечной точке в секунду.</span><span class="sxs-lookup"><span data-stu-id="e05c3-105">Total number of reliable messaging messages that have been dropped at this endpoint in a second.</span></span>  
  
 <span data-ttu-id="e05c3-106">Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.</span><span class="sxs-lookup"><span data-stu-id="e05c3-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="e05c3-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="e05c3-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
