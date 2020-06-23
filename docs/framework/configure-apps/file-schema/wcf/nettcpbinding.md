---
title: <netTcpBinding>
description: Представляет безопасную, надежную, оптимизированную привязку, предназначенную только для обмена данными между компьютерами WCF по протоколу TCP. По умолчанию надежный обмен сообщениями отключен.
ms.date: 03/30/2017
helpviewer_keywords:
- netTcpBinding Element
ms.assetid: 5c5104a7-8754-4335-8233-46a45322503e
ms.openlocfilehash: 95c2c691bf328050f3d189c790d111d2fdeb1bb0
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244001"
---
# \<netTcpBinding>

<span data-ttu-id="e1f4b-103">Задает безопасную, надежную и оптимизированную привязку, пригодную для обмена данными между компьютерами.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-103">Specifies a secure, reliable, optimized binding suitable for cross-machine communication.</span></span> <span data-ttu-id="e1f4b-104">По умолчанию создает стек связи среды выполнения с безопасностью Windows для защиты и проверки подлинности сообщений, с протоколом TCP для доставки сообщений, а также с кодированием двоичных сообщений.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-104">By default, it generates a runtime communication stack with Windows Security for message security and authentication, TCP for message delivery, and binary message encoding.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<netTcpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="e1f4b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e1f4b-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e1f4b-106">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="e1f4b-106">Attributes and elements</span></span>

<span data-ttu-id="e1f4b-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e1f4b-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e1f4b-108">Attributes</span></span>  
  
