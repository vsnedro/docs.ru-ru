---
title: <transport> из <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: f150fb19-7de1-44af-81f4-86cad881cd05
ms.openlocfilehash: e8016eb9058f132722587368f1f8c7c03220af4a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73732786"
---
# <a name="transport-of-webhttpbinding"></a>\<transport> из \<webHttpBinding>
Определяет параметры безопасности уровня транспорта для конечной точки службы, настроенной для получения запросов HTTP.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<webHttpBinding>**](webhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-webhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<webHttpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"
                 proxyCredentialType="None|Basic|Digest|Ntlm|Windows"
                 realm="string">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</webHttpBinding>
```  
  
## <a name="type"></a>Type  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание:|  
|---------------|-----------------|  
|`clientCredentialType`|Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе. Это атрибут типа <xref:System.ServiceModel.HttpClientCredentialType>.|  
|`proxyCredentialType`|Задает учетные данные, используемые для проверки подлинности клиента при подключении к прокси-серверу домена. Это атрибут типа <xref:System.ServiceModel.HttpProxyCredentialType>.|  
|`realm`|Строка, указывающая область проверки подлинности для обычной проверки подлинности или дайджест-проверки подлинности. Значением по умолчанию является пустая строка.<br /><br /> Область проверки подлинности задает по крайней мере имя основного узла, выполняющего проверку подлинности. Она также может указывать коллекцию пользователей, которым разрешен доступ. Пользователь может запросить область проверки подлинности, чтобы выяснить, какое из нескольких возможных сочетаний имен пользователей и паролей можно использовать.|  
|`policyEnforcement`|Это перечисление указывает, когда следует применять <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.<br /><br /> 1. Never — политика никогда не применяется (Расширенная защита отключена).<br />2. WhenSupported — политика применяется, только если клиент поддерживает расширенную защиту.<br />3. всегда — политика всегда применяется принудительно. Клиенты, которые не поддерживают расширенную защиту, не смогут пройти проверку подлинности.|  
  
## <a name="clientcredentialtype-attribute"></a>Атрибут clientCredentialType  
  
|Значение|Описание|  
|-----------|-----------------|  
|`None`|Режим безопасности отключен.|  
|`Basic`|Используется обычная проверка подлинности.|  
|`Certificate`|Для проверки подлинности клиента используются сертификаты X.509.|  
|`Digest`|Используется дайджест-проверка подлинности.|  
|`Ntlm`|Используется проверка подлинности NTLM в качестве резервной в домене Windows.|  
|`Windows`|Используется встроенная проверка подлинности Windows.|  
  
## <a name="proxycredentialtype-attribute"></a>Атрибут proxyCredentialType  
  
|Значение|Описание|  
|-----------|-----------------|  
|`None`|Режим безопасности отключен.|  
|`Basic`|Используется обычная проверка подлинности.|  
|`Digest`|Используется дайджест-проверка подлинности.|  
|`Ntlm`|Используется проверка подлинности NTLM в качестве резервной в домене Windows.|  
|`Windows`|Используется встроенная проверка подлинности Windows.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<security>](security-of-webhttpbinding.md)|Представляет возможности безопасности [\<wsHttpBinding>](wshttpbinding.md) элемента.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.WebHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WebHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [Защита служб и клиентов](../../../wcf/feature-details/securing-services-and-clients.md)
- [Привязки](../../../wcf/bindings.md)
- [Настройка привязок, предоставляемых системой](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Использование привязок для настройки служб и клиентов](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [Модель веб-программирования HTTP WCF](../../../wcf/feature-details/wcf-web-http-programming-model.md)
