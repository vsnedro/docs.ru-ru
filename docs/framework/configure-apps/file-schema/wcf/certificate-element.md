---
title: Элемент <certificate>
ms.date: 03/30/2017
ms.assetid: 9b3d9233-ef35-477a-bf5d-efd1e80a52f4
ms.openlocfilehash: e28e7d16073a56f3b6126439644bfff86c9af18b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400558"
---
# <a name="certificate-element"></a>Элемент \<certificate>
Задает сертификат X.509, используемый для подписи и шифрования сообщений для клиентов одноранговых сетей.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<certificate findValue="String"
             storeLocation="LocalMachine/CurrentUser"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание:|  
|---------------|-----------------|  
|`findValue`|Строка, содержащая значение для поиска в хранилище сертификатов X.509. Тип, указанный в этом атрибуте, должен отвечать требованиям заданного значения `x509FindType`. Значением по умолчанию является пустая строка.|  
|`storeLocation`|Задает расположение хранилища сертификатов Х.509, которое клиент может использовать для проверки сертификата однорангового узла. Допустимые значения.<br /><br /> -LocalMachine — хранилище сертификатов, назначенное локальному компьютеру.<br />-CurrentUser: хранилище сертификатов, назначенное текущему пользователю.<br /><br /> По умолчанию используется значение LocalMachine.|  
|`storeName`|Задает имя открываемого хранилища сертификатов X.509. Допустимые значения.<br /><br /> -AddressBook: хранилище сертификатов для других пользователей.<br />-Аусрут: хранилище сертификатов для сторонних центров сертификации (ЦС).<br />-CertificateAuthority: хранилище сертификатов для промежуточных центров сертификации (ЦС).<br />— Запрещено: хранилище сертификатов для отозванных сертификатов.<br />-My: хранилище сертификатов для личных сертификатов.<br />— Root: хранилище сертификатов для доверенных корневых центров сертификации (CAs).<br />-TrustedPeople: хранилище сертификатов для непосредственно доверенных лиц и ресурсов.<br />-Трустедпублишер: хранилище сертификатов для непосредственно доверенных издателей.<br /><br /> Значение по умолчанию - My.|  
|`X509FindType`|Определяет тип поиска сертификата X.509. Допустимые значения.<br /><br /> -(FindByThumbprint<br />-FindBySubjectName<br />-Финдбисубжектдистингуишеднаме<br />-Финдбиссуернаме<br />-Финдбиссуердистингуишеднаме<br />-Финдбисериалнумбер<br />-Финдбитимевалид<br />-Финдбитименотетвалид<br />-Финдбитемплатенаме<br />-Финдбяппликатионполици<br />-Финдбицертификатеполици<br />-Финдбекстенсион<br />-Финдбикэйусаже<br />-Финдбисубжекткэйидентифиер<br /><br /> Тип, указанный в атрибуте `findValue`, должен отвечать требованиям заданного значения `X509FindType`.<br /><br /> Значение по умолчанию - FindBySubjectDistinguishedName.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<peer>](peer-of-clientcredentials-element.md)|Задает учетные данные, используемые при проверке подлинности одноранговых клиентов.|  
  
## <a name="remarks"></a>Примечания  
 Этот элемент конфигурации содержит экземпляр X509Certificate2, используемый при проверке подлинности соседей в сетке узлов.  
  
 Дополнительные сведения о одноранговых программах см. в разделе одноранговая [сеть](../../../wcf/feature-details/peer-to-peer-networking.md).  
  
## <a name="example"></a>Пример  
 В следующем примере кода показывается, как найти сертификат, используемый в сценарии с одноранговой сетью.  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <peer>
          <certificate findValue="www.contoso.com"
                       storeLocation="LocalMachine"
                       x509FindType="FindByIssuerName" />
        </peer>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>
- <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>
- [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md)
- [Одноранговая сеть](../../../wcf/feature-details/peer-to-peer-networking.md)
- [Проверка подлинности сообщений для однорангового канала](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))
- [Пользовательской проверка подлинности для однорангового канала](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))
- [Защита приложений одноранговых каналов](../../../wcf/feature-details/securing-peer-channel-applications.md)
