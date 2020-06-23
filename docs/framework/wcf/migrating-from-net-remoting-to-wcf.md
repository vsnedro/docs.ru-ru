---
title: Перенос из .NET на платформу WCF
description: Узнайте, как перенести приложение, использующее удаленное взаимодействие .NET, для использования WCF. В WCF можно выполнять несколько распространенных сценариев удаленного взаимодействия.
ms.date: 03/30/2017
ms.assetid: 16902a42-ef80-40e9-8c4c-90e61ddfdfe5
ms.openlocfilehash: f6f526db09806008314980b71233b208d25359fc
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246159"
---
# <a name="migrating-from-net-remoting-to-wcf"></a><span data-ttu-id="def9e-104">Перенос из .NET на платформу WCF</span><span class="sxs-lookup"><span data-stu-id="def9e-104">Migrating from .NET Remoting to WCF</span></span>
<span data-ttu-id="def9e-105">В этой статье описан процесс переноса приложения с переходом от использования удаленного взаимодействия .NET к использованию Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="def9e-105">This article describes how to migrate an application that uses .NET Remoting to use Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="def9e-106">В ней сравниваются сходные принципы работы с этими продуктами и описывается выполнение некоторых наиболее распространенных сценариев удаленного взаимодействия в WCF.</span><span class="sxs-lookup"><span data-stu-id="def9e-106">It compares similar concepts between these products and then describes how to accomplish several common Remoting scenarios in WCF.</span></span>  
  
 <span data-ttu-id="def9e-107">Удаленное взаимодействие .NET — это устаревший продукт, который поддерживается только в целях обеспечения обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="def9e-107">.NET Remoting is a legacy product that is supported only for backward compatibility.</span></span> <span data-ttu-id="def9e-108">Использование этого продукта в средах со смешанными уровнями доверия не является безопасным, поскольку он не может поддерживать отдельные уровни доверия для клиента и сервера.</span><span class="sxs-lookup"><span data-stu-id="def9e-108">It is not secure across mixed-trust environments because it cannot maintain the separate trust levels between client and server.</span></span> <span data-ttu-id="def9e-109">Например, ни при каких обстоятельствах не следует предоставлять конечную точку удаленного взаимодействия .NET интернет-клиентам или недоверенным клиентам.</span><span class="sxs-lookup"><span data-stu-id="def9e-109">For example, you should never expose a .NET Remoting endpoint to the Internet or to untrusted clients.</span></span> <span data-ttu-id="def9e-110">Рекомендуется перенести существующие приложения удаленного взаимодействия на базу более новых и безопасных технологий.</span><span class="sxs-lookup"><span data-stu-id="def9e-110">We recommend existing Remoting applications be migrated to newer and more secure technologies.</span></span> <span data-ttu-id="def9e-111">Если в структуре приложения используется только протокол HTTP и архитектура RESTful, рекомендуется воспользоваться веб-API ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="def9e-111">If the application’s design uses only HTTP and is RESTful, we recommend ASP.NET Web API.</span></span> <span data-ttu-id="def9e-112">Дополнительные сведения см. в статье, посвященной веб-API ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="def9e-112">For more information, see ASP.NET Web API.</span></span> <span data-ttu-id="def9e-113">Если приложение основано на SOAP или требует использования протоколов, отличных от HTTP, например TCP, рекомендуется использовать WCF.</span><span class="sxs-lookup"><span data-stu-id="def9e-113">If the application is based on SOAP or requires non-Http protocols such as TCP, we recommend WCF.</span></span>  

## <a name="comparing-net-remoting-to-wcf"></a><span data-ttu-id="def9e-114">Сравнение удаленного взаимодействия .NET и WCF</span><span class="sxs-lookup"><span data-stu-id="def9e-114">Comparing .NET Remoting to WCF</span></span>  
 <span data-ttu-id="def9e-115">В этом разделе сравниваются основные структурные элементы системы удаленного взаимодействия .NET с аналогичными элементами WCF.</span><span class="sxs-lookup"><span data-stu-id="def9e-115">This section compares the basic building blocks of .NET Remoting with their WCF equivalents.</span></span> <span data-ttu-id="def9e-116">Эти стандартные блоки будут использоваться позже для создания некоторых распространенных сценариев клиент-сервер в WCF.</span><span class="sxs-lookup"><span data-stu-id="def9e-116">We will use these building blocks later to create some common client-server scenarios in WCF.</span></span> <span data-ttu-id="def9e-117">На следующей диаграмме представлены основные сходства и различия между удаленным взаимодействием .NET и WCF.</span><span class="sxs-lookup"><span data-stu-id="def9e-117">The following chart summarizes the main similarities and differences between .NET Remoting and WCF.</span></span>  
  
||<span data-ttu-id="def9e-118">Удаленное взаимодействие .NET</span><span class="sxs-lookup"><span data-stu-id="def9e-118">.NET Remoting</span></span>|<span data-ttu-id="def9e-119">WCF</span><span class="sxs-lookup"><span data-stu-id="def9e-119">WCF</span></span>|  
|-|-------------------|---------|  
|<span data-ttu-id="def9e-120">Тип сервера</span><span class="sxs-lookup"><span data-stu-id="def9e-120">Server type</span></span>|<span data-ttu-id="def9e-121">Подкласс MarshalByRefObject</span><span class="sxs-lookup"><span data-stu-id="def9e-121">Subclass MarshalByRefObject</span></span>|<span data-ttu-id="def9e-122">Отметка атрибутом [ServiceContract]</span><span class="sxs-lookup"><span data-stu-id="def9e-122">Mark with [ServiceContract] attribute</span></span>|  
|<span data-ttu-id="def9e-123">Операции служб</span><span class="sxs-lookup"><span data-stu-id="def9e-123">Service operations</span></span>|<span data-ttu-id="def9e-124">Открытые методы для типа сервера</span><span class="sxs-lookup"><span data-stu-id="def9e-124">Public methods on server type</span></span>|<span data-ttu-id="def9e-125">Отметка атрибутом [OperationContract]</span><span class="sxs-lookup"><span data-stu-id="def9e-125">Mark with [OperationContract] attribute</span></span>|  
|<span data-ttu-id="def9e-126">Сериализация</span><span class="sxs-lookup"><span data-stu-id="def9e-126">Serialization</span></span>|<span data-ttu-id="def9e-127">ISerializable или [Serializable]</span><span class="sxs-lookup"><span data-stu-id="def9e-127">ISerializable or [Serializable]</span></span>|<span data-ttu-id="def9e-128">DataContractSerializer или XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="def9e-128">DataContractSerializer or XmlSerializer</span></span>|  
|<span data-ttu-id="def9e-129">Передаваемые объекты</span><span class="sxs-lookup"><span data-stu-id="def9e-129">Objects passed</span></span>|<span data-ttu-id="def9e-130">По значению или по ссылке</span><span class="sxs-lookup"><span data-stu-id="def9e-130">By-value or by-reference</span></span>|<span data-ttu-id="def9e-131">Только по значению</span><span class="sxs-lookup"><span data-stu-id="def9e-131">By-value only</span></span>|  
|<span data-ttu-id="def9e-132">Ошибки и исключения</span><span class="sxs-lookup"><span data-stu-id="def9e-132">Errors/exceptions</span></span>|<span data-ttu-id="def9e-133">Любые сериализуемые исключения</span><span class="sxs-lookup"><span data-stu-id="def9e-133">Any serializable exception</span></span>|<span data-ttu-id="def9e-134">фаултконтракт\<TDetail></span><span class="sxs-lookup"><span data-stu-id="def9e-134">FaultContract\<TDetail></span></span>|  
|<span data-ttu-id="def9e-135">Прокси-объекты клиента</span><span class="sxs-lookup"><span data-stu-id="def9e-135">Client proxy objects</span></span>|<span data-ttu-id="def9e-136">Строго типизированные прозрачные прокси-объекты создаются автоматически из MarshalByRefObjects.</span><span class="sxs-lookup"><span data-stu-id="def9e-136">Strongly typed transparent proxies are created automatically from MarshalByRefObjects</span></span>|<span data-ttu-id="def9e-137">Строго типизированные прокси-серверы создаются по запросу с помощью ChannelFactory.\<TChannel></span><span class="sxs-lookup"><span data-stu-id="def9e-137">Strongly typed proxies are generated on-demand using ChannelFactory\<TChannel></span></span>|  
|<span data-ttu-id="def9e-138">Требуемая платформа</span><span class="sxs-lookup"><span data-stu-id="def9e-138">Platform required</span></span>|<span data-ttu-id="def9e-139">Клиент и сервер должны использовать ОС Microsoft и .NET.</span><span class="sxs-lookup"><span data-stu-id="def9e-139">Both client and server must use Microsoft OS and .NET</span></span>|<span data-ttu-id="def9e-140">Поддержка разных платформ</span><span class="sxs-lookup"><span data-stu-id="def9e-140">Cross-platform</span></span>|  
|<span data-ttu-id="def9e-141">Формат сообщений</span><span class="sxs-lookup"><span data-stu-id="def9e-141">Message format</span></span>|<span data-ttu-id="def9e-142">Private</span><span class="sxs-lookup"><span data-stu-id="def9e-142">Private</span></span>|<span data-ttu-id="def9e-143">Отраслевые стандарты (SOAP, WS-\* и т. п.)</span><span class="sxs-lookup"><span data-stu-id="def9e-143">Industry standards (SOAP, WS-\*, etc.)</span></span>|  
  
### <a name="server-implementation-comparison"></a><span data-ttu-id="def9e-144">Сравнение реализации сервера</span><span class="sxs-lookup"><span data-stu-id="def9e-144">Server Implementation Comparison</span></span>  
  
#### <a name="creating-a-server-in-net-remoting"></a><span data-ttu-id="def9e-145">Создание сервера в системе удаленного взаимодействия .NET</span><span class="sxs-lookup"><span data-stu-id="def9e-145">Creating a Server in .NET Remoting</span></span>  
 <span data-ttu-id="def9e-146">Типы сервера удаленного взаимодействия .NET должны производиться из подкласса MarshalByRefObject и определять методы, которые может вызывать клиент, следующим образом.</span><span class="sxs-lookup"><span data-stu-id="def9e-146">.NET Remoting server types must derive from MarshalByRefObject and define methods the client can call, like the following:</span></span>  
  
