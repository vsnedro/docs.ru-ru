---
title: <authentication> элемента <serviceCertificate>
ms.date: 03/30/2017
ms.assetid: 733b67b4-08a1-4d25-9741-10046f9357ef
ms.openlocfilehash: c6f2578d85971740e5bd3d75151305a475187492
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201594"
---
# <a name="authentication-of-servicecertificate-element"></a><span data-ttu-id="a479b-102">\<authentication> элемента \<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="a479b-102">\<authentication> of \<serviceCertificate> Element</span></span>

<span data-ttu-id="a479b-103">Задает параметры, которые использует прокси клиента для проверки подлинности сертификатов службы, полученных при помощи согласования SSL/TLS.</span><span class="sxs-lookup"><span data-stu-id="a479b-103">Specifies the settings used by the client proxy to authenticate service certificates that are obtained using SSL/TLS negotiation.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<authentication>**  
  
## <a name="syntax"></a><span data-ttu-id="a479b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a479b-104">Syntax</span></span>  
  
```xml  
<authentication customCertificateValidatorType="String"
                certificateValidationMode="None/PeerTrust/ChainTrust/PeerOrChainTrust/Custom"
                revocationMode="NoCheck/Online/Offline"
                trustedStoreLocation="LocalMachine/CurrentUser" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a479b-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a479b-105">Attributes and Elements</span></span>  

 <span data-ttu-id="a479b-106">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a479b-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a479b-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a479b-107">Attributes</span></span>  
  
|<span data-ttu-id="a479b-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a479b-108">Attribute</span></span>|<span data-ttu-id="a479b-109">Описание</span><span class="sxs-lookup"><span data-stu-id="a479b-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a479b-110">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="a479b-110">customCertificateValidatorType</span></span>|<span data-ttu-id="a479b-111">Строка.</span><span class="sxs-lookup"><span data-stu-id="a479b-111">String.</span></span> <span data-ttu-id="a479b-112">Тип и сборка, используемые для проверки пользовательского типа.</span><span class="sxs-lookup"><span data-stu-id="a479b-112">A type and assembly used to validate a custom type.</span></span>|  
|<span data-ttu-id="a479b-113">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="a479b-113">certificateValidationMode</span></span>|<span data-ttu-id="a479b-114">Задает один из трех режимов для проверки учетных данных.</span><span class="sxs-lookup"><span data-stu-id="a479b-114">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="a479b-115">Если задано значение `Custom`, также необходимо предоставить customCertificateValidator.</span><span class="sxs-lookup"><span data-stu-id="a479b-115">If set to `Custom`, then a customCertificateValidator must also be supplied.</span></span> <span data-ttu-id="a479b-116">Значение по умолчанию — `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="a479b-116">The default is `ChainTrust`.</span></span>|  
|<span data-ttu-id="a479b-117">revocationMode</span><span class="sxs-lookup"><span data-stu-id="a479b-117">revocationMode</span></span>|<span data-ttu-id="a479b-118">Один из режимов, используемых для проверки списков отозванных сертификатов (CRL).</span><span class="sxs-lookup"><span data-stu-id="a479b-118">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="a479b-119">Значение по умолчанию — `Online`.</span><span class="sxs-lookup"><span data-stu-id="a479b-119">The default is `Online`.</span></span>|  
|<span data-ttu-id="a479b-120">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="a479b-120">trustedStoreLocation</span></span>|<span data-ttu-id="a479b-121">Одно из двух местоположений системного хранилища: `LocalMachine` или `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="a479b-121">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="a479b-122">Данное значение используется при согласовании сертификата службы для клиента.</span><span class="sxs-lookup"><span data-stu-id="a479b-122">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="a479b-123">Проверка выполняется для хранилища **доверенных лиц** в указанном расположении магазина.</span><span class="sxs-lookup"><span data-stu-id="a479b-123">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="a479b-124">Значение по умолчанию — `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="a479b-124">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidator-attribute"></a><span data-ttu-id="a479b-125">Атрибут customCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="a479b-125">customCertificateValidator Attribute</span></span>  
  
