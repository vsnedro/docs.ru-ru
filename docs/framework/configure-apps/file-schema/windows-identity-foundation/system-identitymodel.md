---
description: 'Дополнительные сведения о: <System. identityModel>'
title: <system.identityModel>
ms.date: 03/30/2017
ms.assetid: 210ce7e9-d07b-400c-800f-5f525dcf95e8
author: BrucePerlerMS
ms.openlocfilehash: c597f2a849248366f9cf3847c8ef369c13d7a286
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786529"
---
# \<system.identityModel>

Предоставляет конфигурацию для включения параметров Windows Identity Foundation (WIF) в приложениях.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.identityModel>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.identityModel>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  

 None  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|Задает параметры удостоверений уровня службы.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`<configuration>`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
  
## <a name="remarks"></a>Remarks  

 Добавьте `<system.identityModel>` раздел в файл конфигурации, чтобы настроить службу или приложение для использования Windows Identity Foundation (WIF). `<system.identityModel>`Элемент представлен <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> классом.  
  
## <a name="example"></a>Пример  

 В следующем примере показано, как добавить `<system.identityModel>` раздел в файл конфигурации. Сначала необходимо добавить раздел конфигурации и объявление пространства имен в `<configSections>` элемент. Затем можно добавить `<system.IdentityModel>` элемент в файл конфигурации, чтобы указать одну или несколько конфигураций удостоверений.  
  
```xml  
<configuration>  
  <configSections>  
    <!--WIF 4.5 sections -->  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
  </configSections>  
  
  ...  
  
  <system.identityModel>  
    <identityConfiguration>  
      <audienceUris>  
        <add value="http://localhost/WebApplication1/" />  
      </audienceUris>  
      <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089">  
        <trustedIssuers>  
          <add thumbprint="313D3B … 9106A9EC" name="SelfSTS" />  
        </trustedIssuers>  
      </issuerNameRegistry>  
      <certificateValidation certificateValidationMode="None"/>  
    </identityConfiguration>  
  </system.identityModel>  
  
  ...  
  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.IdentityModel.Configuration.SystemIdentityModelSection>
