---
title: Практическое руководство. Как проверить прокси-сервер обнаружения
ms.date: 03/30/2017
ms.assetid: d96e3fa2-3c42-4e5d-8244-2694081bdc32
ms.openlocfilehash: 78921d0a26f1116c87c2931b1472a161d6fed145
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84592818"
---
# <a name="how-to-test-the-discovery-proxy"></a><span data-ttu-id="3ae80-102">Практическое руководство. Как проверить прокси-сервер обнаружения</span><span class="sxs-lookup"><span data-stu-id="3ae80-102">How to: Test the Discovery Proxy</span></span>
<span data-ttu-id="3ae80-103">Это последний из четырех разделов, в которых демонстрируется реализация прокси-сервера обнаружения.</span><span class="sxs-lookup"><span data-stu-id="3ae80-103">This is the fourth of four topics that shows how to implement a discovery proxy.</span></span> <span data-ttu-id="3ae80-104">В предыдущем разделе [как реализовать клиентское приложение, использующее прокси-сервер обнаружения для поиска службы](client-app-discovery-proxy-to-find-a-service.md), вы реализовали клиентское приложение WCF, которое использует прокси-сервер обнаружения для поиска службы и затем вызывает службу.</span><span class="sxs-lookup"><span data-stu-id="3ae80-104">In the previous topic, [How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service](client-app-discovery-proxy-to-find-a-service.md), you implemented a WCF client application that uses the discovery proxy to find a service and then calls the service.</span></span> <span data-ttu-id="3ae80-105">В данном разделе показано, как проверить работу прокси-сервера обнаружения, службы и клиентского приложения.</span><span class="sxs-lookup"><span data-stu-id="3ae80-105">This topic describes how to verify the discovery proxy, the service, and the client application work as expected.</span></span>  
  
### <a name="run-the-discovery-proxy"></a><span data-ttu-id="3ae80-106">Запуск прокси-сервера обнаружения</span><span class="sxs-lookup"><span data-stu-id="3ae80-106">Run the Discovery Proxy</span></span>  
  
1. <span data-ttu-id="3ae80-107">Откройте командную строку как администратор.</span><span class="sxs-lookup"><span data-stu-id="3ae80-107">Open a command prompt as an administrator.</span></span>  
  
2. <span data-ttu-id="3ae80-108">Может появиться диалоговое окно с сообщением «Брандмауэр Windows заблокировал некоторые из функций этой программы».</span><span class="sxs-lookup"><span data-stu-id="3ae80-108">You may see a dialog that says: Windows Firewall has blocked some features of this program.</span></span> <span data-ttu-id="3ae80-109">Если вы видите это сообщение, нажмите кнопку **разблокировать** .</span><span class="sxs-lookup"><span data-stu-id="3ae80-109">If you see this message, click the **Unblock** button.</span></span>  
  
3. <span data-ttu-id="3ae80-110">Запустите из командной строки прокси-сервер обнаружения DiscoveryProxy.exe.</span><span class="sxs-lookup"><span data-stu-id="3ae80-110">Within the command prompt, run the discovery proxy, DiscoveryProxy.exe.</span></span>  
  
4. <span data-ttu-id="3ae80-111">Приложение должно вывести на экран сообщение: `Proxy started. Hit Enter to exit`.</span><span class="sxs-lookup"><span data-stu-id="3ae80-111">The application should display the following text: `Proxy started. Hit Enter to exit`.</span></span>  
  
### <a name="run-the-discoverable-service"></a><span data-ttu-id="3ae80-112">Запуск обнаруживаемой службы</span><span class="sxs-lookup"><span data-stu-id="3ae80-112">Run the Discoverable Service</span></span>  
  
1. <span data-ttu-id="3ae80-113">Откройте командную строку как администратор.</span><span class="sxs-lookup"><span data-stu-id="3ae80-113">Open a command prompt as an administrator.</span></span>  
  
2. <span data-ttu-id="3ae80-114">Из командной строки запустите обнаруживаемую службу Service.exe.</span><span class="sxs-lookup"><span data-stu-id="3ae80-114">Within the command prompt, run the Service.exe discoverable service.</span></span>  
  
