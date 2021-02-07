---
description: 'Дополнительные сведения: <caches>'
title: <caches>
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
ms.openlocfilehash: ebc2fa66ab8b657f7cc3741668c9f27fc60510b4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99681842"
---
# \<caches>

Регистрирует кэши, используемые для маркеров сеансов и определения воспроизведения маркеров.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<caches>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  

 None  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<sessionSecurityTokenCache>](sessionsecuritytokencache.md)|Регистрирует кэш для токенов сеанса с помощью службы или коллекции обработчиков маркеров безопасности.|  
|[\<tokenReplayCache>](tokenreplaycache.md)|Регистрирует кэш воспроизведения токенов с помощью службы или коллекции обработчиков маркеров безопасности.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|Задает параметры удостоверений уровня службы.|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|Предоставляет конфигурацию для коллекции обработчиков маркеров безопасности.|  
  
## <a name="remarks"></a>Remarks  

 `<caches>`Элемент можно указать на уровне службы в `<identityConfiguration>` элементе или на уровне коллекции обработчика маркеров безопасности под `<securityTokenHandlerConfiguration>` элементом. Параметры коллекции обработчиков маркеров переопределяют указанные в службе.  
  
 `<caches>`Элемент представлен <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> классом. Настроенные кэши представлены <xref:System.IdentityModel.Configuration.IdentityModelCaches> классом.  
  
## <a name="example"></a>Пример  

 В следующем коде XML показана конфигурация пользовательского кэша для хранения маркеров безопасности сеанса ( <xref:System.IdentityModel.Tokens.SessionSecurityToken> ). Конфигурация берется из `ClaimsAwareWebFarm` примера.  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
