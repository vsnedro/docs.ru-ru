---
title: Количество сбоев вызовов в секунду
ms.date: 03/30/2017
ms.assetid: e4ef3773-f650-4876-99cf-4d0c02aa03d4
ms.openlocfilehash: d3eafc4b31f0e62093a972b7c9f2325a3648d21b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96285464"
---
# <a name="calls-failed-per-second"></a><span data-ttu-id="87b1a-102">Количество сбоев вызовов в секунду</span><span class="sxs-lookup"><span data-stu-id="87b1a-102">Calls Failed Per Second</span></span>

<span data-ttu-id="87b1a-103">Имя счетчика: Calls Failed Per Second</span><span class="sxs-lookup"><span data-stu-id="87b1a-103">Counter Name: Calls Failed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="87b1a-104">Описание</span><span class="sxs-lookup"><span data-stu-id="87b1a-104">Description</span></span>  

 <span data-ttu-id="87b1a-105">Количество вызовов с необработанными исключениями в данной операции в секунду.</span><span class="sxs-lookup"><span data-stu-id="87b1a-105">Number of calls with unhandled exceptions in this operation in a second.</span></span>  
  
 <span data-ttu-id="87b1a-106">Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.</span><span class="sxs-lookup"><span data-stu-id="87b1a-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="87b1a-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="87b1a-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="87b1a-108">Этот счетчик увеличивается каждый раз, когда в этой операции имеется необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="87b1a-108">This counter is incremented every time there is an unhandled exception in this operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87b1a-109">См. также</span><span class="sxs-lookup"><span data-stu-id="87b1a-109">See also</span></span>

- [<span data-ttu-id="87b1a-110">Задание и обработка сбоев в контрактах и службах</span><span class="sxs-lookup"><span data-stu-id="87b1a-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
