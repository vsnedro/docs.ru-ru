---
title: System.ServiceModel.Channels.FailedPipeConnect
ms.date: 03/30/2017
ms.assetid: 9a827e0f-fb91-46bb-bd54-926d4b74d8a6
ms.openlocfilehash: b3b34b2f4ab2987360030d614c8e65cd878d4d14
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256252"
---
# <a name="systemservicemodelchannelsfailedpipeconnect"></a><span data-ttu-id="cce5a-102">System.ServiceModel.Channels.FailedPipeConnect</span><span class="sxs-lookup"><span data-stu-id="cce5a-102">System.ServiceModel.Channels.FailedPipeConnect</span></span>

<span data-ttu-id="cce5a-103">Сбой попытки соединения с конечной точкой именованного канала.</span><span class="sxs-lookup"><span data-stu-id="cce5a-103">An attempt to connect to the named pipe endpoint failed.</span></span> <span data-ttu-id="cce5a-104">По истечении заданного промежутка времени выполнена еще одна попытка.</span><span class="sxs-lookup"><span data-stu-id="cce5a-104">Another attempt is made within the specified timeout period.</span></span>  
  
## <a name="description"></a><span data-ttu-id="cce5a-105">Описание</span><span class="sxs-lookup"><span data-stu-id="cce5a-105">Description</span></span>  

 <span data-ttu-id="cce5a-106">Данная информационная трассировка показывает сбой соединения с конечной точкой именованного канала.</span><span class="sxs-lookup"><span data-stu-id="cce5a-106">This informational trace indicates a failure to connect to a named pipe endpoint.</span></span> <span data-ttu-id="cce5a-107">Возможная причина: не найдена или занята конечная точка именованного канала.</span><span class="sxs-lookup"><span data-stu-id="cce5a-107">This could happen if the named pipe endpoint is not found or is busy.</span></span> <span data-ttu-id="cce5a-108">Через короткие промежутки времени производится несколько дополнительных попыток, пока одна из них не будет успешной, или до истечения времени, заданного свойством OpenTimeout.</span><span class="sxs-lookup"><span data-stu-id="cce5a-108">Additional attempts are made, each separated by a short amount of time, until one succeeds or the OpenTimeout expires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cce5a-109">См. также</span><span class="sxs-lookup"><span data-stu-id="cce5a-109">See also</span></span>

- [<span data-ttu-id="cce5a-110">Трассировка</span><span class="sxs-lookup"><span data-stu-id="cce5a-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="cce5a-111">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="cce5a-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="cce5a-112">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="cce5a-112">Administration and Diagnostics</span></span>](../index.md)
