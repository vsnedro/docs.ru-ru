---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: c21e5186b8afdf8c72cbfc605af94c95bc2bc0d5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201385"
---
# \<certificateReference>

Задает параметры, используемые для поиска и проверки сертификата X. 509 в хранилище сертификатов.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateReference>**  
  
## <a name="syntax"></a>Синтаксис  
  
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
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|storeName|Имя хранилища сертификатов X.509. Значение по умолчанию — "My". Необязательный элемент.|  
|storeLocation|<xref:System.Security.Cryptography.X509Certificates.StoreLocation>Значение, указывающее расположение хранилища сертификатов X. 509. Значение по умолчанию — LocalMachine. Необязательный элемент.|  
|x509FindType|<xref:System.Security.Cryptography.X509Certificates.X509FindType>Значение типа, указывающее тип выполняемого поиска. Значение по умолчанию — "Финдбисубжектдистингуишеднаме". Необязательный элемент.|  
|findValue|Значение для поиска в хранилище сертификатов X.509. Необязательный элемент.|  
|isChainIncluded|Указывает, следует ли выполнять проверку с помощью цепочки сертификатов. Значение по умолчанию — true; Проверка выполняется с помощью цепочки сертификатов. Необязательный элемент.|  
  
### <a name="child-elements"></a>Дочерние элементы  

 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate.md)|Настраивает сертификат, используемый для шифрования и расшифровки маркеров.|  
  
## <a name="remarks"></a>Remarks  

 `<certificateReference>`Элемент задает параметры, используемые для поиска и проверки сертификата X. 509 в хранилище сертификатов. Если он указан как дочерний элемент `<serviceCertificate>` , он указывает параметры расположения и проверки сертификата X. 509, который используется для шифрования и расшифровки токенов. `<certificateReference>`Элемент представлен <xref:System.ServiceModel.Configuration.CertificateReferenceElement> классом.
