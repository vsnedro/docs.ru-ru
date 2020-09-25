---
title: Элемент <add> для <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: cd920b58290050fcc30ea5d0a1ac113a333902fa
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195367"
---
# <a name="add-element-for-namedcaches"></a>Элемент \<add> для \<namedCaches>

Добавляет `namedCache` запись в `namedCaches` коллекцию для кэша памяти.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<namedCaches>  
    <add name="Default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a>Type  

 `None`  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|-|-|  
|`CacheMemoryLimitMegabytes`|Целочисленное значение, указывающее максимально допустимый размер (в мегабайтах), <xref:System.Runtime.Caching.MemoryCache> до которого может увеличиваться экземпляр. Значение по умолчанию — 0. Это означает, что <xref:System.Runtime.Caching.MemoryCache> по умолчанию используется эвристика автоопределения размеров класса.|  
|`Name`|Имя кэша.|  
|`PhysicalMemoryLimitPercentage`|Целочисленное значение от 0 до 100, которое указывает максимальный процент физической памяти компьютера, который может потребляться кэшем. Значение по умолчанию — 0. Это означает, что <xref:System.Runtime.Caching.MemoryCache> по умолчанию используется эвристика автоопределения размеров класса.|  
|`PollingInterval`|Значение, указывающее интервал, по истечении которого реализация кэша сравнивает текущую загрузку памяти с абсолютными и процентными ограничениями по памяти, заданными для данного экземпляра кэша. Это значение указывается в формате "чч: мм: СС".|  
  
### <a name="child-elements"></a>Дочерние элементы  

 `None`  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|Содержит коллекцию параметров конфигурации для именованных <xref:System.Runtime.Caching.MemoryCache> экземпляров.|  
  
## <a name="remarks"></a>Remarks  

 `add`Элемент добавляет запись в `namedCaches` коллекцию для кэша памяти. Элемент [clear](clear-element-for-namedcaches.md) можно использовать перед тем, как использовать `add` элемент, чтобы убедиться в отсутствии других именованных кэшей в коллекции. Этот элемент можно использовать в файле machine.config и в файле Web.config.  
  
## <a name="example"></a>Пример  

 В следующем примере показано, как определить параметры для записи по умолчанию в `namedCache` `namedCaches` коллекцию для кэша памяти.  
  
```xml  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="Default"
               cacheMemoryLimitMegabytes="0"
               physicalMemoryPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## <a name="see-also"></a>См. также раздел

- [\<namedCaches> Элемент (параметры кэша)](namedcaches-element-cache-settings.md)
