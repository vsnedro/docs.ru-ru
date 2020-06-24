---
title: 'Конечные точки: адреса, привязки и контракты'
description: Узнайте, как все взаимодействия со службой WCF происходит через конечные точки службы, которые предоставляют клиентам доступ к функциональным возможностям, предоставляемым службой.
ms.date: 03/30/2017
helpviewer_keywords:
- endpoints [WCF]
- Windows Communication Foundation [WCF], endpoints
- WCF [WCF], endpoints
ms.assetid: 9ddc46ee-1883-4291-9926-28848c57e858
ms.openlocfilehash: ce0874bfed716716b6fd1801b35a4266095cd752
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247316"
---
# <a name="endpoints-addresses-bindings-and-contracts"></a><span data-ttu-id="1c5ab-103">Конечные точки: адреса, привязки и контракты</span><span class="sxs-lookup"><span data-stu-id="1c5ab-103">Endpoints: Addresses, Bindings, and Contracts</span></span>

<span data-ttu-id="1c5ab-104">Все взаимодействия со службой Windows Communication Foundation (WCF) осуществляется через *конечные точки* службы.</span><span class="sxs-lookup"><span data-stu-id="1c5ab-104">All communication with a Windows Communication Foundation (WCF) service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="1c5ab-105">Конечные точки предоставляют клиентам доступ к функциональным возможностям, предоставляемым службой WCF.</span><span class="sxs-lookup"><span data-stu-id="1c5ab-105">Endpoints provide clients access to the functionality offered by a WCF service.</span></span>

<span data-ttu-id="1c5ab-106">Каждая конечная точка состоит из четырех свойств:</span><span class="sxs-lookup"><span data-stu-id="1c5ab-106">Each endpoint consists of four properties:</span></span>

- <span data-ttu-id="1c5ab-107">адрес, показывающий, где можно найти конечную точку;</span><span class="sxs-lookup"><span data-stu-id="1c5ab-107">An address that indicates where the endpoint can be found.</span></span>

- <span data-ttu-id="1c5ab-108">привязку, показывающую, как клиент может связаться с конечной точкой;</span><span class="sxs-lookup"><span data-stu-id="1c5ab-108">A binding that specifies how a client can communicate with the endpoint.</span></span>

- <span data-ttu-id="1c5ab-109">контракт, определяющий доступные операции;</span><span class="sxs-lookup"><span data-stu-id="1c5ab-109">A contract that identifies the operations available.</span></span>

- <span data-ttu-id="1c5ab-110">набор поведений, задающих сведения о локальной реализации конечной точки.</span><span class="sxs-lookup"><span data-stu-id="1c5ab-110">A set of behaviors that specify local implementation details of the endpoint.</span></span>

<span data-ttu-id="1c5ab-111">В этом разделе рассматривается структура конечной точки и объясняется ее представление в объектной модели WCF.</span><span class="sxs-lookup"><span data-stu-id="1c5ab-111">This topic discusses this endpoint structure and explains how it is represented in the WCF object model.</span></span>

## <a name="the-structure-of-an-endpoint"></a><span data-ttu-id="1c5ab-112">Структура конечной точки</span><span class="sxs-lookup"><span data-stu-id="1c5ab-112">The Structure of an Endpoint</span></span>

<span data-ttu-id="1c5ab-113">Каждая конечная точка состоит из следующего.</span><span class="sxs-lookup"><span data-stu-id="1c5ab-113">Each endpoint consists of the following:</span></span>

