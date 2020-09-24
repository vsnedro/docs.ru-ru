---
title: <claimsAuthorizationManager>
ms.date: 03/30/2017
ms.assetid: 9354eee3-f692-4ad6-8427-3169686b8bcc
author: BrucePerlerMS
ms.openlocfilehash: 0718f789ff4d99fb4e2651a9a704da4248cd5f49
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158439"
---
# \<claimsAuthorizationManager>

Регистрирует диспетчер авторизации утверждений для входящих утверждений.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthorizationManager>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthorizationManager type = xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthorizationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|type|Пользовательский тип, производный от <xref:System.Security.Claims.ClaimsAuthorizationManager> класса. Дополнительные сведения об указании `type` атрибута см. в разделе [ссылки на пользовательские типы](../windows-workflow-foundation/index.md).|  
  
### <a name="child-elements"></a>Дочерние элементы  

 Если `type` атрибут отсутствует или `type` атрибут ссылается на <xref:System.Security.Claims.ClaimsAuthenticationManager> класс, `<claimsAuthorizationManager>` элемент не принимает дочерние элементы, однако классы, производные от, <xref:System.Security.Claims.ClaimsAuthorizationManager> могут определять дочерние элементы конфигурации.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|Задает параметры удостоверений уровня службы.|  
  
## <a name="remarks"></a>Remarks  

 Поведение по умолчанию, предоставляемое <xref:System.Security.Claims.ClaimsAuthorizationManager> классом, всегда разрешает входящие утверждения. Если `type` атрибут не указан или `type` атрибут указывает <xref:System.Security.Claims.ClaimsAuthorizationManager> класс, `<claimsAuthorizationManager>` элемент не принимает дочерние элементы. Можно указать `type` атрибут для регистрации типа, производного от класса, <xref:System.Security.Claims.ClaimsAuthorizationManager> для реализации пользовательского поведения. Производные классы могут поддерживать конфигурацию через дочерние элементы `<claimsAuthorizationManager>` элемента путем переопределения <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> метода для работы с этими элементами. Схема, определенная для дочерних элементов, находится в конструкторе класса.  
  
> [!IMPORTANT]
> При использовании <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> класса или для предоставления управления доступом на основе утверждений в коде конфигурация удостоверения, на которую ссылается элемент, `<federationConfiguration>` настраивает диспетчер авторизации утверждений и политику, которая используется для принятия решений об авторизации. Это справедливо даже в сценариях, которые не являются пассивными веб-сценариями, например Windows Communication Foundation приложений (WCF) или приложение, не основанное на веб-интерфейсе. Если приложение не является пассивным веб-приложением, то `<claimsAuthorizationManager>` к нему применяются только те элементы (и дочерние элемент политики, если таковые имеются) конфигурации удостоверения, на которую указывает ссылка. Все остальные параметры игнорируются. Дополнительные сведения см. в описании [\<federationConfiguration>](federationconfiguration.md) элемента.  
  
 Этот элемент задает <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> свойство.  
  
## <a name="example"></a>Пример  

 В следующем коде XML показана конфигурация для диспетчера авторизации утверждений, который реализует политику, состоящую из пар действий с ресурсами, каждый из которых указывает логические комбинации утверждений, которые должен обладать запрашивающей стороны для выполнения действия с ресурсом. Код, реализующий диспетчер авторизации утверждений, который может использовать эту политику, можно найти в `ClaimsBasedAuthorization` примере.  
  
```xml  
<system.identityModel>  
    <identityConfiguration>  
      <claimsAuthorizationManager type="ClaimsAuthorizationLibrary.MyClaimsAuthorizationManager, ClaimsAuthorizationLibrary">  
        <policy resource="http://localhost:28491/Developers.aspx" action="GET">  
          <or>  
            <claim claimType="http://schemas.microsoft.com/ws/2008/06/identity/claims/role" claimValue="developer" />  
            <claim claimType="http://schemas.xmlsoap.org/claims/Group" claimValue="Administrator" />  
          </or>  
        </policy>  
        <policy resource="http://localhost:28491/Administrators.aspx" action="GET">  
          <and>  
            <claim claimType="http://schemas.xmlsoap.org/claims/Group" claimValue="Administrator" />  
            <claim claimType="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/country" claimValue="USA" />  
          </and>  
        </policy>  
        <policy resource="http://localhost:28491/Default.aspx" action="GET">  
        </policy>  
        <policy resource="http://localhost:28491/" action="GET">  
        </policy>  
        <policy resource="http://localhost:28491/Claims.aspx" action="GET">  
        </policy>  
      </claimsAuthorizationManager>  
    <identityConfiguration>  
<system.identityModel>  
```
