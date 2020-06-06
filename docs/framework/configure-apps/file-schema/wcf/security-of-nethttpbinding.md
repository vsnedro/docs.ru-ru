---
title: <security> из <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: dc41f6f7-cabc-4a64-9fa0-ceabf861b348
ms.openlocfilehash: 97c52fa4f062ed0c65d5b1a8ca47a1439ab04cf5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736490"
---
# <a name="security-of-nethttpbinding"></a><span data-ttu-id="a4485-102">\<security> из \<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="a4485-102">\<security> of \<netHttpBinding></span></span>

<span data-ttu-id="a4485-103">Определяет возможности безопасности для [\<netHttpBinding>](nethttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="a4485-103">Defines the security capabilities of the [\<netHttpBinding>](nethttpbinding.md).</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  

## <a name="syntax"></a><span data-ttu-id="a4485-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a4485-104">Syntax</span></span>

```xml
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a4485-105">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="a4485-105">Attributes and elements</span></span>

<span data-ttu-id="a4485-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a4485-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="a4485-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a4485-107">Attributes</span></span>

|<span data-ttu-id="a4485-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a4485-108">Attribute</span></span>|<span data-ttu-id="a4485-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="a4485-109">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="a4485-110">mode</span><span class="sxs-lookup"><span data-stu-id="a4485-110">mode</span></span>|<span data-ttu-id="a4485-111">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="a4485-111">Optional.</span></span> <span data-ttu-id="a4485-112">Задает тип используемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="a4485-112">Specifies the type of security that is used.</span></span> <span data-ttu-id="a4485-113">Значение по умолчанию — `None`.</span><span class="sxs-lookup"><span data-stu-id="a4485-113">The default is `None`.</span></span> <span data-ttu-id="a4485-114">Это атрибут типа <xref:System.ServiceModel.BasicHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="a4485-114">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|

## <a name="mode-attribute"></a><span data-ttu-id="a4485-115">атрибут mode</span><span class="sxs-lookup"><span data-stu-id="a4485-115">mode attribute</span></span>

|<span data-ttu-id="a4485-116">Значение</span><span class="sxs-lookup"><span data-stu-id="a4485-116">Value</span></span>|<span data-ttu-id="a4485-117">Описание</span><span class="sxs-lookup"><span data-stu-id="a4485-117">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="a4485-118">None</span><span class="sxs-lookup"><span data-stu-id="a4485-118">None</span></span>|<span data-ttu-id="a4485-119">— Сообщения не защищаются во время перемещения.</span><span class="sxs-lookup"><span data-stu-id="a4485-119">-   Messages are not secured during transfer.</span></span>|
|<span data-ttu-id="a4485-120">Транспорт</span><span class="sxs-lookup"><span data-stu-id="a4485-120">Transport</span></span>|<span data-ttu-id="a4485-121">Безопасность обеспечивается с помощью транспорта HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a4485-121">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="a4485-122">Сообщения SOAP защищаются при помощи HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a4485-122">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="a4485-123">Служба проходит проверку подлинности для клиента с использованием сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="a4485-123">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="a4485-124">Проверка подлинности клиента осуществляется с помощью предоставленного ClientCredentialType.</span><span class="sxs-lookup"><span data-stu-id="a4485-124">The client is authenticated using the ClientCredentialType supplied.</span></span>|
|<span data-ttu-id="a4485-125">Сообщение</span><span class="sxs-lookup"><span data-stu-id="a4485-125">Message</span></span>|<span data-ttu-id="a4485-126">Безопасность обеспечивается с помощью средств безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="a4485-126">Security is provided using SOAP message security.</span></span> <span data-ttu-id="a4485-127">По умолчанию текст сообщений шифруется и подписывается.</span><span class="sxs-lookup"><span data-stu-id="a4485-127">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="a4485-128">Для этой привязки система требует, чтобы клиенту был предоставлен сертификат сервера с использованием внештатного канала.</span><span class="sxs-lookup"><span data-stu-id="a4485-128">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="a4485-129">Единственным допустимым значением `ClientCredentialType` для данной привязки является `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="a4485-129">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|
|<span data-ttu-id="a4485-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="a4485-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="a4485-131">Целостность, конфиденциальность и проверка подлинности сервера обеспечиваются с помощью средств безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="a4485-131">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="a4485-132">Проверка подлинности клиента осуществляется при помощи механизма безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="a4485-132">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="a4485-133">Данный режим может использоваться, когда проверка подлинности клиента осуществляется с помощью имени пользователя/пароля и существует развернутый канал HTTP с обеспечением безопасности при передаче сообщений.</span><span class="sxs-lookup"><span data-stu-id="a4485-133">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|
|<span data-ttu-id="a4485-134">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="a4485-134">TransportCredentialOnly</span></span>|<span data-ttu-id="a4485-135">Данный режим не обеспечивает целостности и конфиденциальности сообщений.</span><span class="sxs-lookup"><span data-stu-id="a4485-135">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="a4485-136">Он предоставляет проверку подлинности клиента на основе http.</span><span class="sxs-lookup"><span data-stu-id="a4485-136">It provides http-based client authentication.</span></span> <span data-ttu-id="a4485-137">Этот режим следует использовать с осторожностью.</span><span class="sxs-lookup"><span data-stu-id="a4485-137">This mode should be used with caution.</span></span> <span data-ttu-id="a4485-138">Он должен использоваться в средах, где безопасность транспорта предоставляется другими средствами (например, IPSec), а инфраструктура WCF предоставляет только проверку подлинности клиента.</span><span class="sxs-lookup"><span data-stu-id="a4485-138">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="a4485-139">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a4485-139">Child elements</span></span>

|<span data-ttu-id="a4485-140">Элемент</span><span class="sxs-lookup"><span data-stu-id="a4485-140">Element</span></span>|<span data-ttu-id="a4485-141">Описание</span><span class="sxs-lookup"><span data-stu-id="a4485-141">Description</span></span>|
|-------------|-----------------|
|[\<transport>](transport-of-nethttpbinding.md)|<span data-ttu-id="a4485-142">Определяет параметры безопасности транспорта для базовой службы HTTP.</span><span class="sxs-lookup"><span data-stu-id="a4485-142">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="a4485-143">Данный элемент соответствует <xref:System.ServiceModel.HttpTransportSecurity>.</span><span class="sxs-lookup"><span data-stu-id="a4485-143">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|
|[\<message>](message-of-nethttpbinding.md)|<span data-ttu-id="a4485-144">Определяет параметры безопасности сообщений для базовой службы HTTP.</span><span class="sxs-lookup"><span data-stu-id="a4485-144">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="a4485-145">Данный элемент соответствует <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span><span class="sxs-lookup"><span data-stu-id="a4485-145">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a4485-146">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a4485-146">Parent elements</span></span>

|<span data-ttu-id="a4485-147">Элемент</span><span class="sxs-lookup"><span data-stu-id="a4485-147">Element</span></span>|<span data-ttu-id="a4485-148">Описание</span><span class="sxs-lookup"><span data-stu-id="a4485-148">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="a4485-149">binding</span><span class="sxs-lookup"><span data-stu-id="a4485-149">binding</span></span>|<span data-ttu-id="a4485-150">Элемент Binding объекта [\<basicHttpBinding>](basichttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="a4485-150">The binding element of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|

## <a name="remarks"></a><span data-ttu-id="a4485-151">Примечания</span><span class="sxs-lookup"><span data-stu-id="a4485-151">Remarks</span></span>

 <span data-ttu-id="a4485-152">По умолчанию сообщение SOAP не защищено и проверка подлинности клиента не выполняется.</span><span class="sxs-lookup"><span data-stu-id="a4485-152">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="a4485-153">Данный элемент позволяет настроить дополнительные параметры безопасности для элемента `netHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="a4485-153">This element enables you to configure additional security settings for the `netHttpBinding` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="a4485-154">См. также</span><span class="sxs-lookup"><span data-stu-id="a4485-154">See also</span></span>

- <xref:System.ServiceModel.NetHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetHttpBindingElement.Security%2A>  
- [<span data-ttu-id="a4485-155">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="a4485-155">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="a4485-156">Выбор типа учетных данных</span><span class="sxs-lookup"><span data-stu-id="a4485-156">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="a4485-157">Привязки</span><span class="sxs-lookup"><span data-stu-id="a4485-157">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a4485-158">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="a4485-158">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="a4485-159">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="a4485-159">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
