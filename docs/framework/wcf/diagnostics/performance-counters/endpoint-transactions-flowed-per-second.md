---
title: 'Конечная точка: количество поступивших транзакций в секунду'
ms.date: 03/30/2017
ms.assetid: 0f370ff1-a913-450b-bccb-c279ad165b3d
ms.openlocfilehash: b814d7ca9e286426289c611b3a6bf5a52c1b2335
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256434"
---
# <a name="endpoint-transactions-flowed-per-second"></a><span data-ttu-id="b7d8b-102">Конечная точка: количество поступивших транзакций в секунду</span><span class="sxs-lookup"><span data-stu-id="b7d8b-102">Endpoint: Transactions Flowed Per Second</span></span>

<span data-ttu-id="b7d8b-103">Имя счетчика: Transactions Flowed Per Second.</span><span class="sxs-lookup"><span data-stu-id="b7d8b-103">Counter Name: Transactions Flowed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b7d8b-104">Описание</span><span class="sxs-lookup"><span data-stu-id="b7d8b-104">Description</span></span>  

 <span data-ttu-id="b7d8b-105">Количество транзакций, поступивших в операции в этой конечной точке в секунду.</span><span class="sxs-lookup"><span data-stu-id="b7d8b-105">Number of transactions flowed to operations at this endpoint in a second.</span></span> <span data-ttu-id="b7d8b-106">Значение этого счетчика увеличивается каждый раз, когда в сообщении, отправленном в эту конечную точку, содержится идентификатор транзакции.</span><span class="sxs-lookup"><span data-stu-id="b7d8b-106">This counter is incremented any time a transaction ID is present in a message sent to the endpoint.</span></span>  
  
 <span data-ttu-id="b7d8b-107">Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.</span><span class="sxs-lookup"><span data-stu-id="b7d8b-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="b7d8b-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="b7d8b-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
