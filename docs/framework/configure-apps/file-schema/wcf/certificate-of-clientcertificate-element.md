---
title: <certificate> элемента <clientCertificate>
ms.date: 03/30/2017
ms.assetid: 00297efb-a7f2-4e03-bc2b-943d545610fc
ms.openlocfilehash: 35ea3814e208921abaf44e6ef431c4e1b44cde60
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151145"
---
# <a name="certificate-of-clientcertificate-element"></a><span data-ttu-id="f95d7-102">\<certificate> элемента \<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="f95d7-102">\<certificate> of \<clientCertificate> Element</span></span>

<span data-ttu-id="f95d7-103">Указывает сертификат X.509, используемый для подписания и шифрования сообщений.</span><span class="sxs-lookup"><span data-stu-id="f95d7-103">Specifies an X.509 certificate used to sign and encrypt messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCertificate>**](clientcertificate-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**  
  
## <a name="syntax"></a><span data-ttu-id="f95d7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f95d7-104">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation = "CurrentUser/LocalMachine"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f95d7-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f95d7-105">Attributes and Elements</span></span>  

 <span data-ttu-id="f95d7-106">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f95d7-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f95d7-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f95d7-107">Attributes</span></span>  
  
|<span data-ttu-id="f95d7-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f95d7-108">Attribute</span></span>|<span data-ttu-id="f95d7-109">Описание</span><span class="sxs-lookup"><span data-stu-id="f95d7-109">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="f95d7-110">Строка, содержащая значение для поиска в хранилище сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="f95d7-110">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="f95d7-111">Тип, указанный в атрибуте, должен отвечать требованиям заданного значения X509FindType.</span><span class="sxs-lookup"><span data-stu-id="f95d7-111">The type contained in the attribute must satisfy the requirements of the specified X509FindType.</span></span> <span data-ttu-id="f95d7-112">Значением по умолчанию является пустая строка.</span><span class="sxs-lookup"><span data-stu-id="f95d7-112">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="f95d7-113">Задает расположение хранилища сертификатов Х.509, которое клиент использует для проверки сертификата сервера.</span><span class="sxs-lookup"><span data-stu-id="f95d7-113">Specifies the location of the X.509 certificate store that the client uses to validate the server’s certificate against.</span></span> <span data-ttu-id="f95d7-114">Допустимые значения.</span><span class="sxs-lookup"><span data-stu-id="f95d7-114">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="f95d7-115">-LocalMachine — хранилище сертификатов, назначенное локальному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="f95d7-115">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="f95d7-116">-CurrentUser: хранилище сертификатов, назначенное текущему пользователю.</span><span class="sxs-lookup"><span data-stu-id="f95d7-116">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="f95d7-117">По умолчанию используется значение LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="f95d7-117">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="f95d7-118">Задает имя открываемого хранилища сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="f95d7-118">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="f95d7-119">Допустимые значения.</span><span class="sxs-lookup"><span data-stu-id="f95d7-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="f95d7-120">-AddressBook: хранилище сертификатов для других пользователей.</span><span class="sxs-lookup"><span data-stu-id="f95d7-120">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="f95d7-121">-Аусрут: хранилище сертификатов для сторонних центров сертификации (ЦС).</span><span class="sxs-lookup"><span data-stu-id="f95d7-121">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="f95d7-122">-Цертификатионаусорити: хранилище сертификатов для промежуточных центров сертификации (ЦС).</span><span class="sxs-lookup"><span data-stu-id="f95d7-122">-   CertificationAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="f95d7-123">— Запрещено: хранилище сертификатов для отозванных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="f95d7-123">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="f95d7-124">-My: хранилище сертификатов для личных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="f95d7-124">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="f95d7-125">— Root: хранилище сертификатов для доверенных корневых центров сертификации (CAs).</span><span class="sxs-lookup"><span data-stu-id="f95d7-125">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="f95d7-126">-TrustedPeople: хранилище сертификатов для напрямую доверенных лиц и ресурсов.</span><span class="sxs-lookup"><span data-stu-id="f95d7-126">-   TrustedPeople: Certificate store for directly trusted people and resources.</span></span><br /><span data-ttu-id="f95d7-127">-Трустедпублишер: хранилище сертификатов для напрямую доверенных издателей.</span><span class="sxs-lookup"><span data-stu-id="f95d7-127">-   TrustedPublisher: Certificate store for directly trusted publishers.</span></span><br /><br /> <span data-ttu-id="f95d7-128">Значение по умолчанию - My.</span><span class="sxs-lookup"><span data-stu-id="f95d7-128">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="f95d7-129">Определяет тип поиска сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="f95d7-129">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="f95d7-130">Допустимые значения.</span><span class="sxs-lookup"><span data-stu-id="f95d7-130">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="f95d7-131">-(FindByThumbprint</span><span class="sxs-lookup"><span data-stu-id="f95d7-131">-   FindByThumbPrint</span></span><br /><span data-ttu-id="f95d7-132">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="f95d7-132">-   FindBySubjectName</span></span><br /><span data-ttu-id="f95d7-133">-Финдбисубжектдистингуишеднаме</span><span class="sxs-lookup"><span data-stu-id="f95d7-133">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="f95d7-134">-Финдбиссуернаме</span><span class="sxs-lookup"><span data-stu-id="f95d7-134">-   FindByIssuerName</span></span><br /><span data-ttu-id="f95d7-135">-Финдбиссуердистингуишеднаме</span><span class="sxs-lookup"><span data-stu-id="f95d7-135">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="f95d7-136">-Финдбисериалнумбер</span><span class="sxs-lookup"><span data-stu-id="f95d7-136">-   FindBySerialNumber</span></span><br /><span data-ttu-id="f95d7-137">-Финдбитимевалид</span><span class="sxs-lookup"><span data-stu-id="f95d7-137">-   FindByTimeValid</span></span><br /><span data-ttu-id="f95d7-138">-Финдбитименотетвалид</span><span class="sxs-lookup"><span data-stu-id="f95d7-138">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="f95d7-139">-Финдбитемплатенаме</span><span class="sxs-lookup"><span data-stu-id="f95d7-139">-   FindByTemplateName</span></span><br /><span data-ttu-id="f95d7-140">-Финдбяппликатионполици</span><span class="sxs-lookup"><span data-stu-id="f95d7-140">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="f95d7-141">-Финдбицертификатеполици</span><span class="sxs-lookup"><span data-stu-id="f95d7-141">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="f95d7-142">-Финдбекстенсион</span><span class="sxs-lookup"><span data-stu-id="f95d7-142">-   FindByExtension</span></span><br /><span data-ttu-id="f95d7-143">-Финдбикэйусаже</span><span class="sxs-lookup"><span data-stu-id="f95d7-143">-   FindByKeyUsage</span></span><br /><span data-ttu-id="f95d7-144">-Финдбисубжекткэйидентифиер</span><span class="sxs-lookup"><span data-stu-id="f95d7-144">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="f95d7-145">Тип, указанный в атрибуте `findValue`, должен отвечать требованиям заданного значения X509FindType.</span><span class="sxs-lookup"><span data-stu-id="f95d7-145">The type contained in the `findValue` attribute must satisfy the requirements of the specified X509FindType.</span></span><br /><br /> <span data-ttu-id="f95d7-146">Значение по умолчанию - FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="f95d7-146">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f95d7-147">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f95d7-147">Child Elements</span></span>  

 <span data-ttu-id="f95d7-148">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f95d7-148">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f95d7-149">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f95d7-149">Parent Elements</span></span>  
  
|<span data-ttu-id="f95d7-150">Элемент</span><span class="sxs-lookup"><span data-stu-id="f95d7-150">Element</span></span>|<span data-ttu-id="f95d7-151">Описание</span><span class="sxs-lookup"><span data-stu-id="f95d7-151">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCertificate>](clientcertificate-of-servicecredentials.md)||  
  