```csharp
public class RemotingServer : MarshalByRefObject  
{  
    public Customer GetCustomer(int customerId) { … }  
}  
```  
  
 <span data-ttu-id="def9e-147">Открытые методы этого типа сервера становятся открытым контрактом, доступным для клиентов.</span><span class="sxs-lookup"><span data-stu-id="def9e-147">The public methods of this server type become the public contract available to clients.</span></span>  <span data-ttu-id="def9e-148">Открытый интерфейс сервера и его реализация не разделяются и обрабатываются одним типом.</span><span class="sxs-lookup"><span data-stu-id="def9e-148">There is no separation between the server’s public interface and its implementation – one type handles both.</span></span>  
  
 <span data-ttu-id="def9e-149">После определения типа сервера его можно сделать доступным для клиентов, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="def9e-149">Once the server type has been defined, it can be made available to clients, like in the following example:</span></span>  
  
```csharp
TcpChannel channel = new TcpChannel(8080);  
ChannelServices.RegisterChannel(channel, ensureSecurity : true);  
RemotingConfiguration.RegisterWellKnownServiceType(  
    typeof(RemotingServer),
    "RemotingServer",
    WellKnownObjectMode.Singleton);  
Console.WriteLine("RemotingServer is running.  Press ENTER to terminate...");  
Console.ReadLine();  
```  
  
 <span data-ttu-id="def9e-150">Существуют различные способы предоставления доступа к типу удаленного взаимодействия как к серверу, включая использование файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="def9e-150">There are many ways to make the Remoting type available as a server, including using configuration files.</span></span> <span data-ttu-id="def9e-151">Это лишь один пример.</span><span class="sxs-lookup"><span data-stu-id="def9e-151">This is just one example.</span></span>  
  
#### <a name="creating-a-server-in-wcf"></a><span data-ttu-id="def9e-152">Создание сервера в WCF</span><span class="sxs-lookup"><span data-stu-id="def9e-152">Creating a Server in WCF</span></span>  
 <span data-ttu-id="def9e-153">Эквивалентное действие в WCF включает создание двух типов: открытого «контракта службы» и конкретной реализации.</span><span class="sxs-lookup"><span data-stu-id="def9e-153">The equivalent step in WCF involves creating two types -- the public "service contract" and the concrete implementation.</span></span> <span data-ttu-id="def9e-154">Первый тип объявляется как интерфейс, отмеченный атрибутом [ServiceContract].</span><span class="sxs-lookup"><span data-stu-id="def9e-154">The first is declared as an interface marked with [ServiceContract].</span></span> <span data-ttu-id="def9e-155">Доступные клиентам методы отмечаются атрибутом [OperationContract]:</span><span class="sxs-lookup"><span data-stu-id="def9e-155">Methods available to clients are marked with [OperationContract]:</span></span>  
  
```csharp
[ServiceContract]  
public interface IWCFServer  
{  
    [OperationContract]  
    Customer GetCustomer(int customerId);  
}  
```  
  
 <span data-ttu-id="def9e-156">Реализация сервера определяется в отдельном конкретном классе, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="def9e-156">The server’s implementation is defined in a separate concrete class, like in the following example:</span></span>  
  
```csharp
public class WCFServer : IWCFServer  
{  
    public Customer GetCustomer(int customerId) { … }  
}  
```  
  
 <span data-ttu-id="def9e-157">После определения этих типов клиентам можно предоставить доступ к серверу WCF, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="def9e-157">Once these types have been defined, the WCF server can be made available to clients, like in the following example:</span></span>  
  
```csharp
NetTcpBinding binding = new NetTcpBinding();  
Uri baseAddress = new Uri("net.tcp://localhost:8000/wcfserver");  
  
using (ServiceHost serviceHost = new ServiceHost(typeof(WCFServer), baseAddress))  
{  
    serviceHost.AddServiceEndpoint(typeof(IWCFServer), binding, baseAddress);  
    serviceHost.Open();  
  
    Console.WriteLine($"The WCF server is ready at {baseAddress}.");
    Console.WriteLine("Press <ENTER> to terminate service...");  
    Console.WriteLine();  
    Console.ReadLine();  
}  
```  
  
> [!NOTE]
> <span data-ttu-id="def9e-158">В обоих примерах используется TCP для обеспечения максимального сходства.</span><span class="sxs-lookup"><span data-stu-id="def9e-158">TCP is used in both examples to keep them as similar as possible.</span></span> <span data-ttu-id="def9e-159">См. пошаговые руководства по сценариям, приведенные далее в этой статье, чтобы ознакомиться с примерами с использованием HTTP.</span><span class="sxs-lookup"><span data-stu-id="def9e-159">Refer to the scenario walk-throughs later in this topic for examples using HTTP.</span></span>  
  
 <span data-ttu-id="def9e-160">Существуют различные способы настройки и размещения служб WCF.</span><span class="sxs-lookup"><span data-stu-id="def9e-160">There are many ways to configure and to host WCF services.</span></span> <span data-ttu-id="def9e-161">Это лишь один пример размещения, называемый «резидентным размещением».</span><span class="sxs-lookup"><span data-stu-id="def9e-161">This is just one example, known as "self-hosted".</span></span> <span data-ttu-id="def9e-162">Дополнительные сведения см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="def9e-162">For more information, see the following topics:</span></span>  
  
- [<span data-ttu-id="def9e-163">Практическое руководство. Определение контракта службы</span><span class="sxs-lookup"><span data-stu-id="def9e-163">How to: Define a Service Contract</span></span>](how-to-define-a-wcf-service-contract.md)  
  
- [<span data-ttu-id="def9e-164">Настройка служб с использованием файлов конфигурации</span><span class="sxs-lookup"><span data-stu-id="def9e-164">Configuring Services Using Configuration Files</span></span>](configuring-services-using-configuration-files.md)  
  
- [<span data-ttu-id="def9e-165">Размещение служб</span><span class="sxs-lookup"><span data-stu-id="def9e-165">Hosting Services</span></span>](hosting-services.md)  
  
### <a name="client-implementation-comparison"></a><span data-ttu-id="def9e-166">Сравнение реализации клиента</span><span class="sxs-lookup"><span data-stu-id="def9e-166">Client Implementation Comparison</span></span>  
  
#### <a name="creating-a-client-in-net-remoting"></a><span data-ttu-id="def9e-167">Создание клиента в системе удаленного взаимодействия .NET</span><span class="sxs-lookup"><span data-stu-id="def9e-167">Creating a Client in .NET Remoting</span></span>  
 <span data-ttu-id="def9e-168">После создания доступного объекта-сервера удаленного взаимодействия .NET он может использоваться клиентами, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="def9e-168">Once a .NET Remoting server object has been made available, it can be consumed by clients, like in the following example:</span></span>  
  
```csharp
TcpChannel channel = new TcpChannel();  
ChannelServices.RegisterChannel(channel, ensureSecurity : true);  
RemotingServer server = (RemotingServer)Activator.GetObject(  
                            typeof(RemotingServer),
                            "tcp://localhost:8080/RemotingServer");  
  
RemotingCustomer customer = server.GetCustomer(42);  
Console.WriteLine($"Customer {customer.FirstName} {customer.LastName} received.");
```  
  
 <span data-ttu-id="def9e-169">Экземпляр RemotingServer, возвращаемый Activator.GetObject(), называется «прозрачным прокси-сервером».</span><span class="sxs-lookup"><span data-stu-id="def9e-169">The RemotingServer instance returned from Activator.GetObject() is known as a "transparent proxy."</span></span> <span data-ttu-id="def9e-170">Он реализует открытый API для типа RemotingServer на стороне клиента, но все методы вызова объекта-сервера выполняются в рамках другого процесса или на другом компьютере.</span><span class="sxs-lookup"><span data-stu-id="def9e-170">It implements the public API for the RemotingServer type on the client, but all the methods call the server object running in a different process or machine.</span></span>  
  
#### <a name="creating-a-client-in-wcf"></a><span data-ttu-id="def9e-171">Создание клиента в WCF</span><span class="sxs-lookup"><span data-stu-id="def9e-171">Creating a Client in WCF</span></span>  
 <span data-ttu-id="def9e-172">Аналогичное действие в WCF предполагает использование фабрики каналов для создания прокси-объектов явным образом.</span><span class="sxs-lookup"><span data-stu-id="def9e-172">The equivalent step in WCF involves using a channel factory to create the proxy explicitly.</span></span> <span data-ttu-id="def9e-173">Как и в системе удаленного взаимодействия, прокси-объект можно использовать для вызова операций на сервере, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="def9e-173">Like Remoting, the proxy object can be used to invoke operations on the server, like in the following example:</span></span>  
  
```csharp
NetTcpBinding binding = new NetTcpBinding();  
String url = "net.tcp://localhost:8000/wcfserver";  
EndpointAddress address = new EndpointAddress(url);  
ChannelFactory<IWCFServer> channelFactory =
    new ChannelFactory<IWCFServer>(binding, address);  
IWCFServer server = channelFactory.CreateChannel();  
  
Customer customer = server.GetCustomer(42);  
Console.WriteLine($"  Customer {customer.FirstName} {customer.LastName} received.");
```  
  
 <span data-ttu-id="def9e-174">Это пример программирования на уровне канала, так как он обладает максимальным сходством с примером удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="def9e-174">This example shows programming at the channel level because it is most similar to the Remoting example.</span></span> <span data-ttu-id="def9e-175">Также доступен **Добавление ссылки на службу** подход в Visual Studio, который создает код для упрощения программирования клиента.</span><span class="sxs-lookup"><span data-stu-id="def9e-175">Also available is the **Add Service Reference** approach in Visual Studio that generates code to simplify client programming.</span></span> <span data-ttu-id="def9e-176">Дополнительные сведения см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="def9e-176">For more information, see the following topics:</span></span>  
  
- [<span data-ttu-id="def9e-177">Программирование клиентов на уровне канала</span><span class="sxs-lookup"><span data-stu-id="def9e-177">Client Channel-Level Programming</span></span>](./extending/client-channel-level-programming.md)  
  
- [<span data-ttu-id="def9e-178">Практическое руководство. Добавление, обновление или удаление ссылки на службу</span><span class="sxs-lookup"><span data-stu-id="def9e-178">How to: Add, Update, or Remove a Service Reference</span></span>](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference)  
  
### <a name="serialization-usage"></a><span data-ttu-id="def9e-179">Использование сериализации</span><span class="sxs-lookup"><span data-stu-id="def9e-179">Serialization Usage</span></span>  
 <span data-ttu-id="def9e-180">Удаленное взаимодействие .NET и WCF используют сериализацию для передачи объектов между клиентом и сервером, но они отличаются в следующих важных аспектах.</span><span class="sxs-lookup"><span data-stu-id="def9e-180">Both .NET Remoting and WCF use serialization to send objects between client and server, but they differ in these important ways:</span></span>  
  
