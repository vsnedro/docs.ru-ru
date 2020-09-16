---
title: 'Конечная точка: количество неавторизованных вызовов системы безопасности в секунду'
ms.date: 03/30/2017
ms.assetid: c8a1547b-986b-45c1-b302-dea0cd4b516d
ms.openlocfilehash: 4925a0a53b03b061561aab396377012acd130797
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90549700"
---
# <a name="endpoint-security-calls-not-authorized-per-second"></a><span data-ttu-id="e21ee-102">Конечная точка: количество неавторизованных вызовов системы безопасности в секунду</span><span class="sxs-lookup"><span data-stu-id="e21ee-102">Endpoint: Security Calls Not Authorized Per Second</span></span>
<span data-ttu-id="e21ee-103">Имя счетчика: Security Calls Not Authorized Per Second.</span><span class="sxs-lookup"><span data-stu-id="e21ee-103">Counter Name: Security Calls Not Authorized Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="e21ee-104">Описание</span><span class="sxs-lookup"><span data-stu-id="e21ee-104">Description</span></span>  
 <span data-ttu-id="e21ee-105">Число входящих сообщений в секунду, которые защищены надлежащим образом и поступили от допустимого пользователя, но пользователю не разрешено выполнять определенные задачи.</span><span class="sxs-lookup"><span data-stu-id="e21ee-105">Number of incoming messages in a second that are from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>  
  
 <span data-ttu-id="e21ee-106">Значение этого счетчика увеличивается, когда метод <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> возвращает значение `false`.</span><span class="sxs-lookup"><span data-stu-id="e21ee-106">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span>  
  
 <span data-ttu-id="e21ee-107">Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.</span><span class="sxs-lookup"><span data-stu-id="e21ee-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="e21ee-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="e21ee-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