|<span data-ttu-id="a479b-126">Значение</span><span class="sxs-lookup"><span data-stu-id="a479b-126">Value</span></span>|<span data-ttu-id="a479b-127">Описание</span><span class="sxs-lookup"><span data-stu-id="a479b-127">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a479b-128">Строка</span><span class="sxs-lookup"><span data-stu-id="a479b-128">String</span></span>|<span data-ttu-id="a479b-129">Задает имя типа и сборку, а также другие данные, используемые для поиска типа.</span><span class="sxs-lookup"><span data-stu-id="a479b-129">Specifies the type name and assembly and other data used to find the type.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="a479b-130">Атрибут certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="a479b-130">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="a479b-131">Значение</span><span class="sxs-lookup"><span data-stu-id="a479b-131">Value</span></span>|<span data-ttu-id="a479b-132">Описание</span><span class="sxs-lookup"><span data-stu-id="a479b-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a479b-133">Перечисление</span><span class="sxs-lookup"><span data-stu-id="a479b-133">Enumeration</span></span>|<span data-ttu-id="a479b-134">Одно из следующих значений: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span><span class="sxs-lookup"><span data-stu-id="a479b-134">One of the following values: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span></span><br /><br /> <span data-ttu-id="a479b-135">Дополнительные сведения см. в разделе [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="a479b-135">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="a479b-136">Атрибут revocationMode</span><span class="sxs-lookup"><span data-stu-id="a479b-136">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="a479b-137">Значение</span><span class="sxs-lookup"><span data-stu-id="a479b-137">Value</span></span>|<span data-ttu-id="a479b-138">Описание</span><span class="sxs-lookup"><span data-stu-id="a479b-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a479b-139">Перечисление</span><span class="sxs-lookup"><span data-stu-id="a479b-139">Enumeration</span></span>|<span data-ttu-id="a479b-140">Одно из следующих значений: NoCheck, Online, Offline.</span><span class="sxs-lookup"><span data-stu-id="a479b-140">One of the following values: NoCheck, Online, Offline.</span></span><br /><br /> <span data-ttu-id="a479b-141">Дополнительные сведения см. в разделе [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="a479b-141">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="a479b-142">Атрибут trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="a479b-142">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="a479b-143">Значение</span><span class="sxs-lookup"><span data-stu-id="a479b-143">Value</span></span>|<span data-ttu-id="a479b-144">Описание</span><span class="sxs-lookup"><span data-stu-id="a479b-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a479b-145">Перечисление</span><span class="sxs-lookup"><span data-stu-id="a479b-145">Enumeration</span></span>|<span data-ttu-id="a479b-146">Одно из следующих значений: LocalMachine или CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="a479b-146">One of the following values: LocalMachine or CurrentUser.</span></span> <span data-ttu-id="a479b-147">Значение по умолчанию — CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="a479b-147">The default is CurrentUser.</span></span> <span data-ttu-id="a479b-148">Если клиентское приложение выполняется в контексте системной учетной записи, сертификат обычно находится в LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="a479b-148">If the client application is running under a system account, then the certificate is typically under LocalMachine.</span></span> <span data-ttu-id="a479b-149">Если клиентское приложение выполняется в контексте учетной записи пользователя, то сертификат обычно находится в CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="a479b-149">If the client application is running under a user account, then the certificate is typically in CurrentUser.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a479b-150">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a479b-150">Child Elements</span></span>  

 <span data-ttu-id="a479b-151">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a479b-151">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a479b-152">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a479b-152">Parent Elements</span></span>  
  
