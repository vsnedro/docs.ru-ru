---
title: <netTcpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- netTcpBinding Element
ms.assetid: 5c5104a7-8754-4335-8233-46a45322503e
ms.openlocfilehash: c43c141093c8287adb6d5a841a43ac893deefccd
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "74139342"
---
# \<netTcpBinding>

<span data-ttu-id="be6b5-101">Задает безопасную, надежную и оптимизированную привязку, пригодную для обмена данными между компьютерами.</span><span class="sxs-lookup"><span data-stu-id="be6b5-101">Specifies a secure, reliable, optimized binding suitable for cross-machine communication.</span></span> <span data-ttu-id="be6b5-102">По умолчанию создает стек связи среды выполнения с безопасностью Windows для защиты и проверки подлинности сообщений, с протоколом TCP для доставки сообщений, а также с кодированием двоичных сообщений.</span><span class="sxs-lookup"><span data-stu-id="be6b5-102">By default, it generates a runtime communication stack with Windows Security for message security and authentication, TCP for message delivery, and binary message encoding.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<netTcpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="be6b5-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="be6b5-103">Syntax</span></span>  
  
```xml  
<netTcpBinding>
  <binding closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
           listenBacklog="Integer"
           maxBufferPoolSize="integer"
           maxBufferSize="Integer"
           maxConnections="Integer"
           maxReceivedMessageSize="Integer"
           name="string"
           openTimeout="TimeSpan"
           portSharingEnabled="Boolean"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           transactionFlow="Boolean"
           transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004"
           transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse">
    <reliableSession ordered="Boolean"
                     inactivityTimeout="TimeSpan"
                     enabled="Boolean" />
    <security mode="None/Transport/Message/Both">
      <message clientCredentialType="None/Windows/UserName/Certificate/CardSpace"
               algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15" />
      <transport clientCredentialType="None/Windows/Certificate"
                 protectionLevel="None/Sign/EncryptAndSign" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</netTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="be6b5-104">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="be6b5-104">Attributes and elements</span></span>

<span data-ttu-id="be6b5-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="be6b5-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="be6b5-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="be6b5-106">Attributes</span></span>  
  
|<span data-ttu-id="be6b5-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="be6b5-107">Attribute</span></span>|<span data-ttu-id="be6b5-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="be6b5-108">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="be6b5-109">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="be6b5-109">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="be6b5-110">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="be6b5-110">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="be6b5-111">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="be6b5-111">The default is 00:01:00.</span></span>|  
|`hostNameComparisonMode`|<span data-ttu-id="be6b5-112">Задает режим сравнения имен узлов HTTP для анализа универсальных кодов ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="be6b5-112">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="be6b5-113">Это атрибут типа <xref:System.ServiceModel.HostNameComparisonMode>, который указывает, используется ли имя узла для доступа к службе при сравнении по универсальному коду ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="be6b5-113">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="be6b5-114">Значение по умолчанию — <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, при котором имя узла в найденном соответствии не используется.</span><span class="sxs-lookup"><span data-stu-id="be6b5-114">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|`listenBacklog`|<span data-ttu-id="be6b5-115">Положительное целое число, указывающее максимальное число каналов, ожидающих принятия прослушивателем.</span><span class="sxs-lookup"><span data-stu-id="be6b5-115">A positive integer that specifies the maximum number of channels waiting to be accepted on the listener.</span></span> <span data-ttu-id="be6b5-116">Соединения сверх этого лимита помещаются в очередь и обрабатываются по мере освобождения ресурсов.</span><span class="sxs-lookup"><span data-stu-id="be6b5-116">Connections in excess of this limit are queued until space below the limit becomes available.</span></span> <span data-ttu-id="be6b5-117">Атрибут `connectionTimeout` ограничивает время, в течение которого клиент ожидает установления соединения до создания исключения подключения.</span><span class="sxs-lookup"><span data-stu-id="be6b5-117">The `connectionTimeout` attribute limits the time a client will wait to be connected before throwing a connection exception.</span></span> <span data-ttu-id="be6b5-118">Значение по умолчанию равно 10.</span><span class="sxs-lookup"><span data-stu-id="be6b5-118">The default is 10.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="be6b5-119">Целое число, задающее максимальный размер буферного пула для этой привязки.</span><span class="sxs-lookup"><span data-stu-id="be6b5-119">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="be6b5-120">Значение по умолчанию - 512 \* 1024 байт.</span><span class="sxs-lookup"><span data-stu-id="be6b5-120">The default is 512 \* 1024 bytes.</span></span> <span data-ttu-id="be6b5-121">Многие элементы Windows Communication Foundation (WCF) используют буферы.</span><span class="sxs-lookup"><span data-stu-id="be6b5-121">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="be6b5-122">При создании буферов и их уничтожении после каждого использования расходуется слишком много ресурсов; при сборке мусора для буферов также расходуется слишком много ресурсов.</span><span class="sxs-lookup"><span data-stu-id="be6b5-122">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="be6b5-123">Буферные пулы позволяют брать буфер из пула, использовать его, а затем возвращать обратно, когда он больше не требуется.</span><span class="sxs-lookup"><span data-stu-id="be6b5-123">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="be6b5-124">Это позволяет избежать излишней нагрузки, связанной с созданием и уничтожением буферов.</span><span class="sxs-lookup"><span data-stu-id="be6b5-124">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="be6b5-125">Положительное целое число, указывающее максимальный размер буфера, используемого для хранения сообщений в памяти (в байтах).</span><span class="sxs-lookup"><span data-stu-id="be6b5-125">A positive integer that specifies the maximum size, in bytes, of the buffer used to store messages in memory.</span></span><br /><br /> <span data-ttu-id="be6b5-126">Если атрибут `transferMode` имеет значение `Buffered`, этот атрибут должен быть равен значению атрибута `maxReceivedMessageSize`.</span><span class="sxs-lookup"><span data-stu-id="be6b5-126">If the `transferMode` attribute equals to `Buffered`, this attribute should be equal to the `maxReceivedMessageSize` attribute value.</span></span><br /><br /> <span data-ttu-id="be6b5-127">Если атрибут `transferMode` имеет значение `Streamed`, этот атрибут не может иметь значение большее, чем значение атрибута `maxReceivedMessageSize`, и должен иметь размер, по крайней мере равный размеру заголовков.</span><span class="sxs-lookup"><span data-stu-id="be6b5-127">If the `transferMode` attribute equals to `Streamed`, this attribute cannot be more than the `maxReceivedMessageSize` attribute value, and should be at least the size of the headers.</span></span><br /><br /> <span data-ttu-id="be6b5-128">Значение по умолчанию — 65536.</span><span class="sxs-lookup"><span data-stu-id="be6b5-128">The default is 65536.</span></span> <span data-ttu-id="be6b5-129">Для получения дополнительной информации см. <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>.</span><span class="sxs-lookup"><span data-stu-id="be6b5-129">For more information, see <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>.</span></span>|  
|`maxConnections`|<span data-ttu-id="be6b5-130">Целое число, указывающее максимальное число входящих и исходящих подключений, которые будут созданы/приняты службой.</span><span class="sxs-lookup"><span data-stu-id="be6b5-130">An integer that specifies the maximum number of outbound and inbound connections the service will create/accept.</span></span> <span data-ttu-id="be6b5-131">Входящие и исходящие подключения считаются относительно отдельного предела, определенного этим атрибутом.</span><span class="sxs-lookup"><span data-stu-id="be6b5-131">Incoming and outgoing connections are counted against a separate limit specified by this attribute.</span></span><br /><br /> <span data-ttu-id="be6b5-132">Входящие соединения сверх указанного предела помещаются в очередь и обрабатываются по мере освобождения ресурсов.</span><span class="sxs-lookup"><span data-stu-id="be6b5-132">Inbound connections in excess of the limit are queued until a space below the limit becomes available.</span></span><br /><br /> <span data-ttu-id="be6b5-133">Исходящие соединения сверх указанного предела помещаются в очередь и обрабатываются по мере освобождения ресурсов.</span><span class="sxs-lookup"><span data-stu-id="be6b5-133">Outbound connections in excess of the limit are queued until a space below the limit becomes available.</span></span><br /><br /> <span data-ttu-id="be6b5-134">Значение по умолчанию равно 10.</span><span class="sxs-lookup"><span data-stu-id="be6b5-134">The default is 10.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="be6b5-135">Положительное целое число, задающее, в байтах, максимальный размер сообщения (включая заголовки), которое можно получить по каналу, настроенному с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="be6b5-135">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="be6b5-136">Отправитель сообщения, превышающего это ограничение, получит ошибку SOAP.</span><span class="sxs-lookup"><span data-stu-id="be6b5-136">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="be6b5-137">Получатель отклоняет сообщение и создает запись о событии в журнале трассировки.</span><span class="sxs-lookup"><span data-stu-id="be6b5-137">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="be6b5-138">Значение по умолчанию — 65536.</span><span class="sxs-lookup"><span data-stu-id="be6b5-138">The default is 65536.</span></span>|  
|`name`|<span data-ttu-id="be6b5-139">Строка, содержащая имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="be6b5-139">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="be6b5-140">Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.</span><span class="sxs-lookup"><span data-stu-id="be6b5-140">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="be6b5-141">Начиная с .NET Framework 4, привязки и поведения не обязательно должны иметь имя.</span><span class="sxs-lookup"><span data-stu-id="be6b5-141">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="be6b5-142">Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="be6b5-142">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="be6b5-143">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="be6b5-143">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="be6b5-144">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="be6b5-144">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="be6b5-145">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="be6b5-145">The default is 00:01:00.</span></span>|  
|`portSharingEnabled`|<span data-ttu-id="be6b5-146">Логическое значение, определяющее, включено ли совместное использование порта TCP для этого подключения.</span><span class="sxs-lookup"><span data-stu-id="be6b5-146">A Boolean value that specifies whether TCP port sharing is enabled for this connection.</span></span> <span data-ttu-id="be6b5-147">Если атрибут имеет значение `false`, для каждой привязки используется собственный порт.</span><span class="sxs-lookup"><span data-stu-id="be6b5-147">If this is `false`, each binding uses its own exclusive port.</span></span> <span data-ttu-id="be6b5-148">Этот параметр действителен только для служб, так как он не затрагивает клиенты.</span><span class="sxs-lookup"><span data-stu-id="be6b5-148">This setting is relevant only to services, because clients are not affected.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="be6b5-149">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="be6b5-149">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="be6b5-150">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="be6b5-150">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="be6b5-151">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="be6b5-151">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="be6b5-152">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="be6b5-152">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="be6b5-153">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="be6b5-153">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="be6b5-154">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="be6b5-154">The default is 00:01:00.</span></span>|  
|`transactionFlow`|<span data-ttu-id="be6b5-155">Логическое значение, определяющее, поддерживает ли привязка потоковые спецификации WS-Transactions.</span><span class="sxs-lookup"><span data-stu-id="be6b5-155">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="be6b5-156">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="be6b5-156">The default is `false`.</span></span>|  
|`transactionProtocol`|<span data-ttu-id="be6b5-157">Указывает протокол транзакций, используемый с данной привязкой.</span><span class="sxs-lookup"><span data-stu-id="be6b5-157">Specifies the transaction protocol to be used with this binding.</span></span> <span data-ttu-id="be6b5-158">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="be6b5-158">Valid values are</span></span><br /><br /> <span data-ttu-id="be6b5-159">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="be6b5-159">-   OleTransactions</span></span><br /><span data-ttu-id="be6b5-160">-WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="be6b5-160">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="be6b5-161">Значение по умолчанию - OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="be6b5-161">The default is OleTransactions.</span></span> <span data-ttu-id="be6b5-162">Это атрибут типа <xref:System.ServiceModel.TransactionProtocol>.</span><span class="sxs-lookup"><span data-stu-id="be6b5-162">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
|`transferMode`|<span data-ttu-id="be6b5-163">Значение <xref:System.ServiceModel.TransferMode>, которое указывает, следует ли помещать сообщения в буфер или передавать их потоком по запросу или отклику.</span><span class="sxs-lookup"><span data-stu-id="be6b5-163">A <xref:System.ServiceModel.TransferMode> value that specifies whether messages are buffered or streamed or a request or response.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="be6b5-164">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="be6b5-164">Child elements</span></span>  
  
|<span data-ttu-id="be6b5-165">Элемент</span><span class="sxs-lookup"><span data-stu-id="be6b5-165">Element</span></span>|<span data-ttu-id="be6b5-166">Описание</span><span class="sxs-lookup"><span data-stu-id="be6b5-166">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-nettcpbinding.md)|<span data-ttu-id="be6b5-167">Определяет параметры безопасности привязки.</span><span class="sxs-lookup"><span data-stu-id="be6b5-167">Defines the security settings for the binding.</span></span> <span data-ttu-id="be6b5-168">Это элемент типа <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="be6b5-168">This element is of type <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>.</span></span>|  
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="be6b5-169">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="be6b5-169">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="be6b5-170">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="be6b5-170">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))|<span data-ttu-id="be6b5-171">Указывает, устанавливаются ли между конечными точками канала надежные сеансы.</span><span class="sxs-lookup"><span data-stu-id="be6b5-171">Specifies if reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="be6b5-172">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="be6b5-172">Parent elements</span></span>  
  
|<span data-ttu-id="be6b5-173">Элемент</span><span class="sxs-lookup"><span data-stu-id="be6b5-173">Element</span></span>|<span data-ttu-id="be6b5-174">Описание</span><span class="sxs-lookup"><span data-stu-id="be6b5-174">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="be6b5-175">Этот элемент содержит коллекцию стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="be6b5-175">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be6b5-176">Примечания</span><span class="sxs-lookup"><span data-stu-id="be6b5-176">Remarks</span></span>

<span data-ttu-id="be6b5-177">Эта привязка создает стек связи времени выполнения по умолчанию, использующий режим безопасности транспорта, протокол TCP для доставки сообщений, а также кодирование двоичных сообщений.</span><span class="sxs-lookup"><span data-stu-id="be6b5-177">This binding generates a run-time communication stack by default, which uses transport security, TCP for message delivery, and a binary message encoding.</span></span> <span data-ttu-id="be6b5-178">Эта привязка является подходящей системой Windows Communication Foundation (WCF), предоставляемой для взаимодействия через интрасеть.</span><span class="sxs-lookup"><span data-stu-id="be6b5-178">This binding is an appropriate Windows Communication Foundation (WCF) system-provided choice for communicating over an Intranet.</span></span>  
  
 <span data-ttu-id="be6b5-179">Конфигурация по умолчанию для `netTcpBinding` работает быстрее, чем конфигурация, предоставляемая `wsHttpBinding` , но она предназначена только для взаимодействия WCF.</span><span class="sxs-lookup"><span data-stu-id="be6b5-179">The default configuration for the `netTcpBinding` is faster than the configuration provided by the `wsHttpBinding`, but it is intended only for WCF communication.</span></span> <span data-ttu-id="be6b5-180">Режим безопасности настраивается с помощью дополнительного атрибута `securityMode`.</span><span class="sxs-lookup"><span data-stu-id="be6b5-180">The security behavior is configurable using the optional `securityMode` attribute.</span></span> <span data-ttu-id="be6b5-181">Использование WS-ReliableMessaging настраивается с использованием дополнительного атрибута `reliableSessionEnabled`.</span><span class="sxs-lookup"><span data-stu-id="be6b5-181">The use of WS-ReliableMessaging is configurable using the optional `reliableSessionEnabled` attribute.</span></span> <span data-ttu-id="be6b5-182">Но по умолчанию надежный обмен сообщениями отключен.</span><span class="sxs-lookup"><span data-stu-id="be6b5-182">But reliable messaging is off by default.</span></span> <span data-ttu-id="be6b5-183">В общем случае системные привязки по протоколу HTTP, такие как `wsHttpBinding` и `basicHttpBinding`, настроены на включение основных возможностей по умолчанию, в то время как привязка `netTcpBinding` по умолчанию отключает возможности, так что для получения поддержки, например для спецификаций WS-\*, необходимо специально их включить.</span><span class="sxs-lookup"><span data-stu-id="be6b5-183">More generally, the HTTP system-provided bindings such as `wsHttpBinding` and `basicHttpBinding` are configured to turn things on by default, whereas the `netTcpBinding` binding turns things off by default so that you have to opt-in to get support, for example, for one of the WS-\* specifications.</span></span> <span data-ttu-id="be6b5-184">Это означает, что используемая по умолчанию конфигурация для TCP быстрее при обмене сообщениями между конечными точками, чем конфигурация по умолчанию для привязок HTTP.</span><span class="sxs-lookup"><span data-stu-id="be6b5-184">This means that the default configuration for TCP is faster at exchanging messages between endpoints than those configured for the HTTP bindings by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="be6b5-185">Пример</span><span class="sxs-lookup"><span data-stu-id="be6b5-185">Example</span></span>

<span data-ttu-id="be6b5-186">Привязка задается в файлах конфигурации для клиента и службы.</span><span class="sxs-lookup"><span data-stu-id="be6b5-186">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="be6b5-187">Тип привязки указывается в атрибуте `binding` элемента `<endpoint>`.</span><span class="sxs-lookup"><span data-stu-id="be6b5-187">The binding type is specified in the `binding` attribute of the `<endpoint>` element.</span></span> <span data-ttu-id="be6b5-188">Если необходимо настроить привязку netTcpBinding и изменить некоторые из ее параметров, необходимо определить конфигурацию привязки.</span><span class="sxs-lookup"><span data-stu-id="be6b5-188">If you want to configure the netTcpBinding binding and change some of its settings, it is necessary to define a binding configuration.</span></span> <span data-ttu-id="be6b5-189">Конечная точка должна ссылаться на конфигурацию привязки с атрибутом `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="be6b5-189">The endpoint must reference the binding configuration with a `bindingConfiguration` attribute.</span></span> <span data-ttu-id="be6b5-190">В следующем примере определяется конфигурация привязки.</span><span class="sxs-lookup"><span data-stu-id="be6b5-190">In the following example, a binding configuration is defined.</span></span>  
  
