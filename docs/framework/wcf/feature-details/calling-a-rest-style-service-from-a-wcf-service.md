---
title: Вызов службы в стиле REST из службы WCF
description: Узнайте, как сделать так, чтобы служба WCF использовала правильный контекст с помощью службы в стиле RESTFUL, создав область и вызывая службу из этой области.
ms.date: 03/30/2017
ms.assetid: 77df81d8-7f53-4daf-8d2d-bf7996e94d5a
ms.openlocfilehash: 15f468923cf55feb85e7aeca1a2cc5e38050d665
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245301"
---
# <a name="calling-a-rest-style-service-from-a-wcf-service"></a><span data-ttu-id="2c76b-103">Вызов службы в стиле REST из службы WCF</span><span class="sxs-lookup"><span data-stu-id="2c76b-103">Calling a REST-style service from a WCF service</span></span>

<span data-ttu-id="2c76b-104">При вызове REST-службы из обычной (на основе SOAP) службы WCF контекст операции в методе службы (со сведениями о входящем запросе) переопределяет контекст, который должен использоваться исходящим запросом.</span><span class="sxs-lookup"><span data-stu-id="2c76b-104">When calling a REST-style service from a regular (SOAP-based) WCF service, the operation context on the service method (which contains information about the incoming request) overrides the context which should be used by the outgoing request.</span></span> <span data-ttu-id="2c76b-105">В результате запросы HTTP GET превращаются в запросы HTTP POST.</span><span class="sxs-lookup"><span data-stu-id="2c76b-105">This causes HTTP GET requests to change to HTTP POST requests.</span></span> <span data-ttu-id="2c76b-106">Чтобы заставить службу WCF использовать правильный контекст для вызова REST-службы, создайте новый объект <xref:System.ServiceModel.OperationContextScope> и вызовите REST-службу из области контекста операции.</span><span class="sxs-lookup"><span data-stu-id="2c76b-106">To force the WCF service to use the right context for calling the REST-style service, create a new <xref:System.ServiceModel.OperationContextScope> and call the REST-style service from inside the operation context scope.</span></span> <span data-ttu-id="2c76b-107">В этом разделе описано создание простого примера, иллюстрирующего данный способ.</span><span class="sxs-lookup"><span data-stu-id="2c76b-107">This topic will describe how to create a simple sample that illustrates this technique.</span></span>

## <a name="define-the-rest-style-service-contract"></a><span data-ttu-id="2c76b-108">Определите контракт REST-службы</span><span class="sxs-lookup"><span data-stu-id="2c76b-108">Define the REST-style service contract</span></span>

<span data-ttu-id="2c76b-109">Определите простой контракт службы для REST-службы.</span><span class="sxs-lookup"><span data-stu-id="2c76b-109">Define a simple  REST-style service contract:</span></span>

```csharp
[ServiceContract]
public interface IRestInterface
{
    [OperationContract, WebGet]
    int Add(int x, int y);

    [OperationContract, WebGet]
    string Echo(string input);
}
```

## <a name="implement-the-rest-style-service-contract"></a><span data-ttu-id="2c76b-110">Реализуйте контракт REST-службы</span><span class="sxs-lookup"><span data-stu-id="2c76b-110">Implement the REST-style service contract</span></span>

<span data-ttu-id="2c76b-111">Реализуйте контракт REST-службы.</span><span class="sxs-lookup"><span data-stu-id="2c76b-111">Implement the REST-style service contract:</span></span>

```csharp
public class RestService : IRestInterface
{
    public int Add(int x, int y)
    {
        return x + y;
    }

    public string Echo(string input)
    {
        return input;
    }
}
```

## <a name="define-the-wcf-service-contract"></a><span data-ttu-id="2c76b-112">Определите контракт службы WCF</span><span class="sxs-lookup"><span data-stu-id="2c76b-112">Define the WCF service contract</span></span>

