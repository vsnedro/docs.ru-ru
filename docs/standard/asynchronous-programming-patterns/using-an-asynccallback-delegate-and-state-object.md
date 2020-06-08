---
title: Использование делегата AsyncCallback и объекта состояния
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- asynchronous programming, delegates
- AsyncCallback delegate, samples
- asynchronous programming, state objects
- IAsyncResult interface, samples
ms.assetid: e3e5475d-c5e9-43f0-928e-d18df8ca1f1d
ms.openlocfilehash: e52ed550510253aba9401931c0f612211c7d1bf5
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84276430"
---
# <a name="using-an-asynccallback-delegate-and-state-object"></a><span data-ttu-id="4d6c2-102">Использование делегата AsyncCallback и объекта состояния</span><span class="sxs-lookup"><span data-stu-id="4d6c2-102">Using an AsyncCallback Delegate and State Object</span></span>
<span data-ttu-id="4d6c2-103">Если вы используете делегат <xref:System.AsyncCallback>, чтобы обрабатывать результаты асинхронной операции в отдельном потоке, для передачи сведений между обратными вызовами и получения результата можно использовать объект состояния.</span><span class="sxs-lookup"><span data-stu-id="4d6c2-103">When you use an <xref:System.AsyncCallback> delegate to process the results of the asynchronous operation in a separate thread, you can use a state object to pass information between the callbacks and to retrieve a final result.</span></span> <span data-ttu-id="4d6c2-104">В этой статье для демонстрации этого метода мы дополним пример, приведенный в статье [Использование делегата AsyncCallback для завершения асинхронной операции](using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span><span class="sxs-lookup"><span data-stu-id="4d6c2-104">This topic demonstrates that practice by expanding the example in [Using an AsyncCallback Delegate to End an Asynchronous Operation](using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d6c2-105">Пример</span><span class="sxs-lookup"><span data-stu-id="4d6c2-105">Example</span></span>  
 <span data-ttu-id="4d6c2-106">В следующем примере кода асинхронные методы класса <xref:System.Net.Dns> используются для получения из службы доменных имен (DNS) сведений об указанных пользователем компьютерах.</span><span class="sxs-lookup"><span data-stu-id="4d6c2-106">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System (DNS) information for user-specified computers.</span></span> <span data-ttu-id="4d6c2-107">В примере определяется и используется класс `HostRequest` для хранения сведений о состоянии.</span><span class="sxs-lookup"><span data-stu-id="4d6c2-107">This example defines and uses the `HostRequest` class to store state information.</span></span> <span data-ttu-id="4d6c2-108">Для каждого введенного пользователем имени компьютера создается объект `HostRequest`.</span><span class="sxs-lookup"><span data-stu-id="4d6c2-108">A `HostRequest` object gets created for each computer name entered by the user.</span></span> <span data-ttu-id="4d6c2-109">Этот объект передается в метод <xref:System.Net.Dns.BeginGetHostByName%2A>.</span><span class="sxs-lookup"><span data-stu-id="4d6c2-109">This object is passed to the <xref:System.Net.Dns.BeginGetHostByName%2A> method.</span></span> <span data-ttu-id="4d6c2-110">Метод `ProcessDnsInformation` вызывается каждый раз при завершении запроса.</span><span class="sxs-lookup"><span data-stu-id="4d6c2-110">The `ProcessDnsInformation` method is called each time a request completes.</span></span> <span data-ttu-id="4d6c2-111">Объект `HostRequest` извлекается с помощью свойства <xref:System.IAsyncResult.AsyncState%2A>.</span><span class="sxs-lookup"><span data-stu-id="4d6c2-111">The `HostRequest` object is retrieved using the <xref:System.IAsyncResult.AsyncState%2A> property.</span></span> <span data-ttu-id="4d6c2-112">Метод `ProcessDnsInformation` использует объект `HostRequest` для сохранения значения <xref:System.Net.IPHostEntry> или исключения <xref:System.Net.Sockets.SocketException>, возвращенных запросом.</span><span class="sxs-lookup"><span data-stu-id="4d6c2-112">The `ProcessDnsInformation` method uses the `HostRequest` object to store the <xref:System.Net.IPHostEntry> returned by the request or a <xref:System.Net.Sockets.SocketException> thrown by the request.</span></span> <span data-ttu-id="4d6c2-113">Когда все запросы завершаются, приложение выполняет итерацию всех объектов `HostRequest` и выводит сведения о DNS или сообщение об ошибке <xref:System.Net.Sockets.SocketException>.</span><span class="sxs-lookup"><span data-stu-id="4d6c2-113">When all requests are complete, the application iterates over the `HostRequest` objects and displays the DNS information or <xref:System.Net.Sockets.SocketException> error message.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#5](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateWithStateObject.cs#5)]
 [!code-vb[AsyncDesignPattern#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateWithStateObject.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="4d6c2-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4d6c2-114">See also</span></span>

- [<span data-ttu-id="4d6c2-115">Асинхронная модель на основе событий (EAP)</span><span class="sxs-lookup"><span data-stu-id="4d6c2-115">Event-based Asynchronous Pattern (EAP)</span></span>](event-based-asynchronous-pattern-eap.md)
- [<span data-ttu-id="4d6c2-116">Обзор асинхронной модели, основанной на событиях</span><span class="sxs-lookup"><span data-stu-id="4d6c2-116">Event-based Asynchronous Pattern Overview</span></span>](event-based-asynchronous-pattern-overview.md)
- [<span data-ttu-id="4d6c2-117">Использование делегата AsyncCallback для завершения асинхронной операции</span><span class="sxs-lookup"><span data-stu-id="4d6c2-117">Using an AsyncCallback Delegate to End an Asynchronous Operation</span></span>](using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)
