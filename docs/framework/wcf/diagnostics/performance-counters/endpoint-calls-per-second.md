---
title: 'Конечная точка: количество вызовов в секунду'
ms.date: 03/30/2017
ms.assetid: ca0fc06d-d68f-4236-bd5f-c7ff6214acdd
ms.openlocfilehash: 7a3a9bcdb3485efa01ceed61495dd87d64424d50
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90550323"
---
# <a name="endpoint-calls-per-second"></a><span data-ttu-id="e2977-102">Конечная точка: количество вызовов в секунду</span><span class="sxs-lookup"><span data-stu-id="e2977-102">Endpoint: Calls Per Second</span></span>
<span data-ttu-id="e2977-103">Имя счетчика: Calls Per Second.</span><span class="sxs-lookup"><span data-stu-id="e2977-103">Counter Name: Calls Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="e2977-104">Описание</span><span class="sxs-lookup"><span data-stu-id="e2977-104">Description</span></span>  
 <span data-ttu-id="e2977-105">Количество вызовов данной конечной точки в секунду.</span><span class="sxs-lookup"><span data-stu-id="e2977-105">Number of calls to this endpoint in a second.</span></span>  
  
 <span data-ttu-id="e2977-106">Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.</span><span class="sxs-lookup"><span data-stu-id="e2977-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="e2977-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="e2977-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
