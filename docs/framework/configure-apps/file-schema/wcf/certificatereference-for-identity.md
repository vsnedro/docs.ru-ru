---
title: <certificateReference> для <identity>;
ms.date: 03/30/2017
ms.assetid: ac359c65-c22d-42d2-97de-db53b77cebdb
ms.openlocfilehash: 93a6290d780ff61756f7315cd0c32f0e199ca00f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70849994"
---
# <a name="certificatereference-for-identity"></a>\<certificateReference> для \<identity>;
Задает параметры для проверки сертификата X.509. Клиент Secure Windows Communication Foundation (WCF), который подключается к конечной точке с этим удостоверением, проверяет, что утверждения, представленные сервером, содержат утверждение удостоверения, используемое для создания этого удостоверения.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateReference>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<certificateReference findValue="String"
                      isChainIncluded="Boolean"
                      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                      storeLocation="LocalMachine/CurrentUser"
                      X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier">
</certificateReference>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание:|  
|---------------|-----------------|  
|findValue|Задает значение для поиска в хранилище сертификатов X.509. Тип, указанный в этом атрибуте, должен отвечать требованиям заданного значения `X509FindType`. Значением по умолчанию является пустая строка.|  
|isChainIncluded|Логическое значение, определяющее, выполнена ли проверка с использованием цепочки сертификатов.|  
|storeLocation|Задает расположение хранилища сертификатов, которое клиент может использовать для проверки сертификата сервера.<br /><br /> Допустимые значения.<br /><br /> -LocalMachine: хранилище сертификатов, назначенное локальному компьютеру.<br />-CurrentUser: хранилище сертификатов, назначенное текущему пользователю.<br /><br /> Значение по умолчанию - LocalMachine.<br /><br /> Это атрибут типа <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.|  
|storeName|Задает имя открываемого хранилища сертификатов X.509.<br /><br /> Допустимые значения.<br /><br /> -AddressBook: хранилище сертификатов для других пользователей.<br />-Аусрут: хранилище сертификатов для сторонних центров сертификации (ЦС).<br />-CertificateAuthority: хранилище сертификатов для промежуточных ЦС.<br />— Запрещено: хранилище сертификатов для отозванных сертификатов.<br />-My: хранилище сертификатов для личных сертификатов.<br />— Root: хранилище сертификатов для доверенных корневых центров сертификации.<br />-TrustedPeople: хранилище сертификатов для напрямую доверенных лиц и ресурсов.<br />-Трустедпублишер: хранилище сертификатов для напрямую доверенных издателей.<br /><br /> Значение по умолчанию - «My».<br /><br /> Это атрибут типа <xref:System.Security.Cryptography.X509Certificates.StoreName>.|  
|X509FindType|Определяет тип выполняемого поиска X.509. Тип, указанный в атрибуте `findValue`, должен отвечать требованиям заданного значения X509FindType.<br /><br /> Допустимые значения.<br /><br /> -(FindByThumbprint<br />-FindBySubjectName<br />-Финдбисубжектдистингуишеднаме<br />-Финдбиссуернаме<br />-Финдбиссуердистингуишеднаме<br />-Финдбисериалнумбер<br />-Финдбитимевалид<br />-Финдбитименотетвалид<br />-Финдбитемплатенаме<br />-Финдбяппликатионполици<br />-Финдбицертификатеполици<br />-Финдбекстенсион<br />-Финдбикэйусаже<br />-Финдбисубжекткэйидентифиер<br /><br /> Значение по умолчанию - FindBySubjectDistinguishedName.<br /><br /> Это атрибут типа <xref:System.Security.Cryptography.X509Certificates.X509FindType>.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<identity>](identity.md)|Задает параметры, которые обеспечивают проверку подлинности конечной точки другими конечными точками, с которыми происходит обмен сообщениями.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.CertificateReferenceElement>
- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
