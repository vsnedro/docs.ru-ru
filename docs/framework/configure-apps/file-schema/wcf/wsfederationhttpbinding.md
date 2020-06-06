---
title: <wsFederationHttpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- wsFederationBinding element
ms.assetid: 9c3312b4-2137-4e71-bf3f-de1cf8e9be79
ms.openlocfilehash: 0a77c791d55c6009cf59d5a4b15f3b2a63b7ccf9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "74140476"
---
# \<wsFederationHttpBinding>

<span data-ttu-id="7484a-101">Определяет привязку, которая поддерживает спецификацию WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="7484a-101">Defines a binding that supports WS-Federation.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsFederationHttpBinding>**  

## <a name="syntax"></a><span data-ttu-id="7484a-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7484a-102">Syntax</span></span>

```xml
<wsFederationHttpBinding>
  <binding bypassProxyOnLocal="Boolean"
           closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"
           maxBufferPoolSize="integer"
           maxReceivedMessageSize="integer"
           messageEncoding="Text/Mtom"
           name="string"
           openTimeout="TimeSpan"
           privacyNoticeAt="Uri"
           privacyNoticeVersion="Integer"
           proxyAddress="Uri"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/ Utf8TextEncoding"
           transactionFlow="Boolean"
           useDefaultWebProxy="Boolean">
    <security mode="None/Message/TransportWithMessageCredential">
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey"
               negotiateServiceCredential="Boolean">
        <claimTypeRequirements>
          <add claimType="URI"
               isOptional="Boolean" />
        </claimTypeRequirements>
        <issuer address="Uri" >
          <headers>
            <add name="String"
                 namespace="String" />
          </headers>
          <identity>
            <certificate encodedValue="String" />
            <certificateReference findValue="String"
                                  isChainIncluded="Boolean"
                                  storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                                  storeLocation="LocalMachine/CurrentUser"
                                  X509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
            <dns value="String" />
            <rsa value="String" />
            <servicePrincipalName value="String" />
            <usePrincipalName value="String" />
          </identity>
        </issuer>
        <issuerMetadata address="String">
          <headers>
            <add name="String"
                 namespace="String" />
          </headers>
          <identity>
            <certificate encodedValue="String" />
            <certificateReference findValue="String"
                                  isChainIncluded="Boolean"
                                  storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                                  storeLocation="LocalMachine/CurrentUser"
                                  x509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
            <dns value="String" />
            <rsa value="String" />
            <servicePrincipalName value="String" />
            <usePrincipalName value="String" />
          </identity>
        </issuerMetadata>
        <tokenRequestParameters>
          <xmlElement>
          </xmlElement>
        </tokenRequestParameters>
      </message>
    </security>
    <reliableSession ordered="Boolean"
                     inactivityTimeout="TimeSpan"
                     enabled="Boolean" />
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</wsFederationBinding>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7484a-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7484a-103">Attributes and Elements</span></span>

<span data-ttu-id="7484a-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7484a-104">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="7484a-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7484a-105">Attributes</span></span>

|<span data-ttu-id="7484a-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7484a-106">Attribute</span></span>|<span data-ttu-id="7484a-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="7484a-107">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="7484a-108">bypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="7484a-108">bypassProxyOnLocal</span></span>|<span data-ttu-id="7484a-109">Логическое значение, определяющее, будет ли выполняться обход прокси-сервера для локальных адресов.</span><span class="sxs-lookup"><span data-stu-id="7484a-109">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="7484a-110">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="7484a-110">The default is `false`.</span></span>|
|<span data-ttu-id="7484a-111">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="7484a-111">closeTimeout</span></span>|<span data-ttu-id="7484a-112">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="7484a-112">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="7484a-113">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="7484a-113">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="7484a-114">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="7484a-114">The default is 00:01:00.</span></span>|
|<span data-ttu-id="7484a-115">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="7484a-115">hostnameComparisonMode</span></span>|<span data-ttu-id="7484a-116">Задает режим сравнения имен узлов HTTP для анализа универсальных кодов ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="7484a-116">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="7484a-117">Это атрибут типа <xref:System.ServiceModel.HostNameComparisonMode>, который указывает, используется ли имя узла для доступа к службе при сравнении по универсальному коду ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="7484a-117">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="7484a-118">Значение по умолчанию — <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, при котором имя узла в найденном соответствии не используется.</span><span class="sxs-lookup"><span data-stu-id="7484a-118">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|
|<span data-ttu-id="7484a-119">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="7484a-119">maxBufferPoolSize</span></span>|<span data-ttu-id="7484a-120">Целое число, задающее максимальный размер буферного пула для этой привязки.</span><span class="sxs-lookup"><span data-stu-id="7484a-120">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="7484a-121">Значение по умолчанию - 524 288 байт (512 \* 1024).</span><span class="sxs-lookup"><span data-stu-id="7484a-121">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="7484a-122">Многие элементы Windows Communication Foundation (WCF) используют буферы.</span><span class="sxs-lookup"><span data-stu-id="7484a-122">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="7484a-123">При создании буферов и их уничтожении после каждого использования расходуется слишком много ресурсов; при сборке мусора для буферов также расходуется слишком много ресурсов.</span><span class="sxs-lookup"><span data-stu-id="7484a-123">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="7484a-124">Буферные пулы позволяют брать буфер из пула, использовать его, а затем возвращать обратно, когда он больше не требуется.</span><span class="sxs-lookup"><span data-stu-id="7484a-124">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="7484a-125">Это позволяет избежать излишней нагрузки, связанной с созданием и уничтожением буферов.</span><span class="sxs-lookup"><span data-stu-id="7484a-125">Thus the overhead in creating and destroying buffers is avoided.</span></span>|
|<span data-ttu-id="7484a-126">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="7484a-126">maxReceivedMessageSize</span></span>|<span data-ttu-id="7484a-127">Положительное целое число, задающее, в байтах, максимальный размер сообщения (включая заголовки), которое можно получить по каналу, настроенному с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="7484a-127">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="7484a-128">Отправитель сообщения, превышающего это ограничение, получит ошибку SOAP.</span><span class="sxs-lookup"><span data-stu-id="7484a-128">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="7484a-129">Получатель отклоняет сообщение и создает запись о событии в журнале трассировки.</span><span class="sxs-lookup"><span data-stu-id="7484a-129">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="7484a-130">Значение по умолчанию — 65536.</span><span class="sxs-lookup"><span data-stu-id="7484a-130">The default is 65536.</span></span>|
|<span data-ttu-id="7484a-131">messageEncoding</span><span class="sxs-lookup"><span data-stu-id="7484a-131">messageEncoding</span></span>|<span data-ttu-id="7484a-132">Определяет кодировщик, используемый для кодировки сообщения.</span><span class="sxs-lookup"><span data-stu-id="7484a-132">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="7484a-133">Допустимые значения.</span><span class="sxs-lookup"><span data-stu-id="7484a-133">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="7484a-134">-Text: использование кодировщика текстовых сообщений.</span><span class="sxs-lookup"><span data-stu-id="7484a-134">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="7484a-135">-MTOM: используйте кодировщик обмена сообщениями, механизм передачи сообщений 1,0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="7484a-135">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="7484a-136">Значение по умолчанию - Text.</span><span class="sxs-lookup"><span data-stu-id="7484a-136">The default is Text.</span></span><br /><br /> <span data-ttu-id="7484a-137">Это атрибут типа <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="7484a-137">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|
|<span data-ttu-id="7484a-138">name</span><span class="sxs-lookup"><span data-stu-id="7484a-138">name</span></span>|<span data-ttu-id="7484a-139">Строка, содержащая имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="7484a-139">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="7484a-140">Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.</span><span class="sxs-lookup"><span data-stu-id="7484a-140">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="7484a-141">Начиная с .NET Framework 4, привязки и поведения не обязательно должны иметь имя.</span><span class="sxs-lookup"><span data-stu-id="7484a-141">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="7484a-142">Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="7484a-142">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|
|<span data-ttu-id="7484a-143">openTimeout</span><span class="sxs-lookup"><span data-stu-id="7484a-143">openTimeout</span></span>|<span data-ttu-id="7484a-144">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="7484a-144">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="7484a-145">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="7484a-145">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="7484a-146">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="7484a-146">The default is 00:01:00.</span></span>|
|<span data-ttu-id="7484a-147">privacyNoticeAt</span><span class="sxs-lookup"><span data-stu-id="7484a-147">privacyNoticeAt</span></span>|<span data-ttu-id="7484a-148">Строка, задающая универсальный код ресурса (URI), определяющий расположение примечания о конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="7484a-148">A String that specifies a URI at which the privacy notice is located.</span></span>|
|<span data-ttu-id="7484a-149">privacyNoticeVersion</span><span class="sxs-lookup"><span data-stu-id="7484a-149">privacyNoticeVersion</span></span>|<span data-ttu-id="7484a-150">Целое число, определяющее версию текущего уведомления о конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="7484a-150">An integer that specifies the version of the current privacy notice.</span></span>|
|<span data-ttu-id="7484a-151">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="7484a-151">proxyAddress</span></span>|<span data-ttu-id="7484a-152">Универсальный код ресурса (URI), задающий адрес прокси-сервера HTTP.</span><span class="sxs-lookup"><span data-stu-id="7484a-152">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="7484a-153">Если параметр `useDefaultWebProxy` имеет значение `true`, данный параметр должен иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="7484a-153">If `useDefaultWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="7484a-154">Значение по умолчанию — `null`.</span><span class="sxs-lookup"><span data-stu-id="7484a-154">The default is `null`.</span></span>|
|<span data-ttu-id="7484a-155">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="7484a-155">receiveTimeout</span></span>|<span data-ttu-id="7484a-156">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="7484a-156">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="7484a-157">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="7484a-157">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="7484a-158">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="7484a-158">The default is 00:10:00.</span></span>|
|<span data-ttu-id="7484a-159">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="7484a-159">sendTimeout</span></span>|<span data-ttu-id="7484a-160">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="7484a-160">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="7484a-161">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="7484a-161">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="7484a-162">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="7484a-162">The default is 00:01:00.</span></span>|
|<span data-ttu-id="7484a-163">textEncoding</span><span class="sxs-lookup"><span data-stu-id="7484a-163">textEncoding</span></span>|<span data-ttu-id="7484a-164">Задает кодировку, используемую при отправке сообщений через привязку.</span><span class="sxs-lookup"><span data-stu-id="7484a-164">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="7484a-165">Допустимые значения.</span><span class="sxs-lookup"><span data-stu-id="7484a-165">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="7484a-166">-BigEndianUnicode: Юникод байтов Encoding.</span><span class="sxs-lookup"><span data-stu-id="7484a-166">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="7484a-167">-Unicode: 16-разрядная кодировка.</span><span class="sxs-lookup"><span data-stu-id="7484a-167">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="7484a-168">-UTF8:8-разрядная кодировка</span><span class="sxs-lookup"><span data-stu-id="7484a-168">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="7484a-169">По умолчанию используется значение UTF8.</span><span class="sxs-lookup"><span data-stu-id="7484a-169">The default is UTF8.</span></span> <span data-ttu-id="7484a-170">Это атрибут типа <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="7484a-170">This attribute is of type <xref:System.Text.Encoding>..</span></span>|
|<span data-ttu-id="7484a-171">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="7484a-171">transactionFlow</span></span>|<span data-ttu-id="7484a-172">Логическое значение, определяющее, поддерживает ли привязка потоковые спецификации WS-Transactions.</span><span class="sxs-lookup"><span data-stu-id="7484a-172">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="7484a-173">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="7484a-173">The default is `false`.</span></span>|
|<span data-ttu-id="7484a-174">useDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="7484a-174">useDefaultWebProxy</span></span>|<span data-ttu-id="7484a-175">Логическое значение, указывающее, должен ли использоваться автоматически настроенный системный прокси-сервер HTTP.</span><span class="sxs-lookup"><span data-stu-id="7484a-175">A Boolean value that indicates whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="7484a-176">Если данный атрибут имеет значение `null`, прокси-адрес должен быть равен `true` (то есть не задан).</span><span class="sxs-lookup"><span data-stu-id="7484a-176">The proxy address must be `null` (that is, not set) if this attribute is `true`.</span></span> <span data-ttu-id="7484a-177">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="7484a-177">The default is `true`.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="7484a-178">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7484a-178">Child Elements</span></span>

