---
title: <messageSenderAuthentication> - элемент
ms.date: 03/30/2017
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
ms.openlocfilehash: e7e636571c0dbb1845438c22f7e7509dfc7987f9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204792"
---
# <a name="messagesenderauthentication-element"></a><span data-ttu-id="69140-102">Элемент \<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="69140-102">\<messageSenderAuthentication> element</span></span>

<span data-ttu-id="69140-103">Задает параметры проверки подлинности для одноранговых отправителей сообщений.</span><span class="sxs-lookup"><span data-stu-id="69140-103">Specifies authentication options for peer-to-peer message senders.</span></span>  
  
 <span data-ttu-id="69140-104">Дополнительные сведения о одноранговых программах см. в разделе одноранговая [сеть](../../../wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="69140-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<messageSenderAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="69140-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="69140-105">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="69140-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="69140-106">Attributes and Elements</span></span>  

 <span data-ttu-id="69140-107">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="69140-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="69140-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="69140-108">Attributes</span></span>  
  
|<span data-ttu-id="69140-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="69140-109">Attribute</span></span>|<span data-ttu-id="69140-110">Описание</span><span class="sxs-lookup"><span data-stu-id="69140-110">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="69140-111">Тип и сборка, используемые для проверки пользовательского типа.</span><span class="sxs-lookup"><span data-stu-id="69140-111">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="69140-112">Этот атрибут должен быть задан, когда `certificateValidationMode` имеет значение `Custom`.</span><span class="sxs-lookup"><span data-stu-id="69140-112">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="69140-113">Задает один из трех режимов для проверки учетных данных.</span><span class="sxs-lookup"><span data-stu-id="69140-113">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="69140-114">Если свойству присвоено значение `Custom`, также необходимо указать свойство `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="69140-114">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`revocationMode`|<span data-ttu-id="69140-115">Один из режимов, используемых для проверки списков отозванных сертификатов (CRL).</span><span class="sxs-lookup"><span data-stu-id="69140-115">One of the modes used to check for a revoked certificate lists (CRL).</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="69140-116">Одно из двух местоположений системного хранилища: `LocalMachine` или `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="69140-116">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="69140-117">Данное значение используется при согласовании сертификата службы для клиента.</span><span class="sxs-lookup"><span data-stu-id="69140-117">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="69140-118">Проверка выполняется для хранилища **доверенных лиц** в указанном расположении магазина.</span><span class="sxs-lookup"><span data-stu-id="69140-118">Validation is performed against the **Trusted People** store in the specified store location.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="69140-119">Атрибут customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="69140-119">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="69140-120">Значение</span><span class="sxs-lookup"><span data-stu-id="69140-120">Value</span></span>|<span data-ttu-id="69140-121">Описание</span><span class="sxs-lookup"><span data-stu-id="69140-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="69140-122">Строка</span><span class="sxs-lookup"><span data-stu-id="69140-122">String</span></span>|<span data-ttu-id="69140-123">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="69140-123">Optional.</span></span> <span data-ttu-id="69140-124">Задает имя типа и сборку, а также другие данные, используемые для поиска типа.</span><span class="sxs-lookup"><span data-stu-id="69140-124">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="69140-125">Требуется, как минимум, пространство имен и имя типа.</span><span class="sxs-lookup"><span data-stu-id="69140-125">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="69140-126">К дополнительным сведениям относятся: имя сборки, номер версии, язык и региональные параметры и маркер открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="69140-126">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="69140-127">Атрибут certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="69140-127">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="69140-128">Значение</span><span class="sxs-lookup"><span data-stu-id="69140-128">Value</span></span>|<span data-ttu-id="69140-129">Описание</span><span class="sxs-lookup"><span data-stu-id="69140-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="69140-130">Перечисление</span><span class="sxs-lookup"><span data-stu-id="69140-130">Enumeration</span></span>|<span data-ttu-id="69140-131">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="69140-131">Optional.</span></span> <span data-ttu-id="69140-132">Одно из следующих значений: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="69140-132">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="69140-133">Значение по умолчанию — `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="69140-133">The default is `ChainTrust`.</span></span> <span data-ttu-id="69140-134">Значение по умолчанию — `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="69140-134">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="69140-135">Дополнительные сведения см. в разделе [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="69140-135">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="69140-136">Атрибут revocationMode</span><span class="sxs-lookup"><span data-stu-id="69140-136">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="69140-137">Значение</span><span class="sxs-lookup"><span data-stu-id="69140-137">Value</span></span>|<span data-ttu-id="69140-138">Описание</span><span class="sxs-lookup"><span data-stu-id="69140-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="69140-139">Перечисление</span><span class="sxs-lookup"><span data-stu-id="69140-139">Enumeration</span></span>|<span data-ttu-id="69140-140">Одно из следующих значений: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="69140-140">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="69140-141">Значение по умолчанию — `Online`.</span><span class="sxs-lookup"><span data-stu-id="69140-141">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="69140-142">Дополнительные сведения см. в разделе [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="69140-142">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="69140-143">Атрибут trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="69140-143">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="69140-144">Значение</span><span class="sxs-lookup"><span data-stu-id="69140-144">Value</span></span>|<span data-ttu-id="69140-145">Описание</span><span class="sxs-lookup"><span data-stu-id="69140-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="69140-146">Перечисление</span><span class="sxs-lookup"><span data-stu-id="69140-146">Enumeration</span></span>|<span data-ttu-id="69140-147">Одно из следующих значений: `LocalMachine` или `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="69140-147">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="69140-148">Значение по умолчанию — `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="69140-148">The default is `CurrentUser`.</span></span> <span data-ttu-id="69140-149">Если клиентское приложение выполняется под учетной записью системы, сертификат обычно находится в расположении `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="69140-149">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="69140-150">Если клиентское приложение выполняется под учетной записью пользователя, то сертификат обычно находится в расположении `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="69140-150">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span> <span data-ttu-id="69140-151">Значение по умолчанию — `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="69140-151">The default is `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="69140-152">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="69140-152">Child Elements</span></span>  

 <span data-ttu-id="69140-153">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="69140-153">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="69140-154">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="69140-154">Parent Elements</span></span>  
  
|<span data-ttu-id="69140-155">Элемент</span><span class="sxs-lookup"><span data-stu-id="69140-155">Element</span></span>|<span data-ttu-id="69140-156">Описание</span><span class="sxs-lookup"><span data-stu-id="69140-156">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-clientcredentials-element.md)|<span data-ttu-id="69140-157">Задает учетные данные, используемые для проверки подлинности клиента при подключении к одноранговой службе.</span><span class="sxs-lookup"><span data-stu-id="69140-157">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69140-158">Remarks</span><span class="sxs-lookup"><span data-stu-id="69140-158">Remarks</span></span>  

 <span data-ttu-id="69140-159">Этот элемент должен быть настроен, если выбрана проверка подлинности сообщения.</span><span class="sxs-lookup"><span data-stu-id="69140-159">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="69140-160">Для выходных каналов каждое сообщение подписывается с помощью сертификата, предоставленного [\<certificate>](certificate-element.md) .</span><span class="sxs-lookup"><span data-stu-id="69140-160">For output channels, each message is signed using the certificate provided by [\<certificate>](certificate-element.md).</span></span> <span data-ttu-id="69140-161">Во всех сообщениях перед доставкой приложению проверяются учетные данные сообщения с помощью модуля проверки, заданного атрибутом `customCertificateValidatorType` этого элемента.</span><span class="sxs-lookup"><span data-stu-id="69140-161">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="69140-162">Модуль проверки может принять или отклонить учетные данные.</span><span class="sxs-lookup"><span data-stu-id="69140-162">The validator can either accept or reject the credential.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69140-163">Пример</span><span class="sxs-lookup"><span data-stu-id="69140-163">Example</span></span>  

 <span data-ttu-id="69140-164">В приведенном ниже примере кода устанавливается режим проверки отправителя сообщения `PeerOrChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="69140-164">The following code sets the message sender validation mode to `PeerOrChainTrust`.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <peer>
          <certificate findValue="www.contoso.com"
                       storeLocation="LocalMachine"
                       x509FindType="FindByIssuerName" />
          <messageSenderAuthentication certificateValidationMode="PeerOrChainTrust" />
          <messageSenderAuthentication certificateValidationMode="None" />
        </peer>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="69140-165">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="69140-165">See also</span></span>

- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="69140-166">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="69140-166">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="69140-167">Одноранговая сеть</span><span class="sxs-lookup"><span data-stu-id="69140-167">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="69140-168">[Проверка подлинности сообщений для однорангового канала](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="69140-168">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="69140-169">[Пользовательской проверка подлинности для однорангового канала](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="69140-169">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="69140-170">Защита приложений одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="69140-170">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
