---
title: <wsHttpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- wsHttpBinding Element
ms.assetid: 0eee8ced-ad68-427d-b95a-97260e98deed
ms.openlocfilehash: a71ad2a2279eabbcf917df58d7bedec0e728f9e5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "74140395"
---
# \<wsHttpBinding>
<span data-ttu-id="a6edd-101">Определяет безопасную, надежную, привязку с возможностью взаимодействия, которая может использоваться для недуплексных контрактов службы.</span><span class="sxs-lookup"><span data-stu-id="a6edd-101">Defines a secure, reliable, interoperable binding suitable for non-duplex service contracts.</span></span> <span data-ttu-id="a6edd-102">В привязке реализованы следующие возможности: обмен сообщениями WS-Reliable для обеспечения надежности, а также WS-Security для обеспечения безопасности и проверки подлинности сообщений.</span><span class="sxs-lookup"><span data-stu-id="a6edd-102">The binding implements the following specifications: WS-Reliable Messaging for reliability, and WS-Security for message security and authentication.</span></span> <span data-ttu-id="a6edd-103">В качестве транспорта используется HTTP, а для кодировки сообщений — кодировка Text/XML.</span><span class="sxs-lookup"><span data-stu-id="a6edd-103">The transport is HTTP, and message encoding is Text/XML encoding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsHttpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="a6edd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a6edd-104">Syntax</span></span>  
  