|<span data-ttu-id="7484a-179">Элемент</span><span class="sxs-lookup"><span data-stu-id="7484a-179">Element</span></span>|<span data-ttu-id="7484a-180">Описание</span><span class="sxs-lookup"><span data-stu-id="7484a-180">Description</span></span>|
|-------------|-----------------|
|[\<security>](security-of-wsfederationhttpbinding.md)|<span data-ttu-id="7484a-181">Определяет параметры безопасности сообщения.</span><span class="sxs-lookup"><span data-stu-id="7484a-181">Defines the security settings for the message.</span></span> <span data-ttu-id="7484a-182">Это элемент типа <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="7484a-182">This element is of type <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span></span>|
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="7484a-183">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="7484a-183">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="7484a-184">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="7484a-184">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|
|[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))|<span data-ttu-id="7484a-185">Указывает, устанавливаются ли между конечными точками канала надежные сеансы.</span><span class="sxs-lookup"><span data-stu-id="7484a-185">Specifies if reliable sessions are established between channel endpoints.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="7484a-186">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7484a-186">Parent Elements</span></span>

|<span data-ttu-id="7484a-187">Элемент</span><span class="sxs-lookup"><span data-stu-id="7484a-187">Element</span></span>|<span data-ttu-id="7484a-188">Описание</span><span class="sxs-lookup"><span data-stu-id="7484a-188">Description</span></span>|
|-------------|-----------------|
|[\<bindings>](bindings.md)|<span data-ttu-id="7484a-189">Этот элемент содержит коллекцию стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="7484a-189">This element holds a collection of standard and custom bindings.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7484a-190">Примечания</span><span class="sxs-lookup"><span data-stu-id="7484a-190">Remarks</span></span>