|<span data-ttu-id="a479b-153">Элемент</span><span class="sxs-lookup"><span data-stu-id="a479b-153">Element</span></span>|<span data-ttu-id="a479b-154">Описание</span><span class="sxs-lookup"><span data-stu-id="a479b-154">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="a479b-155">Задает сертификат для использования при проверке подлинности службы для клиента.</span><span class="sxs-lookup"><span data-stu-id="a479b-155">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a479b-156">Remarks</span><span class="sxs-lookup"><span data-stu-id="a479b-156">Remarks</span></span>  

 <span data-ttu-id="a479b-157">Атрибут `certificateValidationMode` данного элемента конфигурации указывает уровень доверия, который используется при проверке подлинности сертификатов.</span><span class="sxs-lookup"><span data-stu-id="a479b-157">The `certificateValidationMode` attribute of this configuration element specifies the level of trust used to authenticate certificates.</span></span> <span data-ttu-id="a479b-158">По умолчанию для уровня устанавливается значение `ChainTrust`, которое указывает, что каждый сертификат должен находиться в иерархии сертификатов, которая на самом верху цепи завершается доверенным центром сертификации.</span><span class="sxs-lookup"><span data-stu-id="a479b-158">By default, the level is set to `ChainTrust`, which specifies that each certificate must be found in a hierarchy of certificates ending in a trusted certification authority at the top of the chain.</span></span> <span data-ttu-id="a479b-159">Это наиболее безопасный режим.</span><span class="sxs-lookup"><span data-stu-id="a479b-159">This is the most secure mode.</span></span> <span data-ttu-id="a479b-160">Также можно установить значение `PeerOrChainTrust`, в этом случае будут приниматься как самостоятельно выдаваемые сертификаты (доверие одноранговой группы), так и сертификаты, которые находятся в цепи доверия.</span><span class="sxs-lookup"><span data-stu-id="a479b-160">You can also set the value to `PeerOrChainTrust`, which specifies that self-issued certificates (peer trust) are accepted as well as certificates that are in a trusted chain.</span></span> <span data-ttu-id="a479b-161">Данное значение используется при разработке и отладке клиентов и служб, так как самостоятельно выданные сертификаты не нужно приобретать у доверенного центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="a479b-161">This value is used when developing and debugging clients and services because self-issued certificates need not be purchased from a trusted authority.</span></span> <span data-ttu-id="a479b-162">При развертывании клиента вместо этого значения следует использовать значение `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="a479b-162">When deploying a client, use the `ChainTrust` value instead.</span></span> <span data-ttu-id="a479b-163">Также можно задать значение `Custom` или `None`.</span><span class="sxs-lookup"><span data-stu-id="a479b-163">You can also set the value to `Custom` or `None`.</span></span> <span data-ttu-id="a479b-164">Чтобы использовать значение `Custom`, необходимо также установить атрибут `customCertificateValidator` для сборки и типа, которые используются при проверке сертификата.</span><span class="sxs-lookup"><span data-stu-id="a479b-164">To use the `Custom` value, you must also set the `customCertificateValidator` attribute to an assembly and type used to validate the certificate.</span></span> <span data-ttu-id="a479b-165">Для создания собственного пользовательского проверяющего элемента управления необходимо унаследовать его от абстрактного класса X509CertificateValidator.</span><span class="sxs-lookup"><span data-stu-id="a479b-165">To create your own custom validator, you must inherit from the abstract X509CertificateValidator class.</span></span> <span data-ttu-id="a479b-166">Дополнительные сведения см. [в разделе инструкции. Создание службы, использующей пользовательский проверяющий элемент управления для сертификатов](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span><span class="sxs-lookup"><span data-stu-id="a479b-166">For more information, see [How to: Create a Service that Employs a Custom Certificate Validator](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span></span>  
  
 <span data-ttu-id="a479b-167">Атрибут `revocationMode` указывает способ проверки отозванных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="a479b-167">The `revocationMode` attribute specifies how certificates are checked for revocation.</span></span> <span data-ttu-id="a479b-168">По умолчанию используется значение `online`, которое указывает, что проверка, является ли сертификат отозванным, будет выполняться автоматически.</span><span class="sxs-lookup"><span data-stu-id="a479b-168">The default is `online` which indicates that certificates will be checked automatically for revocation.</span></span> <span data-ttu-id="a479b-169">Дополнительные сведения см. в разделе [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="a479b-169">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a479b-170">Пример</span><span class="sxs-lookup"><span data-stu-id="a479b-170">Example</span></span>  

 <span data-ttu-id="a479b-171">В следующем примере выполняется две задачи.</span><span class="sxs-lookup"><span data-stu-id="a479b-171">The following example does two tasks.</span></span> <span data-ttu-id="a479b-172">Сначала он указывает сертификат службы, который будет использоваться клиентом при взаимодействии с конечными точками, доменное имя которых находится `www.contoso.com` по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="a479b-172">It first specifies a service certificate for the client to use when communicating with endpoints whose domain name is `www.contoso.com` over the HTTP protocol.</span></span> <span data-ttu-id="a479b-173">Во-вторых, в этом примере указывается режим отзыва и место хранения, которые используются при проверке подлинности.</span><span class="sxs-lookup"><span data-stu-id="a479b-173">Second, it specifies the revocation mode and store location used during authentication.</span></span>  
  
```xml  
<serviceCertificate>
  <defaultCertificate findValue="www.contoso.com"
                      storeLocation="LocalMachine"
                      storeName="TrustedPeople"
                      x509FindType="FindByIssuerDistinguishedName" />
  <scopedCertificates>
     <add targetUri="http://www.contoso.com"
          findValue="www.contoso.com"
          storeLocation="LocalMachine"
          storeName="Root"
          x509FindType="FindByIssuerName" />
  </scopedCertificates>
  <authentication revocationMode="Online"
                  trustedStoreLocation="LocalMachine" />
</serviceCertificate>
```  
  
## <a name="see-also"></a><span data-ttu-id="a479b-174">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a479b-174">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.Authentication%2A>
- <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>
- [<span data-ttu-id="a479b-175">Поведение безопасности</span><span class="sxs-lookup"><span data-stu-id="a479b-175">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="a479b-176">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="a479b-176">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="a479b-177">Практическое руководство. Создание службы, использующей пользовательский проверяющий элемент управления для сертификатов</span><span class="sxs-lookup"><span data-stu-id="a479b-177">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [\<authentication>](authentication-of-clientcertificate-element.md)
- [<span data-ttu-id="a479b-178">Обеспечение безопасности клиентов</span><span class="sxs-lookup"><span data-stu-id="a479b-178">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="a479b-179">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="a479b-179">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
