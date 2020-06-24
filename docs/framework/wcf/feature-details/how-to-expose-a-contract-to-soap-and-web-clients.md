---
title: Практическое руководство. Предоставление контрактов SOAP- и веб-клиентам
description: Сведения о том, как сделать конечную точку сервера WFC доступной для клиентов SOAP и не-SOAP. По умолчанию конечные точки доступны только для клиентов SOAP.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: bb765a48-12f2-430d-a54d-6f0c20f2a23a
ms.openlocfilehash: b1bdb7af51e0e2795c36865058fbeb34a716e3e2
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246978"
---
# <a name="how-to-expose-a-contract-to-soap-and-web-clients"></a><span data-ttu-id="934f4-104">Практическое руководство. Предоставление контрактов SOAP- и веб-клиентам</span><span class="sxs-lookup"><span data-stu-id="934f4-104">How to: Expose a Contract to SOAP and Web Clients</span></span>

<span data-ttu-id="934f4-105">По умолчанию Windows Communication Foundation (WCF) делает конечные точки доступными только для клиентов SOAP.</span><span class="sxs-lookup"><span data-stu-id="934f4-105">By default, Windows Communication Foundation (WCF) makes endpoints available only to SOAP clients.</span></span> <span data-ttu-id="934f4-106">В [процедуре создания базовой веб-службы HTTP WCF](how-to-create-a-basic-wcf-web-http-service.md)конечная точка становится доступной для клиентов, не относящихся к протоколу SOAP.</span><span class="sxs-lookup"><span data-stu-id="934f4-106">In [How to: Create a Basic WCF Web HTTP Service](how-to-create-a-basic-wcf-web-http-service.md), an endpoint is made available to non-SOAP clients.</span></span> <span data-ttu-id="934f4-107">Иногда может потребоваться сделать один и тот же контракт доступным обоими способами: в качестве сетевой конечной точки и в качестве конечной точки SOAP.</span><span class="sxs-lookup"><span data-stu-id="934f4-107">There may be times when you want to make the same contract available both ways, as a Web endpoint and as a SOAP endpoint.</span></span> <span data-ttu-id="934f4-108">В данном разделе приводится пример того, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="934f4-108">This topic shows an example of how to do this.</span></span>

## <a name="to-define-the-service-contract"></a><span data-ttu-id="934f4-109">Определение контракта службы</span><span class="sxs-lookup"><span data-stu-id="934f4-109">To define the service contract</span></span>