|<span data-ttu-id="e1f4b-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e1f4b-109">Attribute</span></span>|<span data-ttu-id="e1f4b-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="e1f4b-110">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="e1f4b-111">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-111">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="e1f4b-112">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-112">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e1f4b-113">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-113">The default is 00:01:00.</span></span>|  
|`hostNameComparisonMode`|<span data-ttu-id="e1f4b-114">Задает режим сравнения имен узлов HTTP для анализа универсальных кодов ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="e1f4b-114">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="e1f4b-115">Это атрибут типа <xref:System.ServiceModel.HostNameComparisonMode>, который указывает, используется ли имя узла для доступа к службе при сравнении по универсальному коду ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="e1f4b-115">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="e1f4b-116">Значение по умолчанию — <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, при котором имя узла в найденном соответствии не используется.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-116">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|`listenBacklog`|<span data-ttu-id="e1f4b-117">Положительное целое число, указывающее максимальное число каналов, ожидающих принятия прослушивателем.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-117">A positive integer that specifies the maximum number of channels waiting to be accepted on the listener.</span></span> <span data-ttu-id="e1f4b-118">Соединения сверх этого лимита помещаются в очередь и обрабатываются по мере освобождения ресурсов.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-118">Connections in excess of this limit are queued until space below the limit becomes available.</span></span> <span data-ttu-id="e1f4b-119">Атрибут `connectionTimeout` ограничивает время, в течение которого клиент ожидает установления соединения до создания исключения подключения.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-119">The `connectionTimeout` attribute limits the time a client will wait to be connected before throwing a connection exception.</span></span> <span data-ttu-id="e1f4b-120">Значение по умолчанию равно 10.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-120">The default is 10.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="e1f4b-121">Целое число, задающее максимальный размер буферного пула для этой привязки.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-121">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="e1f4b-122">Значение по умолчанию - 512 \* 1024 байт.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-122">The default is 512 \* 1024 bytes.</span></span> <span data-ttu-id="e1f4b-123">Многие элементы Windows Communication Foundation (WCF) используют буферы.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-123">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="e1f4b-124">При создании буферов и их уничтожении после каждого использования расходуется слишком много ресурсов; при сборке мусора для буферов также расходуется слишком много ресурсов.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-124">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="e1f4b-125">Буферные пулы позволяют брать буфер из пула, использовать его, а затем возвращать обратно, когда он больше не требуется.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-125">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="e1f4b-126">Это позволяет избежать излишней нагрузки, связанной с созданием и уничтожением буферов.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-126">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="e1f4b-127">Положительное целое число, указывающее максимальный размер буфера, используемого для хранения сообщений в памяти (в байтах).</span><span class="sxs-lookup"><span data-stu-id="e1f4b-127">A positive integer that specifies the maximum size, in bytes, of the buffer used to store messages in memory.</span></span><br /><br /> <span data-ttu-id="e1f4b-128">Если атрибут `transferMode` имеет значение `Buffered`, этот атрибут должен быть равен значению атрибута `maxReceivedMessageSize`.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-128">If the `transferMode` attribute equals to `Buffered`, this attribute should be equal to the `maxReceivedMessageSize` attribute value.</span></span><br /><br /> <span data-ttu-id="e1f4b-129">Если атрибут `transferMode` имеет значение `Streamed`, этот атрибут не может иметь значение большее, чем значение атрибута `maxReceivedMessageSize`, и должен иметь размер, по крайней мере равный размеру заголовков.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-129">If the `transferMode` attribute equals to `Streamed`, this attribute cannot be more than the `maxReceivedMessageSize` attribute value, and should be at least the size of the headers.</span></span><br /><br /> <span data-ttu-id="e1f4b-130">Значение по умолчанию — 65536.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-130">The default is 65536.</span></span> <span data-ttu-id="e1f4b-131">Для получения дополнительной информации см. <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-131">For more information, see <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>.</span></span>|  
|`maxConnections`|<span data-ttu-id="e1f4b-132">Целое число, указывающее максимальное число входящих и исходящих подключений, которые будут созданы/приняты службой.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-132">An integer that specifies the maximum number of outbound and inbound connections the service will create/accept.</span></span> <span data-ttu-id="e1f4b-133">Входящие и исходящие подключения считаются относительно отдельного предела, определенного этим атрибутом.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-133">Incoming and outgoing connections are counted against a separate limit specified by this attribute.</span></span><br /><br /> <span data-ttu-id="e1f4b-134">Входящие соединения сверх указанного предела помещаются в очередь и обрабатываются по мере освобождения ресурсов.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-134">Inbound connections in excess of the limit are queued until a space below the limit becomes available.</span></span><br /><br /> <span data-ttu-id="e1f4b-135">Исходящие соединения сверх указанного предела помещаются в очередь и обрабатываются по мере освобождения ресурсов.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-135">Outbound connections in excess of the limit are queued until a space below the limit becomes available.</span></span><br /><br /> <span data-ttu-id="e1f4b-136">Значение по умолчанию равно 10.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-136">The default is 10.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="e1f4b-137">Положительное целое число, задающее, в байтах, максимальный размер сообщения (включая заголовки), которое можно получить по каналу, настроенному с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-137">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="e1f4b-138">Отправитель сообщения, превышающего это ограничение, получит ошибку SOAP.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-138">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="e1f4b-139">Получатель отклоняет сообщение и создает запись о событии в журнале трассировки.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-139">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="e1f4b-140">Значение по умолчанию — 65536.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-140">The default is 65536.</span></span>|  
|`name`|<span data-ttu-id="e1f4b-141">Строка, содержащая имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-141">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="e1f4b-142">Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-142">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="e1f4b-143">Начиная с .NET Framework 4, привязки и поведения не обязательно должны иметь имя.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-143">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="e1f4b-144">Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="e1f4b-144">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="e1f4b-145">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-145">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="e1f4b-146">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-146">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e1f4b-147">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-147">The default is 00:01:00.</span></span>|  
|`portSharingEnabled`|<span data-ttu-id="e1f4b-148">Логическое значение, определяющее, включено ли совместное использование порта TCP для этого подключения.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-148">A Boolean value that specifies whether TCP port sharing is enabled for this connection.</span></span> <span data-ttu-id="e1f4b-149">Если атрибут имеет значение `false`, для каждой привязки используется собственный порт.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-149">If this is `false`, each binding uses its own exclusive port.</span></span> <span data-ttu-id="e1f4b-150">Этот параметр действителен только для служб, так как он не затрагивает клиенты.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-150">This setting is relevant only to services, because clients are not affected.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="e1f4b-151">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-151">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="e1f4b-152">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-152">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e1f4b-153">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-153">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="e1f4b-154">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-154">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="e1f4b-155">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-155">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e1f4b-156">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-156">The default is 00:01:00.</span></span>|  
|`transactionFlow`|<span data-ttu-id="e1f4b-157">Логическое значение, определяющее, поддерживает ли привязка потоковые спецификации WS-Transactions.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-157">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="e1f4b-158">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-158">The default is `false`.</span></span>|  
|`transactionProtocol`|<span data-ttu-id="e1f4b-159">Указывает протокол транзакций, используемый с данной привязкой.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-159">Specifies the transaction protocol to be used with this binding.</span></span> <span data-ttu-id="e1f4b-160">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="e1f4b-160">Valid values are</span></span><br /><br /> <span data-ttu-id="e1f4b-161">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="e1f4b-161">-   OleTransactions</span></span><br /><span data-ttu-id="e1f4b-162">-WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="e1f4b-162">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="e1f4b-163">Значение по умолчанию - OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-163">The default is OleTransactions.</span></span> <span data-ttu-id="e1f4b-164">Это атрибут типа <xref:System.ServiceModel.TransactionProtocol>.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-164">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
|`transferMode`|<span data-ttu-id="e1f4b-165">Значение <xref:System.ServiceModel.TransferMode>, которое указывает, следует ли помещать сообщения в буфер или передавать их потоком по запросу или отклику.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-165">A <xref:System.ServiceModel.TransferMode> value that specifies whether messages are buffered or streamed or a request or response.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e1f4b-166">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e1f4b-166">Child elements</span></span>  
  
|<span data-ttu-id="e1f4b-167">Элемент</span><span class="sxs-lookup"><span data-stu-id="e1f4b-167">Element</span></span>|<span data-ttu-id="e1f4b-168">Описание</span><span class="sxs-lookup"><span data-stu-id="e1f4b-168">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-nettcpbinding.md)|<span data-ttu-id="e1f4b-169">Определяет параметры безопасности привязки.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-169">Defines the security settings for the binding.</span></span> <span data-ttu-id="e1f4b-170">Это элемент типа <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-170">This element is of type <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>.</span></span>|  
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="e1f4b-171">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-171">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="e1f4b-172">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-172">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))|<span data-ttu-id="e1f4b-173">Указывает, устанавливаются ли между конечными точками канала надежные сеансы.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-173">Specifies if reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e1f4b-174">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e1f4b-174">Parent elements</span></span>  
  
