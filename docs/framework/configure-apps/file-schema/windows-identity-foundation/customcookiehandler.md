---
description: 'Дополнительные сведения: <customCookieHandler>'
title: <customCookieHandler>
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: 6b433769c429ed4149efb324d7c4b216d6042705
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664084"
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

 None  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|Настраивает <xref:System.IdentityModel.Services.CookieHandler> , что <xref:System.IdentityModel.Services.SessionAuthenticationModule> использует для чтения и записи файлов cookie.|  
  
## <a name="remarks"></a>Remarks  

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
