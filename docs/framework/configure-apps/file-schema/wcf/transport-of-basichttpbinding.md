---
description: 'Дополнительные сведения <transport> о: <basicHttpBinding>'
title: <transport> из <basicHttpBinding>
ms.date: 03/30/2017
ms.assetid: 4c5ba293-3d7e-47a6-b84e-e9022857b7e5
ms.openlocfilehash: 6148bbd5fa234adb51266714fff818e72f0abf40
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99773541"
---
# <a name="transport-of-basichttpbinding"></a>\<transport> из \<basicHttpBinding>

Определяет свойства, которые управляют параметрами проверки подлинности для транспорта HTTP.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<basicHttpBinding>**](basichttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-basichttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<basicHttpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"
                 proxyCredentialType="None|Basic|Digest|Ntlm|Windows"
                 realm="String">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</basicHttpBinding>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|clientCredentialType|— Указывает тип учетных данных, используемых при проверке подлинности клиента с помощью проверки подлинности HTTP.  Значение по умолчанию — `None`. Это атрибут типа <xref:System.ServiceModel.HttpClientCredentialType>.|  
|proxyCredentialType|— Указывает тип учетных данных, используемых при выполнении проверки подлинности клиента в домене с использованием прокси-сервера через HTTP. Этот атрибут применим, только если атрибут `mode` родительского элемента `security` имеет значение `Transport` или `TransportCredentialsOnly`. Это атрибут типа <xref:System.ServiceModel.HttpProxyCredentialType>.|  
|realm|Строка, указывающая область, используемую схемой проверки подлинности HTTP для обычной проверки подлинности или дайджест-проверки подлинности. Значение по умолчанию - пустая строка.|  
|policyEnforcement|Это перечисление указывает, когда следует применять <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.<br /><br /> 1. Never — политика никогда не применяется (Расширенная защита отключена).<br />2. WhenSupported — политика применяется, только если клиент поддерживает расширенную защиту.<br />3. всегда — политика всегда применяется принудительно. Клиенты, которые не поддерживают расширенную защиту, не смогут пройти проверку подлинности.|  
|protectionScenario|Это перечисление указывает сценарий защиты, регламентированный политикой.|  
  
## <a name="clientcredentialtype-attribute"></a>Атрибут clientCredentialType  
  
|Значение|Описание|  
|-----------|-----------------|  
|None|Во время передачи сообщения не защищены.|  
|Basic|Задает обычную проверку подлинности.|  
|Digest (дайджест)|Задает дайджест-проверку подлинности.|  
|Ntlm|Задает проверку подлинности NTLM, если это возможно и если не удается выполнить проверку подлинности Windows.|  
|Windows|Задает встроенную проверку подлинности Windows.|  
  
## <a name="proxycredentialtype-attribute"></a>Атрибут proxyCredentialType  
  
|Значение|Описание|  
|-----------|-----------------|  
|None|— Сообщения не защищаются во время перемещения.|  
|Basic|Задает обычную проверку подлинности, как определено документом RFC 2617, который посвящен проверке подлинности HTTP, обычной проверке и дайджест-проверке подлинности.|  
|Digest (дайджест)|Задает дайджест-проверку подлинности, как определено документом RFC 2617, который посвящен проверке подлинности HTTP, обычной проверке и дайджест-проверке подлинности.|  
|Ntlm|Задает проверку подлинности NTLM, если это возможно и если не удается выполнить проверку подлинности Windows.|  
|Windows|Задает встроенную проверку подлинности Windows.|  
|Certificate|Выполняет проверку подлинности клиента с использованием сертификата. Такая возможность действует, только если атрибут `Mode` родительского элемента `security` имеет значение Transport, и не действует, если этот атрибут имеет значение TransportCredentialOnly.|  
  
### <a name="child-elements"></a>Дочерние элементы  

 None  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<security>](security-of-basichttpbinding.md)|Определяет возможности безопасности для [\<basicHttpBinding>](basichttpbinding.md) .|  
  
## <a name="example"></a>Пример  

 В следующем примере демонстрируется использование безопасности транспорта SSL с использованием основной привязки. По умолчанию основная привязка поддерживает взаимодействие по протоколу HTTP.  
  
```xml  
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="basicHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>
  <bindings>
    <basicHttpBinding>
      <!-- Configure basicHttpBinding with Transport security -->
      <!-- mode and clientCredentialType set to None. -->
      <binding name="Binding1">
        <security mode="Transport">
          <transport clientCredentialType="None"
                     proxyCredentialType="None">
            <extendedProtectionPolicy policyEnforcement="WhenSupported"
                                      protectionScenario="TransportSelected">
              <customServiceNames>
              </customServiceNames>
            </extendedProtectionPolicy>
          </transport>
        </security>
      </binding>
    </basicHttpBinding>
  </bindings>
</system.serviceModel>
```  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.BasicHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- <xref:System.ServiceModel.HttpTransportSecurity>
- [Защита служб и клиентов](../../../wcf/feature-details/securing-services-and-clients.md)
- [Привязки](../../../wcf/bindings.md)
- [Настройка привязок, предоставляемых системой](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Использование привязок для настройки служб и клиентов](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
