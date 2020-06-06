---
title: <audienceUris>
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: bd04e4ebdf5c58adaeea0ff0ca5993d7d9ce38f1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252171"
---
# \<audienceUris>
Указывает набор универсальных кодов ресурса (URI), которые являются допустимыми идентификаторами проверяющей стороны (RP). Маркеры не будут приниматься, если они не относятся к одному из разрешенных URI аудитории.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<audienceUris>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <audienceUris mode=xs:string>  
          <add value=xs:string />  
          <clear />  
          <remove value=xs:string />  
        </audienceUris>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание:|  
|---------------|-----------------|  
|mode|<xref:System.IdentityModel.Selectors.AudienceUriMode>Значение типа, указывающее, следует ли применять ограничение аудитории к входящему токену. Возможные значения: "всегда", "Never" и "Беареркэйонли". Значение по умолчанию — Always. Необязательный параметр.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`<add value=xs:string>`|Добавляет URI, указанный `value` атрибутом, в коллекцию audienceUris. Атрибут `value` является обязательным. В URI учитывается регистр.|  
|`<clear>`|Очищает коллекцию audienceUris. Все идентификаторы удаляются из коллекции.|  
|`<remove value=xs:string>`|Удаляет URI, указанный `value` атрибутом из коллекции audienceUris. Атрибут `value` является обязательным. В URI учитывается регистр.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|Предоставляет конфигурацию для коллекции обработчиков маркеров безопасности.|  
  
## <a name="remarks"></a>Примечания  
 По умолчанию коллекция пуста; Используйте `<add>` `<clear>` элементы, и `<remove>` для изменения коллекции. <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler><xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>объекты и используют значения в коллекции URI аудитории для настройки любых допустимых ограничений URI аудитории в <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> объектах.  
  
 `<audienceUris>`Элемент представлен <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> классом. Отдельный URI, добавленный в коллекцию, представлен <xref:System.IdentityModel.Configuration.AudienceUriElement> классом.  
  
> [!NOTE]
> Использование `<audienceUris>` элемента в качестве дочернего элемента [\<identityConfiguration>](identityconfiguration.md) элемента является устаревшим, но по-прежнему поддерживается для обратной совместимости. Параметры `<securityTokenHandlerConfiguration>` элемента переопределяют их для `<identityConfiguration>` элемента.  
  
## <a name="example"></a>Пример  
 В следующем коде XML показано, как настроить допустимые URI аудитории для приложения. В этом примере настраивается один универсальный код ресурса (URI). Маркеры, областью которых является этот URI, будут приняты, все остальные будут отклонены.  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