1. <span data-ttu-id="def9e-181">Они используют разные сериализаторы и соглашения для указания сериализуемых объектов.</span><span class="sxs-lookup"><span data-stu-id="def9e-181">They use different serializers and conventions to indicate what to serialize.</span></span>  
  
2. <span data-ttu-id="def9e-182">Система удаленного взаимодействия .NET поддерживает сериализацию «по ссылке» и разрешает доступ к методу или свойству на одном уровне для выполнения кода на другом уровне, что нарушает границы безопасности.</span><span class="sxs-lookup"><span data-stu-id="def9e-182">.NET Remoting supports "by reference" serialization that allows method or property access on one tier to execute code on the other tier, which is across security boundaries.</span></span> <span data-ttu-id="def9e-183">Эта возможность создает уязвимости системы безопасности и является одной из основных причин, по которым клиентам, не обладающим должным уровнем доверия, не следует предоставлять доступ к конечным точкам удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="def9e-183">This capability exposes security vulnerabilities and is one of the main reasons why Remoting endpoints should never be exposed to untrusted clients.</span></span>  
  
3. <span data-ttu-id="def9e-184">Сериализация в системе удаленного взаимодействия строится на принципе явного отказа (с явным исключением объектов, не подлежащих сериализации), а сериализация в WCF — на принципе явного согласия (с явным указанием объектов для сериализации).</span><span class="sxs-lookup"><span data-stu-id="def9e-184">Serialization used by Remoting is opt-out (explicitly exclude what not to serialize) and WCF serialization is opt-in (explicitly mark which members to serialize).</span></span>  
  
#### <a name="serialization-in-net-remoting"></a><span data-ttu-id="def9e-185">Сериализация в среде удаленного взаимодействия .NET</span><span class="sxs-lookup"><span data-stu-id="def9e-185">Serialization in .NET Remoting</span></span>  
 <span data-ttu-id="def9e-186">Система удаленного взаимодействия .NET поддерживает два способа сериализации и десериализации объектов между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="def9e-186">.NET Remoting supports two ways to serialize and deserialize objects between the client and server:</span></span>  
  
- <span data-ttu-id="def9e-187">*По значению* — значения объекта сериализуются через границы уровня, а новый экземпляр этого объекта создается на другом уровне.</span><span class="sxs-lookup"><span data-stu-id="def9e-187">*By value* – the values of the object are serialized across tier boundaries, and a new instance of that object is created on the other tier.</span></span> <span data-ttu-id="def9e-188">Любые вызовы методов и свойств этого нового экземпляра выполняются только на локальном компьютере и не влияют на исходный объект или уровень.</span><span class="sxs-lookup"><span data-stu-id="def9e-188">Any calls to methods or properties of that new instance execute only locally and do not affect the original object or tier.</span></span>  
  
- <span data-ttu-id="def9e-189">*По ссылке* — специальная "ссылка на объект" сериализуется через границы уровня.</span><span class="sxs-lookup"><span data-stu-id="def9e-189">*By reference* – a special "object reference" is serialized across tier boundaries.</span></span> <span data-ttu-id="def9e-190">Когда один уровень взаимодействует с методами или свойствами данного объекта, он устанавливает обратную связь с исходным объектом на исходном уровне.</span><span class="sxs-lookup"><span data-stu-id="def9e-190">When one tier interacts with methods or properties of that object, it communicates back to the original object on the original tier.</span></span> <span data-ttu-id="def9e-191">Объекты по ссылке могут передаваться в любом направлении — с сервера на клиент или с клиента на сервер.</span><span class="sxs-lookup"><span data-stu-id="def9e-191">By-reference objects can flow in either direction – server to client, or client to server.</span></span>  
  
 <span data-ttu-id="def9e-192">Типы по значению в системе удаленного взаимодействия обозначены атрибутом [Serializable] или реализуют интерфейс ISerializable, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="def9e-192">By-value types in Remoting are marked with the [Serializable] attribute or implement ISerializable, like in the following example:</span></span>  
  
```csharp
[Serializable]  
public class RemotingCustomer  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
    public int CustomerId { get; set; }  
}  
```  
  
 <span data-ttu-id="def9e-193">Типы по ссылке являются производными от класса MarshalByRefObject, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="def9e-193">By-reference types derive from the MarshalByRefObject class, like in the following example:</span></span>  
  
```csharp
public class RemotingCustomerReference : MarshalByRefObject  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
    public int CustomerId { get; set; }  
}  
```  
  
 <span data-ttu-id="def9e-194">Очень важно понимать последствия использования объектов по ссылке в системе удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="def9e-194">It is extremely important to understand the implications of Remoting’s by-reference objects.</span></span> <span data-ttu-id="def9e-195">Если какой-либо уровень (клиент или сервер) отправляет объект по ссылке на другой уровень, все вызовы методов выполняются на уровне, к которому относится объект.</span><span class="sxs-lookup"><span data-stu-id="def9e-195">If either tier (client or server) sends a by-reference object to the other tier, all method calls execute back on the tier owning the object.</span></span> <span data-ttu-id="def9e-196">Например методы вызова клиента для объекта по ссылке, возвращаемого сервером, выполняют код на сервере.</span><span class="sxs-lookup"><span data-stu-id="def9e-196">For example, a client calling methods on a by-reference object returned by the server will execute code on the server.</span></span> <span data-ttu-id="def9e-197">Аналогичным образом, методы вызова сервера объекта по ссылке, предоставляемого клиентом, выполняют код на клиенте.</span><span class="sxs-lookup"><span data-stu-id="def9e-197">Similarly, a server calling methods on a by-reference object provided by the client will execute code back on the client.</span></span> <span data-ttu-id="def9e-198">По этой причине использование системы удаленного взаимодействия .NET рекомендуется только в средах с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="def9e-198">For this reason, the use of .NET Remoting is recommended only within fully-trusted environments.</span></span> <span data-ttu-id="def9e-199">Предоставление открытой конечной точки удаленного взаимодействия .NET ненадежным клиентам делает сервер удаленного взаимодействия уязвимым для атак.</span><span class="sxs-lookup"><span data-stu-id="def9e-199">Exposing a public .NET Remoting endpoint to untrusted clients will make a Remoting server vulnerable to attack.</span></span>  
  
#### <a name="serialization-in-wcf"></a><span data-ttu-id="def9e-200">Сериализация в WCF</span><span class="sxs-lookup"><span data-stu-id="def9e-200">Serialization in WCF</span></span>  
 <span data-ttu-id="def9e-201">WCF поддерживает только сериализацию по значению.</span><span class="sxs-lookup"><span data-stu-id="def9e-201">WCF supports only by-value serialization.</span></span> <span data-ttu-id="def9e-202">Наиболее распространенный способ определения типа для обмена между клиентом и сервером показан в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="def9e-202">The most common way to define a type to exchange between client and server is like in the following example:</span></span>  
  
```csharp
[DataContract]  
public class WCFCustomer  
{  
    [DataMember]  
    public string FirstName { get; set; }  
  
    [DataMember]  
    public string LastName { get; set; }  
  
    [DataMember]  
    public int CustomerId { get; set; }  
}  
```  
  
 <span data-ttu-id="def9e-203">Атрибут [DataContract] определяет этот тип как тип, доступный для сериализации и десериализации между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="def9e-203">The [DataContract] attribute identifies this type as one that can be serialized and deserialized between client and server.</span></span> <span data-ttu-id="def9e-204">Атрибут [DataMember] определяет отдельные свойства или поля для сериализации.</span><span class="sxs-lookup"><span data-stu-id="def9e-204">The [DataMember] attribute identifies the individual properties or fields to serialize.</span></span>  
  
 <span data-ttu-id="def9e-205">Когда WCF отправляет объект между уровнями, он сериализует только значения и создает новый экземпляр объекта на другом уровне.</span><span class="sxs-lookup"><span data-stu-id="def9e-205">When WCF sends an object across tiers, it serializes only the values and creates a new instance of the object on the other tier.</span></span> <span data-ttu-id="def9e-206">Любое взаимодействие со значениями объекта осуществляется только на локальном уровне — они не взаимодействуют с другим уровнем в отличие от объектов по ссылке системы удаленного взаимодействия .NET.</span><span class="sxs-lookup"><span data-stu-id="def9e-206">Any interactions with the values of the object occur only locally – they do not communicate with the other tier the way .NET Remoting by-reference objects do.</span></span> <span data-ttu-id="def9e-207">Дополнительные сведения см. в разделе [сериализация и десериализация](./feature-details/serialization-and-deserialization.md).</span><span class="sxs-lookup"><span data-stu-id="def9e-207">For more information, see [Serialization and Deserialization](./feature-details/serialization-and-deserialization.md).</span></span>  
  
### <a name="exception-handling-capabilities"></a><span data-ttu-id="def9e-208">Возможности обработки исключений</span><span class="sxs-lookup"><span data-stu-id="def9e-208">Exception Handling Capabilities</span></span>  
  
#### <a name="exceptions-in-net-remoting"></a><span data-ttu-id="def9e-209">Исключения в системе удаленного взаимодействия .NET</span><span class="sxs-lookup"><span data-stu-id="def9e-209">Exceptions in .NET Remoting</span></span>  
 <span data-ttu-id="def9e-210">Исключения, создаваемые удаленным сервером, сериализуются, отправляются на клиент и возникают локально на стороне клиента так же, как и любые другие исключения.</span><span class="sxs-lookup"><span data-stu-id="def9e-210">Exceptions thrown by a Remoting server are serialized, sent to the client, and thrown locally on the client like any other exception.</span></span> <span data-ttu-id="def9e-211">Можно создать пользовательские исключения путем формирования подкласса типа «Исключения» и отметки его атрибутом [Serializable].</span><span class="sxs-lookup"><span data-stu-id="def9e-211">Custom exceptions can be created by sub-classing the Exception type and marking it with [Serializable].</span></span>   <span data-ttu-id="def9e-212">Большинство исключений платформы уже отмечены таким образом, что обеспечивает их создание сервером, сериализацию и повторное создание на клиенте.</span><span class="sxs-lookup"><span data-stu-id="def9e-212">Most framework exceptions are already marked in this way, allowing most to be thrown by the server, serialized, and re-thrown on the client.</span></span> <span data-ttu-id="def9e-213">Хотя такой подход удобно применять во время разработки, сведения, хранящиеся на стороне сервера, могут быть случайно раскрыты клиенту.</span><span class="sxs-lookup"><span data-stu-id="def9e-213">Though this design is convenient during development, server-side information can inadvertently be disclosed to the client.</span></span> <span data-ttu-id="def9e-214">Это одна из многих причин, по которым систему удаленного взаимодействия следует использовать только в средах с полным уровнем доверия.</span><span class="sxs-lookup"><span data-stu-id="def9e-214">This is one of many reasons Remoting should be used only in fully-trusted environments.</span></span>  
  