<span data-ttu-id="2c76b-113">Определите контракт службы WCF, которая будет использоваться для вызова REST-службы.</span><span class="sxs-lookup"><span data-stu-id="2c76b-113">Define a WCF service contract  that will be used to call the REST-style service:</span></span>

```csharp
[ServiceContract]
public interface INormalInterface
{
    [OperationContract]
    int CallAdd(int x, int y);

    [OperationContract]
    string CallEcho(string input);
}
```

## <a name="implement-the-wcf-service-contract"></a><span data-ttu-id="2c76b-114">Реализуйте контракт службы WCF</span><span class="sxs-lookup"><span data-stu-id="2c76b-114">Implement the WCF service contract</span></span>

<span data-ttu-id="2c76b-115">Реализуйте контракт службы WCF.</span><span class="sxs-lookup"><span data-stu-id="2c76b-115">Implement the WCF service contract:</span></span>

```csharp
public class NormalService : INormalInterface
{
    static MyRestClient client = new MyRestClient(RestServiceBaseAddress);
    public int CallAdd(int x, int y)
    {
        return client.Add(x, y);
    }

    public string CallEcho(string input)
    {
        return client.Echo(input);
    }
}
```

## <a name="create-the-client-proxy-for-the-rest-style-service"></a><span data-ttu-id="2c76b-116">Создайте клиентский прокси-класс для REST-службы</span><span class="sxs-lookup"><span data-stu-id="2c76b-116">Create the client proxy for the REST-style service</span></span>

<span data-ttu-id="2c76b-117">Использование <xref:System.ServiceModel.ClientBase%601> для реализации прокси клиента.</span><span class="sxs-lookup"><span data-stu-id="2c76b-117">Using <xref:System.ServiceModel.ClientBase%601> to implement the client proxy.</span></span> <span data-ttu-id="2c76b-118">Для каждого вызываемого метода создается и используется для вызова операции новая <xref:System.ServiceModel.OperationContextScope>.</span><span class="sxs-lookup"><span data-stu-id="2c76b-118">For each method called, a new <xref:System.ServiceModel.OperationContextScope> is created and used to call the operation.</span></span>

```csharp
public class MyRestClient : ClientBase<IRestInterface>, IRestInterface
{
    public MyRestClient(string address)
        : base(new WebHttpBinding(), new EndpointAddress(address))
    {
        this.Endpoint.Behaviors.Add(new WebHttpBehavior());
    }

    public int Add(int x, int y)
    {
        using (new OperationContextScope(this.InnerChannel))
        {
            return base.Channel.Add(x, y);
        }
    }

    public string Echo(string input)
    {
        using (new OperationContextScope(this.InnerChannel))
        {
            return base.Channel.Echo(input);
        }
    }
}
```

## <a name="host-and-call-the-services"></a><span data-ttu-id="2c76b-119">Размещение и вызов служб</span><span class="sxs-lookup"><span data-stu-id="2c76b-119">Host and call the services</span></span>

<span data-ttu-id="2c76b-120">Разместите обе службы в консольном приложении, добавив необходимые конечные точки и поведение.</span><span class="sxs-lookup"><span data-stu-id="2c76b-120">Host both services in a console app, adding the needed endpoints and behaviors.</span></span> <span data-ttu-id="2c76b-121">Затем вызовите обычную службу WCF.</span><span class="sxs-lookup"><span data-stu-id="2c76b-121">And then call the regular WCF service:</span></span>

```csharp
public static void Main()
{
    ServiceHost restHost = new ServiceHost(typeof(RestService), new Uri(RestServiceBaseAddress));
    restHost.AddServiceEndpoint(typeof(IRestInterface), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());
    restHost.Open();

    ServiceHost normalHost = new ServiceHost(typeof(NormalService), new Uri(NormalServiceBaseAddress));
    normalHost.AddServiceEndpoint(typeof(INormalInterface), new BasicHttpBinding(), "");
    normalHost.Open();

    Console.WriteLine("Hosts opened");

    ChannelFactory<INormalInterface> factory = new ChannelFactory<INormalInterface>(new BasicHttpBinding(), new EndpointAddress(NormalServiceBaseAddress));
    INormalInterface proxy = factory.CreateChannel();

    Console.WriteLine(proxy.CallAdd(123, 456));
    Console.WriteLine(proxy.CallEcho("Hello world"));
}
```

