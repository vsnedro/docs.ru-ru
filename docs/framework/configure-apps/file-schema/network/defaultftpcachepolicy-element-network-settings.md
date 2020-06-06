---
title: Элемент <defaultFtpCachePolicy> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultFtpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultFtpCachePolicy
helpviewer_keywords:
- <defaultFtpCachePolicy> element
- defaultFtpCachePolicy element
ms.assetid: 0eb0c5cb-dd97-484d-8614-785e88877abb
ms.openlocfilehash: 9261a430642cb4d5ac4507835bd0fd3561bd8c02
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088427"
---
# <a name="defaultftpcachepolicy-element-network-settings"></a>Элемент \<defaultFtpCachePolicy> (параметры сети)
Описывает, активно ли кэширование FTP и описывает политику кэширования по умолчанию.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<requestCaching>**](requestcaching-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultFtpCachePolicy>**

## <a name="syntax"></a>Синтаксис  
  
```xml  
<defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание:|  
|---------------|-----------------|  
|`policyLevel`|Указывает политику кэширования FTP. Значение по умолчанию — `Default`.|  
  
## <a name="policylevel-attribute"></a>Атрибут Полицилевел  
  
|Значение|Описание|  
|-----------|-----------------|  
|`Default`|Возвращает кэшированный ресурс, если ресурс является актуальным, длина содержимого является точной, а атрибуты срока действия, изменения и длины содержимого существуют.|  
|`BypassCache`|Возвращает ресурс с сервера.|  
|`CacheOnly`|Возвращает кэшированный ресурс, если длина содержимого имеется и соответствует размеру записи.|  
|`CacheIfAvailable`|Возвращает кэшированный ресурс, если длина содержимого указана и соответствует размеру записи. в противном случае ресурс загружается с сервера и возвращается вызывающему объекту.|  
|`Revalidate`|Возвращает кэшированный ресурс, если метка времени кэшированного ресурса совпадает с меткой времени ресурса на сервере. в противном случае ресурс загружается с сервера, хранится в кэше и возвращается вызывающему объекту.|  
|`Reload`|Скачивает ресурс с сервера, сохраняет его в кэше и возвращает ресурс вызывающему объекту.|  
|`NoCacheNoStore`|Если кэшированный ресурс существует, он удаляется. Ресурс загружается с сервера и возвращается вызывающему.|  
|`Revalidate`|Выполняет запрос, используя кэшированную копию ресурса, если метка времени ресурса совпадает с меткой времени ресурса на сервере, в противном случае ресурс загружается с сервера, представляется вызывающему объекту и сохраняется в кэше.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[requestCaching](requestcaching-element-network-settings.md)|Управляет механизмом кэширования для сетевых запросов.|  
  
## <a name="remarks"></a>Примечания  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как задать политику кэширования FTP для `NoCacheNoStore` .  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultFtpCachePolicy  
        policyLevel="NoCacheNoStore">  
      </defaultFtpCachePolicy>  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [Схема параметров сети](index.md)