```xml  
<wsHttpBinding>
  <binding allowCookies="Boolean"
           bypassProxyOnLocal="Boolean"
           closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
           maxBufferPoolSize="integer"
           maxReceivedMessageSize="Integer"
           messageEncoding="Text/Mtom"
           name="string"
           openTimeout="TimeSpan"
           proxyAddress="URI"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"
           transactionFlow="Boolean"
           useDefaultWebProxy="Boolean">
    <reliableSession ordered="Boolean"
                     inactivityTimeout="TimeSpan"
                     enabled="Boolean" />
    <security mode="Message/None/Transport/TransportWithCredential">
      <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
                 proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
                 realm="string" />
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
               establishSecurityContext="Boolean"
               negotiateServiceCredential="Boolean" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</wsHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a6edd-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a6edd-105">Attributes and Elements</span></span>  
 <span data-ttu-id="a6edd-106">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a6edd-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a6edd-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a6edd-107">Attributes</span></span>  
  
|<span data-ttu-id="a6edd-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a6edd-108">Attribute</span></span>|<span data-ttu-id="a6edd-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="a6edd-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a6edd-110">allowCookies</span><span class="sxs-lookup"><span data-stu-id="a6edd-110">allowCookies</span></span>|<span data-ttu-id="a6edd-111">Логическое значение, определяющее, принимает ли клиент файлы Cookie и распространяет ли он их на будущие запросы.</span><span class="sxs-lookup"><span data-stu-id="a6edd-111">A Boolean value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="a6edd-112">Значение по умолчанию – false.</span><span class="sxs-lookup"><span data-stu-id="a6edd-112">The default is false.</span></span><br /><br /> <span data-ttu-id="a6edd-113">Это свойство можно использовать при взаимодействии с веб-службами ASMX, которые используют файлы Cookie.</span><span class="sxs-lookup"><span data-stu-id="a6edd-113">You can use this property when you interact with ASMX Web services that use cookies.</span></span> <span data-ttu-id="a6edd-114">В этом случае можно быть уверенным, что файлы cookie, возвращаемые с сервера, автоматически копируются во все последующие клиентские запросы к этой службе.</span><span class="sxs-lookup"><span data-stu-id="a6edd-114">In this way, you can be sure that the cookies returned from the server are automatically copied to all future client requests for that service.</span></span>|  
|<span data-ttu-id="a6edd-115">bypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="a6edd-115">bypassProxyOnLocal</span></span>|<span data-ttu-id="a6edd-116">Логическое значение, определяющее, будет ли выполняться обход прокси-сервера для локальных адресов.</span><span class="sxs-lookup"><span data-stu-id="a6edd-116">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="a6edd-117">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="a6edd-117">The default is `false`.</span></span>|  
|<span data-ttu-id="a6edd-118">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="a6edd-118">closeTimeout</span></span>|<span data-ttu-id="a6edd-119">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="a6edd-119">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="a6edd-120">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="a6edd-120">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a6edd-121">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="a6edd-121">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="a6edd-122">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="a6edd-122">hostnameComparisonMode</span></span>|<span data-ttu-id="a6edd-123">Задает режим сравнения имен узлов HTTP для анализа универсальных кодов ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="a6edd-123">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="a6edd-124">Это атрибут типа <xref:System.ServiceModel.HostNameComparisonMode>, который указывает, используется ли имя узла для доступа к службе при сравнении по универсальному коду ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="a6edd-124">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="a6edd-125">Значение по умолчанию — <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, при котором имя узла в найденном соответствии не используется.</span><span class="sxs-lookup"><span data-stu-id="a6edd-125">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|<span data-ttu-id="a6edd-126">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="a6edd-126">maxBufferPoolSize</span></span>|<span data-ttu-id="a6edd-127">Целое число, задающее максимальный размер буферного пула для этой привязки.</span><span class="sxs-lookup"><span data-stu-id="a6edd-127">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="a6edd-128">Значение по умолчанию - 524 288 байт (512 \* 1024).</span><span class="sxs-lookup"><span data-stu-id="a6edd-128">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="a6edd-129">Многие элементы Windows Communication Foundation (WCF) используют буферы.</span><span class="sxs-lookup"><span data-stu-id="a6edd-129">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="a6edd-130">При создании буферов и их уничтожении после каждого использования расходуется слишком много ресурсов; при сборке мусора для буферов также расходуется слишком много ресурсов.</span><span class="sxs-lookup"><span data-stu-id="a6edd-130">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="a6edd-131">Буферные пулы позволяют брать буфер из пула, использовать его, а затем возвращать обратно, когда он больше не требуется.</span><span class="sxs-lookup"><span data-stu-id="a6edd-131">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="a6edd-132">Это позволяет избежать излишней нагрузки, связанной с созданием и уничтожением буферов.</span><span class="sxs-lookup"><span data-stu-id="a6edd-132">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="a6edd-133">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="a6edd-133">maxReceivedMessageSize</span></span>|<span data-ttu-id="a6edd-134">Положительное целое число, задающее, в байтах, максимальный размер сообщения (включая заголовки), которое можно получить по каналу, настроенному с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="a6edd-134">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="a6edd-135">Отправитель сообщения, превышающего это ограничение, получит ошибку SOAP.</span><span class="sxs-lookup"><span data-stu-id="a6edd-135">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="a6edd-136">Получатель отклоняет сообщение и создает запись о событии в журнале трассировки.</span><span class="sxs-lookup"><span data-stu-id="a6edd-136">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="a6edd-137">Значение по умолчанию — 65536.</span><span class="sxs-lookup"><span data-stu-id="a6edd-137">The default is 65536.</span></span>|  
|<span data-ttu-id="a6edd-138">messageEncoding</span><span class="sxs-lookup"><span data-stu-id="a6edd-138">messageEncoding</span></span>|<span data-ttu-id="a6edd-139">Определяет кодировщик, используемый для кодировки сообщения.</span><span class="sxs-lookup"><span data-stu-id="a6edd-139">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="a6edd-140">Допустимые значения.</span><span class="sxs-lookup"><span data-stu-id="a6edd-140">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a6edd-141">-Text: использование кодировщика текстовых сообщений.</span><span class="sxs-lookup"><span data-stu-id="a6edd-141">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="a6edd-142">-MTOM: используйте кодировщик обмена сообщениями, механизм передачи сообщений 1,0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="a6edd-142">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><span data-ttu-id="a6edd-143">— Значение по умолчанию — Text.</span><span class="sxs-lookup"><span data-stu-id="a6edd-143">-   The default is Text.</span></span><br /><br /> <span data-ttu-id="a6edd-144">Это атрибут типа <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="a6edd-144">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|<span data-ttu-id="a6edd-145">name</span><span class="sxs-lookup"><span data-stu-id="a6edd-145">name</span></span>|<span data-ttu-id="a6edd-146">Строка, содержащая имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="a6edd-146">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="a6edd-147">Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.</span><span class="sxs-lookup"><span data-stu-id="a6edd-147">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="a6edd-148">Начиная с .NET Framework 4, привязки и поведения не обязательно должны иметь имя.</span><span class="sxs-lookup"><span data-stu-id="a6edd-148">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="a6edd-149">Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="a6edd-149">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="a6edd-150">openTimeout</span><span class="sxs-lookup"><span data-stu-id="a6edd-150">openTimeout</span></span>|<span data-ttu-id="a6edd-151">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="a6edd-151">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="a6edd-152">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="a6edd-152">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a6edd-153">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="a6edd-153">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="a6edd-154">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="a6edd-154">proxyAddress</span></span>|<span data-ttu-id="a6edd-155">Универсальный код ресурса (URI), задающий адрес прокси-сервера HTTP.</span><span class="sxs-lookup"><span data-stu-id="a6edd-155">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="a6edd-156">Если параметр `useSystemWebProxy` имеет значение `true`, данный параметр должен иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="a6edd-156">If `useSystemWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="a6edd-157">Значение по умолчанию — `null`.</span><span class="sxs-lookup"><span data-stu-id="a6edd-157">The default is `null`.</span></span>|  
|<span data-ttu-id="a6edd-158">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="a6edd-158">receiveTimeout</span></span>|<span data-ttu-id="a6edd-159">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="a6edd-159">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="a6edd-160">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="a6edd-160">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a6edd-161">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="a6edd-161">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="a6edd-162">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="a6edd-162">sendTimeout</span></span>|<span data-ttu-id="a6edd-163">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="a6edd-163">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="a6edd-164">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="a6edd-164">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a6edd-165">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="a6edd-165">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="a6edd-166">textEncoding</span><span class="sxs-lookup"><span data-stu-id="a6edd-166">textEncoding</span></span>|<span data-ttu-id="a6edd-167">Задает кодировку, используемую при отправке сообщений через привязку.</span><span class="sxs-lookup"><span data-stu-id="a6edd-167">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="a6edd-168">Допустимые значения.</span><span class="sxs-lookup"><span data-stu-id="a6edd-168">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a6edd-169">-Уникодефффетекстенкодинг: Юникод байтов Encoding.</span><span class="sxs-lookup"><span data-stu-id="a6edd-169">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="a6edd-170">-Utf16TextEncoding: 16-разрядная кодировка.</span><span class="sxs-lookup"><span data-stu-id="a6edd-170">-   Utf16TextEncoding: 16-bit encoding.</span></span><br /><span data-ttu-id="a6edd-171">-Utf8TextEncoding: 8-разрядная кодировка.</span><span class="sxs-lookup"><span data-stu-id="a6edd-171">-   Utf8TextEncoding: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="a6edd-172">Значение по умолчанию - Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="a6edd-172">The default is Utf8TextEncoding.</span></span><br /><br /> <span data-ttu-id="a6edd-173">Это атрибут типа <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="a6edd-173">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|<span data-ttu-id="a6edd-174">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="a6edd-174">transactionFlow</span></span>|<span data-ttu-id="a6edd-175">Логическое значение, определяющее, поддерживает ли привязка потоковые спецификации WS-Transactions.</span><span class="sxs-lookup"><span data-stu-id="a6edd-175">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="a6edd-176">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="a6edd-176">The default is `false`.</span></span>|  
|<span data-ttu-id="a6edd-177">useDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="a6edd-177">useDefaultWebProxy</span></span>|<span data-ttu-id="a6edd-178">Логическое значение, определяющее, должен ли использоваться автоматически настроенный системный прокси-сервер HTTP.</span><span class="sxs-lookup"><span data-stu-id="a6edd-178">A Boolean value that specifies whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="a6edd-179">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="a6edd-179">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a6edd-180">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a6edd-180">Child Elements</span></span>  
  
