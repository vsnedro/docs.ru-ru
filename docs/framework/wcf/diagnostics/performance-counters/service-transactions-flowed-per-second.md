---
title: 'Служба: количество поступивших транзакций в секунду'
ms.date: 03/30/2017
ms.assetid: ec72eb49-2942-4811-91df-d6e5dad81fd8
ms.openlocfilehash: 158bd7e2f2f98e91215ef7351cf90493a2d3059d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236836"
---
# <a name="service-transactions-flowed-per-second"></a><span data-ttu-id="775ac-102">Служба: количество поступивших транзакций в секунду</span><span class="sxs-lookup"><span data-stu-id="775ac-102">Service: Transactions Flowed Per Second</span></span>

<span data-ttu-id="775ac-103">Имя счетчика: Transactions Flowed Per Second.</span><span class="sxs-lookup"><span data-stu-id="775ac-103">Counter Name: Transactions Flowed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="775ac-104">Описание</span><span class="sxs-lookup"><span data-stu-id="775ac-104">Description</span></span>  

 <span data-ttu-id="775ac-105">Количество транзакций в операциях для данной службы в секунду.</span><span class="sxs-lookup"><span data-stu-id="775ac-105">Number of transactions flowed to operations in this service in a second.</span></span>  
  
 <span data-ttu-id="775ac-106">Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.</span><span class="sxs-lookup"><span data-stu-id="775ac-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="775ac-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="775ac-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
