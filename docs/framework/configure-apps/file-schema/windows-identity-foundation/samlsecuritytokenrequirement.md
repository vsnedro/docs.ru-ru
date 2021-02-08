---
description: 'Дополнительные сведения: <samlSecurityTokenRequirement>'
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: 21e584480aae6f620e0809be77e02789536db426
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786568"
---
# \<samlSecurityTokenRequirement>

Предоставляет конфигурацию для <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> класса, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> класса или производного класса любого из этих классов. Представляется <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> классом.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<samlSecurityTokenRequirement>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement
            issuerCertificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
            issuerCertificateRevocationMode="NoCheck||Offline||Online"  
            issuerCertificateTrustedStoreLocation="CurrentLocation||LocalMachine"  
            issuerCertificateValidator="Namespace.Class Assembly"  
            mapToWindows=xs:boolean  
          <nameClaimType value=xs:string />  
          <roleClaimType value=xs:string />  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|mapToWindows|Указывает, должен ли обработчик маркера сопоставлять проверяющий токен с учетной записью Windows, используя входящее утверждение имени участника-пользователя. Значение по умолчанию — «false».|  
|иссуерцертификатеревокатионмоде|<xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>Значение типа, указывающее режим отзыва, используемый для сертификата X. 509. Значение по умолчанию — "Online".|  
|иссуерцертификатевалидатионмоде|<xref:System.ServiceModel.Security.X509CertificateValidationMode>Значение типа, указывающее режим проверки, используемый для сертификата X. 509. Значение по умолчанию — "PeerOrChainTrust".|  
|иссуерцертификатетрустедсторелокатион|<xref:System.Security.Cryptography.X509Certificates.StoreLocation>Значение типа, указывающее хранилище сертификатов X. 509. Значение по умолчанию — LocalMachine.|  
|иссуерцертификатевалидатор|Пользовательский тип, производный от <xref:System.IdentityModel.Selectors.X509CertificateValidator> . Если `issuerCertificateValidationMode` атрибут имеет значение Custom, для проверки сертификата издателя используется экземпляр этого типа.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<nameClaimType>](nameclaimtype.md)|Задает тип утверждения, указывающий <xref:System.Security.Principal.IIdentity.Name%2A> свойство.|  
|[\<roleClaimType>](roleclaimtype.md)|Указывает тип утверждения, определяющего утверждения типа роли в коллекции <xref:System.Security.Claims.ClaimsIdentity> объектов, возвращаемых <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> методом обработчика маркеров.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<add>](add.md)|Добавляет указанный обработчик маркеров безопасности в коллекцию обработчиков маркеров.|  
  
## <a name="remarks"></a>Remarks  

 `<samlSecurityTokenRequirement>`Элемент представлен <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> классом в объектной модели и используется для настройки `SamlSecurityTokenRequirement` свойства в <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> или <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> .  
  
## <a name="example"></a>Пример  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement issuerCertificateValidationMode="PeerOrChainTrust"  
                                  issuerCertificateRevocationMode="Online"  
                                  issuerCertificateTrustedStoreLocation="LocalMachine"  
                                  mapToWindows="false">  
  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```
