---
title: Службы типа "запрос-ответ"
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation [WCF], request-reply services
- contracts [WCF], request-reply services
- WCF [WCF], request-reply services
- request-reply contracts [WCF]
ms.assetid: 2fa710f1-47f4-4598-b063-3ab3bd22ebba
ms.openlocfilehash: 10b82e859369dae4f57e0e13782e2375a304ab02
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295526"
---
# <a name="request-reply-services"></a><span data-ttu-id="81b36-102">Службы типа "запрос-ответ"</span><span class="sxs-lookup"><span data-stu-id="81b36-102">Request-Reply Services</span></span>

<span data-ttu-id="81b36-103">Службы "запрос-ответ" являются типом контракта операции по умолчанию в Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="81b36-103">Request-reply services are the default type of operation contract in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="81b36-104">Клиенты вызывают операции службы и ожидают ответа от службы.</span><span class="sxs-lookup"><span data-stu-id="81b36-104">Clients make calls to service operations and wait for a response from the service.</span></span> <span data-ttu-id="81b36-105">Вызывать операции службы можно либо синхронно (клиент блокируется до тех пор, пока не получит ответ от службы или не истечет время вызова), либо асинхронно (клиент вызывает операцию службы, продолжает работать и получает ответ от службы в другом потоке).</span><span class="sxs-lookup"><span data-stu-id="81b36-105">You can perform calls to a service operation either synchronously, where the client blocks until it receives a response from the service or the call times, or asynchronously, where the client makes a call to the service operation, continues working, and receives the response from the service on another thread.</span></span>  
  
 <span data-ttu-id="81b36-106">Чтобы создать контракт службы типа запрос-ответ, определите контракт службы и примените класс <xref:System.ServiceModel.OperationContractAttribute> к каждой из операций, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="81b36-106">To create a request-reply service contract, define your service contract, and apply the <xref:System.ServiceModel.OperationContractAttribute> class to each operation, as shown in the following sample code.</span></span>  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IRequestReplyCalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
}  
```  
  
 <span data-ttu-id="81b36-107">Присваивать свойству <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> значение `false`, поскольку это поведение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="81b36-107">You do not have to set the  <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> property to `false` because this is the default behavior.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81b36-108">См. также</span><span class="sxs-lookup"><span data-stu-id="81b36-108">See also</span></span>

- [<span data-ttu-id="81b36-109">Односторонние службы</span><span class="sxs-lookup"><span data-stu-id="81b36-109">One-Way Services</span></span>](one-way-services.md)
- [<span data-ttu-id="81b36-110">Дуплексные службы</span><span class="sxs-lookup"><span data-stu-id="81b36-110">Duplex Services</span></span>](duplex-services.md)
