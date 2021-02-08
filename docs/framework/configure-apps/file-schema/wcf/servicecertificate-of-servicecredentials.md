---
description: 'Дополнительные сведения <serviceCertificate> о: <serviceCredentials>'
title: <serviceCertificate> из <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 597ae6d5-4938-4950-9f5e-b2280e816182
ms.openlocfilehash: ab52f27949168562ec0cab0433c95843a7c312d0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786737"
---
# <a name="servicecertificate-of-servicecredentials"></a>\<serviceCertificate> из \<serviceCredentials>

Задает сертификат X.509, который будет использоваться для проверки подлинности службы при подключении к клиентам с использованием режима безопасности сообщений.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCertificate>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<serviceCertificate findValue="String"
                    storeLocation="LocalMachine/CurrentUser"
                    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                    x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`findValue`|Строка, содержащая значение для поиска в хранилище сертификатов X.509. Тип, указанный в атрибуте, должен отвечать требованиям заданного значения X509FindType. Значение по умолчанию - пустая строка.|  
|`storeLocation`|Задает расположение хранилища сертификатов Х.509, которое клиент использует для проверки сертификата сервера. Допустимые значения.<br /><br /> -LocalMachine — хранилище сертификатов, назначенное локальному компьютеру.<br />-CurrentUser: хранилище сертификатов, назначенное текущему пользователю.<br /><br /> По умолчанию используется значение LocalMachine.|  
|`storeName`|Задает имя открываемого хранилища сертификатов X.509. Допустимые значения.<br /><br /> -AddressBook: хранилище сертификатов для других пользователей.<br />-Аусрут: хранилище сертификатов для сторонних центров сертификации (ЦС).<br />-Цертификатаусорити: хранилище сертификатов для промежуточных центров сертификации (ЦС).<br />— Запрещено: хранилище сертификатов для отозванных сертификатов.<br />-My: хранилище сертификатов для личных сертификатов.<br />— Root: хранилище сертификатов для доверенных корневых центров сертификации (CAs).<br />-TrustedPeople: хранилище сертификатов для напрямую доверенных лиц и ресурсов.<br />-Трустедпублишер: хранилище сертификатов для напрямую доверенных издателей.<br /><br /> Значение по умолчанию - My.|  
|`x509FindType`|Определяет тип поиска сертификата X.509. Допустимые значения.<br /><br /> -(FindByThumbprint<br />-FindBySubjectName<br />-Финдбисубжектдистингуишеднаме<br />-Финдбиссуернаме<br />-Финдбиссуердистингуишеднаме<br />-Финдбисериалнумбер<br />-Финдбитимевалид<br />-Финдбитименотетвалид<br />-Финдбитемплатенаме<br />-Финдбяппликатионполици<br />-Финдбицертификатеполици<br />-Финдбекстенсион<br />-Финдбикэйусаже<br />-Финдбисубжекткэйидентифиер<br /><br /> Тип, указанный в атрибуте `findValue`, должен отвечать требованиям заданного значения X509FindType.<br /><br /> Значение по умолчанию - FindBySubjectDistinguishedName.|  
  
### <a name="child-elements"></a>Дочерние элементы  

 None  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.|  
  
## <a name="remarks"></a>Remarks  

 Этот элемент используется для задания сертификата X.509, который будет использоваться для проверки подлинности службы при подключении к клиентам с использованием режима безопасности сообщений. Если используется сертификат, который будет периодически обновляться, то его отпечаток изменится. В этом случае следует использовать имя субъекта в виде `x509FindType`, поскольку сертификат может быть выдан повторно с тем же именем субъекта.  
  
 Дополнительные сведения об использовании элемента см. в разделе [инструкции. Указание значений учетных данных клиента](../../../wcf/how-to-specify-client-credential-values.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ServiceCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>
- <xref:System.ServiceModel.Description.ServiceCredentials.ServiceCertificate%2A>
- [Практическое руководство. Задание значений учетных данных клиента](../../../wcf/how-to-specify-client-credential-values.md)
- [Поведение безопасности](../../../wcf/feature-details/security-behaviors-in-wcf.md)