## <a name="remarks"></a><span data-ttu-id="f95d7-152">Remarks</span><span class="sxs-lookup"><span data-stu-id="f95d7-152">Remarks</span></span>  

 <span data-ttu-id="f95d7-153">Элемент `<certificate>` используется в случаях, когда служба должна заранее получить клиентский сертификат для безопасного обмена данными с клиентом.</span><span class="sxs-lookup"><span data-stu-id="f95d7-153">The `<certificate>` element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="f95d7-154">Это характерно для дуплексного обмена данными.</span><span class="sxs-lookup"><span data-stu-id="f95d7-154">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="f95d7-155">В более распространенном варианте «запрос/отклик» клиент включает сертификат в запрос, который используется службой для шифрования и подписания отклика.</span><span class="sxs-lookup"><span data-stu-id="f95d7-155">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="f95d7-156">Тем не менее при дуплексном обмене данными служба не получает запроса от клиента, и ей, таким образом, необходим сертификат клиента заранее, чтобы обеспечить защиту сообщения, отправляемого клиенту.</span><span class="sxs-lookup"><span data-stu-id="f95d7-156">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="f95d7-157">Следовательно, необходимо получить сертификат клиента при согласовании вне диапазона и указать сертификат с помощью этого элемента.</span><span class="sxs-lookup"><span data-stu-id="f95d7-157">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="f95d7-158">Дополнительные сведения о дуплексных службах см. [в разделе инструкции. Создание дуплексного контракта](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="f95d7-158">For more information about duplex services, see [How to: Create a Duplex Contract](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f95d7-159">Пример</span><span class="sxs-lookup"><span data-stu-id="f95d7-159">Example</span></span>  

 <span data-ttu-id="f95d7-160">В следующем примере кода демонстрируется поиск соответствующего сертификата X.509 и пользовательского типа проверки в элементе `<authentication>`.</span><span class="sxs-lookup"><span data-stu-id="f95d7-160">The following code specifies how to find an appropriate X.509 certificate and a custom validation type in the `<authentication>` element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f95d7-161">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f95d7-161">See also</span></span>

- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509ClientCertificateCredentialsElement>
- [<span data-ttu-id="f95d7-162">Поведение безопасности</span><span class="sxs-lookup"><span data-stu-id="f95d7-162">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="f95d7-163">Практическое руководство. Создание службы, использующей пользовательский проверяющий элемент управления для сертификатов</span><span class="sxs-lookup"><span data-stu-id="f95d7-163">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [<span data-ttu-id="f95d7-164">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="f95d7-164">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
