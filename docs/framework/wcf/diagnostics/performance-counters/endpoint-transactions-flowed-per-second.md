---
title: 'Конечная точка: количество поступивших транзакций в секунду'
ms.date: 03/30/2017
ms.assetid: 0f370ff1-a913-450b-bccb-c279ad165b3d
ms.openlocfilehash: 9391651eaaca130ef47ddee9daa95b1f8c116892
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553796"
---
# <a name="endpoint-transactions-flowed-per-second"></a><span data-ttu-id="7587e-102">Конечная точка: количество поступивших транзакций в секунду</span><span class="sxs-lookup"><span data-stu-id="7587e-102">Endpoint: Transactions Flowed Per Second</span></span>
<span data-ttu-id="7587e-103">Имя счетчика: Transactions Flowed Per Second.</span><span class="sxs-lookup"><span data-stu-id="7587e-103">Counter Name: Transactions Flowed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="7587e-104">Описание</span><span class="sxs-lookup"><span data-stu-id="7587e-104">Description</span></span>  
 <span data-ttu-id="7587e-105">Количество транзакций, поступивших в операции в этой конечной точке в секунду.</span><span class="sxs-lookup"><span data-stu-id="7587e-105">Number of transactions flowed to operations at this endpoint in a second.</span></span> <span data-ttu-id="7587e-106">Значение этого счетчика увеличивается каждый раз, когда в сообщении, отправленном в эту конечную точку, содержится идентификатор транзакции.</span><span class="sxs-lookup"><span data-stu-id="7587e-106">This counter is incremented any time a transaction ID is present in a message sent to the endpoint.</span></span>  
  
 <span data-ttu-id="7587e-107">Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.</span><span class="sxs-lookup"><span data-stu-id="7587e-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="7587e-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="7587e-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
