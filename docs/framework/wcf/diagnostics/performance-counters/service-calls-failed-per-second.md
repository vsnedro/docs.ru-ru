---
title: 'Служба: количество сбоев вызовов в секунду'
ms.date: 03/30/2017
ms.assetid: 5a2c7939-107d-4f0c-b43c-e02e079e8a9d
ms.openlocfilehash: c97e4b0c6c2c71756a9bed7b1a2359ad0c118a98
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96252976"
---
# <a name="service-calls-failed-per-second"></a><span data-ttu-id="eb8ee-102">Служба: количество сбоев вызовов в секунду</span><span class="sxs-lookup"><span data-stu-id="eb8ee-102">Service: Calls Failed Per Second</span></span>

<span data-ttu-id="eb8ee-103">Имя счетчика: Calls Failed Per Second.</span><span class="sxs-lookup"><span data-stu-id="eb8ee-103">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="eb8ee-104">Описание</span><span class="sxs-lookup"><span data-stu-id="eb8ee-104">Description</span></span>  

 <span data-ttu-id="eb8ee-105">Число вызовов с необработанными исключениями, получаемых этой службой за секунду.</span><span class="sxs-lookup"><span data-stu-id="eb8ee-105">Number of calls that have unhandled exceptions, and are received by this service in a second.</span></span>  
  
 <span data-ttu-id="eb8ee-106">Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.</span><span class="sxs-lookup"><span data-stu-id="eb8ee-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="eb8ee-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="eb8ee-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="eb8ee-108">В управляемом коде исключения создаются в случае возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="eb8ee-108">In managed code, exceptions are thrown when error conditions occur.</span></span>  
  
 <span data-ttu-id="eb8ee-109">В управляемом коде исключения создаются в случае возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="eb8ee-109">In managed code, exceptions are thrown when error conditions occur.</span></span>  
  
 <span data-ttu-id="eb8ee-110">Значение этого счетчика увеличивается при каждом обнаружении необработанного исключения в данной службе.</span><span class="sxs-lookup"><span data-stu-id="eb8ee-110">This counter is incremented every time there is an unhandled exception in this service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb8ee-111">См. также</span><span class="sxs-lookup"><span data-stu-id="eb8ee-111">See also</span></span>

- [<span data-ttu-id="eb8ee-112">Задание и обработка сбоев в контрактах и службах</span><span class="sxs-lookup"><span data-stu-id="eb8ee-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