<span data-ttu-id="7484a-191">Федерация - это возможность совместного использования удостоверений в нескольких системах в целях проверки подлинности и авторизации.</span><span class="sxs-lookup"><span data-stu-id="7484a-191">Federation is the ability to share identities across multiple systems for authentication and authorization.</span></span> <span data-ttu-id="7484a-192">Эти удостоверения могут ссылаться на пользователей или на компьютеры.</span><span class="sxs-lookup"><span data-stu-id="7484a-192">These identities can refer to users or to machines.</span></span> <span data-ttu-id="7484a-193">Федеративный протокол HTTP поддерживает безопасность SOAP и безопасность в смешанном режиме, но не поддерживает использование исключительно безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="7484a-193">Federated HTTP supports SOAP security as well as mixed-mode security, but it does not support exclusively using transport security.</span></span> <span data-ttu-id="7484a-194">Эта привязка обеспечивает поддержку Windows Communication Foundation (WCF) для протокола WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="7484a-194">This binding provides Windows Communication Foundation (WCF) support for the WS-Federation protocol.</span></span> <span data-ttu-id="7484a-195">Службы, настроенные с использованием этой привязки, должны использовать транспорт HTTP.</span><span class="sxs-lookup"><span data-stu-id="7484a-195">Services configured with this binding must use the HTTP transport.</span></span>