1. <span data-ttu-id="934f4-110">Определите контракт службы с помощью интерфейса, помеченного <xref:System.ServiceModel.ServiceContractAttribute> <xref:System.ServiceModel.Web.WebInvokeAttribute> атрибутом, и <xref:System.ServiceModel.Web.WebGetAttribute> атрибутов, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="934f4-110">Define a service contract using an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.Web.WebInvokeAttribute> and the <xref:System.ServiceModel.Web.WebGetAttribute> attributes, as shown in the following code:</span></span>

    [!code-csharp[htSoapWeb#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#0)]
    [!code-vb[htSoapWeb#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#0)]

    > [!NOTE]
    > <span data-ttu-id="934f4-111">По умолчанию атрибут <xref:System.ServiceModel.Web.WebInvokeAttribute> сопоставляет с операцией вызовы POST.</span><span class="sxs-lookup"><span data-stu-id="934f4-111">By default <xref:System.ServiceModel.Web.WebInvokeAttribute> maps POST calls to the operation.</span></span> <span data-ttu-id="934f4-112">Однако можно указать метод для сопоставления с операцией, задав параметр «method=».</span><span class="sxs-lookup"><span data-stu-id="934f4-112">You can, however, specify the method to map to the operation by specifying a "method=" parameter.</span></span> <span data-ttu-id="934f4-113">В методе <xref:System.ServiceModel.Web.WebGetAttribute> отсутствует параметр «method=», при этом метод сопоставляет с операцией службы только вызовы GET.</span><span class="sxs-lookup"><span data-stu-id="934f4-113"><xref:System.ServiceModel.Web.WebGetAttribute> does not have a "method=" parameter and only maps GET calls to the service operation.</span></span>

2. <span data-ttu-id="934f4-114">Реализуйте контракт службы, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="934f4-114">Implement the service contract, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#1)]
     [!code-vb[htSoapWeb#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#1)]

## <a name="to-host-the-service"></a><span data-ttu-id="934f4-115">Размещение службы</span><span class="sxs-lookup"><span data-stu-id="934f4-115">To host the service</span></span>

1. <span data-ttu-id="934f4-116">Создайте <xref:System.ServiceModel.ServiceHost> объект, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="934f4-116">Create a <xref:System.ServiceModel.ServiceHost> object, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#2)]
     [!code-vb[htSoapWeb#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#2)]

2. <span data-ttu-id="934f4-117">Добавьте <xref:System.ServiceModel.Description.ServiceEndpoint> с помощью <xref:System.ServiceModel.BasicHttpBinding> для КОНЕЧНОЙ точки SOAP, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="934f4-117">Add a <xref:System.ServiceModel.Description.ServiceEndpoint> with <xref:System.ServiceModel.BasicHttpBinding> for the SOAP endpoint, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#3)]
     [!code-vb[htSoapWeb#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#3)]

3. <span data-ttu-id="934f4-118">Добавьте <xref:System.ServiceModel.Description.ServiceEndpoint> с помощью <xref:System.ServiceModel.WebHttpBinding> для конечной точки, отличной от SOAP, и добавьте в <xref:System.ServiceModel.Description.WebHttpBehavior> конечную точку, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="934f4-118">Add a <xref:System.ServiceModel.Description.ServiceEndpoint> with <xref:System.ServiceModel.WebHttpBinding> for the non-SOAP endpoint and add the <xref:System.ServiceModel.Description.WebHttpBehavior> to the endpoint, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#4)]
     [!code-vb[htSoapWeb#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#4)]

4. <span data-ttu-id="934f4-119">Вызовите `Open()` в <xref:System.ServiceModel.ServiceHost> экземпляре, чтобы открыть узел службы, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="934f4-119">Call `Open()` on a <xref:System.ServiceModel.ServiceHost> instance to open the service host, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#5)]
     [!code-vb[htSoapWeb#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#5)]

## <a name="to-call-service-operations-mapped-to-get-in-internet-explorer"></a><span data-ttu-id="934f4-120">Вызов операций службы, сопоставленных с операцией GET, в Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="934f4-120">To call service operations mapped to GET in Internet Explorer</span></span>

1. <span data-ttu-id="934f4-121">Откройте Internet Explorer и введите " `http://localhost:8000/Web/EchoWithGet?s=Hello, world!` " и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="934f4-121">Open Internet Explorer and type "`http://localhost:8000/Web/EchoWithGet?s=Hello, world!`" and press ENTER.</span></span> <span data-ttu-id="934f4-122">URL-адрес содержит базовый адрес службы ( `http://localhost:8000/` ), относительный адрес конечной точки (""), операцию службы для вызова ("ечовисжет") и вопросительный знак, за которым следует список именованных параметров, разделенных амперсандом (&).</span><span class="sxs-lookup"><span data-stu-id="934f4-122">The URL contains the base address of the service (`http://localhost:8000/`), the relative address of the endpoint (""), the service operation to call ("EchoWithGet"), and a question mark followed by a list of named parameters separated by an ampersand (&).</span></span>

## <a name="to-call-service-operations-on-the-web-endpoint-in-code"></a><span data-ttu-id="934f4-123">Вызов операций службы в сетевой конечной точке в коде</span><span class="sxs-lookup"><span data-stu-id="934f4-123">To call service operations on the Web endpoint in code</span></span>

1. <span data-ttu-id="934f4-124">Создайте экземпляр класса <xref:System.ServiceModel.Web.WebChannelFactory%601> в блоке `using`, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="934f4-124">Create an instance of <xref:System.ServiceModel.Web.WebChannelFactory%601> within a `using` block, as shown in the following code.</span></span>

     [!code-csharp[htSoapWeb#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#6)]
     [!code-vb[htSoapWeb#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#6)]

> [!NOTE]
> <span data-ttu-id="934f4-125">Метод `Close()` автоматически вызывается для канала в конце блока `using`.</span><span class="sxs-lookup"><span data-stu-id="934f4-125">`Close()` is automatically called on the channel at the end of the `using` block.</span></span>

1. <span data-ttu-id="934f4-126">Создайте канал и вызовите службу, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="934f4-126">Create the channel and call the service, as shown in the following code.</span></span>

     [!code-csharp[htSoapWeb#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#8)]
     [!code-vb[htSoapWeb#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#8)]

## <a name="to-call-service-operations-on-the-soap-endpoint"></a><span data-ttu-id="934f4-127">Вызов операций службы в конечной точке SOAP</span><span class="sxs-lookup"><span data-stu-id="934f4-127">To call service operations on the SOAP endpoint</span></span>

1. <span data-ttu-id="934f4-128">Создайте экземпляр класса <xref:System.ServiceModel.ChannelFactory> в блоке `using`, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="934f4-128">Create an instance of <xref:System.ServiceModel.ChannelFactory> within a `using` block, as shown in the following code.</span></span>

    [!code-csharp[htSoapWeb#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#10)]
    [!code-vb[htSoapWeb#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#10)]

2. <span data-ttu-id="934f4-129">Создайте канал и вызовите службу, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="934f4-129">Create the channel and call the service, as shown in the following code.</span></span>

    [!code-csharp[htSoapWeb#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#11)]
    [!code-vb[htSoapWeb#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#11)]

## <a name="to-close-the-service-host"></a><span data-ttu-id="934f4-130">Закрытие узла службы</span><span class="sxs-lookup"><span data-stu-id="934f4-130">To close the service host</span></span>

1. <span data-ttu-id="934f4-131">Закройте ведущее приложение службы, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="934f4-131">Close the service host, as shown in the following code.</span></span>

    [!code-csharp[htSoapWeb#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#9)]
    [!code-vb[htSoapWeb#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#9)]

## <a name="example"></a><span data-ttu-id="934f4-132">Пример</span><span class="sxs-lookup"><span data-stu-id="934f4-132">Example</span></span>

<span data-ttu-id="934f4-133">Ниже приведен полный листинг кода для этого раздела:</span><span class="sxs-lookup"><span data-stu-id="934f4-133">The following is the full code listing for this topic:</span></span>

[!code-csharp[htSoapWeb#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#13)]
[!code-vb[htSoapWeb#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#13)]

## <a name="compiling-the-code"></a><span data-ttu-id="934f4-134">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="934f4-134">Compiling the code</span></span>

 <span data-ttu-id="934f4-135">При компиляции Service.cs обращается к файлам System.ServiceModel.dll и System.ServiceModel.Web.dll.</span><span class="sxs-lookup"><span data-stu-id="934f4-135">When compiling Service.cs, reference System.ServiceModel.dll and System.ServiceModel.Web.dll.</span></span>

## <a name="see-also"></a><span data-ttu-id="934f4-136">См. также</span><span class="sxs-lookup"><span data-stu-id="934f4-136">See also</span></span>

- <xref:System.ServiceModel.WebHttpBinding>
- <xref:System.ServiceModel.Web.WebGetAttribute>
- <xref:System.ServiceModel.Web.WebInvokeAttribute>
- <xref:System.ServiceModel.Web.WebServiceHost>
- <xref:System.ServiceModel.ChannelFactory>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [<span data-ttu-id="934f4-137">Модель веб-программирования HTTP WCF</span><span class="sxs-lookup"><span data-stu-id="934f4-137">WCF Web HTTP Programming Model</span></span>](wcf-web-http-programming-model.md)
