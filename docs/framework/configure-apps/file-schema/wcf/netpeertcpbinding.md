---
title: <netPeerTcpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- netPeerBinding element
ms.assetid: 2dd77ada-a176-47c7-a740-900b279f1aad
ms.openlocfilehash: 0f702788cf623651fd980b0443821b37acc7387c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204558"
---
# \<netPeerTcpBinding>

<span data-ttu-id="c095f-101">Определяет привязку для обмена TCP-сообщениями через одноранговый канал.</span><span class="sxs-lookup"><span data-stu-id="c095f-101">Defines a binding for peer channel specific TCP messaging.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<netPeerTcpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="c095f-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c095f-102">Syntax</span></span>  
  
```xml  
<netPeerBinding>
  <binding name="string"
           closeTimeout="TimeSpan"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           listenIPAddress="String"
           maxBufferPoolSize="integer"
           maxReceiveMessageSize="Integer"
           port="Integer">
    <security mode="None/Transport/Message/TransportWithMessageCredential">
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c095f-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c095f-103">Attributes and Elements</span></span>  

 <span data-ttu-id="c095f-104">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c095f-104">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c095f-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c095f-105">Attributes</span></span>  
  
|<span data-ttu-id="c095f-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c095f-106">Attribute</span></span>|<span data-ttu-id="c095f-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c095f-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c095f-108">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="c095f-108">closeTimeout</span></span>|<span data-ttu-id="c095f-109">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="c095f-109">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="c095f-110">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="c095f-110">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="c095f-111">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="c095f-111">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="c095f-112">listenIPAddress</span><span class="sxs-lookup"><span data-stu-id="c095f-112">listenIPAddress</span></span>|<span data-ttu-id="c095f-113">Строка, указывающая IP-адрес, на котором одноранговый узел будет ожидать TCP-сообщения.</span><span class="sxs-lookup"><span data-stu-id="c095f-113">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="c095f-114">Значение по умолчанию — `null`.</span><span class="sxs-lookup"><span data-stu-id="c095f-114">The default is `null`.</span></span>|  
|<span data-ttu-id="c095f-115">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="c095f-115">maxBufferPoolSize</span></span>|<span data-ttu-id="c095f-116">Целое число, задающее максимальный размер буферного пула для этой привязки.</span><span class="sxs-lookup"><span data-stu-id="c095f-116">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="c095f-117">Значение по умолчанию - 524 288 байт (512 \* 1024).</span><span class="sxs-lookup"><span data-stu-id="c095f-117">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="c095f-118">Многие элементы Windows Communication Foundation (WCF) используют буферы.</span><span class="sxs-lookup"><span data-stu-id="c095f-118">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="c095f-119">При создании буферов и их уничтожении после каждого использования расходуется слишком много ресурсов; при сборке мусора для буферов также расходуется слишком много ресурсов.</span><span class="sxs-lookup"><span data-stu-id="c095f-119">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="c095f-120">Буферные пулы позволяют брать буфер из пула, использовать его, а затем возвращать обратно, когда он больше не требуется.</span><span class="sxs-lookup"><span data-stu-id="c095f-120">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="c095f-121">Это позволяет избежать излишней нагрузки, связанной с созданием и уничтожением буферов.</span><span class="sxs-lookup"><span data-stu-id="c095f-121">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="c095f-122">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="c095f-122">maxReceivedMessageSize</span></span>|<span data-ttu-id="c095f-123">Положительное целое число, задающее, в байтах, максимальный размер сообщения (включая заголовки), которое можно получить по каналу, настроенному с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="c095f-123">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="c095f-124">Отправитель сообщения, превышающего это ограничение, получит ошибку SOAP.</span><span class="sxs-lookup"><span data-stu-id="c095f-124">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="c095f-125">Получатель отклоняет сообщение и создает запись о событии в журнале трассировки.</span><span class="sxs-lookup"><span data-stu-id="c095f-125">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="c095f-126">Значение по умолчанию — 65536.</span><span class="sxs-lookup"><span data-stu-id="c095f-126">The default is 65536.</span></span>|  
|<span data-ttu-id="c095f-127">name</span><span class="sxs-lookup"><span data-stu-id="c095f-127">name</span></span>|<span data-ttu-id="c095f-128">Строка, содержащая имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="c095f-128">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="c095f-129">Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.</span><span class="sxs-lookup"><span data-stu-id="c095f-129">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="c095f-130">Начиная с .NET Framework 4, привязки и поведения не обязательно должны иметь имя.</span><span class="sxs-lookup"><span data-stu-id="c095f-130">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="c095f-131">Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="c095f-131">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="c095f-132">openTimeout</span><span class="sxs-lookup"><span data-stu-id="c095f-132">openTimeout</span></span>|<span data-ttu-id="c095f-133">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="c095f-133">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="c095f-134">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="c095f-134">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="c095f-135">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="c095f-135">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="c095f-136">порт</span><span class="sxs-lookup"><span data-stu-id="c095f-136">port</span></span>|<span data-ttu-id="c095f-137">Целое число, задающее порт сетевого интерфейса, на котором эта привязка будет обрабатывать TCP-сообщения однорангового канала.</span><span class="sxs-lookup"><span data-stu-id="c095f-137">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="c095f-138">Это значение должно принадлежать диапазону от <xref:System.Net.IPEndPoint.MinPort> до <xref:System.Net.IPEndPoint.MaxPort>.</span><span class="sxs-lookup"><span data-stu-id="c095f-138">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="c095f-139">Значение по умолчанию равно 0.</span><span class="sxs-lookup"><span data-stu-id="c095f-139">The default is 0.</span></span>|  
|<span data-ttu-id="c095f-140">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="c095f-140">receiveTimeout</span></span>|<span data-ttu-id="c095f-141">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="c095f-141">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="c095f-142">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="c095f-142">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="c095f-143">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="c095f-143">The default is 00:10:00.</span></span>|  
|<span data-ttu-id="c095f-144">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="c095f-144">sendTimeout</span></span>|<span data-ttu-id="c095f-145">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="c095f-145">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="c095f-146">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="c095f-146">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="c095f-147">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="c095f-147">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c095f-148">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c095f-148">Child Elements</span></span>  
  
|<span data-ttu-id="c095f-149">Элемент</span><span class="sxs-lookup"><span data-stu-id="c095f-149">Element</span></span>|<span data-ttu-id="c095f-150">Описание</span><span class="sxs-lookup"><span data-stu-id="c095f-150">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="c095f-151">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="c095f-151">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="c095f-152">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="c095f-152">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[\<resolver>](resolver.md)|<span data-ttu-id="c095f-153">Указывает распознаватель одноранговых узлов, используемый данной привязкой для разрешения идентификаторов сетки одноранговых узлов в IP-адреса конечных точек узлов этой сетки.</span><span class="sxs-lookup"><span data-stu-id="c095f-153">Specifies a peer resolver used by this binding to resolve a peer mesh ID to the endpoint IP addresses of nodes within the peer mesh.</span></span>|  
|[\<security>](security-of-netpeerbinding.md)|<span data-ttu-id="c095f-154">Определяет параметры безопасности сообщения.</span><span class="sxs-lookup"><span data-stu-id="c095f-154">Defines the security settings for the message.</span></span> <span data-ttu-id="c095f-155">Это элемент типа <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="c095f-155">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c095f-156">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c095f-156">Parent Elements</span></span>  
  
|<span data-ttu-id="c095f-157">Элемент</span><span class="sxs-lookup"><span data-stu-id="c095f-157">Element</span></span>|<span data-ttu-id="c095f-158">Описание</span><span class="sxs-lookup"><span data-stu-id="c095f-158">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="c095f-159">Этот элемент содержит коллекцию стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="c095f-159">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c095f-160">Remarks</span><span class="sxs-lookup"><span data-stu-id="c095f-160">Remarks</span></span>  

 <span data-ttu-id="c095f-161">Эта привязка обеспечивает поддержку для создания одноранговых и многопользовательских приложений, использующих передачу данных по протоколу TCP.</span><span class="sxs-lookup"><span data-stu-id="c095f-161">This binding provides support for the creation of peer-to-peer or multiparty applications using peer transport over TCP.</span></span> <span data-ttu-id="c095f-162">Каждый одноранговый узел может содержать несколько одноранговых каналов, определенных этим типом привязки.</span><span class="sxs-lookup"><span data-stu-id="c095f-162">Each peer node can host multiple peer channels defined with this binding type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c095f-163">Пример</span><span class="sxs-lookup"><span data-stu-id="c095f-163">Example</span></span>  

 <span data-ttu-id="c095f-164">Следующий пример демонстрирует применение привязки NetPeerTcpBinding, обеспечивающей многопользовательскую связь с использованием однорангового канала.</span><span class="sxs-lookup"><span data-stu-id="c095f-164">The following example demonstrates using the NetPeerTcpBinding binding, which provides multiparty communication using a peer channel.</span></span> <span data-ttu-id="c095f-165">Подробный сценарий использования этой привязки см. в разделе [net peer TCP](/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="c095f-165">For a detailed scenario of using this binding, see [Net Peer TCP](/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90)).</span></span>  
  
```xml  
<configuration>
  <system.ServiceModel>
    <bindings>
      <netPeerBinding>
        <binding closeTimeout="00:00:10"
                 openTimeout="00:00:20"
                 receiveTimeout="00:00:30"
                 sendTimeout="00:00:40"
                 maxBufferSize="1001"
                 maxConnections="123"
                 maxReceiveMessageSize="1000">
          <reliableSession ordered="false"
                           inactivityTimeout="00:02:00"
                           enabled="true" />
          <security mode="TransportWithMessageCredential">
            <message clientCredentialType="CardSpace" />
          </security>
        </binding>
      </netPeerBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="c095f-166">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c095f-166">See also</span></span>

- <xref:System.ServiceModel.NetPeerTcpBinding>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement>
- [<span data-ttu-id="c095f-167">Привязки</span><span class="sxs-lookup"><span data-stu-id="c095f-167">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c095f-168">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="c095f-168">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="c095f-169">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="c095f-169">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- <span data-ttu-id="c095f-170">[Привязка NetPeerTcpBinding](/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="c095f-170">[Net Peer TCP](/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90))</span></span>
- [<span data-ttu-id="c095f-171">Одноранговая сеть</span><span class="sxs-lookup"><span data-stu-id="c095f-171">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
