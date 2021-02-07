---
description: 'Дополнительные сведения: <tokenReplayCache>'
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 793b1f88a9eeb0ebce4cd440e248e81377f17e9b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749003"
---
# \<tokenReplayCache>

Регистрирует кэш воспроизведения токенов с помощью службы или коллекции обработчиков маркеров безопасности.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayCache>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <tokenReplayCache type=xs:string>  
      </tokenReplayCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|type|Тип, производный от <xref:System.IdentityModel.Tokens.TokenReplayCache> класса. Дополнительные сведения о том, как указать пользовательский параметр `type` , см. в разделе [ссылки на пользовательские типы].
  
### <a name="child-elements"></a>Дочерние элементы  

 None  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<caches>](caches.md)|Регистрирует кэши, используемые службой или коллекцией обработчиков маркеров безопасности.|  
  
## <a name="remarks"></a>Remarks  

 Кэш воспроизведения токенов используется для обнаружения воспроизводимых токенов. Обнаружение воспроизведения токенов включается [\<tokenReplayDetection>](tokenreplaydetection.md) элементом, который также указывает максимальное время окончания срока действия токенов.  
  
## <a name="example"></a>Пример  

 В следующем коде XML показана конфигурация пользовательского кэша для обнаружения воспроизводимых токенов.  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [\<tokenReplayDetection>](tokenreplaydetection.md)
