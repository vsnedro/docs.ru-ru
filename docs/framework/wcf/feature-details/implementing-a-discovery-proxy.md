---
title: Реализация прокси-сервера обнаружения
ms.date: 03/30/2017
ms.assetid: dda20e79-8df3-438e-a281-69d779d978ec
ms.openlocfilehash: ae003c89bb0f14623c5d31a1596533d821380336
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96268304"
---
# <a name="implementing-a-discovery-proxy"></a><span data-ttu-id="80bf8-102">Реализация прокси-сервера обнаружения</span><span class="sxs-lookup"><span data-stu-id="80bf8-102">Implementing a Discovery Proxy</span></span>

<span data-ttu-id="80bf8-103">В данном разделе приводятся инструкции по реализации прокси-сервера обнаружения.</span><span class="sxs-lookup"><span data-stu-id="80bf8-103">This section describes the steps required to implement a discovery proxy.</span></span> <span data-ttu-id="80bf8-104">Прокси-сервер обнаружения - это автономная служба, содержащая репозиторий служб.</span><span class="sxs-lookup"><span data-stu-id="80bf8-104">A discovery proxy is a standalone service that contains a repository of services.</span></span> <span data-ttu-id="80bf8-105">Клиенты могут выполнять запросы к прокси-серверу обнаружения, чтобы найти обнаружимые службы, доступные серверу.</span><span class="sxs-lookup"><span data-stu-id="80bf8-105">Clients can query a discovery proxy to find discoverable services that the proxy is aware of.</span></span> <span data-ttu-id="80bf8-106">Метод заполнения прокси-сервера службами определяется разработчиком.</span><span class="sxs-lookup"><span data-stu-id="80bf8-106">How a proxy is populated with services is up to the implementer.</span></span> <span data-ttu-id="80bf8-107">Например, прокси-сервер обнаружения может подключаться к существующему репозиторию служб и сделать эту информацию обнаружимой, администратор может при помощи API управления добавить обнаружимые службы к прокси-серверу, а прокси-сервер обнаружения может при помощи функции объявлений обновить свой внутренний кэш.</span><span class="sxs-lookup"><span data-stu-id="80bf8-107">For example, a discovery proxy can connect to an existing service repository and make that information discoverable, an administrator can use a management API to add discoverable services to a proxy, or a discovery proxy can use the announcement functionality to update its internal cache.</span></span>  
  
 <span data-ttu-id="80bf8-108">Реализация WCF обеспечивает базовые классы, которые позволят легко создавать прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="80bf8-108">The WCF implementation provides base classes that allow you to easily build a proxy.</span></span> <span data-ttu-id="80bf8-109">Эти API-интерфейсы можно использовать для создания прокси-сервера обнаружения поверх существующего репозитория.</span><span class="sxs-lookup"><span data-stu-id="80bf8-109">You can utilize these APIs to build a Discovery Proxy on top of your existing repository.</span></span>  
  
 <span data-ttu-id="80bf8-110">Используемый здесь прокси-сервер обнаружения похож на любую другую службу WCF в том, что можно сделать прокси-сервер обнаруживаемым и позволить клиентам находить его конечные точки.</span><span class="sxs-lookup"><span data-stu-id="80bf8-110">The discovery proxy implemented here is like any other WCF services, in that you can also make the discovery proxy discoverable and have the clients locate its endpoints.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="80bf8-111">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="80bf8-111">In This Section</span></span>  

 [<span data-ttu-id="80bf8-112">Практическое руководство. Как реализовать прокси-сервер обнаружения</span><span class="sxs-lookup"><span data-stu-id="80bf8-112">How to: Implement a Discovery Proxy</span></span>](how-to-implement-a-discovery-proxy.md)  
 <span data-ttu-id="80bf8-113">Реализация прокси-сервера обнаружения.</span><span class="sxs-lookup"><span data-stu-id="80bf8-113">Describes how to implement a discovery proxy.</span></span>  
  
 [<span data-ttu-id="80bf8-114">Практическое руководство. Как реализовать обнаружимую службу, которая регистрируется в прокси-сервере обнаружения</span><span class="sxs-lookup"><span data-stu-id="80bf8-114">How to: Implement a Discoverable Service that Registers with the Discovery Proxy</span></span>](discoverable-service-that-registers-with-the-discovery-proxy.md)  
 <span data-ttu-id="80bf8-115">Описывает, как реализовать обнаруживаемую службу WCF, которая регистрируется в прокси-сервере обнаружения.</span><span class="sxs-lookup"><span data-stu-id="80bf8-115">Describes how to implement a discoverable WCF service that registers with the discovery proxy.</span></span>  
  
 [<span data-ttu-id="80bf8-116">Практическое руководство. Как реализовать клиентское приложение, которое для поиска служб использует прокси-сервер обнаружения</span><span class="sxs-lookup"><span data-stu-id="80bf8-116">How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service</span></span>](client-app-discovery-proxy-to-find-a-service.md)  
 <span data-ttu-id="80bf8-117">Описание реализации клиентского приложения WCF, использующего прокси-сервер обнаружения для поиска службы.</span><span class="sxs-lookup"><span data-stu-id="80bf8-117">Describes how to implement a WCF client application that uses the discovery proxy to search for a service.</span></span>  
  
 [<span data-ttu-id="80bf8-118">Практическое руководство. Как проверить прокси-сервер обнаружения</span><span class="sxs-lookup"><span data-stu-id="80bf8-118">How to: Test the Discovery Proxy</span></span>](how-to-test-the-discovery-proxy.md)  
 <span data-ttu-id="80bf8-119">Описывает, как проверить код, приведенный в предыдущих трех разделах.</span><span class="sxs-lookup"><span data-stu-id="80bf8-119">Describes how to test the code written in the previous three topics.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80bf8-120">См. также</span><span class="sxs-lookup"><span data-stu-id="80bf8-120">See also</span></span>

- [<span data-ttu-id="80bf8-121">Обнаружение WCF</span><span class="sxs-lookup"><span data-stu-id="80bf8-121">WCF Discovery</span></span>](wcf-discovery.md)
- [<span data-ttu-id="80bf8-122">Практическое руководство. Как программно добавить возможность обнаружения к службе и клиенту WCF</span><span class="sxs-lookup"><span data-stu-id="80bf8-122">How to: Programmatically Add Discoverability to a WCF Service and Client</span></span>](how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)