3. <span data-ttu-id="3ae80-115">В DiscoveryProxy. exe должен отображаться следующий текст: `******* Adding the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 3.******* Done *******` .</span><span class="sxs-lookup"><span data-stu-id="3ae80-115">The DiscoveryProxy.exe should display the following text: `******* Adding the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 3.******* Done *******` .</span></span>  
  
### <a name="run-the-client-application"></a><span data-ttu-id="3ae80-116">Запуск клиентского приложения</span><span class="sxs-lookup"><span data-stu-id="3ae80-116">Run the Client Application</span></span>  
  
1. <span data-ttu-id="3ae80-117">Откройте командную строку.</span><span class="sxs-lookup"><span data-stu-id="3ae80-117">Open a command prompt.</span></span>  
  
2. <span data-ttu-id="3ae80-118">Из командной строки запустите приложение client.exe.</span><span class="sxs-lookup"><span data-stu-id="3ae80-118">Within the command prompt, run the client.exe application.</span></span>  
  
3. <span data-ttu-id="3ae80-119">Через несколько секунд клиентское приложение выведет на экран сообщение: «Connecting to [Service-Endpoint]».</span><span class="sxs-lookup"><span data-stu-id="3ae80-119">After a few seconds the client application displays the following text: Connecting to [Service-Endpoint].</span></span>  
  
4. <span data-ttu-id="3ae80-120">Программа service.exe должна затем вывести на экран сообщение: «Greeting request received, I will respond».</span><span class="sxs-lookup"><span data-stu-id="3ae80-120">The service.exe should then display the following text: Greeting request received, I will respond.</span></span>  
  
5. <span data-ttu-id="3ae80-121">Приложение client.exe должно затем вывести на экран сообщение: «Hello Client!»</span><span class="sxs-lookup"><span data-stu-id="3ae80-121">The client.exe should then display the following text: Hello Client!</span></span>  
  
### <a name="shut-down-the-applications"></a><span data-ttu-id="3ae80-122">Завершение работы приложений</span><span class="sxs-lookup"><span data-stu-id="3ae80-122">Shut Down the Applications</span></span>  
  
1. <span data-ttu-id="3ae80-123">Закройте клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="3ae80-123">Shut down the client application.</span></span>  
  
2. <span data-ttu-id="3ae80-124">Завершите работу службы.</span><span class="sxs-lookup"><span data-stu-id="3ae80-124">Shut down the service.</span></span> <span data-ttu-id="3ae80-125">Прокси-сервер обнаружения выведет на экран сообщение: `******* Removing the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 2.3.******* Done *******`.</span><span class="sxs-lookup"><span data-stu-id="3ae80-125">The discovery proxy displays the following text: `******* Removing the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 2.3.******* Done *******`.</span></span>  
  
3. <span data-ttu-id="3ae80-126">Завершите работу прокси-сервера обнаружения.</span><span class="sxs-lookup"><span data-stu-id="3ae80-126">Shut down the discovery proxy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ae80-127">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="3ae80-127">See also</span></span>

- [<span data-ttu-id="3ae80-128">Общие сведения об обнаружении WCF</span><span class="sxs-lookup"><span data-stu-id="3ae80-128">WCF Discovery Overview</span></span>](wcf-discovery-overview.md)
- [<span data-ttu-id="3ae80-129">Практическое руководство. Как реализовать прокси-сервер обнаружения</span><span class="sxs-lookup"><span data-stu-id="3ae80-129">How to: Implement a Discovery Proxy</span></span>](how-to-implement-a-discovery-proxy.md)
- [<span data-ttu-id="3ae80-130">Практическое руководство. Как реализовать обнаружимую службу, которая регистрируется в прокси-сервере обнаружения</span><span class="sxs-lookup"><span data-stu-id="3ae80-130">How to: Implement a Discoverable Service that Registers with the Discovery Proxy</span></span>](discoverable-service-that-registers-with-the-discovery-proxy.md)
- [<span data-ttu-id="3ae80-131">Практическое руководство. Как реализовать клиентское приложение, которое для поиска служб использует прокси-сервер обнаружения</span><span class="sxs-lookup"><span data-stu-id="3ae80-131">How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service</span></span>](client-app-discovery-proxy-to-find-a-service.md)