#### <a name="exceptions-and-faults-in-wcf"></a><span data-ttu-id="def9e-215">Исключения и сбои в WCF</span><span class="sxs-lookup"><span data-stu-id="def9e-215">Exceptions and Faults in WCF</span></span>  
 <span data-ttu-id="def9e-216">WCF не допускает возврата произвольных типов исключений с сервера на клиент, поскольку это может привести к непреднамеренному разглашению сведений.</span><span class="sxs-lookup"><span data-stu-id="def9e-216">WCF does not allow arbitrary exception types to be returned from the server to the client because it could lead to inadvertent information disclosure.</span></span> <span data-ttu-id="def9e-217">Если операция службы вызывает непредвиденное исключение, это приводит к созданию общего исключения FaultException на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="def9e-217">If a service operation throws an unexpected exception, it causes a general purpose FaultException to be thrown on the client.</span></span> <span data-ttu-id="def9e-218">Это исключение не несет никакой информации о том, почему или где возникла проблема, и для некоторых приложений этого достаточно.</span><span class="sxs-lookup"><span data-stu-id="def9e-218">This exception does not carry any information why or where the problem occurred, and for some applications this is sufficient.</span></span> <span data-ttu-id="def9e-219">Если приложениям требуется передача на клиент более полных сведений об ошибке, это осуществляется путем определения контракта сбоя.</span><span class="sxs-lookup"><span data-stu-id="def9e-219">Applications that need to communicate richer error information to the client do this by defining a fault contract.</span></span>  
  
 <span data-ttu-id="def9e-220">Для этого сначала создайте тип [DataContract], содержащий сведения о сбое.</span><span class="sxs-lookup"><span data-stu-id="def9e-220">To do this, first create a [DataContract] type to carry the fault information.</span></span>  
  
```csharp
[DataContract]  
public class CustomerServiceFault  
{  
    [DataMember]  
    public string ErrorMessage { get; set; }  
  
    [DataMember]  
    public int CustomerId {get;set;}  
}  
```  
  
 <span data-ttu-id="def9e-221">Укажите контракт сбоя для каждой операции службы.</span><span class="sxs-lookup"><span data-stu-id="def9e-221">Specify the fault contract to use for each service operation.</span></span>  
  
```csharp
[ServiceContract]  
public interface IWCFServer  
{  
    [OperationContract]  
    [FaultContract(typeof(CustomerServiceFault))]  
    Customer GetCustomer(int customerId);  
}  
```  
  
 <span data-ttu-id="def9e-222">Сервер сообщает о состоянии сбоя путем создания исключения FaultException.</span><span class="sxs-lookup"><span data-stu-id="def9e-222">The server reports error conditions by throwing a FaultException.</span></span>  
  
```csharp
throw new FaultException<CustomerServiceFault>(  
    new CustomerServiceFault() {
        CustomerId = customerId,
        ErrorMessage = "Illegal customer Id"
    });  
```  
  
 <span data-ttu-id="def9e-223">И каждый раз, когда клиент отправляет запрос на сервер, он может перехватить сбои как обычное исключение.</span><span class="sxs-lookup"><span data-stu-id="def9e-223">And whenever the client makes a request to the server, it can catch faults as normal exceptions.</span></span>  
  
```csharp
try  
{  
    Customer customer = server.GetCustomer(-1);  
}  
catch (FaultException<CustomerServiceFault> fault)  
{  
    Console.WriteLine($"Fault received: {fault.Detail.ErrorMessage}");
}  
```  
  
 <span data-ttu-id="def9e-224">Дополнительные сведения о контрактах сбоев см. в описании класса <xref:System.ServiceModel.FaultException>.</span><span class="sxs-lookup"><span data-stu-id="def9e-224">For more information about fault contracts, see <xref:System.ServiceModel.FaultException>.</span></span>  
  
### <a name="security-considerations"></a><span data-ttu-id="def9e-225">Соображения безопасности</span><span class="sxs-lookup"><span data-stu-id="def9e-225">Security Considerations</span></span>  
  
#### <a name="security-in-net-remoting"></a><span data-ttu-id="def9e-226">Безопасность в системе удаленного взаимодействия .NET</span><span class="sxs-lookup"><span data-stu-id="def9e-226">Security in .NET Remoting</span></span>  
 <span data-ttu-id="def9e-227">Некоторые каналы удаленного взаимодействия .NET поддерживают различные функции обеспечения безопасности, такие как проверка подлинности и шифрование на уровне канала (IPC и TCP).</span><span class="sxs-lookup"><span data-stu-id="def9e-227">Some .NET Remoting channels support security features such as authentication and encryption at the channel layer (IPC and TCP).</span></span> <span data-ttu-id="def9e-228">Для канала HTTP проверка подлинности и шифрование строятся на основе служб Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="def9e-228">The HTTP channel relies on Internet Information Services (IIS) for both authentication and encryption.</span></span> <span data-ttu-id="def9e-229">Несмотря на это, следует рассматривать систему удаленного взаимодействия .NET как небезопасный протокол связи, который следует использовать только в среде с полным уровнем доверия.</span><span class="sxs-lookup"><span data-stu-id="def9e-229">Despite this support, you should consider .NET Remoting an unsecure communication protocol and use it only within fully-trusted environments.</span></span> <span data-ttu-id="def9e-230">Никогда не предоставляйте доступ к открытой конечной точке удаленного взаимодействия интернет-клиентам или клиентам без должного уровня доверия.</span><span class="sxs-lookup"><span data-stu-id="def9e-230">Never expose a public Remoting endpoint to the Internet or untrusted clients.</span></span>  
  
#### <a name="security-in-wcf"></a><span data-ttu-id="def9e-231">Безопасность в WCF</span><span class="sxs-lookup"><span data-stu-id="def9e-231">Security in WCF</span></span>  
 <span data-ttu-id="def9e-232">Система WCF была разработана с учетом аспектов безопасности, в частности для устранения ряда уязвимостей, присущих среде удаленного взаимодействия .NET.</span><span class="sxs-lookup"><span data-stu-id="def9e-232">WCF was designed with security in mind, in part to address the kinds of vulnerabilities found in .NET Remoting.</span></span> <span data-ttu-id="def9e-233">WCF обеспечивает безопасность на уровне транспорта и сообщений и предоставляет множество функций для проверки подлинности, авторизации, шифрования и т. д.</span><span class="sxs-lookup"><span data-stu-id="def9e-233">WCF offers security at both the transport and message level, and offers many options for authentication, authorization, encryption, and so on.</span></span> <span data-ttu-id="def9e-234">Дополнительные сведения см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="def9e-234">For more information, see the following topics:</span></span>  
  
- [<span data-ttu-id="def9e-235">Безопасность</span><span class="sxs-lookup"><span data-stu-id="def9e-235">Security</span></span>](./feature-details/security.md)  
  
- [<span data-ttu-id="def9e-236">Руководство по безопасности WCF</span><span class="sxs-lookup"><span data-stu-id="def9e-236">WCF Security Guidance</span></span>](./feature-details/security-guidance-and-best-practices.md)  
  
## <a name="migrating-to-wcf"></a><span data-ttu-id="def9e-237">Миграция в WCF</span><span class="sxs-lookup"><span data-stu-id="def9e-237">Migrating to WCF</span></span>  
  
### <a name="why-migrate-from-remoting-to-wcf"></a><span data-ttu-id="def9e-238">Почему необходимо выполнить миграцию с переходом от удаленного взаимодействия на WCF?</span><span class="sxs-lookup"><span data-stu-id="def9e-238">Why Migrate from Remoting to WCF?</span></span>  
  
- <span data-ttu-id="def9e-239">**Удаленное взаимодействие .NET — это устаревший продукт.**</span><span class="sxs-lookup"><span data-stu-id="def9e-239">**.NET Remoting is a legacy product.**</span></span> <span data-ttu-id="def9e-240">Как описано в разделе [удаленное взаимодействие .NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507%28v=vs.100%29), оно считается устаревшим продуктом и не рекомендуется для новых разработчиков.</span><span class="sxs-lookup"><span data-stu-id="def9e-240">As described in [.NET Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507%28v=vs.100%29), it is considered a legacy product and is not recommended for new development.</span></span> <span data-ttu-id="def9e-241">Для новых и существующих приложений рекомендуется использовать платформу WCF или веб-интерфейс API ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="def9e-241">WCF or ASP.NET Web API are recommended for new and existing applications.</span></span>  
  
- <span data-ttu-id="def9e-242">**WCF использует кроссплатформенные стандарты.**</span><span class="sxs-lookup"><span data-stu-id="def9e-242">**WCF uses cross-platform standards.**</span></span> <span data-ttu-id="def9e-243">Решение WCF было разработано с учетом кроссплатформенного взаимодействия и поддерживает различные отраслевые стандарты (SOAP, WS-Security, WS-Trust, и т. д.).</span><span class="sxs-lookup"><span data-stu-id="def9e-243">WCF was designed with cross-platform interoperability in mind and supports many industry standards (SOAP, WS-Security, WS-Trust, etc.).</span></span> <span data-ttu-id="def9e-244">Служба WCF может взаимодействовать с клиентами, работающими под управлением других операционных систем, отличных от Windows.</span><span class="sxs-lookup"><span data-stu-id="def9e-244">A WCF service can interoperate with clients running on operating systems other than Windows.</span></span> <span data-ttu-id="def9e-245">Удаленное взаимодействие разрабатывалось главным образом для сред, в которых серверные и клиентские приложения работают с использованием .NET Framework в операционной системе Windows.</span><span class="sxs-lookup"><span data-stu-id="def9e-245">Remoting was designed primarily for environments where both the server and client applications run using .NET Framework on a Windows operating system.</span></span>
  