|<span data-ttu-id="e1f4b-175">Элемент</span><span class="sxs-lookup"><span data-stu-id="e1f4b-175">Element</span></span>|<span data-ttu-id="e1f4b-176">Описание</span><span class="sxs-lookup"><span data-stu-id="e1f4b-176">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="e1f4b-177">Этот элемент содержит коллекцию стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-177">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1f4b-178">Комментарии</span><span class="sxs-lookup"><span data-stu-id="e1f4b-178">Remarks</span></span>

<span data-ttu-id="e1f4b-179">Эта привязка создает стек связи времени выполнения по умолчанию, использующий режим безопасности транспорта, протокол TCP для доставки сообщений, а также кодирование двоичных сообщений.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-179">This binding generates a run-time communication stack by default, which uses transport security, TCP for message delivery, and a binary message encoding.</span></span> <span data-ttu-id="e1f4b-180">Эта привязка является подходящей системой Windows Communication Foundation (WCF), предоставляемой для взаимодействия через интрасеть.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-180">This binding is an appropriate Windows Communication Foundation (WCF) system-provided choice for communicating over an Intranet.</span></span>  
  
 <span data-ttu-id="e1f4b-181">Конфигурация по умолчанию для `netTcpBinding` работает быстрее, чем конфигурация, предоставляемая `wsHttpBinding` , но она предназначена только для взаимодействия WCF.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-181">The default configuration for the `netTcpBinding` is faster than the configuration provided by the `wsHttpBinding`, but it is intended only for WCF communication.</span></span> <span data-ttu-id="e1f4b-182">Режим безопасности настраивается с помощью дополнительного атрибута `securityMode`.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-182">The security behavior is configurable using the optional `securityMode` attribute.</span></span> <span data-ttu-id="e1f4b-183">Использование WS-ReliableMessaging настраивается с использованием дополнительного атрибута `reliableSessionEnabled`.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-183">The use of WS-ReliableMessaging is configurable using the optional `reliableSessionEnabled` attribute.</span></span> <span data-ttu-id="e1f4b-184">Но по умолчанию надежный обмен сообщениями отключен.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-184">But reliable messaging is off by default.</span></span> <span data-ttu-id="e1f4b-185">В общем случае системные привязки по протоколу HTTP, такие как `wsHttpBinding` и `basicHttpBinding`, настроены на включение основных возможностей по умолчанию, в то время как привязка `netTcpBinding` по умолчанию отключает возможности, так что для получения поддержки, например для спецификаций WS-\*, необходимо специально их включить.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-185">More generally, the HTTP system-provided bindings such as `wsHttpBinding` and `basicHttpBinding` are configured to turn things on by default, whereas the `netTcpBinding` binding turns things off by default so that you have to opt-in to get support, for example, for one of the WS-\* specifications.</span></span> <span data-ttu-id="e1f4b-186">Это означает, что используемая по умолчанию конфигурация для TCP быстрее при обмене сообщениями между конечными точками, чем конфигурация по умолчанию для привязок HTTP.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-186">This means that the default configuration for TCP is faster at exchanging messages between endpoints than those configured for the HTTP bindings by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1f4b-187">Пример</span><span class="sxs-lookup"><span data-stu-id="e1f4b-187">Example</span></span>

<span data-ttu-id="e1f4b-188">Привязка задается в файлах конфигурации для клиента и службы.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-188">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="e1f4b-189">Тип привязки указывается в атрибуте `binding` элемента `<endpoint>`.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-189">The binding type is specified in the `binding` attribute of the `<endpoint>` element.</span></span> <span data-ttu-id="e1f4b-190">Если необходимо настроить привязку netTcpBinding и изменить некоторые из ее параметров, необходимо определить конфигурацию привязки.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-190">If you want to configure the netTcpBinding binding and change some of its settings, it is necessary to define a binding configuration.</span></span> <span data-ttu-id="e1f4b-191">Конечная точка должна ссылаться на конфигурацию привязки с атрибутом `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-191">The endpoint must reference the binding configuration with a `bindingConfiguration` attribute.</span></span> <span data-ttu-id="e1f4b-192">В следующем примере определяется конфигурация привязки.</span><span class="sxs-lookup"><span data-stu-id="e1f4b-192">In the following example, a binding configuration is defined.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e1f4b-193">См. также</span><span class="sxs-lookup"><span data-stu-id="e1f4b-193">See also</span></span>

- <xref:System.ServiceModel.NetTcpBinding>
- <xref:System.ServiceModel.Configuration.NetTcpBindingElement>
- [<span data-ttu-id="e1f4b-194">Привязки</span><span class="sxs-lookup"><span data-stu-id="e1f4b-194">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e1f4b-195">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="e1f4b-195">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e1f4b-196">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="e1f4b-196">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
