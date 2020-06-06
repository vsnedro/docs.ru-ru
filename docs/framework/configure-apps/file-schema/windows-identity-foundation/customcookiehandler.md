---
title: <customCookieHandler>
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: e1f32e17cf0da5e948d778e8b61aca6053eff4ef
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252021"
---
# \<customCookieHandler>
Задает тип обработчика пользовательских файлов cookie. Этот элемент может присутствовать только в том случае, если `mode` атрибут `<cookieHandler>` элемента имеет значение Custom. Пользовательский тип должен быть производным от <xref:System.IdentityModel.Services.CookieHandler> класса.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cookieHandler>**](cookiehandler.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customCookieHandler>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Custom">  
      <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" >  
      </customCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|type|Указывает пользовательский тип, производный от <xref:System.IdentityModel.Services.CookieHandler> класса. Дополнительные сведения об указании `type` атрибута см. в разделе [ссылки на пользовательские типы](../windows-workflow-foundation/index.md).|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|Настраивает <xref:System.IdentityModel.Services.CookieHandler> , что <xref:System.IdentityModel.Services.SessionAuthenticationModule> использует для чтения и записи файлов cookie.|  
  
## <a name="remarks"></a>Примечания  
 При указании пользовательского обработчика файлов cookie путем присвоения `mode` атрибуту `<cookieHandler>` элемента значения "Custom" необходимо указать тип пользовательского обработчика файлов cookie, добавив `<customCookieHandler>` дочерний элемент, ссылающийся на тип обработчика файлов cookie. Этот элемент не может быть указан, если `mode` для атрибута задано значение "фрагментированный" или "по умолчанию". Пользовательские обработчики файлов cookie должны быть производными от <xref:System.IdentityModel.Services.CookieHandler> класса.  
  
 `<customCookieHandler>`Элемент представлен <xref:System.IdentityModel.Configuration.CustomTypeElement> классом.  
  
## <a name="example"></a>Пример  
 В следующем примере SAM настраивается для использования пользовательского обработчика файлов cookie типа `MyNamespace.MyCustomCookieHandler` .  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.IdentityModel.Services.CookieHandler>