- <span data-ttu-id="def9e-246">**WCF включает встроенные функции обеспечения безопасности.**</span><span class="sxs-lookup"><span data-stu-id="def9e-246">**WCF has built-in security.**</span></span> <span data-ttu-id="def9e-247">WCF разрабатывалась с учетом соображений безопасности и предлагает множество вариантов для проверки подлинности, безопасности на уровне транспорта, безопасности на уровне сообщений и т. д. Удаленное взаимодействие было предназначено для упрощения взаимодействия приложений, но не предназначено для обеспечения безопасности в средах, не являющихся доверенными.</span><span class="sxs-lookup"><span data-stu-id="def9e-247">WCF was designed with security in mind and offers many options for authentication, transport level security, message level security, etc. Remoting was designed to make it easy for applications to interoperate but was not designed to be secure in non-trusted environments.</span></span> <span data-ttu-id="def9e-248">Решение WCF было разработано для работы как в доверенных, так и в недоверенных средах.</span><span class="sxs-lookup"><span data-stu-id="def9e-248">WCF was designed to work in both trusted and non-trusted environments.</span></span>  
  
### <a name="migration-recommendations"></a><span data-ttu-id="def9e-249">Рекомендации по миграции</span><span class="sxs-lookup"><span data-stu-id="def9e-249">Migration Recommendations</span></span>  
 <span data-ttu-id="def9e-250">Ниже приведены рекомендуемые действия по миграции от удаленного взаимодействия .NET к WCF.</span><span class="sxs-lookup"><span data-stu-id="def9e-250">The following are the recommended steps to migrate from .NET Remoting to WCF:</span></span>  
  
- <span data-ttu-id="def9e-251">**Создайте контракт службы.**</span><span class="sxs-lookup"><span data-stu-id="def9e-251">**Create the service contract.**</span></span> <span data-ttu-id="def9e-252">Определите типы интерфейсов службы и отметьте их атрибутом [ServiceContract]. Отметьте все методы, доступные для вызова клиентами, атрибутом [OperationContract].</span><span class="sxs-lookup"><span data-stu-id="def9e-252">Define your service interface types, and mark them with the [ServiceContract] attribute.Mark all the methods the clients will be allowed to call with [OperationContract].</span></span>  
  
- <span data-ttu-id="def9e-253">**Создайте контракт данных.**</span><span class="sxs-lookup"><span data-stu-id="def9e-253">**Create the data contract.**</span></span> <span data-ttu-id="def9e-254">Определите типы данных, которыми будут обмениваться сервер и клиент, и отметьте их атрибутом [DataContract].</span><span class="sxs-lookup"><span data-stu-id="def9e-254">Define the data types that will be exchanged between server and client, and mark them with the [DataContract] attribute.</span></span> <span data-ttu-id="def9e-255">Отметьте все поля и свойства, доступные для использования клиентом, атрибутом [DataMember].</span><span class="sxs-lookup"><span data-stu-id="def9e-255">Mark all the fields and properties the client will be allowed to use with [DataMember].</span></span>  
  
- <span data-ttu-id="def9e-256">**Создайте контракт ошибок (необязательно).**</span><span class="sxs-lookup"><span data-stu-id="def9e-256">**Create the fault contract (optional).**</span></span> <span data-ttu-id="def9e-257">Создайте типы, которыми будут обмениваться сервер и клиент при возникновении ошибок.</span><span class="sxs-lookup"><span data-stu-id="def9e-257">Create the types that will be exchanged between server and client when errors are encountered.</span></span> <span data-ttu-id="def9e-258">Отметьте эти типы атрибутами [DataContract] и [DataMember], чтобы обеспечить возможность их сериализации.</span><span class="sxs-lookup"><span data-stu-id="def9e-258">Mark these types with [DataContract] and [DataMember] to make them serializable.</span></span> <span data-ttu-id="def9e-259">Для всех операций службы, отмеченных атрибутом [OperationContract], также задайте атрибут [FaultContract], чтобы указать, какие ошибки они могут возвращать.</span><span class="sxs-lookup"><span data-stu-id="def9e-259">For all service operations you marked with [OperationContract], also mark them with [FaultContract] to indicate which errors they may return.</span></span>  
  
