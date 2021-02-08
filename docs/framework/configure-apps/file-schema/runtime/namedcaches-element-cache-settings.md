---
description: 'Дополнительные сведения о <namedCaches> элементе: Element (параметры кэша)'
title: Элемент <namedCaches> (параметры кэша)
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
ms.openlocfilehash: 543650513270c0cee24d965b8efe98a75d7b8f9a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782329"
---
# <a name="namedcaches-element-cache-settings"></a>Элемент \<namedCaches> (параметры кэша)

Задает коллекцию параметров конфигурации для именованных <xref:System.Runtime.Caching.MemoryCache> экземпляров. <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A>Свойство ссылается на коллекцию параметров конфигурации из одного или нескольких `namedCaches` элементов файла конфигурации.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namedCaches>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<namedCaches>  
  <add name="default"/>
</namedCaches>  
```  
  
## <a name="type"></a>Тип  

 `None`  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|Целочисленное значение, указывающее максимально допустимый размер (в мегабайтах), <xref:System.Runtime.Caching.MemoryCache> до которого может увеличиваться экземпляр. Значение по умолчанию — 0. Это означает, что по умолчанию используется эвристика автоподбора размера <xref:System.Runtime.Caching.MemoryCache> класса.|  
|`name`|Имя кэша.|  
|`physicalMemoryLimitPercentage`|Целочисленное значение от 0 до 100, которое указывает максимальный процент физической памяти компьютера, который может потребляться кэшем. Значение по умолчанию — 0. Это означает, что по умолчанию используется эвристика автоподбора размера <xref:System.Runtime.Caching.MemoryCache> класса.|  
|`pollingInterval`|Значение, указывающее интервал, по истечении которого реализация кэша сравнивает текущую загрузку памяти с абсолютными и процентными ограничениями по памяти, заданными для данного экземпляра кэша. Это значение указывается в формате "чч: мм: СС".|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<add>](add-element-for-namedcaches.md)|Добавляет именованный кэш к коллекции `namedCaches` для кэша памяти.|  
|[\<clear>](clear-element-for-namedcaches.md)|Очищает коллекцию `namedCaches` для кэша памяти.|  
|[\<remove>](remove-element-for-namedcaches.md)|Удаляет элемент именованного кэша из коллекции `namedCaches` для кэша памяти.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|Указывает корневой элемент в каждом файле конфигурации, который используется средой CLR и платформа .NET Framework приложениями.|  
|[\<memoryCache>](memorycache-element-cache-settings.md)|Определяет элемент, используемый для настройки кэша, который основан на классе <xref:System.Runtime.Caching.MemoryCache> .|  
|[\<system.runtime.caching>](system-runtime-caching-element-cache-settings.md)|Содержит типы, позволяющие реализовать кэширование вывода в приложениях, встроенных в платформа .NET Framework.|  
  
## <a name="remarks"></a>Remarks  

 Раздел конфигурации кэша памяти файла Web.config может содержать `add` `remove` атрибуты, и `clear` для `namedCaches` коллекции. Каждая `namedCaches` запись уникально идентифицируется `name` атрибутом.  
  
 Экземпляры записей кэша памяти можно получить, обратившись к сведениям в файлах конфигурации приложения. По умолчанию в файле конфигурации содержится запись только для экземпляра кэша по умолчанию. Экземпляром кэша по умолчанию является экземпляр, который возвращается из <xref:System.Runtime.Caching.MemoryCache.Default%2A> Свойства.  
  
 Если для атрибута name задано значение Default, то элемент использует экземпляр кэша памяти по умолчанию.  
  
## <a name="example"></a>Пример  

 В следующем примере показано, как задать имя кэша в качестве имени записи кэша по умолчанию, задав `name` для атрибута значение Default.  
  
 Атрибутам `cacheMemoryLimitMegabytes` и `physicalMemoryPercentage` присваивается нулевое значение. Установка этих атрибутов равным нулю означает, что используется эвристический подход автоподбора размера <xref:System.Runtime.Caching.MemoryCache> класса. Реализация кэша сравнивает текущую загрузку памяти с абсолютными и процентными ограничениями памяти каждые две минуты.  
  
```xml  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="default"
               cacheMemoryLimitMegabytes="0"
               physicalMemoryLimitPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- [\<memoryCache> Элемент (параметры кэша)](memorycache-element-cache-settings.md)
