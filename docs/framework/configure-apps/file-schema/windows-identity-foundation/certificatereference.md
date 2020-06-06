---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: 47d432a84d070476ddffd9b98a4ba46d8163bdc3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152818"
---
# \<certificateReference>
<span data-ttu-id="9d229-101">Задает параметры, используемые для поиска и проверки сертификата X. 509 в хранилище сертификатов.</span><span class="sxs-lookup"><span data-stu-id="9d229-101">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateReference>**  
  
## <a name="syntax"></a><span data-ttu-id="9d229-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9d229-102">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
      <certificateReference
        storeName="AddressBook||AuthRoot||CertificateAuthority||Disallowed||My||Root||TrustedPeople||TrustedPublisher"  
        storeLocation="CurrentUser||LocalMachine"  
        x509FindType="FindByThumbprint||FindBySubjectName||FindBySubjectDistinguishedName||FindByIssuerName||FindByIssuerDistinguishedName||FindBySerialNumber||FindByTimeValid||FindByTimeNotYetValid||FindByTimeExpired||FindByTemplateName||FindByApplicationPolicy||FindByCertificatePolicy||FindByExtension||FindByKeyUsage||FindBySubjectKeyIdentifier"  
        findValue=xs:String  
        isChainIncluded=xs:Boolean >  
      </certificateReference>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9d229-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9d229-103">Attributes and Elements</span></span>  
 <span data-ttu-id="9d229-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9d229-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9d229-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9d229-105">Attributes</span></span>  
  
|<span data-ttu-id="9d229-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="9d229-106">Attribute</span></span>|<span data-ttu-id="9d229-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="9d229-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9d229-108">storeName</span><span class="sxs-lookup"><span data-stu-id="9d229-108">storeName</span></span>|<span data-ttu-id="9d229-109">Имя хранилища сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="9d229-109">The name of the X.509 certificate store.</span></span> <span data-ttu-id="9d229-110">Значение по умолчанию — "My".</span><span class="sxs-lookup"><span data-stu-id="9d229-110">The default is "My".</span></span> <span data-ttu-id="9d229-111">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="9d229-111">Optional.</span></span>|  
|<span data-ttu-id="9d229-112">storeLocation</span><span class="sxs-lookup"><span data-stu-id="9d229-112">storeLocation</span></span>|<span data-ttu-id="9d229-113"><xref:System.Security.Cryptography.X509Certificates.StoreLocation>Значение, указывающее расположение хранилища сертификатов X. 509.</span><span class="sxs-lookup"><span data-stu-id="9d229-113">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="9d229-114">Значение по умолчанию — LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="9d229-114">The default value is "LocalMachine".</span></span> <span data-ttu-id="9d229-115">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="9d229-115">Optional.</span></span>|  
|<span data-ttu-id="9d229-116">x509FindType</span><span class="sxs-lookup"><span data-stu-id="9d229-116">x509FindType</span></span>|<span data-ttu-id="9d229-117"><xref:System.Security.Cryptography.X509Certificates.X509FindType>Значение типа, указывающее тип выполняемого поиска.</span><span class="sxs-lookup"><span data-stu-id="9d229-117">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="9d229-118">Значение по умолчанию — "Финдбисубжектдистингуишеднаме".</span><span class="sxs-lookup"><span data-stu-id="9d229-118">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="9d229-119">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="9d229-119">Optional.</span></span>|  
|<span data-ttu-id="9d229-120">findValue</span><span class="sxs-lookup"><span data-stu-id="9d229-120">findValue</span></span>|<span data-ttu-id="9d229-121">Значение для поиска в хранилище сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="9d229-121">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="9d229-122">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="9d229-122">Optional.</span></span>|  
|<span data-ttu-id="9d229-123">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="9d229-123">isChainIncluded</span></span>|<span data-ttu-id="9d229-124">Указывает, следует ли выполнять проверку с помощью цепочки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="9d229-124">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="9d229-125">Значение по умолчанию — true; Проверка выполняется с помощью цепочки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="9d229-125">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="9d229-126">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="9d229-126">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9d229-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9d229-127">Child Elements</span></span>  
 <span data-ttu-id="9d229-128">Нет</span><span class="sxs-lookup"><span data-stu-id="9d229-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9d229-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9d229-129">Parent Elements</span></span>  
  
|<span data-ttu-id="9d229-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="9d229-130">Element</span></span>|<span data-ttu-id="9d229-131">Описание</span><span class="sxs-lookup"><span data-stu-id="9d229-131">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate.md)|<span data-ttu-id="9d229-132">Настраивает сертификат, используемый для шифрования и расшифровки маркеров.</span><span class="sxs-lookup"><span data-stu-id="9d229-132">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d229-133">Примечания</span><span class="sxs-lookup"><span data-stu-id="9d229-133">Remarks</span></span>  
 <span data-ttu-id="9d229-134">`<certificateReference>`Элемент задает параметры, используемые для поиска и проверки сертификата X. 509 в хранилище сертификатов.</span><span class="sxs-lookup"><span data-stu-id="9d229-134">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="9d229-135">Если он указан как дочерний элемент `<serviceCertificate>` , он указывает параметры расположения и проверки сертификата X. 509, который используется для шифрования и расшифровки токенов.</span><span class="sxs-lookup"><span data-stu-id="9d229-135">When it is specified as the child element of the `<serviceCertificate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="9d229-136">`<certificateReference>`Элемент представлен <xref:System.ServiceModel.Configuration.CertificateReferenceElement> классом.</span><span class="sxs-lookup"><span data-stu-id="9d229-136">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>
