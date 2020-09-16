---
title: Количество отброшенных сообщений, передаваемых по надежным каналам, в секунду
ms.date: 03/30/2017
ms.assetid: a11b0b80-b242-48e1-b0bb-7f756db5486b
ms.openlocfilehash: fbc4db354908b45b941799f0352135675293063d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90543004"
---
# <a name="reliable-messaging-messages-dropped-per-second"></a><span data-ttu-id="7fa35-102">Количество отброшенных сообщений, передаваемых по надежным каналам, в секунду</span><span class="sxs-lookup"><span data-stu-id="7fa35-102">Reliable Messaging Messages Dropped Per Second</span></span>
<span data-ttu-id="7fa35-103">Имя счетчика: Reliable Messaging Sessions Dropped Per Second.</span><span class="sxs-lookup"><span data-stu-id="7fa35-103">Counter Name: Reliable Messaging Sessions Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="7fa35-104">Описание</span><span class="sxs-lookup"><span data-stu-id="7fa35-104">Description</span></span>  
 <span data-ttu-id="7fa35-105">Общее количество надежных сообщений, которые были отклонены в данной службе в течение секунды.</span><span class="sxs-lookup"><span data-stu-id="7fa35-105">Total number of reliable messaging messages that have been dropped in this service in a second.</span></span>  
  
 <span data-ttu-id="7fa35-106">Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.</span><span class="sxs-lookup"><span data-stu-id="7fa35-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="7fa35-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="7fa35-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
