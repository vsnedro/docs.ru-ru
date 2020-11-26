---
title: 'Служба: количество неавторизованных вызовов системы безопасности'
ms.date: 03/30/2017
ms.assetid: 3024b20a-5250-4bd1-a38c-c6d79f89610b
ms.openlocfilehash: 32b0a62ecf9364270f5580787b7e129af5ac80b2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236914"
---
# <a name="service-security-calls-not-authorized"></a><span data-ttu-id="24e97-102">Служба: количество неавторизованных вызовов системы безопасности</span><span class="sxs-lookup"><span data-stu-id="24e97-102">Service: Security Calls Not Authorized</span></span>

<span data-ttu-id="24e97-103">Имя счетчика: Security Calls Not Authorized.</span><span class="sxs-lookup"><span data-stu-id="24e97-103">Counter Name: Security Calls Not Authorized.</span></span>  
  
## <a name="description"></a><span data-ttu-id="24e97-104">Описание</span><span class="sxs-lookup"><span data-stu-id="24e97-104">Description</span></span>  

 <span data-ttu-id="24e97-105">Значение этого счетчика увеличивается, когда метод <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> возвращает значение `false`.</span><span class="sxs-lookup"><span data-stu-id="24e97-105">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span> <span data-ttu-id="24e97-106">Это показывает, что входящее сообщение было надлежащим образом защищено и поступило от допустимого пользователя, не авторизованного для выполнения определенных задач.</span><span class="sxs-lookup"><span data-stu-id="24e97-106">It indicates that the incoming message is from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>