```xml  
<services>
  <service name="Microsoft.ServiceModel.Samples.CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    ...
    <endpoint address=""
              binding="netTcpBinding"
              contract="Microsoft.ServiceModel.Samples.ICalculator" />
    ...
  </service>
</services>
<bindings>
  <netTcpBinding>
    <binding closeTimeout="00:01:00"
             openTimeout="00:01:00"
             receiveTimeout="00:10:00"
             sendTimeout="00:01:00"
             transactionFlow="false"
             transferMode="Buffered"
             transactionProtocol="OleTransactions"
             hostNameComparisonMode="StrongWildcard"
             listenBacklog="10"
             maxBufferPoolSize="524288"
             maxBufferSize="65536"
             maxConnections="10"
             maxReceivedMessageSize="65536">
      <readerQuotas maxDepth="32"
                    maxStringContentLength="8192"
                    maxArrayLength="16384"
                    maxBytesPerRead="4096"
                    maxNameTableCharCount="16384" />
      <reliableSession ordered="true"
                       inactivityTimeout="00:10:00"
                       enabled="false" />
      <security mode="Transport">
        <transport clientCredentialType="Windows" protectionLevel="EncryptAndSign" />
      </security>
    </binding>
  </netTcpBinding>
</bindings>
```  
  
## <a name="see-also"></a><span data-ttu-id="be6b5-191">См. также</span><span class="sxs-lookup"><span data-stu-id="be6b5-191">See also</span></span>

- <xref:System.ServiceModel.NetTcpBinding>
- <xref:System.ServiceModel.Configuration.NetTcpBindingElement>
- [<span data-ttu-id="be6b5-192">Привязки</span><span class="sxs-lookup"><span data-stu-id="be6b5-192">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="be6b5-193">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="be6b5-193">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="be6b5-194">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="be6b5-194">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