- <span data-ttu-id="1c5ab-114">Адрес: адрес однозначно определяет конечную точку и указывает потенциальным потребителям на место расположения службы.</span><span class="sxs-lookup"><span data-stu-id="1c5ab-114">Address: The address uniquely identifies the endpoint and tells potential consumers of the service where it is located.</span></span> <span data-ttu-id="1c5ab-115">Он представлен в объектной модели WCF <xref:System.ServiceModel.EndpointAddress> классом.</span><span class="sxs-lookup"><span data-stu-id="1c5ab-115">It is represented in the WCF object model by the <xref:System.ServiceModel.EndpointAddress> class.</span></span> <span data-ttu-id="1c5ab-116">Класс <xref:System.ServiceModel.EndpointAddress> содержит следующее.</span><span class="sxs-lookup"><span data-stu-id="1c5ab-116">An <xref:System.ServiceModel.EndpointAddress> class contains:</span></span>

  - <span data-ttu-id="1c5ab-117">Свойство <xref:System.ServiceModel.EndpointAddress.Uri%2A>, представляющее адрес службы.</span><span class="sxs-lookup"><span data-stu-id="1c5ab-117">A <xref:System.ServiceModel.EndpointAddress.Uri%2A> property, which represents the address of the service.</span></span>

  - <span data-ttu-id="1c5ab-118">Свойство <xref:System.ServiceModel.EndpointAddress.Identity%2A>, представляющее удостоверение безопасности службы и коллекцию необязательных заголовков сообщений.</span><span class="sxs-lookup"><span data-stu-id="1c5ab-118">An <xref:System.ServiceModel.EndpointAddress.Identity%2A> property, which represents the security identity of the service and a collection of optional message headers.</span></span> <span data-ttu-id="1c5ab-119">Необязательные заголовки сообщений используются для вывода дополнительной и более подробной информации, необходимой для идентификации конечной точки или взаимодействия с ней.</span><span class="sxs-lookup"><span data-stu-id="1c5ab-119">The optional message headers are used to provide additional and more detailed addressing information to identify or interact with the endpoint.</span></span>

  <span data-ttu-id="1c5ab-120">Дополнительные сведения см. в разделе [Указание адреса конечной точки](../specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="1c5ab-120">For more information, see [Specifying an Endpoint Address](../specifying-an-endpoint-address.md).</span></span>

- <span data-ttu-id="1c5ab-121">Привязка. Привязка задает способ связи клиента с конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="1c5ab-121">Binding: The binding specifies how to communicate with the endpoint.</span></span> <span data-ttu-id="1c5ab-122">В том числе:</span><span class="sxs-lookup"><span data-stu-id="1c5ab-122">This includes:</span></span>

  - <span data-ttu-id="1c5ab-123">используемый транспортный протокол (например, TCP или HTTP);</span><span class="sxs-lookup"><span data-stu-id="1c5ab-123">The transport protocol to use (for example, TCP or HTTP).</span></span>

  - <span data-ttu-id="1c5ab-124">используемую в сообщениях кодировку (например, текст или двоичное кодирование);</span><span class="sxs-lookup"><span data-stu-id="1c5ab-124">The encoding to use for the messages (for example, text or binary).</span></span>

  - <span data-ttu-id="1c5ab-125">необходимые требования безопасности (например, безопасность сообщений SSL или SOAP).</span><span class="sxs-lookup"><span data-stu-id="1c5ab-125">The necessary security requirements (for example, SSL or SOAP message security).</span></span>

  <span data-ttu-id="1c5ab-126">Дополнительные сведения см. в разделе [Общие сведения о привязках WCF](../bindings-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1c5ab-126">For more information, see [WCF Bindings Overview](../bindings-overview.md).</span></span> <span data-ttu-id="1c5ab-127">Привязка представлена в объектной модели WCF абстрактным базовым классом <xref:System.ServiceModel.Channels.Binding> .</span><span class="sxs-lookup"><span data-stu-id="1c5ab-127">A binding is represented in the WCF object model by the abstract base class <xref:System.ServiceModel.Channels.Binding>.</span></span> <span data-ttu-id="1c5ab-128">В большинстве сценариев пользователи могут использовать только одну из предусмотренных системой привязок.</span><span class="sxs-lookup"><span data-stu-id="1c5ab-128">For most scenarios, users can use one of the system-provided bindings.</span></span> <span data-ttu-id="1c5ab-129">Дополнительные сведения см. в разделе [привязки, предоставляемые системой](../system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="1c5ab-129">For more information, see [System-Provided Bindings](../system-provided-bindings.md).</span></span>

- <span data-ttu-id="1c5ab-130">Контракты. Контракты показывают, какие функциональные возможности дает клиенту конечная точка.</span><span class="sxs-lookup"><span data-stu-id="1c5ab-130">Contracts: The contract outlines what functionality the endpoint exposes to the client.</span></span> <span data-ttu-id="1c5ab-131">В контракте задается следующее:</span><span class="sxs-lookup"><span data-stu-id="1c5ab-131">A contract specifies:</span></span>

  - <span data-ttu-id="1c5ab-132">операции, которые могут быть вызваны клиентом;</span><span class="sxs-lookup"><span data-stu-id="1c5ab-132">What operations can be called by a client.</span></span>

  - <span data-ttu-id="1c5ab-133">форма сообщения;</span><span class="sxs-lookup"><span data-stu-id="1c5ab-133">The form of the message.</span></span>

  - <span data-ttu-id="1c5ab-134">тип входных параметров или данных, требуемых для вызова операции;</span><span class="sxs-lookup"><span data-stu-id="1c5ab-134">The type of input parameters or data required to call the operation.</span></span>

  - <span data-ttu-id="1c5ab-135">тип обработки или ответного сообщения, который может ожидать клиент.</span><span class="sxs-lookup"><span data-stu-id="1c5ab-135">What type of processing or response message the client can expect.</span></span>

  <span data-ttu-id="1c5ab-136">Дополнительные сведения об определении контракта см. в разделе [проектирование контрактов служб](../designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="1c5ab-136">For more information about defining a contract, see [Designing Service Contracts](../designing-service-contracts.md).</span></span>

- <span data-ttu-id="1c5ab-137">Поведения. Поведения конечной точки можно использовать для настройки локального поведения конечной точки службы.</span><span class="sxs-lookup"><span data-stu-id="1c5ab-137">Behaviors: You can use endpoint behaviors to customize the local behavior of the service endpoint.</span></span> <span data-ttu-id="1c5ab-138">Поведение конечной точки достигается за счет участия в процессе создания среды выполнения WCF.</span><span class="sxs-lookup"><span data-stu-id="1c5ab-138">Endpoint behaviors achieve this by participating in the process of building a WCF runtime.</span></span> <span data-ttu-id="1c5ab-139">Примером поведения является свойство <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A>, позволяющее указывать отличный от адреса SOAP или WSDL адрес прослушивания.</span><span class="sxs-lookup"><span data-stu-id="1c5ab-139">An example of an endpoint behavior is the <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A> property, which allows you to specify a different listening address than the SOAP or Web Services Description Language (WSDL) address.</span></span> <span data-ttu-id="1c5ab-140">Дополнительные сведения см. в разделе [клиентвиабехавиор](../diagnostics/wmi/clientviabehavior.md).</span><span class="sxs-lookup"><span data-stu-id="1c5ab-140">For more information, see [ClientViaBehavior](../diagnostics/wmi/clientviabehavior.md).</span></span>

## <a name="defining-endpoints"></a><span data-ttu-id="1c5ab-141">Определение конечных точек</span><span class="sxs-lookup"><span data-stu-id="1c5ab-141">Defining Endpoints</span></span>

<span data-ttu-id="1c5ab-142">Адрес конечной точки службы можно задать императивно с помощью кода или декларативно с помощью конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1c5ab-142">You can specify the endpoint for a service either imperatively using code or declaratively through configuration.</span></span> <span data-ttu-id="1c5ab-143">Дополнительные сведения см. в разделе [как создать конечную точку службы в конфигурации](how-to-create-a-service-endpoint-in-configuration.md) и [как создать конечную точку службы в коде](how-to-create-a-service-endpoint-in-code.md).</span><span class="sxs-lookup"><span data-stu-id="1c5ab-143">For more information, see [How to: Create a Service Endpoint in Configuration](how-to-create-a-service-endpoint-in-configuration.md) and [How to: Create a Service Endpoint in Code](how-to-create-a-service-endpoint-in-code.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="1c5ab-144">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="1c5ab-144">In This Section</span></span>

<span data-ttu-id="1c5ab-145">В данном разделе объясняется назначение привязок, конечных точек и адресов; показано, как конфигурировать привязку и конечную точку, и демонстрируется, как использовать поведение `ClientVia` и свойство `ListenUri`.</span><span class="sxs-lookup"><span data-stu-id="1c5ab-145">This section explains the purpose of bindings, endpoints, and addresses; shows how to configure a binding and an endpoint; and demonstrates how to use the `ClientVia` behavior and `ListenUri` property.</span></span>

<span data-ttu-id="1c5ab-146">[Addresses](endpoint-addresses.md)</span><span class="sxs-lookup"><span data-stu-id="1c5ab-146">[Addresses](endpoint-addresses.md)</span></span>\
<span data-ttu-id="1c5ab-147">Описывает, как конечные точки решаются в WCF.</span><span class="sxs-lookup"><span data-stu-id="1c5ab-147">Describes how endpoints are addressed in WCF.</span></span>

<span data-ttu-id="1c5ab-148">[Привязки](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="1c5ab-148">[Bindings](bindings.md)</span></span>\
<span data-ttu-id="1c5ab-149">Описывается, как привязки используются для указания транспорта, кодировки и данных протокола, требуемых для связи клиентов и служб.</span><span class="sxs-lookup"><span data-stu-id="1c5ab-149">Describes how bindings are used to specify the transport, encoding, and protocol details required for clients and services to communicate with each other.</span></span>

<span data-ttu-id="1c5ab-150">[Контракты](contracts.md)</span><span class="sxs-lookup"><span data-stu-id="1c5ab-150">[Contracts](contracts.md)</span></span>\
<span data-ttu-id="1c5ab-151">Описывается, как контакты определяют методы службы.</span><span class="sxs-lookup"><span data-stu-id="1c5ab-151">Describes how contracts define the methods of a service.</span></span>

<span data-ttu-id="1c5ab-152">[Как создать конечную точку службы в конфигурации](how-to-create-a-service-endpoint-in-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="1c5ab-152">[How to: Create a Service Endpoint in Configuration](how-to-create-a-service-endpoint-in-configuration.md)</span></span>\
<span data-ttu-id="1c5ab-153">Описывается, как создать конечную точку службы в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1c5ab-153">Describes how to create a service endpoint in configuration.</span></span>

<span data-ttu-id="1c5ab-154">[Как создать конечную точку службы в коде](how-to-create-a-service-endpoint-in-code.md)</span><span class="sxs-lookup"><span data-stu-id="1c5ab-154">[How to: Create a Service Endpoint in Code](how-to-create-a-service-endpoint-in-code.md)</span></span>\
<span data-ttu-id="1c5ab-155">Описывается, как создать конечную точку службы в коде.</span><span class="sxs-lookup"><span data-stu-id="1c5ab-155">Describes how to create a service endpoint in code.</span></span>

<span data-ttu-id="1c5ab-156">[Как использовать Svcutil.exe для проверки скомпилированного кода службы](how-to-use-svcutil-exe-to-validate-compiled-service-code.md)</span><span class="sxs-lookup"><span data-stu-id="1c5ab-156">[How to: Use Svcutil.exe to Validate Compiled Service Code](how-to-use-svcutil-exe-to-validate-compiled-service-code.md)</span></span>\
<span data-ttu-id="1c5ab-157">Описывает, как обнаруживать ошибки в реализациях и конфигурациях служб без размещения службы с помощью [средства служебной программы метаданных ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="1c5ab-157">Describes how to detect errors in service implementations and configurations without hosting the service using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1c5ab-158">См. также</span><span class="sxs-lookup"><span data-stu-id="1c5ab-158">See also</span></span>

- [<span data-ttu-id="1c5ab-159">Настройка служб</span><span class="sxs-lookup"><span data-stu-id="1c5ab-159">Configuring Services</span></span>](../configuring-services.md)
- [<span data-ttu-id="1c5ab-160">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="1c5ab-160">Extending Bindings</span></span>](../extending/extending-bindings.md)
