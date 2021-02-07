---
description: 'Дополнительные сведения о: <messageSenderAuthentication> element'
title: <messageSenderAuthentication> - элемент
ms.date: 03/30/2017
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
ms.openlocfilehash: 03c1cd626e7c3ad71026c076df3d757419810d74
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749341"
---
# <a name="messagesenderauthentication-element"></a>Элемент \<messageSenderAuthentication>

Задает параметры проверки подлинности для одноранговых отправителей сообщений.  
  
 Дополнительные сведения о одноранговых программах см. в разделе одноранговая [сеть](../../../wcf/feature-details/peer-to-peer-networking.md).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<messageSenderAuthentication>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`customCertificateValidatorType`|Тип и сборка, используемые для проверки пользовательского типа. Этот атрибут должен быть задан, когда `certificateValidationMode` имеет значение `Custom`.|  
|`certificateValidationMode`|Задает один из трех режимов для проверки учетных данных. Если свойству присвоено значение `Custom`, также необходимо указать свойство `customCertificateValidator`.|  
|`revocationMode`|Один из режимов, используемых для проверки списков отозванных сертификатов (CRL).|  
|`trustedStoreLocation`|Одно из двух местоположений системного хранилища: `LocalMachine` или `CurrentUser`. Данное значение используется при согласовании сертификата службы для клиента. Проверка выполняется для хранилища **доверенных лиц** в указанном расположении магазина.|  
  
## <a name="customcertificatevalidatortype-attribute"></a>Атрибут customCertificateValidatorType  
  
|Значение|Описание|  
|-----------|-----------------|  
|Строка|Необязательный параметр. Задает имя типа и сборку, а также другие данные, используемые для поиска типа. Требуется, как минимум, пространство имен и имя типа. К дополнительным сведениям относятся: имя сборки, номер версии, язык и региональные параметры и маркер открытого ключа.|  
  
## <a name="certificatevalidationmode-attribute"></a>Атрибут certificateValidationMode  
  
|Значение|Описание|  
|-----------|-----------------|  
|Перечисление|Необязательный элемент. Одно из следующих значений: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`. Значение по умолчанию — `ChainTrust`. Значение по умолчанию — `ChainTrust`.<br /><br /> Дополнительные сведения см. в разделе [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md).|  
  
## <a name="revocationmode-attribute"></a>Атрибут revocationMode  
  
|Значение|Описание|  
|-----------|-----------------|  
|Перечисление|Одно из следующих значений: `NoCheck`, `Online`, `Offline`. Значение по умолчанию — `Online`.<br /><br /> Дополнительные сведения см. в разделе [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md).|  
  
## <a name="trustedstorelocation-attribute"></a>Атрибут trustedStoreLocation  
  
|Значение|Описание|  
|-----------|-----------------|  
|Перечисление|Одно из следующих значений: `LocalMachine` или `CurrentUser`. Значение по умолчанию — `CurrentUser`. Если клиентское приложение выполняется под учетной записью системы, сертификат обычно находится в расположении `LocalMachine`. Если клиентское приложение выполняется под учетной записью пользователя, то сертификат обычно находится в расположении `CurrentUser`. Значение по умолчанию — `CurrentUser`.|  
  
### <a name="child-elements"></a>Дочерние элементы  

 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<peer>](peer-of-clientcredentials-element.md)|Задает учетные данные, используемые для проверки подлинности клиента при подключении к одноранговой службе.|  
  
## <a name="remarks"></a>Remarks  

 Этот элемент должен быть настроен, если выбрана проверка подлинности сообщения. Для выходных каналов каждое сообщение подписывается с помощью сертификата, предоставленного [\<certificate>](certificate-element.md) . Во всех сообщениях перед доставкой приложению проверяются учетные данные сообщения с помощью модуля проверки, заданного атрибутом `customCertificateValidatorType` этого элемента. Модуль проверки может принять или отклонить учетные данные.  
  
## <a name="example"></a>Пример  

 В приведенном ниже примере кода устанавливается режим проверки отправителя сообщения `PeerOrChainTrust`.  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <peer>
          <certificate findValue="www.contoso.com"
                       storeLocation="LocalMachine"
                       x509FindType="FindByIssuerName" />
          <messageSenderAuthentication certificateValidationMode="PeerOrChainTrust" />
          <messageSenderAuthentication certificateValidationMode="None" />
        </peer>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md)
- [Одноранговая сеть](../../../wcf/feature-details/peer-to-peer-networking.md)
- [Проверка подлинности сообщений для однорангового канала](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))
- [Пользовательской проверка подлинности для однорангового канала](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))
- [Защита приложений одноранговых каналов](../../../wcf/feature-details/securing-peer-channel-applications.md)