|<span data-ttu-id="a6edd-181">Элемент</span><span class="sxs-lookup"><span data-stu-id="a6edd-181">Element</span></span>|<span data-ttu-id="a6edd-182">Описание</span><span class="sxs-lookup"><span data-stu-id="a6edd-182">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-wshttpbinding.md)|<span data-ttu-id="a6edd-183">Определяет параметры безопасности привязки.</span><span class="sxs-lookup"><span data-stu-id="a6edd-183">Defines the security settings for the binding.</span></span> <span data-ttu-id="a6edd-184">Это элемент типа <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="a6edd-184">This element is of type <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.</span></span>|  
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="a6edd-185">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="a6edd-185">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="a6edd-186">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="a6edd-186">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))|<span data-ttu-id="a6edd-187">Указывает, устанавливаются ли между конечными точками канала надежные сеансы.</span><span class="sxs-lookup"><span data-stu-id="a6edd-187">Specifies if reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a6edd-188">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a6edd-188">Parent Elements</span></span>  
  
|<span data-ttu-id="a6edd-189">Элемент</span><span class="sxs-lookup"><span data-stu-id="a6edd-189">Element</span></span>|<span data-ttu-id="a6edd-190">Описание</span><span class="sxs-lookup"><span data-stu-id="a6edd-190">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="a6edd-191">Этот элемент содержит коллекцию стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="a6edd-191">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6edd-192">Примечания</span><span class="sxs-lookup"><span data-stu-id="a6edd-192">Remarks</span></span>  
 <span data-ttu-id="a6edd-193">Привязка `WSHttpBinding` аналогична привязке `BasicHttpBinding`, но при этом предоставляет больше функциональных возможностей веб-служб.</span><span class="sxs-lookup"><span data-stu-id="a6edd-193">The `WSHttpBinding` is similar to the `BasicHttpBinding` but provides more Web service features.</span></span> <span data-ttu-id="a6edd-194">В ней используется транспорт HTTP и обеспечивается безопасность сообщения, как и в привязке BasicHttpBinding, но вместе с тем также предоставляются транзакции, надежный обмен сообщениями и WS-Addressing, включенные по умолчанию или доступные посредством одного управляющего параметра.</span><span class="sxs-lookup"><span data-stu-id="a6edd-194">It uses the HTTP transport and provides message security, as does BasicHttpBinding, but it also provides transactions, reliable messaging, and WS-Addressing, either enabled by default or available through a single control setting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6edd-195">Пример</span><span class="sxs-lookup"><span data-stu-id="a6edd-195">Example</span></span>  
  
