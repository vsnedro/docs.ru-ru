---
title: <authentication> элемента <clientCertificate>
ms.date: 03/30/2017
ms.assetid: 4a55eea2-1826-4026-b911-b7cc9e9c8bfe
ms.openlocfilehash: 13296dbc2b3bc8836770197a1549586c841b4635
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201607"
---
# <a name="authentication-of-clientcertificate-element"></a><span data-ttu-id="e616f-102">\<authentication> элемента \<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="e616f-102">\<authentication> of \<clientCertificate> Element</span></span>

<span data-ttu-id="e616f-103">Указывает расширения функциональности аутентификации для сертификатов клиентов, используемых службой.</span><span class="sxs-lookup"><span data-stu-id="e616f-103">Specifies authentication behaviors for client certificates used by a service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCertificate>**](clientcertificate-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<authentication>**  
  
## <a name="syntax"></a><span data-ttu-id="e616f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e616f-104">Syntax</span></span>  
  
```xml  
<authentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                includeWindowsGroups="Boolean"
                mapClientCertificateToWindowsAccount="Boolean"
                revocationMode="NoCheck/Online/Offline"
                trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e616f-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e616f-105">Attributes and Elements</span></span>  

 <span data-ttu-id="e616f-106">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e616f-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e616f-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e616f-107">Attributes</span></span>  
  
|<span data-ttu-id="e616f-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e616f-108">Attribute</span></span>|<span data-ttu-id="e616f-109">Описание</span><span class="sxs-lookup"><span data-stu-id="e616f-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e616f-110">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="e616f-110">customCertificateValidatorType</span></span>|<span data-ttu-id="e616f-111">Необязательная строка.</span><span class="sxs-lookup"><span data-stu-id="e616f-111">Optional string.</span></span> <span data-ttu-id="e616f-112">Тип и сборка, используемые для проверки пользовательского типа.</span><span class="sxs-lookup"><span data-stu-id="e616f-112">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="e616f-113">Этот атрибут должен быть задан, когда `certificateValidationMode` имеет значение `Custom`.</span><span class="sxs-lookup"><span data-stu-id="e616f-113">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|<span data-ttu-id="e616f-114">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="e616f-114">certificateValidationMode</span></span>|<span data-ttu-id="e616f-115">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="e616f-115">Optional enumeration.</span></span> <span data-ttu-id="e616f-116">Задает один из режимов для проверки учетных данных.</span><span class="sxs-lookup"><span data-stu-id="e616f-116">Specifies one of the modes used to validate credentials.</span></span> <span data-ttu-id="e616f-117">Это атрибут типа <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="e616f-117">This attribute is of the <xref:System.ServiceModel.Security.X509CertificateValidationMode> type.</span></span> <span data-ttu-id="e616f-118">Если свойству присвоено значение <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom?displayProperty=nameWithType>, также необходимо указать свойство `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="e616f-118">If set to <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom?displayProperty=nameWithType>, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="e616f-119">Значение по умолчанию — <xref:System.ServiceModel.Security.X509CertificateValidationMode.ChainTrust?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e616f-119">The default is <xref:System.ServiceModel.Security.X509CertificateValidationMode.ChainTrust?displayProperty=nameWithType>.</span></span>|  
|<span data-ttu-id="e616f-120">includeWindowsGroups</span><span class="sxs-lookup"><span data-stu-id="e616f-120">includeWindowsGroups</span></span>|<span data-ttu-id="e616f-121">Необязательный логический атрибут.</span><span class="sxs-lookup"><span data-stu-id="e616f-121">Optional Boolean.</span></span> <span data-ttu-id="e616f-122">Указывает, включены ли группы Windows в контекст безопасности.</span><span class="sxs-lookup"><span data-stu-id="e616f-122">Specifies if Windows groups are included in the security context.</span></span> <span data-ttu-id="e616f-123">Установка для этого атрибута значения `true` снижает производительность, поскольку приводит к расширению всей группы.</span><span class="sxs-lookup"><span data-stu-id="e616f-123">Setting this attribute to `true` has a performance impact, as it results in a full group expansion.</span></span> <span data-ttu-id="e616f-124">Если нет необходимости устанавливать список групп, к которым принадлежит пользователь, установите для этого атрибута значение `false`.</span><span class="sxs-lookup"><span data-stu-id="e616f-124">Set this attribute to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|<span data-ttu-id="e616f-125">мапклиентцертификатетовиндовсаккаунт</span><span class="sxs-lookup"><span data-stu-id="e616f-125">mapClientCertificateToWindowsAccount</span></span>|<span data-ttu-id="e616f-126">Логическое.</span><span class="sxs-lookup"><span data-stu-id="e616f-126">Boolean.</span></span> <span data-ttu-id="e616f-127">Указывает, может ли клиент сопоставляться с удостоверением Windows с помощью сертификата.</span><span class="sxs-lookup"><span data-stu-id="e616f-127">Specifies whether the client can be mapped to a Windows identity using the certificate.</span></span> <span data-ttu-id="e616f-128">Для этого необходимо включить службу Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e616f-128">Active Directory must be enabled to do this.</span></span>|  
|<span data-ttu-id="e616f-129">revocationMode</span><span class="sxs-lookup"><span data-stu-id="e616f-129">revocationMode</span></span>|<span data-ttu-id="e616f-130">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="e616f-130">Optional enumeration.</span></span> <span data-ttu-id="e616f-131">Один из режимов, используемых для проверки списков отозванных сертификатов (RCL).</span><span class="sxs-lookup"><span data-stu-id="e616f-131">One of the modes used to check for a revoked certificate lists (RCL).</span></span> <span data-ttu-id="e616f-132">Значение по умолчанию — `Online`.</span><span class="sxs-lookup"><span data-stu-id="e616f-132">The default is `Online`.</span></span> <span data-ttu-id="e616f-133">Это значение не учитывается при использовании безопасности транспорта HTTP.</span><span class="sxs-lookup"><span data-stu-id="e616f-133">This value is ignored when using HTTP transport security.</span></span>|  
|<span data-ttu-id="e616f-134">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="e616f-134">trustedStoreLocation</span></span>|<span data-ttu-id="e616f-135">Необязательное перечисление.</span><span class="sxs-lookup"><span data-stu-id="e616f-135">Optional enumeration.</span></span> <span data-ttu-id="e616f-136">Одно из двух местоположений системного хранилища: `LocalMachine` или `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="e616f-136">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="e616f-137">Данное значение используется при согласовании сертификата службы для клиента.</span><span class="sxs-lookup"><span data-stu-id="e616f-137">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="e616f-138">Проверка выполняется для хранилища **доверенных лиц** в указанном расположении магазина.</span><span class="sxs-lookup"><span data-stu-id="e616f-138">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="e616f-139">Значение по умолчанию — `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="e616f-139">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="e616f-140">Атрибут customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="e616f-140">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="e616f-141">Значение</span><span class="sxs-lookup"><span data-stu-id="e616f-141">Value</span></span>|<span data-ttu-id="e616f-142">Описание</span><span class="sxs-lookup"><span data-stu-id="e616f-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e616f-143">Строка</span><span class="sxs-lookup"><span data-stu-id="e616f-143">String</span></span>|<span data-ttu-id="e616f-144">Задает имя типа и сборку, а также другие данные, используемые для поиска типа.</span><span class="sxs-lookup"><span data-stu-id="e616f-144">Specifies the type name and assembly and other data used to find the type.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="e616f-145">Атрибут certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="e616f-145">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="e616f-146">Значение</span><span class="sxs-lookup"><span data-stu-id="e616f-146">Value</span></span>|<span data-ttu-id="e616f-147">Описание</span><span class="sxs-lookup"><span data-stu-id="e616f-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e616f-148">Перечисление</span><span class="sxs-lookup"><span data-stu-id="e616f-148">Enumeration</span></span>|<span data-ttu-id="e616f-149">Одно из следующих значений: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span><span class="sxs-lookup"><span data-stu-id="e616f-149">One of the following values: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span></span><br /><br /> <span data-ttu-id="e616f-150">Дополнительные сведения см. в разделе [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="e616f-150">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="e616f-151">Атрибут revocationMode</span><span class="sxs-lookup"><span data-stu-id="e616f-151">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="e616f-152">Значение</span><span class="sxs-lookup"><span data-stu-id="e616f-152">Value</span></span>|<span data-ttu-id="e616f-153">Описание</span><span class="sxs-lookup"><span data-stu-id="e616f-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e616f-154">Перечисление</span><span class="sxs-lookup"><span data-stu-id="e616f-154">Enumeration</span></span>|<span data-ttu-id="e616f-155">Одно из следующих значений: NoCheck, Online, Offline.</span><span class="sxs-lookup"><span data-stu-id="e616f-155">One of the following values: NoCheck, Online, Offline.</span></span> <span data-ttu-id="e616f-156">Дополнительные сведения см. в разделе [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="e616f-156">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="e616f-157">Атрибут trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="e616f-157">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="e616f-158">Значение</span><span class="sxs-lookup"><span data-stu-id="e616f-158">Value</span></span>|<span data-ttu-id="e616f-159">Описание</span><span class="sxs-lookup"><span data-stu-id="e616f-159">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e616f-160">Перечисление</span><span class="sxs-lookup"><span data-stu-id="e616f-160">Enumeration</span></span>|<span data-ttu-id="e616f-161">Одно из следующих значений: `LocalMachine` или `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="e616f-161">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="e616f-162">Значение по умолчанию — `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="e616f-162">The default is `CurrentUser`.</span></span> <span data-ttu-id="e616f-163">Если клиентское приложение выполняется под учетной записью системы, сертификат обычно находится в расположении `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="e616f-163">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="e616f-164">Если клиентское приложение выполняется под учетной записью пользователя, то сертификат обычно находится в расположении `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="e616f-164">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e616f-165">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e616f-165">Child Elements</span></span>  

 <span data-ttu-id="e616f-166">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e616f-166">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e616f-167">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e616f-167">Parent Elements</span></span>  
  
|<span data-ttu-id="e616f-168">Элемент</span><span class="sxs-lookup"><span data-stu-id="e616f-168">Element</span></span>|<span data-ttu-id="e616f-169">Описание</span><span class="sxs-lookup"><span data-stu-id="e616f-169">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCertificate>](clientcertificate-of-servicecredentials.md)|<span data-ttu-id="e616f-170">Определяет сертификат X.509, используемый для проверки подлинности клиента по отношению к службе.</span><span class="sxs-lookup"><span data-stu-id="e616f-170">Defines an X.509 certificate used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e616f-171">Remarks</span><span class="sxs-lookup"><span data-stu-id="e616f-171">Remarks</span></span>  

 <span data-ttu-id="e616f-172">Элемент `<authentication>` соответствует классу <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>.</span><span class="sxs-lookup"><span data-stu-id="e616f-172">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> class.</span></span> <span data-ttu-id="e616f-173">Это дает возможность настраивать способ проверки подлинности клиентов.</span><span class="sxs-lookup"><span data-stu-id="e616f-173">It enables you to customize how clients are authenticated.</span></span> <span data-ttu-id="e616f-174">Для атрибута `certificateValidationMode` можно задать значение `None`, `ChainTrust`, `PeerOrChainTrust`, `PeerTrust` или `Custom`.</span><span class="sxs-lookup"><span data-stu-id="e616f-174">You can set the `certificateValidationMode` attribute to `None`, `ChainTrust`, `PeerOrChainTrust`, `PeerTrust`, or `Custom`.</span></span> <span data-ttu-id="e616f-175">По умолчанию уровень имеет значение `ChainTrust` , которое указывает, что каждый сертификат должен быть найден в иерархии сертификатов, которые заканчиваются *корневым центром* в верхней части цепочки.</span><span class="sxs-lookup"><span data-stu-id="e616f-175">By default, the level is set to `ChainTrust`, which specifies that each certificate must be found in a hierarchy of certificates ending in a *root authority* at the top of the chain.</span></span> <span data-ttu-id="e616f-176">Это наиболее безопасный режим.</span><span class="sxs-lookup"><span data-stu-id="e616f-176">This is the most secure mode.</span></span> <span data-ttu-id="e616f-177">Также можно установить значение `PeerOrChainTrust`, в этом случае будут приниматься как самостоятельно выдаваемые сертификаты (доверие одноранговой группы), так и сертификаты, которые находятся в цепи доверия.</span><span class="sxs-lookup"><span data-stu-id="e616f-177">You can also set the value to `PeerOrChainTrust`, which specifies that self-issued certificates (peer trust) are accepted as well as certificates that are in a trusted chain.</span></span> <span data-ttu-id="e616f-178">Данное значение используется при разработке и отладке клиентов и служб, так как самостоятельно выданные сертификаты не нужно приобретать у доверенного центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="e616f-178">This value is used when developing and debugging clients and services because self-issued certificates need not be purchased from a trusted authority.</span></span> <span data-ttu-id="e616f-179">При развертывании клиента вместо этого значения следует использовать значение `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="e616f-179">When deploying a client, use the `ChainTrust` value instead.</span></span>  
  
 <span data-ttu-id="e616f-180">Также можно установить значение `Custom`.</span><span class="sxs-lookup"><span data-stu-id="e616f-180">You can also set the value to `Custom`.</span></span> <span data-ttu-id="e616f-181">При установке значения `Custom` необходимо также задать атрибут `customCertificateValidatorType` для сборки и тип, который используется при проверке сертификата.</span><span class="sxs-lookup"><span data-stu-id="e616f-181">When set to the `Custom` value, you must also set the `customCertificateValidatorType` attribute to an assembly and type used to validate the certificate.</span></span> <span data-ttu-id="e616f-182">Для создания собственного пользовательского модуля проверки необходимо наследование от абстрактного класса <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="e616f-182">To create your own custom validator, you must inherit from the abstract <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="e616f-183">Дополнительные сведения см. [в разделе инструкции. Создание службы, использующей пользовательский проверяющий элемент управления для сертификатов](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span><span class="sxs-lookup"><span data-stu-id="e616f-183">For more information, see [How to: Create a Service that Employs a Custom Certificate Validator](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e616f-184">Пример</span><span class="sxs-lookup"><span data-stu-id="e616f-184">Example</span></span>  

 <span data-ttu-id="e616f-185">В следующем примере кода задается сертификат X.509 и пользовательский тип проверки в элементе `<authentication>`.</span><span class="sxs-lookup"><span data-stu-id="e616f-185">The following code specifies an X.509 certificate and a custom validation type in the `<authentication>` element.</span></span>  
  
```xml  
<serviceBehaviors>
  <behavior name="myServiceBehavior">
    <clientCertificate>
      <certificate findValue="www.cohowinery.com"
                   storeLocation="CurrentUser"
                   storeName="TrustedPeople"
                   x509FindType="FindByIssuerName" />
      <authentication customCertificateValidatorType="MyTypes.Coho"
                      certificateValidationMode="Custom"
                      revocationMode="Offline"
                      includeWindowsGroups="false"
                      mapClientCertificateToWindowsAccount="true" />
    </clientCertificate>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="e616f-186">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e616f-186">See also</span></span>

- <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>
- <xref:System.ServiceModel.Security.X509CertificateValidationMode>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Authentication%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Authentication%2A>
- <xref:System.ServiceModel.Configuration.X509ClientCertificateAuthenticationElement>
- [<span data-ttu-id="e616f-187">Поведение безопасности</span><span class="sxs-lookup"><span data-stu-id="e616f-187">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="e616f-188">Практическое руководство. Создание службы, использующей пользовательский проверяющий элемент управления для сертификатов</span><span class="sxs-lookup"><span data-stu-id="e616f-188">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [<span data-ttu-id="e616f-189">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="e616f-189">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
