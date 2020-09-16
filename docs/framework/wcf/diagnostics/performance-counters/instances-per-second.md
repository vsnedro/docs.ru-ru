---
title: Количество экземпляров в секунду
ms.date: 03/30/2017
ms.assetid: 74579397-1058-4278-80cf-2d00854a480f
ms.openlocfilehash: 9b78707f3815fd370d3398f1a7b422ee4bf2d369
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90541230"
---
# <a name="instances-per-second"></a><span data-ttu-id="dc8f9-102">Количество экземпляров в секунду</span><span class="sxs-lookup"><span data-stu-id="dc8f9-102">Instances Per Second</span></span>
<span data-ttu-id="dc8f9-103">Имя счетчика: Instances Created Per Second.</span><span class="sxs-lookup"><span data-stu-id="dc8f9-103">Counter Name: Instances Created Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="dc8f9-104">Описание</span><span class="sxs-lookup"><span data-stu-id="dc8f9-104">Description</span></span>  
 <span data-ttu-id="dc8f9-105">Общее количество экземпляров службы, создаваемых за секунду.</span><span class="sxs-lookup"><span data-stu-id="dc8f9-105">Total number of service instances created in a second.</span></span>  
  
 <span data-ttu-id="dc8f9-106">Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.</span><span class="sxs-lookup"><span data-stu-id="dc8f9-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="dc8f9-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="dc8f9-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