```xml  
<configuration>
  <system.ServiceModel>
    <bindings>
      <wsHttpBinding>
        <binding closeTimeout="00:00:10"
                 openTimeout="00:00:20"
                 receiveTimeout="00:00:30"
                 sendTimeout="00:00:40"
                 bypassProxyOnLocal="false"
                 transactionFlow="false"
                 hostNameComparisonMode="WeakWildcard"
                 maxReceivedMessageSize="1000"
                 messageEncoding="Mtom"
                 proxyAddress="http://foo/bar"
                 textEncoding="utf-16"
                 useDefaultWebProxy="false">
          <reliableSession ordered="false"
                           inactivityTimeout="00:02:00"
                           enabled="true" />
          <security mode="Transport">
            <transport clientCredentialType="Digest"
                       proxyCredentialType="None"
                       realm="someRealm" />
            <message clientCredentialType="Windows"
                     negotiateServiceCredential="false"
                     algorithmSuite="Aes128"
                     defaultProtectionLevel="None" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="a6edd-196">См. также</span><span class="sxs-lookup"><span data-stu-id="a6edd-196">See also</span></span>

- <xref:System.ServiceModel.WSHttpBinding>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement>
- [<span data-ttu-id="a6edd-197">Привязки</span><span class="sxs-lookup"><span data-stu-id="a6edd-197">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a6edd-198">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="a6edd-198">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="a6edd-199">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="a6edd-199">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
