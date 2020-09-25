---
title: <security> из <basicHttpBinding>
ms.date: 03/30/2017
ms.assetid: 6432708d-5465-4bd9-bfc2-466742db99cb
ms.openlocfilehash: 6144e5448526d7f2a7c89693f70f71a7f26c4a22
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183667"
---
# <a name="security-of-basichttpbinding"></a><span data-ttu-id="e92f2-102">\<security> из \<basicHttpBinding></span><span class="sxs-lookup"><span data-stu-id="e92f2-102">\<security> of \<basicHttpBinding></span></span>

<span data-ttu-id="e92f2-103">Определяет возможности безопасности для [\<basicHttpBinding>](basichttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="e92f2-103">Defines the security capabilities of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<basicHttpBinding>**](basichttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="e92f2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e92f2-104">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e92f2-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e92f2-105">Attributes and Elements</span></span>  

 <span data-ttu-id="e92f2-106">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e92f2-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e92f2-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e92f2-107">Attributes</span></span>  
  
|<span data-ttu-id="e92f2-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e92f2-108">Attribute</span></span>|<span data-ttu-id="e92f2-109">Описание</span><span class="sxs-lookup"><span data-stu-id="e92f2-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e92f2-110">mode</span><span class="sxs-lookup"><span data-stu-id="e92f2-110">mode</span></span>|<span data-ttu-id="e92f2-111">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="e92f2-111">Optional.</span></span> <span data-ttu-id="e92f2-112">Задает тип используемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="e92f2-112">Specifies the type of security that is used.</span></span> <span data-ttu-id="e92f2-113">Значение по умолчанию — `None`.</span><span class="sxs-lookup"><span data-stu-id="e92f2-113">The default is `None`.</span></span> <span data-ttu-id="e92f2-114">Это атрибут типа <xref:System.ServiceModel.BasicHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="e92f2-114">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="e92f2-115">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="e92f2-115">mode Attribute</span></span>  
  
|<span data-ttu-id="e92f2-116">Значение</span><span class="sxs-lookup"><span data-stu-id="e92f2-116">Value</span></span>|<span data-ttu-id="e92f2-117">Описание</span><span class="sxs-lookup"><span data-stu-id="e92f2-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e92f2-118">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="e92f2-118">None</span></span>|<span data-ttu-id="e92f2-119">— Сообщения не защищаются во время перемещения.</span><span class="sxs-lookup"><span data-stu-id="e92f2-119">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="e92f2-120">Транспорт</span><span class="sxs-lookup"><span data-stu-id="e92f2-120">Transport</span></span>|<span data-ttu-id="e92f2-121">Безопасность обеспечивается с помощью транспорта HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e92f2-121">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="e92f2-122">Сообщения SOAP защищаются при помощи HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e92f2-122">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="e92f2-123">Служба проходит проверку подлинности для клиента с использованием сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="e92f2-123">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="e92f2-124">Проверка подлинности клиента осуществляется с помощью предоставленного ClientCredentialType.</span><span class="sxs-lookup"><span data-stu-id="e92f2-124">The client is authenticated using the ClientCredentialType supplied.</span></span> <span data-ttu-id="e92f2-125">См [\<transport>](transport-of-basichttpbinding.md) . раздел.</span><span class="sxs-lookup"><span data-stu-id="e92f2-125">See the [\<transport>](transport-of-basichttpbinding.md).</span></span>|  
|<span data-ttu-id="e92f2-126">Сообщение</span><span class="sxs-lookup"><span data-stu-id="e92f2-126">Message</span></span>|<span data-ttu-id="e92f2-127">Безопасность обеспечивается с помощью средств безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="e92f2-127">Security is provided using SOAP message security.</span></span> <span data-ttu-id="e92f2-128">По умолчанию текст сообщений шифруется и подписывается.</span><span class="sxs-lookup"><span data-stu-id="e92f2-128">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="e92f2-129">Для этой привязки система требует, чтобы клиенту был предоставлен сертификат сервера с использованием внештатного канала.</span><span class="sxs-lookup"><span data-stu-id="e92f2-129">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="e92f2-130">Единственным допустимым значением `ClientCredentialType` для данной привязки является `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="e92f2-130">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|  
|<span data-ttu-id="e92f2-131">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="e92f2-131">TransportWithMessageCredential</span></span>|<span data-ttu-id="e92f2-132">Целостность, конфиденциальность и проверка подлинности сервера обеспечиваются с помощью средств безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="e92f2-132">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="e92f2-133">Проверка подлинности клиента осуществляется при помощи механизма безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="e92f2-133">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="e92f2-134">Данный режим может использоваться, когда проверка подлинности клиента осуществляется с помощью имени пользователя/пароля и существует развернутый канал HTTP с обеспечением безопасности при передаче сообщений.</span><span class="sxs-lookup"><span data-stu-id="e92f2-134">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|  
|<span data-ttu-id="e92f2-135">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="e92f2-135">TransportCredentialOnly</span></span>|<span data-ttu-id="e92f2-136">Данный режим не обеспечивает целостности и конфиденциальности сообщений.</span><span class="sxs-lookup"><span data-stu-id="e92f2-136">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="e92f2-137">Он предоставляет проверку подлинности клиента на основе http.</span><span class="sxs-lookup"><span data-stu-id="e92f2-137">It provides http-based client authentication.</span></span> <span data-ttu-id="e92f2-138">Этот режим следует использовать с осторожностью.</span><span class="sxs-lookup"><span data-stu-id="e92f2-138">This mode should be used with caution.</span></span> <span data-ttu-id="e92f2-139">Он должен использоваться в средах, где безопасность транспорта предоставляется другими средствами (например, IPSec), а инфраструктура WCF предоставляет только проверку подлинности клиента.</span><span class="sxs-lookup"><span data-stu-id="e92f2-139">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e92f2-140">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e92f2-140">Child Elements</span></span>  
  
|<span data-ttu-id="e92f2-141">Элемент</span><span class="sxs-lookup"><span data-stu-id="e92f2-141">Element</span></span>|<span data-ttu-id="e92f2-142">Описание</span><span class="sxs-lookup"><span data-stu-id="e92f2-142">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-basichttpbinding.md)|<span data-ttu-id="e92f2-143">Определяет параметры безопасности транспорта для базовой службы HTTP.</span><span class="sxs-lookup"><span data-stu-id="e92f2-143">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="e92f2-144">Данный элемент соответствует <xref:System.ServiceModel.HttpTransportSecurity>.</span><span class="sxs-lookup"><span data-stu-id="e92f2-144">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|  
|[\<message>](message-of-basichttpbinding.md)|<span data-ttu-id="e92f2-145">Определяет параметры безопасности сообщений для базовой службы HTTP.</span><span class="sxs-lookup"><span data-stu-id="e92f2-145">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="e92f2-146">Данный элемент соответствует <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span><span class="sxs-lookup"><span data-stu-id="e92f2-146">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e92f2-147">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e92f2-147">Parent Elements</span></span>  
  
|<span data-ttu-id="e92f2-148">Элемент</span><span class="sxs-lookup"><span data-stu-id="e92f2-148">Element</span></span>|<span data-ttu-id="e92f2-149">Описание</span><span class="sxs-lookup"><span data-stu-id="e92f2-149">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e92f2-150">binding</span><span class="sxs-lookup"><span data-stu-id="e92f2-150">binding</span></span>|<span data-ttu-id="e92f2-151">Элемент Binding объекта [\<basicHttpBinding>](basichttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="e92f2-151">The binding element of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e92f2-152">Remarks</span><span class="sxs-lookup"><span data-stu-id="e92f2-152">Remarks</span></span>  

 <span data-ttu-id="e92f2-153">По умолчанию сообщение SOAP не защищено и проверка подлинности клиента не выполняется.</span><span class="sxs-lookup"><span data-stu-id="e92f2-153">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="e92f2-154">Данный элемент позволяет настроить дополнительные параметры безопасности для элемента `basicHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="e92f2-154">This element enables you to configure additional security settings for the `basicHttpBinding` element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e92f2-155">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e92f2-155">See also</span></span>

- <xref:System.ServiceModel.BasicHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="e92f2-156">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="e92f2-156">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="e92f2-157">Выбор типа учетных данных</span><span class="sxs-lookup"><span data-stu-id="e92f2-157">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="e92f2-158">Привязки</span><span class="sxs-lookup"><span data-stu-id="e92f2-158">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e92f2-159">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="e92f2-159">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e92f2-160">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="e92f2-160">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
