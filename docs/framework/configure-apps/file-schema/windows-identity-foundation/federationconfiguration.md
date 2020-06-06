---
title: <federationConfiguration>
ms.date: 03/30/2017
ms.assetid: 8b14054c-6d07-46ab-ab58-03f14beac0f2
author: BrucePerlerMS
ms.openlocfilehash: bcd8e00b770517e3faff011b4acee08ebdc5a0df
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152740"
---
# \<federationConfiguration>
Настраивает <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (всфам) и <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) при использовании федеративной проверки подлинности через протокол WS-Federation. Настраивает <xref:System.Security.Claims.ClaimsAuthorizationManager> при использовании <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> класса или для предоставления управления доступом на основе утверждений.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<federationConfiguration>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|name|Имя этого элемента конфигурации федерации. Этот атрибут в основном предоставляет точку расширения для будущих протоколов. Необязательный параметр.|  
|идентитиконфигуратионнаме|Имя раздела конфигурации удостоверений, указанное в [\<identityConfiguration>](identityconfiguration.md) используемом элементе. Если этот атрибут не указан, используется раздел конфигурации удостоверения по умолчанию. Необязательный параметр.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|Настраивает обработчик файлов cookie, используемый SAM. Необязательный параметр.|  
|[\<serviceCertificate>](servicecertificate.md)|Настраивает сертификат, используемый для шифрования и расшифровки маркеров. Необязательный параметр.|  
|[\<wsFederation>](wsfederation.md)|Настраивает модуль проверки подлинности WS-Federation (ВСФАМ). Необязательный параметр.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<system.identityModel.services>](system-identitymodel-services.md)|Раздел конфигурации для проверки подлинности с помощью протокола WS-Federation.|  
  
## <a name="remarks"></a>Примечания  
 \<federationConfiguration>Элемент предоставляет параметры в двух различных сценариях:  
  
- При использовании WS-Federation в пассивном веб-приложении элемент содержит параметры, которые настраивают <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (всфам) и <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM). Он также ссылается на конфигурацию удостоверения, которая будет использоваться для настройки обработчиков маркеров безопасности и сертификатов, и таких компонентов, как диспетчер авторизации утверждений и диспетчер проверки подлинности утверждений.  
  
- При использовании <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> класса или для предоставления управления доступом на основе утверждений в коде элемент ссылается на конфигурацию удостоверения, которая настраивает диспетчер авторизации утверждений и политику, используемые для принятия решений об авторизации. Это справедливо даже в сценариях, которые не являются пассивными веб-сценариями. Например, Windows Communication Foundation приложения (WCF) или приложение, не основанное на веб-интерфейсе. Если приложение не является пассивным веб-приложением, то [\<claimsAuthorizationManager>](claimsauthorizationmanager.md) `<federationConfiguration>` к нему будут применены только элементы (и дочерние элемент политики, если таковые имеются) конфигурации удостоверений, на которые ссылается элемент. Другие атрибуты игнорируются.  
  
 Независимо от сценария среда выполнения загружает конфигурацию Федерации по умолчанию. Поведение определяется следующим образом:  
  
1. Если `<federationConfiguration>` элемент отсутствует, среда выполнения создает конфигурацию Федерации и заполняет ее значениями по умолчанию. Эта конфигурация Федерации по умолчанию будет ссылаться на конфигурацию удостоверения по умолчанию.  
  
2. Если имеется один `<federationConfiguration>` элемент, то это конфигурация Федерации по умолчанию, независимо от того, является ли она именованной или безымянной. Если `identityConfiguration` указан его атрибут, указывается именованная конфигурация удостоверений; в противном случае указывается ссылка на конфигурацию удостоверения по умолчанию.  
  
3. Если неименованный `<federationConfiguration>` элемент имеется, это конфигурация Федерации по умолчанию. Если `identityConfiguration` указан его атрибут, указывается именованная конфигурация удостоверений; в противном случае указывается ссылка на конфигурацию удостоверения по умолчанию.  
  
4. Если имеется несколько именованных `<federationConfiguration>` элементов и отсутствует неименованный `<federationConfiguration>` элемент, возникает исключение.  
  
 Как правило, определен только один `<federationConfiguration>` раздел. Этот раздел является конфигурацией Федерации по умолчанию. Можно указать несколько элементов с уникальными именами, `<federationConfiguration>` однако в этом случае, если требуется загрузить конфигурацию Федерации, отличную от безымянной, необходимо предоставить обработчик для. <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated>и установить <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> свойство внутри обработчика в <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> объект, инициализируемый значениями из соответствующего `<federationConfiguration>` элемента в файле конфигурации.  
  
 `<federationConfiguration>`Элемент представлен <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> классом. Сам объект конфигурации представлен <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> классом. Для <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> свойства задается единственный экземпляр <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> и обеспечивается Федеративная конфигурация для приложения.  
  
## <a name="example"></a>Пример  
 В следующем XML-коде показан `<federationConfiguration>` элемент, указывающий параметры для всфам и указывающий, что SAM использует обработчик файлов cookie по умолчанию (экземпляр <xref:System.IdentityModel.Services.ChunkedCookieHandler> класса).  
  
> [!WARNING]
> В этом примере ни обработчику файлов cookie, ни ВСФАМ не требуются для использования HTTPS. Это обусловлено тем, что `requireHttps` атрибут `<wsFederation>` элемента и `requireSsl` атрибут в имеют значение `<cookieHandlerElement>` `false` . Эти параметры не рекомендуются для большинства рабочих сред, так как они могут представлять угрозу безопасности.  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <wsFederation passiveRedirectEnabled="true"
      issuer="http://localhost:15839/wsFederationSTS/Issue"
      realm="http://localhost:50969/" reply="http://localhost:50969/"
      requireHttps="false"
      signOutReply="http://localhost:50969/SignedOutPage.html"
      signOutQueryString="Param1=value2&Param2=value2"
      persistentCookiesOnPassiveRedirects="true" />  
    <cookieHandler requireSsl="false" />  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>
- <xref:System.IdentityModel.Services.SessionAuthenticationModule>
- <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>
- [\<identityConfiguration>](identityconfiguration.md)