## <a name="complete-code-listing"></a><span data-ttu-id="2c76b-122">Полный листинг кода</span><span class="sxs-lookup"><span data-stu-id="2c76b-122">Complete code listing</span></span>

<span data-ttu-id="2c76b-123">Ниже полностью приведен код примера, представленного в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="2c76b-123">The following is a complete listing of the sample implemented in this topic:</span></span>

```csharp
public class CallingRESTSample
{
    static readonly string RestServiceBaseAddress = "http://" + Environment.MachineName + ":8008/Service";
    static readonly string NormalServiceBaseAddress = "http://" + Environment.MachineName + ":8000/Service";

    [ServiceContract]
    public interface IRestInterface
    {
        [OperationContract, WebGet]
        int Add(int x, int y);
        [OperationContract, WebGet]
        string Echo(string input);
    }

    [ServiceContract]
    public interface INormalInterface
    {
        [OperationContract]
        int CallAdd(int x, int y);
        [OperationContract]
        string CallEcho(string input);
    }

    public class RestService : IRestInterface
    {
        public int Add(int x, int y)
        {
            return x + y;
        }

        public string Echo(string input)
        {
            return input;
        }
    }

    public class MyRestClient : ClientBase<IRestInterface>, IRestInterface
    {
        public MyRestClient(string address)
            : base(new WebHttpBinding(), new EndpointAddress(address))
        {
            this.Endpoint.Behaviors.Add(new WebHttpBehavior());
        }

        public int Add(int x, int y)
        {
            using (new OperationContextScope(this.InnerChannel))
            {
                return base.Channel.Add(x, y);
            }
        }

        public string Echo(string input)
        {
            using (new OperationContextScope(this.InnerChannel))
            {
                return base.Channel.Echo(input);
            }
        }
    }

    public class NormalService : INormalInterface
    {
        static MyRestClient client = new MyRestClient(RestServiceBaseAddress);
        public int CallAdd(int x, int y)
        {
            return client.Add(x, y);
        }

        public string CallEcho(string input)
        {
            return client.Echo(input);
        }
    }

    public static void Main()
    {
        ServiceHost restHost = new ServiceHost(typeof(RestService), new Uri(RestServiceBaseAddress));
        restHost.AddServiceEndpoint(typeof(IRestInterface), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());
        restHost.Open();

        ServiceHost normalHost = new ServiceHost(typeof(NormalService), new Uri(NormalServiceBaseAddress));
        normalHost.AddServiceEndpoint(typeof(INormalInterface), new BasicHttpBinding(), "");
        normalHost.Open();

        Console.WriteLine("Hosts opened");

        ChannelFactory<INormalInterface> factory = new ChannelFactory<INormalInterface>(new BasicHttpBinding(), new EndpointAddress(NormalServiceBaseAddress));
        INormalInterface proxy = factory.CreateChannel();

        Console.WriteLine(proxy.CallAdd(123, 456));
        Console.WriteLine(proxy.CallEcho("Hello world"));
    }
}
```

## <a name="see-also"></a><span data-ttu-id="2c76b-124">См. также</span><span class="sxs-lookup"><span data-stu-id="2c76b-124">See also</span></span>

- [<span data-ttu-id="2c76b-125">Практическое руководство. Как создать простую веб-службу WCF HTTP</span><span class="sxs-lookup"><span data-stu-id="2c76b-125">How to: Create a Basic WCF Web HTTP Service</span></span>](how-to-create-a-basic-wcf-web-http-service.md)
- [<span data-ttu-id="2c76b-126">Объектная модель программирования WCF Web HTTP</span><span class="sxs-lookup"><span data-stu-id="2c76b-126">WCF Web HTTP Programming Object Model</span></span>](wcf-web-http-programming-object-model.md)
