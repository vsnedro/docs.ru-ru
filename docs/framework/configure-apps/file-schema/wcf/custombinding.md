---
title: <customBinding>
ms.date: 03/30/2017
ms.assetid: 9da4f960-f64e-4d8a-894d-2b09eba5ce4b
ms.openlocfilehash: cdaaacf0dfa75209d001f6e8d6ac7175816048aa
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "74140794"
---
# \<customBinding>

<span data-ttu-id="e150a-101">Обеспечивает пользователю полный контроль над стеком обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="e150a-101">Provides full control over the messaging stack for the user.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customBinding>**  

## <a name="syntax"></a><span data-ttu-id="e150a-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e150a-102">Syntax</span></span>

```xml
<customBinding>
  <binding name="String"
           closeTimeout="TimeSpan"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan">
    <compositeDuplex clientBaseAddress="Uri" />
    <reliableSession acknowledgementInterval="TimeSpan"
                     advancedFlowControl="Boolean"
                     bufferedMessagesQuota="Integer"
                     inactivityTimeout="TimeSpan"
                     maxPendingChannels="Integer"
                     maxRetryCount="Integer"
                     ordered="Boolean" />
    <pnrpPeerResolver />
    <windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
    <sslStreamSecurity requireClientCertificate="Boolean" />
    <transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004" />
    <security defaultAlgorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
              authenticationMode="UserNameForAnonymous"
              contextMode="Cookie"
              defaultProtectionLevel="Sign"
              enableKeyDerivation="false"
              keyEntropyMode="ClientEntropy"
              messageProtectionOrder="SignBeforeEncryptAndEncryptSignature"
              securityVersion="WSSecurityXXX2005">
      <localClientSettings cacheCookies="false"
                           detectReplays="false"
                           maxCookieCachingTime="00:07:24" />
      <localServiceSettings replayCacheSize="9"
                            maxClockSkew="00:00:03"
                            replayWindow="00:07:22.2190000" />
    </security>
    <binaryMessageEncoding maxReadPoolSize="Integer"
                           maxWritePoolSize="Integer"
                           maxSessionSize="Integer" />
    <httpsTransport manualAddressing="Boolean"
                    maxMessageSize="Integer"
                    authenticationScheme="Negotiate"
                    bypassProxyOnLocal="Boolean"
                    hostNameComparisonMode="Exact"
                    mapAddressingHeadersToHttpHeaders="Boolean"
                    proxyaddress="Uri"
                    realm="String"
                    requireClientCertificate="Boolean" />
    <peerTransport manualAddressing="false"
                   maxMessageSize="20002"
                   listenIPAddress="202.10.1.9"
                   messageAuthentication="false"
                   peerNodeAuthenticationMode="None"
                   port="1000" />
    <security defaultAlgorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
              authenticationMode="UserNameForAnonymous"
              bootstrapBindingConfiguration="String"
              bootstrapBindingSectionName="String"
              defaultProtectionLevel="None/Sign/EncryptAndSign"
              requireDerivedKeys="Boolean"
              securityHeaderLayout="Strict/Lax/LaxTimestampFirst/LaxTimestampLast"
              includeTimestamp="Boolean"
              keyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"
              messageProtectionOrder="SignBeforeEncrypt/SignBeforeEncryptAndEncryptSignature/EncryptBeforeSign"
              protectTokens="Boolean"
              requireSecurityContextCancellation="Boolean"
              securityVersion=" WSSecurityJan2004/WSSecurityXXX2005"
              requireSignatureConfirmation="Boolean">
      <localClientSettings cacheCookies="Boolean"
                           detectReplays="Boolean"
                           replayCacheSize="Integer"
                           maxClockSkew="TimeSpan"
                           maxCookieCachingTime="TimeSpan"
                           replayWindow="TimeSpan"
                           sessionKeyRenewalInterval="TimeSpan"
                           sessionKeyRolloverInterval="TimeSpan"
                           reconnectOnTransportFailure="Boolean"
                           timestampValidityDuration="TimeSpan"
                           cookieRenewalThresholdPercentage="Integer" />
      <localServiceSettings detectReplays="Boolean"
                            issuedCookieLifeTime="TimeSpan"
                            maxStatefulNegotiations="Integer"
                            replayCacheSize="Integer"
                            maxClockSkew="TimeSpan"
                            negotiationTimeout="TimeSpan"
                            replayWindow="TimeSpan"
                            inactivityTimeout="TimeSpan"
                            sessionKeyRenewalInterval="TimeSpan"
                            sessionKeyRolloverInterval="TimeSpan"
                            reconnectOnTransportFailure="Boolean"
                            maxConcurrentSessions="Integer"
                            timestampValidityDuration="TimeSpan" />
      <federationParameters trustVersion="WSTrustApr2004/WSTrustFeb2005" />
    </security>
    <security defaultAlgorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
              authenticationMode="UserNameForAnonymous"
              bootstrapBindingConfiguration="String"
              bootstrapBindingSectionName="String"
              defaultProtectionLevel="None/Sign/EncryptAndSign"
              requireDerivedKeys="Boolean"
              securityHeaderLayout="Strict/Lax/LaxTimestampFirst/LaxTimestampLast"
              includeTimestamp="Boolean"
              keyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"
              messageProtectionOrder="SignBeforeEncrypt/SignBeforeEncryptAndEncryptSignature/EncryptBeforeSign"
              protectTokens="Boolean"
              requireSecurityContextCancellation="Boolean"
              securityVersion=" WSSecurityJan2004/WSSecurityXXX2005"
              requireSignatureConfirmation="Boolean" >
      <localClientSettings cacheCookies="Boolean"
                           detectReplays="Boolean"
                           replayCacheSize="Integer"
                           maxClockSkew="TimeSpan"
                           maxCookieCachingTime="TimeSpan"
                           replayWindow="TimeSpan"
                           sessionKeyRenewalInterval="TimeSpan"
                           sessionKeyRolloverInterval="TimeSpan"
                           reconnectOnTransportFailure="Boolean"
                           timestampValidityDuration="TimeSpan"
                           cookieRenewalThresholdPercentage="Integer" />
      <localServiceSettings detectReplays="Boolean"
                           issuedCookieLifeTime="TimeSpan"
                           maxStatefulNegotiations="Integer"
                           replayCacheSize="Integer"
                           maxClockSkew="TimeSpan"
                           negotiationTimeout="TimeSpan"
                           replayWindow="TimeSpan"
                           inactivityTimeout="TimeSpan"
                           sessionKeyRenewalInterval="TimeSpan"
                           sessionKeyRolloverInterval="TimeSpan"
                           reconnectOnTransportFailure="Boolean"
                           maxConcurrentSessions="Integer"
                           timestampValidityDuration="TimeSpan" />
      <federationParameters trustVersion="WSTrustApr2004/WSTrustFeb2005" />
      <genericIssuedTokenParameters>
        <localIssuerIssuedTokenParameters keyType="SymmetricKey/PublicKey"
                                          keySize="Integer"
                                          tokenType="String" />
        <issuedTokenParametersEndpointAddress address="URI"
                                              bindingConfiguration="String"
                                              binding="String" />
        <issuedTokenClient localIssuerChannelBehaviors="String"
                           cacheIssuedTokens="Boolean"
                           maxIssuedTokenCachingTime="TimeSpan"
                           keyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy" />
        <issuedTokenClientBehavior issuerAddress="String"
                                   behaviorConfiguration="String" />
        <issuedTokenClientBehavior address="URI"
                                   bindingConfiguration="String"
                                   binding="String" />
      </genericIssuedTokenParameters>
    </security>
  </binding>
</customBinding>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e150a-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e150a-103">Attributes and Elements</span></span>

<span data-ttu-id="e150a-104">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e150a-104">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="e150a-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e150a-105">Attributes</span></span>

|<span data-ttu-id="e150a-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e150a-106">Attribute</span></span>|<span data-ttu-id="e150a-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="e150a-107">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="e150a-108">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="e150a-108">closeTimeout</span></span>|<span data-ttu-id="e150a-109">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="e150a-109">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="e150a-110">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="e150a-110">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e150a-111">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="e150a-111">The default is 00:01:00.</span></span>|
|<span data-ttu-id="e150a-112">name</span><span class="sxs-lookup"><span data-stu-id="e150a-112">name</span></span>|<span data-ttu-id="e150a-113">Строка, содержащая имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="e150a-113">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="e150a-114">Это значение является определяемой пользователем строкой, которая используется как строка идентификации для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="e150a-114">This value is a user-defined string that acts as the identification string for the custom binding.</span></span> <span data-ttu-id="e150a-115">Начиная с .NET Framework 4, привязки и поведения не обязательно должны иметь имя.</span><span class="sxs-lookup"><span data-stu-id="e150a-115">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="e150a-116">Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="e150a-116">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|
|<span data-ttu-id="e150a-117">openTimeout</span><span class="sxs-lookup"><span data-stu-id="e150a-117">openTimeout</span></span>|<span data-ttu-id="e150a-118">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="e150a-118">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="e150a-119">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="e150a-119">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e150a-120">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="e150a-120">The default is 00:01:00.</span></span>|
|<span data-ttu-id="e150a-121">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="e150a-121">receiveTimeout</span></span>|<span data-ttu-id="e150a-122">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="e150a-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="e150a-123">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="e150a-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e150a-124">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="e150a-124">The default is 00:01:00.</span></span>|
|<span data-ttu-id="e150a-125">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="e150a-125">sendTimeout</span></span>|<span data-ttu-id="e150a-126">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="e150a-126">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="e150a-127">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="e150a-127">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e150a-128">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="e150a-128">The default is 00:01:00.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="e150a-129">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e150a-129">Child Elements</span></span>

|<span data-ttu-id="e150a-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="e150a-130">Element</span></span>|<span data-ttu-id="e150a-131">Описание</span><span class="sxs-lookup"><span data-stu-id="e150a-131">Description</span></span>|
|-------------|-----------------|
|[\<compositeDuplex>](compositeduplex.md)|<span data-ttu-id="e150a-132">Определяет двусторонний обмен сообщениями в пользовательской привязке.</span><span class="sxs-lookup"><span data-stu-id="e150a-132">Specifies two-way messaging to the custom binding.</span></span> <span data-ttu-id="e150a-133">Используется транспортными протоколами, которые не имеют встроенной поддержки дуплексной связи, например HTTP.</span><span class="sxs-lookup"><span data-stu-id="e150a-133">It is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="e150a-134">Напротив, протокол TCP имеет встроенную поддержку дуплексной связи, и для него не требуется использовать этот элемент привязки для службы при отправке сообщений обратно клиенту.</span><span class="sxs-lookup"><span data-stu-id="e150a-134">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span><br /><br /> <span data-ttu-id="e150a-135">Для осуществления контакта и установления подключения клиент должен предоставить службе адрес.</span><span class="sxs-lookup"><span data-stu-id="e150a-135">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="e150a-136">Этот адрес клиента предоставляется атрибутом `ClientBaseAddress`.</span><span class="sxs-lookup"><span data-stu-id="e150a-136">This client address is provided by the `ClientBaseAddress` attribute.</span></span><br /><br /> <span data-ttu-id="e150a-137">Это элемент типа <xref:System.ServiceModel.Configuration.CompositeDuplexElement>.</span><span class="sxs-lookup"><span data-stu-id="e150a-137">This element is of type <xref:System.ServiceModel.Configuration.CompositeDuplexElement>.</span></span>|
|[\<pnrpPeerResolver>](pnrppeerresolver.md)|<span data-ttu-id="e150a-138">Определяет распознавателя имен узлов в протоколе однорангового разрешения имен (PNRP).</span><span class="sxs-lookup"><span data-stu-id="e150a-138">Specifies a Peer Name Resolution Protocol (PNRP) peer name resolver.</span></span> <span data-ttu-id="e150a-139">Это элемент типа <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>.</span><span class="sxs-lookup"><span data-stu-id="e150a-139">This element is of type <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>.</span></span>|
|[\<reliableSession>](reliablesession.md)|<span data-ttu-id="e150a-140">Определяет параметры WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="e150a-140">Specifies the setting for WS-Reliable Messaging.</span></span> <span data-ttu-id="e150a-141">Когда этот элемент добавляется к пользовательской привязке, получаемый канал может поддерживать гарантии доставки только один раз.</span><span class="sxs-lookup"><span data-stu-id="e150a-141">When this element is added to a custom binding, the resulting channel can support exactly-once delivery assurances.</span></span> <span data-ttu-id="e150a-142">Это элемент типа <xref:System.ServiceModel.Configuration.ReliableSessionElement>.</span><span class="sxs-lookup"><span data-stu-id="e150a-142">This element is of type <xref:System.ServiceModel.Configuration.ReliableSessionElement>.</span></span>|
|[\<security>](security-of-custombinding.md)|<span data-ttu-id="e150a-143">Определяет параметры безопасности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="e150a-143">Specifies the options for security of the custom binding.</span></span> <span data-ttu-id="e150a-144">Это элемент типа <xref:System.ServiceModel.Configuration.SecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="e150a-144">This element is of type <xref:System.ServiceModel.Configuration.SecurityElement>.</span></span>|
|[\<sslStreamSecurity>](sslstreamsecurity.md)|<span data-ttu-id="e150a-145">Определяет параметры безопасности привязки потока SSL.</span><span class="sxs-lookup"><span data-stu-id="e150a-145">Specifies the security settings for a SSL stream binding.</span></span> <span data-ttu-id="e150a-146">Это элемент типа <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="e150a-146">This element is of type <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>.</span></span>|
|[\<transactionFlow>](transactionflow.md)|<span data-ttu-id="e150a-147">Указывает, что привязка поддерживает поток транзакций, и задает используемый протокол в атрибуте `transactionProtocol`.</span><span class="sxs-lookup"><span data-stu-id="e150a-147">Specifies that the binding supports transaction flow, and the protocol to be used by the `transactionProtocol` attribute.</span></span> <span data-ttu-id="e150a-148">Это элемент типа <xref:System.ServiceModel.Configuration.TransactionFlowElement>.</span><span class="sxs-lookup"><span data-stu-id="e150a-148">This element is of type <xref:System.ServiceModel.Configuration.TransactionFlowElement>.</span></span>|
|[\<windowsStreamSecurity>](windowsstreamsecurity.md)|<span data-ttu-id="e150a-149">Определяет параметры для потоковой безопасности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="e150a-149">Specifies the options for streaming security of the custom binding.</span></span> <span data-ttu-id="e150a-150">Это элемент типа <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="e150a-150">This element is of type <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e150a-151">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e150a-151">Parent Elements</span></span>

|<span data-ttu-id="e150a-152">Элемент</span><span class="sxs-lookup"><span data-stu-id="e150a-152">Element</span></span>|<span data-ttu-id="e150a-153">Описание</span><span class="sxs-lookup"><span data-stu-id="e150a-153">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="e150a-154">привязки</span><span class="sxs-lookup"><span data-stu-id="e150a-154">bindings</span></span>|<span data-ttu-id="e150a-155">Содержит все привязки для приложений Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="e150a-155">Contains all bindings for Windows Communication Foundation applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e150a-156">Примечания</span><span class="sxs-lookup"><span data-stu-id="e150a-156">Remarks</span></span>

<span data-ttu-id="e150a-157">Пользовательские привязки предоставляют полный контроль над стеком обмена сообщениями WCF.</span><span class="sxs-lookup"><span data-stu-id="e150a-157">Custom bindings provide full control over the WCF messaging stack.</span></span> <span data-ttu-id="e150a-158">Путем добавления элементов конфигурации к определенным сущностям можно создавать специально настроенные привязки.</span><span class="sxs-lookup"><span data-stu-id="e150a-158">Special tailored bindings can be created my adding the configuration elements for specific entities.</span></span> <span data-ttu-id="e150a-159">Например, чтобы создать надежную и безопасную привязку на основе протокола HTTPS, пользователь может объединить разделы `httpsTransport`, `reliableSession` и `security`.</span><span class="sxs-lookup"><span data-stu-id="e150a-159">For example, the user can combine the `httpsTransport` section, `reliableSession` section and the `security` section to create a reliable and secure https based binding.</span></span>

<span data-ttu-id="e150a-160">Отдельная привязка определяет стек обмена сообщениями, задавая элементы конфигурации для элементов стека в том порядке, в котором они присутствуют в стеке.</span><span class="sxs-lookup"><span data-stu-id="e150a-160">An individual binding defines the message stack by specifying the configuration elements for the stack elements in the order they appear on the stack.</span></span> <span data-ttu-id="e150a-161">Каждый элемент определяет и задает параметры одного элемента стека.</span><span class="sxs-lookup"><span data-stu-id="e150a-161">Each element defines and configures the one element of the stack.</span></span> <span data-ttu-id="e150a-162">В каждой пользовательской привязке должен быть один и только один транспортный элемент.</span><span class="sxs-lookup"><span data-stu-id="e150a-162">There must be one and only one transport element in each custom binding.</span></span> <span data-ttu-id="e150a-163">Без этого элемента стек обмена сообщениями является неполным.</span><span class="sxs-lookup"><span data-stu-id="e150a-163">Without this element, the messaging stack is incomplete.</span></span>

<span data-ttu-id="e150a-164">Важен порядок, в котором элементы присутствуют в стеке, поскольку именно в этом порядке к сообщению применяются операции.</span><span class="sxs-lookup"><span data-stu-id="e150a-164">The order in which elements appear in the stack matters, because it is the order in which operations are applied to the message.</span></span> <span data-ttu-id="e150a-165">Рекомендуется следующий порядок элементов стека:</span><span class="sxs-lookup"><span data-stu-id="e150a-165">The recommended order of stack elements is the following:</span></span>

1. <span data-ttu-id="e150a-166">Транзакции (необязательный)</span><span class="sxs-lookup"><span data-stu-id="e150a-166">Transactions (optional)</span></span>

2. <span data-ttu-id="e150a-167">Надежный обмен сообщениями (необязательный)</span><span class="sxs-lookup"><span data-stu-id="e150a-167">Reliable Messaging (optional)</span></span>

3. <span data-ttu-id="e150a-168">Безопасность (необязательный)</span><span class="sxs-lookup"><span data-stu-id="e150a-168">Security (optional)</span></span>

4. <span data-ttu-id="e150a-169">Транспорт</span><span class="sxs-lookup"><span data-stu-id="e150a-169">Transport</span></span>

5. <span data-ttu-id="e150a-170">Кодировщик (необязательный)</span><span class="sxs-lookup"><span data-stu-id="e150a-170">Encoder (optional)</span></span>

<span data-ttu-id="e150a-171">Используйте пользовательские привязки в случае, когда ни одна из системных привязок не соответствует требованиям службы.</span><span class="sxs-lookup"><span data-stu-id="e150a-171">Use a custom binding when one of the system-provided bindings does not meet the requirements of your service.</span></span> <span data-ttu-id="e150a-172">Так, с помощью пользовательской привязки можно разрешить использование нового транспорта или нового кодировщика в конечной точке службы.</span><span class="sxs-lookup"><span data-stu-id="e150a-172">A custom binding could be used, for example, to enable the use of a new transport or a new encoder at a service endpoint.</span></span>

<span data-ttu-id="e150a-173">Пользовательская привязка создается с использованием одного из <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> из коллекции элементов привязки, которые располагаются в определенном порядке.</span><span class="sxs-lookup"><span data-stu-id="e150a-173">A custom binding is constructed using one of the <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> from a collection of binding elements that are "stacked" in a specific order:</span></span>

- <span data-ttu-id="e150a-174">Вверху расположен необязательный элемент <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>, который разрешает поток транзакций.</span><span class="sxs-lookup"><span data-stu-id="e150a-174">At the top is an optional <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> that allows flowing transactions.</span></span>

- <span data-ttu-id="e150a-175">Далее следует необязательный элемент <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>, который предоставляет сеанс и механизм сортировки в соответствии со спецификацией WS-ReliableMessaging.</span><span class="sxs-lookup"><span data-stu-id="e150a-175">Next is an optional <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> that provides a session and ordering mechanism as defined in the WS-ReliableMessaging specification.</span></span> <span data-ttu-id="e150a-176">Это понятие сеанса может выходить за пределы посредников SOAP и транспорта.</span><span class="sxs-lookup"><span data-stu-id="e150a-176">This notion of a session can cross SOAP and transport intermediaries.</span></span>

- <span data-ttu-id="e150a-177">Далее следует необязательный элемент привязки безопасности, который предоставляет функции безопасности, например авторизацию, проверку подлинности, защиту и конфиденциальность.</span><span class="sxs-lookup"><span data-stu-id="e150a-177">Next is an optional security binding element that provides security features like authorization, authentication, protection, and confidentiality.</span></span> <span data-ttu-id="e150a-178">Windows Communication Foundation (WCF) предоставляет следующие элементы привязки безопасности:</span><span class="sxs-lookup"><span data-stu-id="e150a-178">The following security binding elements are provided by Windows Communication Foundation (WCF):</span></span>

  - <xref:System.ServiceModel.Channels.SecurityBindingElement>

  - <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>

- <span data-ttu-id="e150a-179">Далее следуют необязательные шаблоны сообщений, задаваемые элементами привязки.</span><span class="sxs-lookup"><span data-stu-id="e150a-179">Next are the optional message-patterns specified by binding elements:</span></span>

- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>

- <span data-ttu-id="e150a-180">Затем — необязательные элементы привязки обновлений/поддержки транспорта.</span><span class="sxs-lookup"><span data-stu-id="e150a-180">Next are the optional transport upgrades/helpers binding elements:</span></span>

  - <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>

  - <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>

- <span data-ttu-id="e150a-181">Далее следует обязательный элемент привязки для кодирования сообщений.</span><span class="sxs-lookup"><span data-stu-id="e150a-181">Next is a required message encoding binding element.</span></span> <span data-ttu-id="e150a-182">Можно использовать собственный транспорт или одну из следующих привязок кодирования сообщений.</span><span class="sxs-lookup"><span data-stu-id="e150a-182">You can use your own transport or use one of the following message encoding bindings:</span></span>

  - <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>

- <span data-ttu-id="e150a-183">Внизу расположен обязательный элемент транспорта.</span><span class="sxs-lookup"><span data-stu-id="e150a-183">At the bottom is a required transport element.</span></span> <span data-ttu-id="e150a-184">Можно использовать собственный транспорт или один из элементов привязки транспорта, предоставляемых Windows Communication Foundation (WCF):</span><span class="sxs-lookup"><span data-stu-id="e150a-184">You can use your own transport or use one of transport binding elements provided by Windows Communication Foundation (WCF):</span></span>

  - <xref:System.ServiceModel.Channels.TcpTransportBindingElement>

  - <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>

  - <xref:System.ServiceModel.Channels.HttpTransportBindingElement>

  - <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>

  - <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>

  - <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBindingElement>

  - <xref:System.ServiceModel.Channels.PeerTransportBindingElement>

<span data-ttu-id="e150a-185">В следующей таблице приведены сводные данные по параметрам каждого уровня.</span><span class="sxs-lookup"><span data-stu-id="e150a-185">The following table summarizes the options for each layer.</span></span>

|<span data-ttu-id="e150a-186">Уровень</span><span class="sxs-lookup"><span data-stu-id="e150a-186">Layer</span></span>|<span data-ttu-id="e150a-187">Параметры</span><span class="sxs-lookup"><span data-stu-id="e150a-187">Options</span></span>|<span data-ttu-id="e150a-188">Обязательно</span><span class="sxs-lookup"><span data-stu-id="e150a-188">Required</span></span>|
|-----------|-------------|--------------|
|<span data-ttu-id="e150a-189">Поток транзакций</span><span class="sxs-lookup"><span data-stu-id="e150a-189">Transaction Flow</span></span>|<xref:System.ServiceModel.Channels.TransactionFlowBindingElement>|<span data-ttu-id="e150a-190">Нет</span><span class="sxs-lookup"><span data-stu-id="e150a-190">No</span></span>|
|<span data-ttu-id="e150a-191">Надежность</span><span class="sxs-lookup"><span data-stu-id="e150a-191">Reliability</span></span>|<xref:System.ServiceModel.Channels.ReliableSessionBindingElement>|<span data-ttu-id="e150a-192">Нет</span><span class="sxs-lookup"><span data-stu-id="e150a-192">No</span></span>|
|<span data-ttu-id="e150a-193">Безопасность</span><span class="sxs-lookup"><span data-stu-id="e150a-193">Security</span></span>|<span data-ttu-id="e150a-194">Симметричный, асимметричный, транспортного уровня</span><span class="sxs-lookup"><span data-stu-id="e150a-194">Symmetric, Asymmetric, Transport-Level</span></span>|<span data-ttu-id="e150a-195">Нет</span><span class="sxs-lookup"><span data-stu-id="e150a-195">No</span></span>|
|<span data-ttu-id="e150a-196">Изменение формы</span><span class="sxs-lookup"><span data-stu-id="e150a-196">Shape Change</span></span>|<xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>|<span data-ttu-id="e150a-197">Нет</span><span class="sxs-lookup"><span data-stu-id="e150a-197">No</span></span>|
|<span data-ttu-id="e150a-198">Обновления транспорта</span><span class="sxs-lookup"><span data-stu-id="e150a-198">Transport Upgrades</span></span>|<span data-ttu-id="e150a-199">Поток SSL, поток Windows, распознаватель одноранговых узлов</span><span class="sxs-lookup"><span data-stu-id="e150a-199">SSL stream, Windows stream, Peer Resolver</span></span>|<span data-ttu-id="e150a-200">Нет</span><span class="sxs-lookup"><span data-stu-id="e150a-200">No</span></span>|
|<span data-ttu-id="e150a-201">Кодирование</span><span class="sxs-lookup"><span data-stu-id="e150a-201">Encoding</span></span>|<span data-ttu-id="e150a-202">Текстовая, двоичная, MTOM, пользовательская</span><span class="sxs-lookup"><span data-stu-id="e150a-202">Text, Binary, MTOM, Custom</span></span>|<span data-ttu-id="e150a-203">Да</span><span class="sxs-lookup"><span data-stu-id="e150a-203">Yes</span></span>|
|<span data-ttu-id="e150a-204">Транспорт</span><span class="sxs-lookup"><span data-stu-id="e150a-204">Transport</span></span>|<span data-ttu-id="e150a-205">TCP, именованные каналы, HTTP, HTTPS, разновидности MSMQ, пользовательский</span><span class="sxs-lookup"><span data-stu-id="e150a-205">TCP, Named Pipes, HTTP, HTTPS, flavors of MSMQ, Custom</span></span>|<span data-ttu-id="e150a-206">Да</span><span class="sxs-lookup"><span data-stu-id="e150a-206">Yes</span></span>|

<span data-ttu-id="e150a-207">Кроме того, можно определить собственные элементы привязки и вставить их между любыми из приведенных выше заданных уровней.</span><span class="sxs-lookup"><span data-stu-id="e150a-207">In addition, you can define your own binding elements and insert them between any of the preceding defined layers.</span></span>

<span data-ttu-id="e150a-208">Обсуждение того, как использовать пользовательскую привязку для изменения привязки, предоставляемой системой, см. в разделе [как настроить привязку, предоставляемую системой](../../../wcf/extending/how-to-customize-a-system-provided-binding.md).</span><span class="sxs-lookup"><span data-stu-id="e150a-208">For a discussion on how to use a custom binding to modify a system-provided binding, see [How to: Customize a System-Provided Binding](../../../wcf/extending/how-to-customize-a-system-provided-binding.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e150a-209">См. также</span><span class="sxs-lookup"><span data-stu-id="e150a-209">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.Configuration.BindingsSection>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [\<binding>](bindings.md)
- [<span data-ttu-id="e150a-210">Привязки</span><span class="sxs-lookup"><span data-stu-id="e150a-210">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e150a-211">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="e150a-211">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="e150a-212">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="e150a-212">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="e150a-213">customBinding, элемент</span><span class="sxs-lookup"><span data-stu-id="e150a-213">customBinding Element</span></span>](custombinding.md)
- [<span data-ttu-id="e150a-214">Привязки</span><span class="sxs-lookup"><span data-stu-id="e150a-214">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e150a-215">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="e150a-215">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e150a-216">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="e150a-216">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
