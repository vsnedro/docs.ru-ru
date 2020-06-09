---
title: System.ServiceModel.Channels.FailedAcceptFromPool
ms.date: 03/30/2017
ms.assetid: d535b1b5-ee58-45e8-b400-7d9570f4eb9a
ms.openlocfilehash: 5bfa31d0eaf3b00017512eddc60bfa99eda619e3
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84582586"
---
# <a name="systemservicemodelchannelsfailedacceptfrompool"></a><span data-ttu-id="6c379-102">System.ServiceModel.Channels.FailedAcceptFromPool</span><span class="sxs-lookup"><span data-stu-id="6c379-102">System.ServiceModel.Channels.FailedAcceptFromPool</span></span>
<span data-ttu-id="6c379-103">При попытке повторного использования подключения в пуле произошел сбой.</span><span class="sxs-lookup"><span data-stu-id="6c379-103">An attempt to reuse a pooled connection failed.</span></span> <span data-ttu-id="6c379-104">По истечении заданного промежутка времени выполнена еще одна попытка.</span><span class="sxs-lookup"><span data-stu-id="6c379-104">Another attempt is made within the specified timeout period.</span></span>  
  
## <a name="description"></a><span data-ttu-id="6c379-105">Описание</span><span class="sxs-lookup"><span data-stu-id="6c379-105">Description</span></span>  
 <span data-ttu-id="6c379-106">Данная информационная трассировка показывает, что при попытке повторного использования подключения в пуле произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="6c379-106">This informational trace indicates that an error has occurred while attempting to reuse a pooled connection.</span></span> <span data-ttu-id="6c379-107">Ошибка могла произойти из-за несовместимости или неготовности подключения в пуле, либо того, что оно до сих пор активно.</span><span class="sxs-lookup"><span data-stu-id="6c379-107">This could happen because the pooled connection was not compatible, ready, or still active.</span></span> <span data-ttu-id="6c379-108">Дополнительные попытки повторного использования другого подключения в пуле предпринимаются по истечении заданного промежутка времени, и если не найдено ни одного используемого подключения, создается новое подключение.</span><span class="sxs-lookup"><span data-stu-id="6c379-108">Additional attempts to reuse other pooled connection are made within a given timeout and a new connection is created in case no usable connections are found.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c379-109">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="6c379-109">See also</span></span>

- [<span data-ttu-id="6c379-110">Трассировка</span><span class="sxs-lookup"><span data-stu-id="6c379-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="6c379-111">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="6c379-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="6c379-112">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="6c379-112">Administration and Diagnostics</span></span>](../index.md)