<span data-ttu-id="7484a-196">Привязки состоят из стека элементов привязки.</span><span class="sxs-lookup"><span data-stu-id="7484a-196">Bindings consist of a stack of binding elements.</span></span> <span data-ttu-id="7484a-197">Стек элементов привязки в</span><span class="sxs-lookup"><span data-stu-id="7484a-197">The stack of binding elements in</span></span>

<span data-ttu-id="7484a-198">`wsFederationHttpBinding` идентичен тому, что содержится в `wsHttpBinding`</span><span class="sxs-lookup"><span data-stu-id="7484a-198">`wsFederationHttpBinding` is the same as that contained in `wsHttpBinding`</span></span>

<span data-ttu-id="7484a-199">Если [\<security>](security-of-wsfederationhttpbinding.md) для задано значение по умолчанию <xref:System.ServiceModel.WSFederationHttpSecurityMode.Message> .</span><span class="sxs-lookup"><span data-stu-id="7484a-199">when [\<security>](security-of-wsfederationhttpbinding.md) is set to the default value of <xref:System.ServiceModel.WSFederationHttpSecurityMode.Message>.</span></span>

<span data-ttu-id="7484a-200">Элемент `wsFederationHttpBinding` управления определяет сведения о параметрах безопасности сообщений в [\<message>](message-element-of-wsfederationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="7484a-200">The `wsFederationHttpBinding` controls the details of the message security settings in [\<message>](message-element-of-wsfederationhttpbinding.md).</span></span> <span data-ttu-id="7484a-201">Обратите внимание, что [\<security>](security-of-wsfederationhttpbinding.md) элемент предоставляет доступ get, только так как безопасность, используемая привязкой, не может быть изменена после создания привязки.</span><span class="sxs-lookup"><span data-stu-id="7484a-201">Note that the [\<security>](security-of-wsfederationhttpbinding.md) element provides get access only as the security used by the binding cannot be changed once the binding is created.</span></span>

<span data-ttu-id="7484a-202">`wsFederationHttpBinding`Также предоставляет атрибут привацинотицеат для задания и получения универсального кода ресурса (URI), в котором находится уведомление о конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="7484a-202">The `wsFederationHttpBinding` also provides a privacyNoticeAt attribute to set and retrieve the URI at which the privacy notice is located.</span></span>

<span data-ttu-id="7484a-203">Обеспечение безопасности политики особенно важно в федеративных сценариях.</span><span class="sxs-lookup"><span data-stu-id="7484a-203">Keeping policy secure is especially important in federation scenarios.</span></span> <span data-ttu-id="7484a-204">Для защиты политики от злоумышленников рекомендуется использовать определенную систему безопасности, например протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="7484a-204">The recommendation is to use some form of security, such as HTTPS, to protect the policy from malicious users.</span></span>

<span data-ttu-id="7484a-205">В федеративных сценариях с использованием этой привязки политика службы потенциально содержит важные сведения, например ключ для шифрования выдаваемого маркера (SAML), тип утверждений, помещаемых в маркер, и так далее.</span><span class="sxs-lookup"><span data-stu-id="7484a-205">In federation scenarios using this binding, the service policy potentially has important information such as the key to use to encrypt the issued (SAML) token, the type of claims to put in the token, and so forth.</span></span> <span data-ttu-id="7484a-206">Если политика подделана, атакующий может обнаружить ключ выданного маркера, что приводит к дальнейшим подделкам, раскрытию сведений и другим вредоносным действиям.</span><span class="sxs-lookup"><span data-stu-id="7484a-206">If this policy is tampered with, an attacker could discover the key of the issued token leading to further tampering, info disclosure and other malicious behavior.</span></span> <span data-ttu-id="7484a-207">Чтобы предупредить злонамеренные действия, политика должна быть получена от службы безопасным способом (например, с помощью протокола HTTPS).</span><span class="sxs-lookup"><span data-stu-id="7484a-207">To help prevent this, the policy must be obtained securely (for example using HTTPS) from the service.</span></span>

<span data-ttu-id="7484a-208">Дополнительные сведения об этой привязке см. в разделе [инструкции. Создание WSFederationHttpBinding](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="7484a-208">For more information on this binding, see [How to: Create a WSFederationHttpBinding](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md).</span></span>

## <a name="example"></a><span data-ttu-id="7484a-209">Пример</span><span class="sxs-lookup"><span data-stu-id="7484a-209">Example</span></span>

```xml
<configuration>
  <system.ServiceModel>
    <bindings>
      <wsFederationHttpBinding>
        <binding bypassProxyOnLocal="false"
                 transactionFlow="false"
                 hostNameComparisonMode="WeakWildcard"
                 maxReceivedMessageSize="1000"
                 messageEncoding="Mtom"
                 proxyAddress="http://foo/bar"
                 textEncoding="Utf16TextEncoding"
                 useDefaultWebProxy="false">
          <reliableSession ordered="false"
                           inactivityTimeout="00:02:00"
                           enabled="true" />
          <security mode="None">
            <message negotiateServiceCredential="false"
                     algorithmSuite="Aes128"
                     issuedTokenType="saml"
                     issuedKeyType="PublicKey">
              <issuer address="http://localhost/Sts" />
            </message>
          </security>
        </binding>
      </wsFederationBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="7484a-210">См. также</span><span class="sxs-lookup"><span data-stu-id="7484a-210">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpBinding>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement>
- [<span data-ttu-id="7484a-211">Практическое руководство. Создание WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="7484a-211">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="7484a-212">Привязки</span><span class="sxs-lookup"><span data-stu-id="7484a-212">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="7484a-213">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="7484a-213">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="7484a-214">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="7484a-214">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
