---
title: Счетчики производительности службы
ms.date: 03/30/2017
ms.assetid: 4210f549-31f2-4ea7-99bd-69eaffb98ddf
ms.openlocfilehash: f3e3a798bf04f24aaea03b5d70762d52b67a82f0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96252833"
---
# <a name="service-performance-counters"></a><span data-ttu-id="2f08f-102">Счетчики производительности службы</span><span class="sxs-lookup"><span data-stu-id="2f08f-102">Service Performance Counters</span></span>

<span data-ttu-id="2f08f-103">Счетчики производительности службы измеряют поведение службы в целом, их можно использовать для диагностики производительности всей службы.</span><span class="sxs-lookup"><span data-stu-id="2f08f-103">Service performance counters measure the service behavior as a whole and can be used to diagnose the performance of the whole service.</span></span> <span data-ttu-id="2f08f-104">При просмотре с помощью системного монитора (Perfmon.exe) счетчики находятся под объектом производительности `ServiceModelService 4.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="2f08f-104">They can be found under the `ServiceModelService 4.0.0.0` performance object when viewing with Performance Monitor (Perfmon.exe).</span></span> <span data-ttu-id="2f08f-105">Экземпляры именуются по следующей схеме:</span><span class="sxs-lookup"><span data-stu-id="2f08f-105">The instances are named using the following pattern:</span></span>  
  
`ServiceName@ServiceBaseAddress`
  
> [!CAUTION]
> <span data-ttu-id="2f08f-106">Длина имени экземпляра счетчика производительности ограничена.</span><span class="sxs-lookup"><span data-stu-id="2f08f-106">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="2f08f-107">Если имя экземпляра счетчика Windows Communication Foundation (WCF) превышает максимальную длину, WCF заменяет часть имени экземпляра на хэш-значение.</span><span class="sxs-lookup"><span data-stu-id="2f08f-107">When a Windows Communication Foundation (WCF) counter instance name exceeds the maximum length, WCF replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f08f-108">См. также</span><span class="sxs-lookup"><span data-stu-id="2f08f-108">See also</span></span>

- [<span data-ttu-id="2f08f-109">Счетчики производительности</span><span class="sxs-lookup"><span data-stu-id="2f08f-109">Performance Counters</span></span>](index.md)
