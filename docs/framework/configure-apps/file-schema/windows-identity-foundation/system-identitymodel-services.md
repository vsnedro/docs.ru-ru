---
title: <system.identityModel.services>
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
ms.openlocfilehash: 57757aaec39bc5c552e7ba12c9779cb3a92a9025
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152508"
---
# \<system.identityModel.services>
Раздел конфигурации для проверки подлинности с помощью протокола WS-Federation.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.identityModel.services>**  
  
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
 Нет  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<federationConfiguration>](federationconfiguration.md)|Содержит параметры, которые настраивают <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (всфам) и <xref:System.IdentityModel.Services.SessionAuthenticationModule> HTTP-модули (SAM).|  
  
### <a name="parent-elements"></a>Родительские элементы  
 None  
  
## <a name="remarks"></a>Remarks  
 Добавьте `<system.identityModel.services>` раздел в файл конфигурации приложения, чтобы указать параметры для SAM и всфам.  
  
> [!IMPORTANT]
> При использовании <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> класса или для предоставления управления доступом на основе утверждений в коде Диспетчер авторизации утверждений ( <xref:System.Security.Claims.ClaimsAuthorizationManager> ) и политика, используемые для принятия решений об авторизации, настраиваются с помощью `<identityConfiguration>` элемента, который неявно или явно упоминается в `<federationConfiguration>` элементе в этом разделе. Дополнительные сведения см. в разделе **Примечания** в [\<federationConfiguration>](federationconfiguration.md) элементе.  
  
 `<system.identityModel.services>`Раздел представлен <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> классом. Коллекция дочерних элементов, `<federationConfiguration>` настроенных в разделе, представлена <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> классом.  
  
## <a name="example"></a>Пример  
 В следующем коде XML показано, как добавить `<system.identityModel.services>` раздел в файл конфигурации. Сначала необходимо добавить объявления разделов как для `<system.identityModel.services>` раздела, так и для `<system.identityModel>` разделов. (При добавлении раздела необходимо `<system.identityModel.services>` также добавить объявление для `<system.identityModel>` раздела, чтобы гарантировать, что при необходимости раздел по умолчанию `<identityConfiguration>` может быть создан средой выполнения.) После добавления объявлений разделов можно настроить параметры федеративной проверки подлинности в `<system.identityModel.services>` элементе.  
  
```xml  
<configuration>  
  <configSections>  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
  </configSections>  
  
  <!-- Additional elements (not shown) -->  
  
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
  
</configuration>  
```
