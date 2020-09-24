---
title: Элемент <defaultCertificate>
ms.date: 03/30/2017
ms.assetid: f1ddf364-9a00-45d3-b989-ff381c154ce6
ms.openlocfilehash: 2eaec4f4296f90579ca32d817f0a20da4ccc9a37
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153902"
---
# <a name="defaultcertificate-element"></a><span data-ttu-id="bd9fc-102">Элемент \<defaultCertificate></span><span class="sxs-lookup"><span data-stu-id="bd9fc-102">\<defaultCertificate> Element</span></span>

<span data-ttu-id="bd9fc-103">Задает сертификат X.509 для использования, когда служба или служба маркеров безопасности не предоставляет сертификат посредством протокола согласования.</span><span class="sxs-lookup"><span data-stu-id="bd9fc-103">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="bd9fc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bd9fc-104">Syntax</span></span>  
  
```xml  
<defaultCertificate findValue="String"
                    storeLocation=" CurrentUser/LocalMachine"
                    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                    x509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialiNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bd9fc-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bd9fc-105">Attributes and Elements</span></span>  

 <span data-ttu-id="bd9fc-106">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bd9fc-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bd9fc-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bd9fc-107">Attributes</span></span>  
  
|<span data-ttu-id="bd9fc-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="bd9fc-108">Attribute</span></span>|<span data-ttu-id="bd9fc-109">Описание</span><span class="sxs-lookup"><span data-stu-id="bd9fc-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bd9fc-110">findValue</span><span class="sxs-lookup"><span data-stu-id="bd9fc-110">findValue</span></span>|<span data-ttu-id="bd9fc-111">Строка.</span><span class="sxs-lookup"><span data-stu-id="bd9fc-111">String.</span></span> <span data-ttu-id="bd9fc-112">Значение, которое нужно найти.</span><span class="sxs-lookup"><span data-stu-id="bd9fc-112">The value to search for.</span></span>|  
|<span data-ttu-id="bd9fc-113">x509FindType</span><span class="sxs-lookup"><span data-stu-id="bd9fc-113">x509FindType</span></span>|<span data-ttu-id="bd9fc-114">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="bd9fc-114">Enumeration.</span></span> <span data-ttu-id="bd9fc-115">Одно из полей сертификата, где следует проводить поиск.</span><span class="sxs-lookup"><span data-stu-id="bd9fc-115">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="bd9fc-116">storeLocation</span><span class="sxs-lookup"><span data-stu-id="bd9fc-116">storeLocation</span></span>|<span data-ttu-id="bd9fc-117">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="bd9fc-117">Enumeration.</span></span> <span data-ttu-id="bd9fc-118">Одно из двух системных расположений хранилища, где следует проводить поиск.</span><span class="sxs-lookup"><span data-stu-id="bd9fc-118">One of the two system store locations to search.</span></span>|  
|<span data-ttu-id="bd9fc-119">storeName</span><span class="sxs-lookup"><span data-stu-id="bd9fc-119">storeName</span></span>|<span data-ttu-id="bd9fc-120">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="bd9fc-120">Enumeration.</span></span> <span data-ttu-id="bd9fc-121">Одно из системных хранилищ, где следует проводить поиск.</span><span class="sxs-lookup"><span data-stu-id="bd9fc-121">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="bd9fc-122">Атрибут findValue</span><span class="sxs-lookup"><span data-stu-id="bd9fc-122">findValue Attribute</span></span>  
  
|<span data-ttu-id="bd9fc-123">Значение</span><span class="sxs-lookup"><span data-stu-id="bd9fc-123">Value</span></span>|<span data-ttu-id="bd9fc-124">Описание</span><span class="sxs-lookup"><span data-stu-id="bd9fc-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bd9fc-125">Строка</span><span class="sxs-lookup"><span data-stu-id="bd9fc-125">String</span></span>|<span data-ttu-id="bd9fc-126">Значение зависит от поля (заданного атрибутом x509FindType), поиск которого выполняется.</span><span class="sxs-lookup"><span data-stu-id="bd9fc-126">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="bd9fc-127">Например, при поиске отпечатка значение должно быть строкой шестнадцатеричных чисел.</span><span class="sxs-lookup"><span data-stu-id="bd9fc-127">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="bd9fc-128">Атрибут x509FindType</span><span class="sxs-lookup"><span data-stu-id="bd9fc-128">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="bd9fc-129">Значение</span><span class="sxs-lookup"><span data-stu-id="bd9fc-129">Value</span></span>|<span data-ttu-id="bd9fc-130">Описание</span><span class="sxs-lookup"><span data-stu-id="bd9fc-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bd9fc-131">Перечисление</span><span class="sxs-lookup"><span data-stu-id="bd9fc-131">Enumeration</span></span>|<span data-ttu-id="bd9fc-132">К числу значений относятся следующие: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="bd9fc-132">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="bd9fc-133">Атрибут storeLocation</span><span class="sxs-lookup"><span data-stu-id="bd9fc-133">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="bd9fc-134">Значение</span><span class="sxs-lookup"><span data-stu-id="bd9fc-134">Value</span></span>|<span data-ttu-id="bd9fc-135">Описание</span><span class="sxs-lookup"><span data-stu-id="bd9fc-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bd9fc-136">Перечисление</span><span class="sxs-lookup"><span data-stu-id="bd9fc-136">Enumeration</span></span>|<span data-ttu-id="bd9fc-137">CurrentUser или LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="bd9fc-137">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="bd9fc-138">Атрибут storeName</span><span class="sxs-lookup"><span data-stu-id="bd9fc-138">storeName Attribute</span></span>  
  
|<span data-ttu-id="bd9fc-139">Значение</span><span class="sxs-lookup"><span data-stu-id="bd9fc-139">Value</span></span>|<span data-ttu-id="bd9fc-140">Описание</span><span class="sxs-lookup"><span data-stu-id="bd9fc-140">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bd9fc-141">Перечисление</span><span class="sxs-lookup"><span data-stu-id="bd9fc-141">Enumeration</span></span>|<span data-ttu-id="bd9fc-142">К числу значений относятся следующие: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople и TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="bd9fc-142">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bd9fc-143">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bd9fc-143">Child Elements</span></span>  

 <span data-ttu-id="bd9fc-144">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="bd9fc-144">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bd9fc-145">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bd9fc-145">Parent Elements</span></span>  
  
|<span data-ttu-id="bd9fc-146">Элемент</span><span class="sxs-lookup"><span data-stu-id="bd9fc-146">Element</span></span>|<span data-ttu-id="bd9fc-147">Описание</span><span class="sxs-lookup"><span data-stu-id="bd9fc-147">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="bd9fc-148">Задает сертификат для использования при проверке подлинности службы для клиента.</span><span class="sxs-lookup"><span data-stu-id="bd9fc-148">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bd9fc-149">Remarks</span><span class="sxs-lookup"><span data-stu-id="bd9fc-149">Remarks</span></span>  

 <span data-ttu-id="bd9fc-150">Для привязок, использующих безопасность сообщений на основе сертификатов, сертификат, заданный этим элементом конфигурации, используется для шифрования сообщений службе; предполагается также, что он будет использоваться службой для подписи ответов клиенту.</span><span class="sxs-lookup"><span data-stu-id="bd9fc-150">For bindings that use certificate-based message security, certificate specified by this configuration element is used to encrypt messages to the service and is expected to be used by the service for signing replies to the client.</span></span> <span data-ttu-id="bd9fc-151">Он сохраняет один сертификат для использования при отсутствии сертификата, заданного службой сертификата.</span><span class="sxs-lookup"><span data-stu-id="bd9fc-151">It stores a single certificate to be used when no certificate is specified by a service.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd9fc-152">Пример</span><span class="sxs-lookup"><span data-stu-id="bd9fc-152">Example</span></span>  

 <span data-ttu-id="bd9fc-153">В следующем примере указывается сертификат, который будет использоваться для конечных точек, URI которых начинается с `http://www.contoso.com` , и сертификат, который будет использоваться для всех остальных конечных точек, не выполняющих согласование сертификатов.</span><span class="sxs-lookup"><span data-stu-id="bd9fc-153">The following example specifies a certificate to use for endpoints whose URI begins with `http://www.contoso.com` and a certificate to use for all other endpoints that do not perform certificate negotiation.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bd9fc-154">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bd9fc-154">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509DefaultServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.DefaultCertificate%2A>
- [<span data-ttu-id="bd9fc-155">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="bd9fc-155">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [\<authentication>](authentication-of-clientcertificate-element.md)
- [<span data-ttu-id="bd9fc-156">Обеспечение безопасности клиентов</span><span class="sxs-lookup"><span data-stu-id="bd9fc-156">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="bd9fc-157">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="bd9fc-157">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
