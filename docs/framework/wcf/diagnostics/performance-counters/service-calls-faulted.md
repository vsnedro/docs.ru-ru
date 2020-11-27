---
title: 'Служба: сбои вызовов'
ms.date: 03/30/2017
ms.assetid: 6da7f100-3f61-4b3c-9409-fe1360829b8a
ms.openlocfilehash: 613de88df8aaa955539a4e9586dacd64e155161e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96252937"
---
# <a name="service-calls-faulted"></a><span data-ttu-id="18b75-102">Служба: сбои вызовов</span><span class="sxs-lookup"><span data-stu-id="18b75-102">Service: Calls Faulted</span></span>

<span data-ttu-id="18b75-103">Имя счетчика: Calls Faulted</span><span class="sxs-lookup"><span data-stu-id="18b75-103">Counter Name: Calls Faulted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="18b75-104">Описание</span><span class="sxs-lookup"><span data-stu-id="18b75-104">Description</span></span>  

 <span data-ttu-id="18b75-105">Количество вызовов данной службы, которые возвратили сообщение о сбое.</span><span class="sxs-lookup"><span data-stu-id="18b75-105">Number of calls to this service that have returned faults.</span></span> <span data-ttu-id="18b75-106">В приложениях Windows Communication Foundation (WCF) методы служб обмениваются сведениями об ошибках обработки с помощью сообщений о сбоях SOAP.</span><span class="sxs-lookup"><span data-stu-id="18b75-106">In Windows Communication Foundation (WCF) applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="18b75-107">Сообщения об ошибках SOAP - это типы сообщений, которые включаются в метаданные, связанные с операцией службы, и таким образом создают контракт ошибок, который клиенты могут использовать для повышения надежности и интерактивности своей работы.</span><span class="sxs-lookup"><span data-stu-id="18b75-107">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="18b75-108">Поскольку сообщения об ошибках SOAP передаются клиентам в формате XML, они поддерживают возможность взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="18b75-108">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18b75-109">См. также</span><span class="sxs-lookup"><span data-stu-id="18b75-109">See also</span></span>

- [<span data-ttu-id="18b75-110">Задание и обработка сбоев в контрактах и службах</span><span class="sxs-lookup"><span data-stu-id="18b75-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
