---
title: 'Конечная точка: количество неавторизованных вызовов системы безопасности'
ms.date: 03/30/2017
ms.assetid: d25095ff-9ff0-4c69-a674-4e6a9fe3f4dc
ms.openlocfilehash: 3979eec15759989b638e1cc813cb78a0c008c3a4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256512"
---
# <a name="endpoint-security-calls-not-authorized"></a><span data-ttu-id="3fce9-102">Конечная точка: количество неавторизованных вызовов системы безопасности</span><span class="sxs-lookup"><span data-stu-id="3fce9-102">Endpoint: Security Calls Not Authorized</span></span>

<span data-ttu-id="3fce9-103">Имя счетчика: Security Calls Not Authorized.</span><span class="sxs-lookup"><span data-stu-id="3fce9-103">Counter Name: Security Calls Not Authorized.</span></span>  
  
## <a name="description"></a><span data-ttu-id="3fce9-104">Описание</span><span class="sxs-lookup"><span data-stu-id="3fce9-104">Description</span></span>  

 <span data-ttu-id="3fce9-105">Значение этого счетчика увеличивается, когда метод <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> возвращает значение `false`.</span><span class="sxs-lookup"><span data-stu-id="3fce9-105">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span> <span data-ttu-id="3fce9-106">Это показывает, что входящее сообщение было надлежащим образом защищено и поступило от допустимого пользователя, не авторизованного для выполнения определенных задач.</span><span class="sxs-lookup"><span data-stu-id="3fce9-106">It indicates that the incoming message is from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>
