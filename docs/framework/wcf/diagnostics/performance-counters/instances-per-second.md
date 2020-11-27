---
title: Количество экземпляров в секунду
ms.date: 03/30/2017
ms.assetid: 74579397-1058-4278-80cf-2d00854a480f
ms.openlocfilehash: ac535de1e8dacb97c136d72d096631d838d26700
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266094"
---
# <a name="instances-per-second"></a><span data-ttu-id="9afa6-102">Количество экземпляров в секунду</span><span class="sxs-lookup"><span data-stu-id="9afa6-102">Instances Per Second</span></span>

<span data-ttu-id="9afa6-103">Имя счетчика: Instances Created Per Second.</span><span class="sxs-lookup"><span data-stu-id="9afa6-103">Counter Name: Instances Created Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="9afa6-104">Описание</span><span class="sxs-lookup"><span data-stu-id="9afa6-104">Description</span></span>  

 <span data-ttu-id="9afa6-105">Общее количество экземпляров службы, создаваемых за секунду.</span><span class="sxs-lookup"><span data-stu-id="9afa6-105">Total number of service instances created in a second.</span></span>  
  
 <span data-ttu-id="9afa6-106">Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.</span><span class="sxs-lookup"><span data-stu-id="9afa6-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="9afa6-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="9afa6-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
