---
title: <add> элемента <scopedCertificates>
ms.date: 03/30/2017
ms.assetid: e21c1ef8-d6d6-4bca-ac5a-6fbf4bd77412
ms.openlocfilehash: b00a342108beca69a906fbf6212915768e98778f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398345"
---
# <a name="add-of-scopedcertificates-element"></a><span data-ttu-id="d5361-102">\<add> элемента \<scopedCertificates></span><span class="sxs-lookup"><span data-stu-id="d5361-102">\<add> of \<scopedCertificates> Element</span></span>
<span data-ttu-id="d5361-103">Добавляет сертификат X.509 в коллекцию сертификатов в области действия.</span><span class="sxs-lookup"><span data-stu-id="d5361-103">Adds an X.509 certificate to the collection of scoped certificates.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<scopedCertificates>**](scopedcertificates-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="d5361-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d5361-104">Syntax</span></span>  
  
```xml  
<add findValue="String"
     storeLocation="CurrentUser/LocalMachine"
     storeName=" CurrentUser/LocalMachine"
     targetUri="string"
     x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d5361-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d5361-105">Attributes and Elements</span></span>  
 <span data-ttu-id="d5361-106">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d5361-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d5361-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d5361-107">Attributes</span></span>  
  
|<span data-ttu-id="d5361-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d5361-108">Attribute</span></span>|<span data-ttu-id="d5361-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="d5361-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d5361-110">targetUri</span><span class="sxs-lookup"><span data-stu-id="d5361-110">targetUri</span></span>|<span data-ttu-id="d5361-111">Строка.</span><span class="sxs-lookup"><span data-stu-id="d5361-111">String.</span></span> <span data-ttu-id="d5361-112">Задает универсальный код ресурса (URI) службы, связанной с сертификатом.</span><span class="sxs-lookup"><span data-stu-id="d5361-112">Specifies the URI of the service associated with the certificate.</span></span>|  
|<span data-ttu-id="d5361-113">findValue</span><span class="sxs-lookup"><span data-stu-id="d5361-113">findValue</span></span>|<span data-ttu-id="d5361-114">Строка.</span><span class="sxs-lookup"><span data-stu-id="d5361-114">String.</span></span> <span data-ttu-id="d5361-115">Значение, которое нужно найти.</span><span class="sxs-lookup"><span data-stu-id="d5361-115">The value to search for.</span></span>|  
|<span data-ttu-id="d5361-116">x509FindType</span><span class="sxs-lookup"><span data-stu-id="d5361-116">x509FindType</span></span>|<span data-ttu-id="d5361-117">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="d5361-117">Enumeration.</span></span> <span data-ttu-id="d5361-118">Одно из полей сертификата, где следует проводить поиск.</span><span class="sxs-lookup"><span data-stu-id="d5361-118">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="d5361-119">storeLocation</span><span class="sxs-lookup"><span data-stu-id="d5361-119">storeLocation</span></span>|<span data-ttu-id="d5361-120">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="d5361-120">Enumeration.</span></span> <span data-ttu-id="d5361-121">Одно из двух местоположений хранилища, где следует проводить поиск.</span><span class="sxs-lookup"><span data-stu-id="d5361-121">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="d5361-122">storeName</span><span class="sxs-lookup"><span data-stu-id="d5361-122">storeName</span></span>|<span data-ttu-id="d5361-123">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="d5361-123">Enumeration.</span></span> <span data-ttu-id="d5361-124">Одно из системных хранилищ, где следует проводить поиск.</span><span class="sxs-lookup"><span data-stu-id="d5361-124">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="d5361-125">Атрибут findValue</span><span class="sxs-lookup"><span data-stu-id="d5361-125">findValue Attribute</span></span>  
  
|<span data-ttu-id="d5361-126">Значение</span><span class="sxs-lookup"><span data-stu-id="d5361-126">Value</span></span>|<span data-ttu-id="d5361-127">Описание</span><span class="sxs-lookup"><span data-stu-id="d5361-127">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d5361-128">Строка</span><span class="sxs-lookup"><span data-stu-id="d5361-128">String</span></span>|<span data-ttu-id="d5361-129">Значение зависит от поля (заданного атрибутом x509FindType), поиск которого выполняется.</span><span class="sxs-lookup"><span data-stu-id="d5361-129">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="d5361-130">Например, при поиске отпечатка значение должно быть строкой шестнадцатеричных чисел.</span><span class="sxs-lookup"><span data-stu-id="d5361-130">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="d5361-131">Атрибут x509FindType</span><span class="sxs-lookup"><span data-stu-id="d5361-131">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="d5361-132">Значение</span><span class="sxs-lookup"><span data-stu-id="d5361-132">Value</span></span>|<span data-ttu-id="d5361-133">Описание</span><span class="sxs-lookup"><span data-stu-id="d5361-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d5361-134">Перечисление</span><span class="sxs-lookup"><span data-stu-id="d5361-134">Enumeration</span></span>|<span data-ttu-id="d5361-135">К числу значений относятся следующие: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="d5361-135">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="d5361-136">Атрибут storeLocation</span><span class="sxs-lookup"><span data-stu-id="d5361-136">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="d5361-137">Значение</span><span class="sxs-lookup"><span data-stu-id="d5361-137">Value</span></span>|<span data-ttu-id="d5361-138">Описание</span><span class="sxs-lookup"><span data-stu-id="d5361-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d5361-139">Перечисление</span><span class="sxs-lookup"><span data-stu-id="d5361-139">Enumeration</span></span>|<span data-ttu-id="d5361-140">CurrentUser или LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="d5361-140">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="d5361-141">Атрибут storeName</span><span class="sxs-lookup"><span data-stu-id="d5361-141">storeName Attribute</span></span>  
  
|<span data-ttu-id="d5361-142">Значение</span><span class="sxs-lookup"><span data-stu-id="d5361-142">Value</span></span>|<span data-ttu-id="d5361-143">Описание</span><span class="sxs-lookup"><span data-stu-id="d5361-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d5361-144">Перечисление</span><span class="sxs-lookup"><span data-stu-id="d5361-144">Enumeration</span></span>|<span data-ttu-id="d5361-145">К числу значений относятся следующие: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople и TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="d5361-145">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d5361-146">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d5361-146">Child Elements</span></span>  
 <span data-ttu-id="d5361-147">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d5361-147">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d5361-148">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d5361-148">Parent Elements</span></span>  
  
|<span data-ttu-id="d5361-149">Элемент</span><span class="sxs-lookup"><span data-stu-id="d5361-149">Element</span></span>|<span data-ttu-id="d5361-150">Описание</span><span class="sxs-lookup"><span data-stu-id="d5361-150">Description</span></span>|  
|-------------|-----------------|  
|[\<scopedCertificates>](scopedcertificates-element.md)|<span data-ttu-id="d5361-151">Представляет коллекцию сертификатов X.509, предоставленную конкретными службами (в области действия) для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="d5361-151">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5361-152">Примечания</span><span class="sxs-lookup"><span data-stu-id="d5361-152">Remarks</span></span>  
 <span data-ttu-id="d5361-153">Этот элемент позволяет клиенту настроить сертификат службы для использования на основе URL-адреса службы, с которой он связывается.</span><span class="sxs-lookup"><span data-stu-id="d5361-153">This element enables the client to configure a service certificate to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="d5361-154">Это особенно полезно в сценариях с выданным маркером, в которых клиент может связываться с несколькими службами (с конечной службой, а также с промежуточными службами маркеров безопасности).</span><span class="sxs-lookup"><span data-stu-id="d5361-154">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="d5361-155">Для привязок, в которых используется безопасность сообщений на основе сертификатов, этот сертификат используется для шифрования сообщений службе; предполагается также, что он будет использоваться службой для подписи ответов клиенту.</span><span class="sxs-lookup"><span data-stu-id="d5361-155">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="d5361-156">Если для привязки необходим сертификат для службы, а конкретный сертификат для URL-адреса службы в элементе ScopedCertificates отсутствует, то используется сертификат по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d5361-156">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="d5361-157">Дополнительные сведения см. в разделе «сертификаты с заданной областью» раздела [о создании федеративного клиента](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span><span class="sxs-lookup"><span data-stu-id="d5361-157">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5361-158">Пример</span><span class="sxs-lookup"><span data-stu-id="d5361-158">Example</span></span>  
 <span data-ttu-id="d5361-159">В следующем примере к коллекции добавляется сертификат X.509.</span><span class="sxs-lookup"><span data-stu-id="d5361-159">The following example adds an X.509 certificate the collection.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <serviceCertificate>
          <scopedCertificates>
            <add targetUri="http://www.contoso.com"
                 findValue="www.Contoso.com"
                 storeLocation="LocalMachine"
                 storeName="Root"
                 x509FindType="FindByIssuerName" />
          </scopedCertificates>
        </serviceCertificate>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="d5361-160">См. также</span><span class="sxs-lookup"><span data-stu-id="d5361-160">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>
- [<span data-ttu-id="d5361-161">Практическое руководство. Создание федеративного клиента</span><span class="sxs-lookup"><span data-stu-id="d5361-161">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="d5361-162">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="d5361-162">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="d5361-163">Обеспечение безопасности клиентов</span><span class="sxs-lookup"><span data-stu-id="d5361-163">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="d5361-164">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="d5361-164">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