- <span data-ttu-id="def9e-260">**Настройте и разместите службу.**</span><span class="sxs-lookup"><span data-stu-id="def9e-260">**Configure and host the service.**</span></span> <span data-ttu-id="def9e-261">После создания контракта службы необходимо настроить привязку для предоставления службы в конечной точке.</span><span class="sxs-lookup"><span data-stu-id="def9e-261">Once the service contract has been created, the next step is to configure a binding to expose the service at an endpoint.</span></span> <span data-ttu-id="def9e-262">Дополнительные сведения см. в разделе [конечные точки: адреса, привязки и контракты](./feature-details/endpoints-addresses-bindings-and-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="def9e-262">For more information, see [Endpoints: Addresses, Bindings, and Contracts](./feature-details/endpoints-addresses-bindings-and-contracts.md).</span></span>  
  
 <span data-ttu-id="def9e-263">После переноса приложения удаленного взаимодействия на платформу WCF необходимо удалить зависимости от решения удаленного взаимодействия .NET.</span><span class="sxs-lookup"><span data-stu-id="def9e-263">Once a Remoting application has been migrated to WCF, it is still important to remove dependencies on .NET Remoting.</span></span> <span data-ttu-id="def9e-264">Это позволит удалить какие-либо уязвимости удаленного взаимодействия из приложения.</span><span class="sxs-lookup"><span data-stu-id="def9e-264">This ensures that any Remoting vulnerabilities are removed from the application.</span></span> <span data-ttu-id="def9e-265">Вот эти шаги.</span><span class="sxs-lookup"><span data-stu-id="def9e-265">These steps include the following:</span></span>  
  
- <span data-ttu-id="def9e-266">**Прекратите использование MarshalByRefObject.**</span><span class="sxs-lookup"><span data-stu-id="def9e-266">**Discontinue use of MarshalByRefObject.**</span></span> <span data-ttu-id="def9e-267">Тип MarshalByRefObject существует только для решения удаленного взаимодействия и не используется в WCF.</span><span class="sxs-lookup"><span data-stu-id="def9e-267">The MarshalByRefObject type exists only for Remoting and is not used by WCF.</span></span> <span data-ttu-id="def9e-268">Все типы приложений с вложенным классом MarshalByRefObject должны быть удалены или изменены.</span><span class="sxs-lookup"><span data-stu-id="def9e-268">Any application types that sub-class MarshalByRefObject should be removed or changed.</span></span>  
  
- <span data-ttu-id="def9e-269">**Прекратите использование [Serializable] и ISerializable.**</span><span class="sxs-lookup"><span data-stu-id="def9e-269">**Discontinue use of [Serializable] and ISerializable.**</span></span> <span data-ttu-id="def9e-270">Атрибут [Serializable] и интерфейс ISerializable изначально были разработаны для сериализации типов в доверенных средах, и они используются при удаленном взаимодействии.</span><span class="sxs-lookup"><span data-stu-id="def9e-270">The [Serializable] attribute and ISerializable interface were originally designed to serialize types within trusted environments, and they are used by Remoting.</span></span> <span data-ttu-id="def9e-271">При сериализации WCF используются типы с атрибутом [DataContract] и [DataMember].</span><span class="sxs-lookup"><span data-stu-id="def9e-271">WCF serialization relies on types being marked with [DataContract] and [DataMember].</span></span> <span data-ttu-id="def9e-272">Типы данных, используемых приложением, следует изменить таким образом, чтобы использовать [DataContract] и отказаться от использования ISerializable или [Serializable].</span><span class="sxs-lookup"><span data-stu-id="def9e-272">Data types used by an application should be modified to use [DataContract] and not to use ISerializable or [Serializable].</span></span>  
  
### <a name="migration-scenarios"></a><span data-ttu-id="def9e-273">Сценарии миграции</span><span class="sxs-lookup"><span data-stu-id="def9e-273">Migration Scenarios</span></span>  
 <span data-ttu-id="def9e-274">Теперь давайте рассмотрим выполнение следующих распространенных сценариев удаленного взаимодействия в WCF.</span><span class="sxs-lookup"><span data-stu-id="def9e-274">Now let’s see how to accomplish the following common Remoting scenarios in WCF:</span></span>  
  
1. <span data-ttu-id="def9e-275">Сервер возвращает клиенту объект по значению.</span><span class="sxs-lookup"><span data-stu-id="def9e-275">Server returns an object by-value to the client</span></span>  
  
2. <span data-ttu-id="def9e-276">Сервер возвращает клиенту объект по ссылке.</span><span class="sxs-lookup"><span data-stu-id="def9e-276">Server returns an object by-reference to the client</span></span>  
  
3. <span data-ttu-id="def9e-277">Клиент отправляет серверу объект по значению.</span><span class="sxs-lookup"><span data-stu-id="def9e-277">Client sends an object by-value to the server</span></span>  
  
> [!NOTE]
> <span data-ttu-id="def9e-278">В среде WCF отправка клиентом серверу объекта по ссылке не разрешена.</span><span class="sxs-lookup"><span data-stu-id="def9e-278">Sending an object by-reference from the client to the server is not allowed in WCF.</span></span>  
  
 <span data-ttu-id="def9e-279">При просмотре сценариев предполагается, что базовые интерфейсы для удаленного взаимодействия .NET выглядят так, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="def9e-279">When reading through these scenarios, assume our baseline interfaces for .NET Remoting look like the following example.</span></span> <span data-ttu-id="def9e-280">Реализация удаленного взаимодействия .NET в данном случае не имеет значения, поскольку мы хотим показать только способы использования WCF для реализации аналогичных функциональных возможностей.</span><span class="sxs-lookup"><span data-stu-id="def9e-280">The .NET Remoting implementation is not important here because we want to illustrate only how to use WCF to implement equivalent functionality.</span></span>  
  
```csharp
public class RemotingServer : MarshalByRefObject  
{  
    // Demonstrates server returning object by-value  
    public Customer GetCustomer(int customerId) {…}  
  
    // Demonstrates server returning object by-reference  
    public CustomerReference GetCustomerReference(int customerId) {…}  
  
    // Demonstrates client passing object to server by-value  
    public bool UpdateCustomer(Customer customer) {…}  
}  
```  
  
#### <a name="scenario-1-service-returns-an-object-by-value"></a><span data-ttu-id="def9e-281">Сценарий 1. Служба возвращает объект по значению</span><span class="sxs-lookup"><span data-stu-id="def9e-281">Scenario 1: Service Returns an Object by Value</span></span>  
 <span data-ttu-id="def9e-282">В этом сценарии показана ситуация, когда сервер возвращает объект клиенту по ссылке.</span><span class="sxs-lookup"><span data-stu-id="def9e-282">This scenario demonstrates a server returning an object to the client by value.</span></span> <span data-ttu-id="def9e-283">WCF всегда возвращает объекты с сервера по значению, поэтому ниже просто приведено описание создания стандартной службы WCF.</span><span class="sxs-lookup"><span data-stu-id="def9e-283">WCF always returns objects from the server by value, so the following steps simply describe how to build a normal WCF service.</span></span>  
  
1. <span data-ttu-id="def9e-284">Сначала определите открытый интерфейс для службы WCF и пометьте его атрибутом [ServiceContract].</span><span class="sxs-lookup"><span data-stu-id="def9e-284">Start by defining a public interface for the WCF service and mark it with the [ServiceContract] attribute.</span></span> <span data-ttu-id="def9e-285">Мы используем [OperationContract] для определения методов на стороне сервера, которые будет вызывать клиент.</span><span class="sxs-lookup"><span data-stu-id="def9e-285">We use [OperationContract] to identify the server-side methods our client will call.</span></span>  
  
   ```csharp
   [ServiceContract]  
   public interface ICustomerService  
   {  
       [OperationContract]  
       Customer GetCustomer(int customerId);  
  
       [OperationContract]  
       bool UpdateCustomer(Customer customer);  
   }  
   ```  
  
2. <span data-ttu-id="def9e-286">Следующим шагом является создание контракта данных для этой службы.</span><span class="sxs-lookup"><span data-stu-id="def9e-286">The next step is to create the data contract for this service.</span></span> <span data-ttu-id="def9e-287">Это осуществляется путем создания классов (а не интерфейсов), отмеченных атрибутом [DataContract].</span><span class="sxs-lookup"><span data-stu-id="def9e-287">We do this by creating classes (not interfaces) marked with the [DataContract] attribute.</span></span> <span data-ttu-id="def9e-288">Отдельные свойства или поля, которые должны быть видны и для клиента, и для сервера, отмечаются атрибутом [DataMember].</span><span class="sxs-lookup"><span data-stu-id="def9e-288">The individual properties or fields we want visible to both client and server are marked with [DataMember].</span></span> <span data-ttu-id="def9e-289">Если следует разрешить производные типы, необходимо использовать атрибут [KnownType] для их идентификации.</span><span class="sxs-lookup"><span data-stu-id="def9e-289">If we want derived types to be allowed, we must use the [KnownType] attribute to identify them.</span></span> <span data-ttu-id="def9e-290">Единственными типами, сериализацию или десериализацию которых для этой службы разрешает WCF, являются типы в интерфейсе службы и эти «известные типы».</span><span class="sxs-lookup"><span data-stu-id="def9e-290">The only types WCF will allow to be serialized or deserialized for this service are those in the service interface and these "known types".</span></span> <span data-ttu-id="def9e-291">Попытки обмена любыми другими типами, не указанными в списке, будут отклонены.</span><span class="sxs-lookup"><span data-stu-id="def9e-291">Attempting to exchange any other type not in this list will be rejected.</span></span>  
  
   ```csharp
   [DataContract]  
   [KnownType(typeof(PremiumCustomer))]  
   public class Customer  
   {  
       [DataMember]  
       public string FirstName { get; set; }  
  
       [DataMember]  
       public string LastName { get; set; }  
  
       [DataMember]  
       public int CustomerId { get; set; }  
   }  
  
   [DataContract]  
   public class PremiumCustomer : Customer
   {  
       [DataMember]  
       public int AccountId { get; set; }  
   }  
   ```  
  
3. <span data-ttu-id="def9e-292">Далее представлена реализация интерфейса службы.</span><span class="sxs-lookup"><span data-stu-id="def9e-292">Next, we provide the implementation for the service interface.</span></span>  
  
   ```csharp  
   public class CustomerService : ICustomerService  
   {  
       public Customer GetCustomer(int customerId)  
       {  
           // read from database  
       }  
  
       public bool UpdateCustomer(Customer customer)  
       {  
           // write to database  
       }  
   }  
   ```  
  
4. <span data-ttu-id="def9e-293">Для запуска службы WCF необходимо объявить конечную точку, предоставляющую доступ к интерфейсу службы по определенному URL-адресу с помощью определенной привязки WCF.</span><span class="sxs-lookup"><span data-stu-id="def9e-293">To run the WCF service, we need to declare an endpoint that exposes that service interface at a specific URL using a specific WCF binding.</span></span> <span data-ttu-id="def9e-294">Как правило, это осуществляется путем добавления в файл web.config серверного проекта следующих разделов.</span><span class="sxs-lookup"><span data-stu-id="def9e-294">This is typically done by adding the following sections to the server project’s web.config file.</span></span>  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <services>  
          <service name="Server.CustomerService">  
            <endpoint address="http://localhost:8083/CustomerService"  
                      binding="basicHttpBinding"  
                      contract="Shared.ICustomerService" />  
          </service>  
        </services>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
5. <span data-ttu-id="def9e-295">После этого можно запустить службу WCF с помощью следующего кода:</span><span class="sxs-lookup"><span data-stu-id="def9e-295">The WCF service can then be started with the following code:</span></span>  
  
   ```csharp
   ServiceHost customerServiceHost = new ServiceHost(typeof(CustomerService));  
       customerServiceHost.Open();  
   ```  
  
     <span data-ttu-id="def9e-296">При запуске метод ServiceHost использует файл web.config для установления надлежащего контракта, привязки и конечной точки.</span><span class="sxs-lookup"><span data-stu-id="def9e-296">When this ServiceHost is started, it uses the web.config file to establish the proper contract, binding and endpoint.</span></span> <span data-ttu-id="def9e-297">Дополнительные сведения о файлах конфигурации см. в разделе [Настройка служб с помощью файлов конфигурации](./configuring-services-using-configuration-files.md).</span><span class="sxs-lookup"><span data-stu-id="def9e-297">For more information about configuration files, see [Configuring Services Using Configuration Files](./configuring-services-using-configuration-files.md).</span></span> <span data-ttu-id="def9e-298">Этот метод запуска сервера называется резидентным размещением.</span><span class="sxs-lookup"><span data-stu-id="def9e-298">This style of starting the server is known as self-hosting.</span></span> <span data-ttu-id="def9e-299">Дополнительные сведения о других вариантах размещения служб WCF см. в разделе [службы хостинга](./hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="def9e-299">To learn more about other choices for hosting WCF services, see [Hosting Services](./hosting-services.md).</span></span>  
  
6. <span data-ttu-id="def9e-300">В файле app.config клиентского проекта должны быть объявлены соответствующие сведения о привязке для конечной точки службы.</span><span class="sxs-lookup"><span data-stu-id="def9e-300">The client project’s app.config must declare matching binding information for the service’s endpoint.</span></span> <span data-ttu-id="def9e-301">Самый простой способ сделать это в Visual Studio — использовать **Добавление ссылки на службу**, который автоматически обновит файл app.config.</span><span class="sxs-lookup"><span data-stu-id="def9e-301">The easiest way to do this in Visual Studio is to use **Add Service Reference**, which will automatically update the app.config file.</span></span> <span data-ttu-id="def9e-302">Эти же изменения также можно добавить вручную.</span><span class="sxs-lookup"><span data-stu-id="def9e-302">Alternatively, these same changes can be added manually.</span></span>  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <client>  
          <endpoint name="customerservice"  
                    address="http://localhost:8083/CustomerService"  
                    binding="basicHttpBinding"  
                    contract="Shared.ICustomerService"/>  
        </client>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
     <span data-ttu-id="def9e-303">Дополнительные сведения об использовании **Добавление ссылки на службу**см. [в разделе как добавить, обновить или удалить ссылку на службу](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference).</span><span class="sxs-lookup"><span data-stu-id="def9e-303">For more information about using **Add Service Reference**, see [How to: Add, Update, or Remove a Service Reference](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference).</span></span>  
  
7. <span data-ttu-id="def9e-304">Теперь мы можем вызвать службу WCF из клиента.</span><span class="sxs-lookup"><span data-stu-id="def9e-304">Now we can call the WCF service from the client.</span></span> <span data-ttu-id="def9e-305">Для этого мы создаем фабрику каналов для этой службы, запрашиваем канал и напрямую вызываем требуемый метод по этому каналу.</span><span class="sxs-lookup"><span data-stu-id="def9e-305">We do this by creating a channel factory for that service, asking it for a channel, and directly calling the method we want on that channel.</span></span> <span data-ttu-id="def9e-306">Это возможно благодаря тому, что канал реализует интерфейс службы и обрабатывает базовую логику запроса/ответа.</span><span class="sxs-lookup"><span data-stu-id="def9e-306">We can do this because the channel implements the service’s interface and handles the underlying request/reply logic for us.</span></span> <span data-ttu-id="def9e-307">Возвращаемым значением при выполнении данного вызова метода является десериализованная копия ответа сервера.</span><span class="sxs-lookup"><span data-stu-id="def9e-307">The return value from that method call is the deserialized copy of the server’s response.</span></span>  
  
   ```csharp
   ChannelFactory<ICustomerService> factory =  
       new ChannelFactory<ICustomerService>("customerservice");  
   ICustomerService service = factory.CreateChannel();  
   Customer customer = service.GetCustomer(42);  
   Console.WriteLine($"  Customer {customer.FirstName} {customer.LastName} received.");
   ```  
  
 <span data-ttu-id="def9e-308">Объекты, возвращаемые WCF с сервера на клиент, всегда передаются по значению.</span><span class="sxs-lookup"><span data-stu-id="def9e-308">Objects returned by WCF from the server to the client are always by value.</span></span> <span data-ttu-id="def9e-309">Объекты представляют собой десериализованные копии данных, отправленных сервером.</span><span class="sxs-lookup"><span data-stu-id="def9e-309">The objects are deserialized copies of the data sent by the server.</span></span> <span data-ttu-id="def9e-310">Клиент может вызывать методы в этих локальных копиях без опасности вызова серверного кода в ходе обратных вызовов.</span><span class="sxs-lookup"><span data-stu-id="def9e-310">The client can call methods on these local copies without any danger of invoking server code through callbacks.</span></span>  
  
#### <a name="scenario-2-server-returns-an-object-by-reference"></a><span data-ttu-id="def9e-311">Сценарий 2. Служба возвращает объект по ссылке</span><span class="sxs-lookup"><span data-stu-id="def9e-311">Scenario 2: Server Returns an Object By Reference</span></span>  
 <span data-ttu-id="def9e-312">В этом сценарии показана ситуация, когда сервер предоставляет объект клиенту по ссылке.</span><span class="sxs-lookup"><span data-stu-id="def9e-312">This scenario demonstrates the server providing an object to the client by reference.</span></span> <span data-ttu-id="def9e-313">В удаленном взаимодействии .NET эта операция обрабатывается автоматически для любого типа, производного от MarshalByRefObject, который сериализуется по ссылке.</span><span class="sxs-lookup"><span data-stu-id="def9e-313">In .NET Remoting, this is handled automatically for any type derived from MarshalByRefObject, which is serialized by-reference.</span></span> <span data-ttu-id="def9e-314">Примером такого сценария является разрешение нескольким клиентам иметь независимые объекты, связанные с сеансами, на стороне сервера.</span><span class="sxs-lookup"><span data-stu-id="def9e-314">An example of this scenario is allowing multiple clients to have independent sessionful server-side objects.</span></span> <span data-ttu-id="def9e-315">Как упоминалось ранее, объекты, возвращаемые службой WCF, всегда передаются по значению, поэтому прямой эквивалент объектов, передаваемых по ссылке, отсутствует, но существует возможность реализации метода, сходного с семантикой возвращения по ссылке, с использованием объекта <xref:System.ServiceModel.EndpointAddress10>.</span><span class="sxs-lookup"><span data-stu-id="def9e-315">As previously mentioned, objects returned by a WCF service are always by value, so there is no direct equivalent of a by-reference object, but it is possible to achieve something similar to by-reference semantics using an <xref:System.ServiceModel.EndpointAddress10> object.</span></span> <span data-ttu-id="def9e-316">Это сериализуемый объект, передаваемый по значению, с помощью которого клиент может получить на сервере объект, переданный по ссылке в рамках сеанса.</span><span class="sxs-lookup"><span data-stu-id="def9e-316">This is a serializable by-value object that can be used by the client to obtain a sessionful by-reference object on the server.</span></span> <span data-ttu-id="def9e-317">Это обеспечивает возможность реализации сценария, при котором различные клиенты обладают независимыми объектами, связанными с сеансами, на стороне сервера.</span><span class="sxs-lookup"><span data-stu-id="def9e-317">This enables the scenario of having multiple clients with independent sessionful server-side objects.</span></span>  
  
1. <span data-ttu-id="def9e-318">Сначала необходимо определить контракт службы WCF, соответствующий самому объекту, связанному с сеансами.</span><span class="sxs-lookup"><span data-stu-id="def9e-318">First, we need to define a WCF service contract that corresponds to the sessionful object itself.</span></span>  
  
   ```csharp
   [ServiceContract(SessionMode = SessionMode.Allowed)]  
       public interface ISessionBoundObject  
       {  
           [OperationContract]  
           string GetCurrentValue();  
  
           [OperationContract]  
           void SetCurrentValue(string value);  
       }  
   ```  
  
    > [!TIP]
    > <span data-ttu-id="def9e-319">Обратите внимание, что объект, связанный с сеансами, отмечен атрибутом [ServiceContract], что делает его обычным интерфейсом службы WCF.</span><span class="sxs-lookup"><span data-stu-id="def9e-319">Notice that the sessionful object is marked with [ServiceContract], making it a normal WCF service interface.</span></span> <span data-ttu-id="def9e-320">Настройка свойства SessionMode указывает на связь службы с сеансом.</span><span class="sxs-lookup"><span data-stu-id="def9e-320">Setting the SessionMode property indicates it will be a sessionful service.</span></span> <span data-ttu-id="def9e-321">В WCF сеанс — это способ согласования нескольких сообщений, пересылаемых между двумя конечными точками.</span><span class="sxs-lookup"><span data-stu-id="def9e-321">In WCF, a session is a way of correlating multiple messages sent between two endpoints.</span></span> <span data-ttu-id="def9e-322">Это означает, что, как только клиент устанавливает подключение к службе, между ним и сервером создается сеанс.</span><span class="sxs-lookup"><span data-stu-id="def9e-322">This means that once a client obtains a connection to this service, a session will be established between the client and the server.</span></span> <span data-ttu-id="def9e-323">Клиент использует единственный уникальный экземпляр объекта на стороне сервера для любых взаимодействий в рамках данного сеанса.</span><span class="sxs-lookup"><span data-stu-id="def9e-323">The client will use a single unique instance of the server-side object for all its interactions within this single session.</span></span>  
  
2. <span data-ttu-id="def9e-324">Далее необходимо представить реализацию этого интерфейса службы.</span><span class="sxs-lookup"><span data-stu-id="def9e-324">Next, we need to provide the implementation of this service interface.</span></span> <span data-ttu-id="def9e-325">Обозначение его при помощи атрибута [ServiceBehavior] и настройка InstanceContextMode позволяет сообщить WCF, что мы хотим использовать уникальный экземпляр этого типа для каждого сеанса.</span><span class="sxs-lookup"><span data-stu-id="def9e-325">By denoting it with [ServiceBehavior] and setting the InstanceContextMode, we tell WCF we want to use a unique instance of this type for an each session.</span></span>  
  
   ```csharp
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.PerSession)]  
       public class MySessionBoundObject : ISessionBoundObject  
       {  
           private string _value;  
  
           public string GetCurrentValue()  
           {  
               return _value;  
           }  
  
           public void SetCurrentValue(string val)  
           {  
               _value = val;  
           }  
  
       }  
   ```  
  
3. <span data-ttu-id="def9e-326">Теперь нам требуется способ получения экземпляра этого объекта, связанного с сеансом.</span><span class="sxs-lookup"><span data-stu-id="def9e-326">Now we need a way to obtain an instance of this sessionful object.</span></span> <span data-ttu-id="def9e-327">Для этого необходимо создать другой интерфейс службы WCF, который возвращает объект EndpointAddress10.</span><span class="sxs-lookup"><span data-stu-id="def9e-327">We do this by creating another WCF service interface that returns an EndpointAddress10 object.</span></span> <span data-ttu-id="def9e-328">Это сериализуемая форма конечной точки, с помощью которой клиент может создать объект сеанса.</span><span class="sxs-lookup"><span data-stu-id="def9e-328">This is a serializable form of an endpoint that the client can use to create the sessionful object.</span></span>  
  
   ```csharp
   [ServiceContract]  
       public interface ISessionBoundFactory  
       {  
           [OperationContract]  
           EndpointAddress10 GetInstanceAddress();  
       }  
   ```  
  
     <span data-ttu-id="def9e-329">И мы реализуем эту службу WCF:</span><span class="sxs-lookup"><span data-stu-id="def9e-329">And we implement this WCF service:</span></span>  
  
   ```csharp
   public class SessionBoundFactory : ISessionBoundFactory  
       {  
           public static ChannelFactory<ISessionBoundObject> _factory =
               new ChannelFactory<ISessionBoundObject>("sessionbound");  

           public SessionBoundFactory()  
           {  
           }  
  
           public EndpointAddress10 GetInstanceAddress()  
           {  
               IClientChannel channel = (IClientChannel)_factory.CreateChannel();  
               return EndpointAddress10.FromEndpointAddress(channel.RemoteAddress);  
           }  
       }  
   ```  
  
     <span data-ttu-id="def9e-330">Эта реализация поддерживает единственную фабрику каналов для создания объектов, связанных с сеансами.</span><span class="sxs-lookup"><span data-stu-id="def9e-330">This implementation maintains a singleton channel factory to create sessionful objects.</span></span> <span data-ttu-id="def9e-331">При вызове метода GetInstanceAddress() создается канал и объект EndpointAddress10, указывающий на удаленный адрес, связанный с этим каналом.</span><span class="sxs-lookup"><span data-stu-id="def9e-331">When GetInstanceAddress() is called, it creates a channel and creates an EndpointAddress10 object that effectively points to the remote address associated with this channel.</span></span> <span data-ttu-id="def9e-332">EndpointAddress10 — это просто тип данных, который можно вернуть клиенту по значению.</span><span class="sxs-lookup"><span data-stu-id="def9e-332">EndpointAddress10 is simply a data type that can be returned to the client by-value.</span></span>  
  
4. <span data-ttu-id="def9e-333">Нам нужно изменить файл конфигурации сервера, выполнив два действия, представленные в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="def9e-333">We need to modify the server’s configuration file by doing the following two things as shown in the example below:</span></span>  
  
    1. <span data-ttu-id="def9e-334">Объявите \<client> раздел, описывающий конечную точку для объекта сеанса.</span><span class="sxs-lookup"><span data-stu-id="def9e-334">Declare a \<client> section that describes the endpoint for the sessionful object.</span></span> <span data-ttu-id="def9e-335">Это необходимо, поскольку сервер также выступает в качестве клиента в данной ситуации.</span><span class="sxs-lookup"><span data-stu-id="def9e-335">This is necessary because the server also acts as a client in this situation.</span></span>  
  
    2. <span data-ttu-id="def9e-336">Объявите конечные точки для фабрики и объекта, связанного с сеансом.</span><span class="sxs-lookup"><span data-stu-id="def9e-336">Declare endpoints for the factory and sessionful object.</span></span> <span data-ttu-id="def9e-337">Это необходимо, чтобы клиент мог взаимодействовать с конечными точками службы для получения EndpointAddress10 и создания канала сеанса.</span><span class="sxs-lookup"><span data-stu-id="def9e-337">This is necessary to allow the client to communicate with the service endpoints to acquire the EndpointAddress10 and to create the sessionful channel.</span></span>  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
         <client>  
          <endpoint name="sessionbound"  
                    address="net.tcp://localhost:8081/SessionBoundObject"  
                    binding="netTcpBinding"  
                    contract="Shared.ISessionBoundObject"/>  
        </client>  
        <services>  
          <service name="Server.CustomerService">  
            <endpoint address="http://localhost:8083/CustomerService"  
                      binding="basicHttpBinding"  
                      contract="Shared.ICustomerService" />  
          </service>  
          <service name="Server.MySessionBoundObject">  
            <endpoint address="net.tcp://localhost:8081/SessionBoundObject"  
                      binding="netTcpBinding"  
                      contract="Shared.ISessionBoundObject" />  
          </service>  
          <service name="Server.SessionBoundFactory">  
            <endpoint address="net.tcp://localhost:8081/SessionBoundFactory"  
                      binding="netTcpBinding"  
                      contract="Shared.ISessionBoundFactory" />  
          </service>  
        </services>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
     <span data-ttu-id="def9e-338">И затем мы можем запустить эти службы:</span><span class="sxs-lookup"><span data-stu-id="def9e-338">And then we can start these services:</span></span>  
  
   ```csharp
   ServiceHost factoryHost = new ServiceHost(typeof(SessionBoundFactory));  
   factoryHost.Open();  
  
   ServiceHost sessionHost = new ServiceHost(typeof(MySessionBoundObject));  
   sessionHost.Open();  
   ```  
  
5. <span data-ttu-id="def9e-339">Мы настраиваем клиент путем объявления тех же конечных точек в файле app.config проекта.</span><span class="sxs-lookup"><span data-stu-id="def9e-339">We configure the client by declaring these same endpoints in its project’s app.config file.</span></span>  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <client>  
          <endpoint name="customerservice"  
                    address="http://localhost:8083/CustomerService"  
                    binding="basicHttpBinding"  
                    contract="Shared.ICustomerService"/>  
          <endpoint name="sessionbound"  
                    address="net.tcp://localhost:8081/SessionBoundObject"  
                    binding="netTcpBinding"  
                    contract="Shared.ISessionBoundObject"/>  
          <endpoint name="factory"  
                    address="net.tcp://localhost:8081/SessionBoundFactory"  
                    binding="netTcpBinding"  
                    contract="Shared.ISessionBoundFactory"/>  
        </client>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
6. <span data-ttu-id="def9e-340">Чтобы создать и использовать этот объект, связанный с сеансом, клиент должен выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="def9e-340">In order to create and use this sessionful object, the client must do the following steps:</span></span>  
  
    1. <span data-ttu-id="def9e-341">Создать канал для службы ISessionBoundFactory.</span><span class="sxs-lookup"><span data-stu-id="def9e-341">Create a channel to the ISessionBoundFactory service.</span></span>  
  
    2. <span data-ttu-id="def9e-342">Использовать этот канал для вызова данной службы в целях получения EndpointAddress10.</span><span class="sxs-lookup"><span data-stu-id="def9e-342">Use that channel to invoke that service to obtain an EndpointAddress10.</span></span>  
  
    3. <span data-ttu-id="def9e-343">Использовать EndpointAddress10 для создания канала в целях получения объекта, связанного с сеансом.</span><span class="sxs-lookup"><span data-stu-id="def9e-343">Use the EndpointAddress10 to create a channel to obtain a sessionful object.</span></span>  
  
    4. <span data-ttu-id="def9e-344">Взаимодействовать с объектом, связанным с сеансом, чтобы продемонстрировать сохранение одного и того же экземпляра при нескольких вызовах.</span><span class="sxs-lookup"><span data-stu-id="def9e-344">Interact with the sessionful object to demonstrate it remains the same instance across multiple calls.</span></span>  
  
   ```csharp
   ChannelFactory<ISessionBoundFactory> channelFactory =
       new ChannelFactory<ISessionBoundFactory>("factory");  
   ISessionBoundFactory sessionFactory = channelFactory.CreateChannel();  
  
   EndpointAddress10 address1 = sessionFactory.GetInstanceAddress();  
   EndpointAddress10 address2 = sessionFactory.GetInstanceAddress();  
  
   ChannelFactory<ISessionBoundObject> sessionObjectFactory1 =
       new ChannelFactory<ISessionBoundObject>(new NetTcpBinding(),
                                               address1.ToEndpointAddress());  
   ChannelFactory<ISessionBoundObject> sessionObjectFactory2 =
       new ChannelFactory<ISessionBoundObject>(new NetTcpBinding(),
                                               address2.ToEndpointAddress());  
  
   ISessionBoundObject sessionInstance1 = sessionObjectFactory1.CreateChannel();  
   ISessionBoundObject sessionInstance2 = sessionObjectFactory2.CreateChannel();  
  
   sessionInstance1.SetCurrentValue("Hello");  
   sessionInstance2.SetCurrentValue("World");  
  
   if (sessionInstance1.GetCurrentValue() == "Hello" &&  
       sessionInstance2.GetCurrentValue() == "World")  
   {  
       Console.WriteLine("sessionful server object works as expected");  
   }  
   ```  
  
 <span data-ttu-id="def9e-345">WCF всегда возвращает объекты по значению, но существует возможность поддержки аналога семантики возвращения по ссылке посредством EndpointAddress10.</span><span class="sxs-lookup"><span data-stu-id="def9e-345">WCF always returns objects by value, but it is possible to support the equivalent of by-reference semantics through the use of EndpointAddress10.</span></span> <span data-ttu-id="def9e-346">Это позволяет клиенту запрашивать экземпляр службы WCF, связанный с сеансом, после чего он может взаимодействовать с ней так же, как и с любой другой службой WCF.</span><span class="sxs-lookup"><span data-stu-id="def9e-346">This permits the client to request a sessionful WCF service instance, after which it can interact with it like any other WCF service.</span></span>  
  
#### <a name="scenario-3-client-sends-server-a-by-value-instance"></a><span data-ttu-id="def9e-347">Сценарий 3. Клиент отправляет серверу экземпляр по значению</span><span class="sxs-lookup"><span data-stu-id="def9e-347">Scenario 3: Client Sends Server a By-Value Instance</span></span>  
 <span data-ttu-id="def9e-348">В этом сценарии показан клиент, отправляющий серверу экземпляр объекта, не являющийся примитивом, по значению.</span><span class="sxs-lookup"><span data-stu-id="def9e-348">This scenario demonstrates the client sending a non-primitive object instance to the server by value.</span></span> <span data-ttu-id="def9e-349">Поскольку WCF отправляет объекты только по значению, в этом сценарии показано обычное использование WCF.</span><span class="sxs-lookup"><span data-stu-id="def9e-349">Because WCF only sends objects by value, this scenario demonstrates normal WCF usage.</span></span>  
  
1. <span data-ttu-id="def9e-350">Используйте ту же службу WCF, которая использовалась в сценарии 1.</span><span class="sxs-lookup"><span data-stu-id="def9e-350">Use the same WCF Service from Scenario 1.</span></span>  
  
2. <span data-ttu-id="def9e-351">Используйте клиент для создания нового объекта по значению (Customer), создайте канал для взаимодействия со службой ICustomerService и отправьте в нее объект.</span><span class="sxs-lookup"><span data-stu-id="def9e-351">Use the client to create a new by-value object (Customer), create a channel to communicate with the ICustomerService service, and send the object to it.</span></span>  
  
   ```csharp
   ChannelFactory<ICustomerService> factory =  
       new ChannelFactory<ICustomerService>("customerservice");  
   ICustomerService service = factory.CreateChannel();  
   PremiumCustomer customer = new PremiumCustomer {
   FirstName = "Bob",
   LastName = "Jones",
   CustomerId = 43,
   AccountId = 99};  
   bool success = service.UpdateCustomer(customer);  
   Console.WriteLine($"  Server returned {success}.");
   ```  
  
     <span data-ttu-id="def9e-352">Объект Customer будет сериализован и отправлен на сервер, где он десериализуется в новую копию этого объекта.</span><span class="sxs-lookup"><span data-stu-id="def9e-352">The customer object will be serialized, and sent to the server, where it is deserialized into a new copy of that object.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="def9e-353">Этот код также демонстрирует отправку производного типа (PremiumCustomer).</span><span class="sxs-lookup"><span data-stu-id="def9e-353">This code also illustrates sending a derived type (PremiumCustomer).</span></span> <span data-ttu-id="def9e-354">Интерфейс службы ожидает получения объекта Customer, но атрибут [KnownType] класса Customer указывает, что был также разрешен тип PremiumCustomer.</span><span class="sxs-lookup"><span data-stu-id="def9e-354">The service interface expects a Customer object, but the [KnownType] attribute on the Customer class indicated PremiumCustomer was also allowed.</span></span> <span data-ttu-id="def9e-355">Любая попытка сериализации или десериализации любого другого типа посредством этого интерфейса службы WCF завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="def9e-355">WCF will fail any attempt to serialize or deserialize any other type through this service interface.</span></span>  
  
 <span data-ttu-id="def9e-356">Стандартные обмены данными в службе WCF осуществляются по значению.</span><span class="sxs-lookup"><span data-stu-id="def9e-356">Normal WCF exchanges of data are by value.</span></span> <span data-ttu-id="def9e-357">Это гарантирует, что методы вызова этих объектов данных реализуются только локально без вызова кода на другом уровне.</span><span class="sxs-lookup"><span data-stu-id="def9e-357">This guarantees that invoking methods on one of these data objects executes only locally – it will not invoke code on the other tier.</span></span> <span data-ttu-id="def9e-358">Хотя можно получить нечто вроде объектов по ссылке, возвращаемых *с* сервера, клиент не может *передать на сервер объект по* ссылке.</span><span class="sxs-lookup"><span data-stu-id="def9e-358">While it is possible to achieve something like by-reference objects returned *from* the server, it is not possible for a client to pass a by-reference object *to* the server.</span></span> <span data-ttu-id="def9e-359">Сценарий, при котором клиенту и серверу необходимо обмениваться сообщениями друг с другом, можно реализовать в WCF с помощью дуплексной службы.</span><span class="sxs-lookup"><span data-stu-id="def9e-359">A scenario that requires a conversation back and forth between client and server can be achieved in WCF using a duplex service.</span></span> <span data-ttu-id="def9e-360">Дополнительные сведения см. в разделе [Дуплексные службы](./feature-details/duplex-services.md).</span><span class="sxs-lookup"><span data-stu-id="def9e-360">For more information, see [Duplex Services](./feature-details/duplex-services.md).</span></span>  
  
## <a name="summary"></a><span data-ttu-id="def9e-361">Сводка</span><span class="sxs-lookup"><span data-stu-id="def9e-361">Summary</span></span>  
 <span data-ttu-id="def9e-362">Удаленное взаимодействие .NET — это платформа взаимодействия, предназначенная для использования только в средах с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="def9e-362">.NET Remoting is a communication framework intended to be used only within fully-trusted environments.</span></span> <span data-ttu-id="def9e-363">Это устаревший продукт, который поддерживается только в целях обеспечения обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="def9e-363">It is a legacy product and supported only for backward compatibility.</span></span> <span data-ttu-id="def9e-364">Он не должен использоваться для разработки новых приложений.</span><span class="sxs-lookup"><span data-stu-id="def9e-364">It should not be used to build new applications.</span></span> <span data-ttu-id="def9e-365">И напротив, служба WCF была разработана с учетом безопасности, поэтому ее рекомендуется использовать для поддержки новых и существующих приложений.</span><span class="sxs-lookup"><span data-stu-id="def9e-365">Conversely, WCF was designed with security in mind and is recommended for new and existing applications.</span></span> <span data-ttu-id="def9e-366">Корпорация Майкрософт рекомендует выполнить перенос существующих приложений удаленного взаимодействия с переходом к использованию WCF или веб-интерфейса API ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="def9e-366">Microsoft recommends that existing Remoting applications be migrated to use WCF or ASP.NET Web API instead.</span></span>
