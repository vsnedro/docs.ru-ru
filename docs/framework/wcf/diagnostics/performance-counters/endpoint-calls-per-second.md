---
title: 'Конечная точка: количество вызовов в секунду'
ms.date: 03/30/2017
ms.assetid: ca0fc06d-d68f-4236-bd5f-c7ff6214acdd
ms.openlocfilehash: 3c9f9882be935474ec187e2829e8e1e58b091afa
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96253158"
---
# <a name="endpoint-calls-per-second"></a><span data-ttu-id="ebe52-102">Конечная точка: количество вызовов в секунду</span><span class="sxs-lookup"><span data-stu-id="ebe52-102">Endpoint: Calls Per Second</span></span>

<span data-ttu-id="ebe52-103">Имя счетчика: Calls Per Second.</span><span class="sxs-lookup"><span data-stu-id="ebe52-103">Counter Name: Calls Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ebe52-104">Описание</span><span class="sxs-lookup"><span data-stu-id="ebe52-104">Description</span></span>  

 <span data-ttu-id="ebe52-105">Количество вызовов данной конечной точки в секунду.</span><span class="sxs-lookup"><span data-stu-id="ebe52-105">Number of calls to this endpoint in a second.</span></span>  
  
 <span data-ttu-id="ebe52-106">Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.</span><span class="sxs-lookup"><span data-stu-id="ebe52-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="ebe52-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="ebe52-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
