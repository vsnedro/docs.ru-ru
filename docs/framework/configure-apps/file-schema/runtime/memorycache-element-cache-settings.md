---
title: Элемент <memoryCache> (параметры кэша)
ms.date: 03/30/2017
helpviewer_keywords:
- <memoryCache> element
- caching [.NET Framework], configuration
- memoryCache element
ms.assetid: 182a622f-f7cf-472d-9d0b-451d2fd94525
ms.openlocfilehash: 14480682c5d221216df5da3844897855d1d92a0d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192429"
---
# <a name="memorycache-element-cache-settings"></a><span data-ttu-id="abd71-102">Элемент \<memoryCache> (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="abd71-102">\<memoryCache> Element (Cache Settings)</span></span>

<span data-ttu-id="abd71-103">Определяет элемент, используемый для настройки кэша, который основан на классе <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="abd71-103">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span> <span data-ttu-id="abd71-104">Класс <xref:System.Runtime.Caching.Configuration.MemoryCacheElement> определяет элемент [memoryCache](memorycache-element-cache-settings.md) , который можно использовать для настройки кэша.</span><span class="sxs-lookup"><span data-stu-id="abd71-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheElement> class defines a [memoryCache](memorycache-element-cache-settings.md) element that you can use to configure the cache.</span></span> <span data-ttu-id="abd71-105">В одном приложении может использоваться несколько экземпляров класса <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="abd71-105">Multiple instances of the <xref:System.Runtime.Caching.MemoryCache> class can be used in a single application.</span></span> <span data-ttu-id="abd71-106">Каждый элемент `memoryCache` в файле конфигурации может содержать параметры для именованного экземпляра <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="abd71-106">Each `memoryCache` element in the configuration file can contain settings for a named <xref:System.Runtime.Caching.MemoryCache> instance.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<memoryCache>**  
  
## <a name="syntax"></a><span data-ttu-id="abd71-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="abd71-107">Syntax</span></span>  
  
```xml  
<memoryCache>
    <namedCaches>  
        <!-- child elements -->  
    </namedCaches>
</memoryCache>  
```  
  
## <a name="type"></a><span data-ttu-id="abd71-108">Type</span><span class="sxs-lookup"><span data-stu-id="abd71-108">Type</span></span>  

 <span data-ttu-id="abd71-109">Класс<xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="abd71-109"><xref:System.Runtime.Caching.MemoryCache> class.</span></span>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="abd71-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="abd71-110">Attributes and Elements</span></span>  

 <span data-ttu-id="abd71-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="abd71-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="abd71-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="abd71-112">Attributes</span></span>  
  
|<span data-ttu-id="abd71-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="abd71-113">Attribute</span></span>|<span data-ttu-id="abd71-114">Описание</span><span class="sxs-lookup"><span data-stu-id="abd71-114">Description</span></span>|  
|---------------|-----------------|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="abd71-115">Максимальный объем памяти в мегабайтах, который может занимать экземпляр объекта <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="abd71-115">The maximum memory size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> object can grow to.</span></span> <span data-ttu-id="abd71-116">Значение по умолчанию — 0. Это означает, что эвристика автомасштабирования класса <xref:System.Runtime.Caching.MemoryCache> используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="abd71-116">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosize heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="abd71-117">Имя конфигурации кэша.</span><span class="sxs-lookup"><span data-stu-id="abd71-117">The name of the cache configuration.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="abd71-118">Процент физической памяти, который может использоваться кэшем.</span><span class="sxs-lookup"><span data-stu-id="abd71-118">The percentage of physical memory that can be used by the cache.</span></span> <span data-ttu-id="abd71-119">Значение по умолчанию — 0. Это означает, что эвристика автомасштабирования класса <xref:System.Runtime.Caching.MemoryCache> используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="abd71-119">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosize heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="abd71-120">Значение, указывающее интервал, по истечении которого реализация кэша сравнивает текущую загрузку памяти с абсолютными и процентными ограничениями по памяти, заданными для данного экземпляра кэша.</span><span class="sxs-lookup"><span data-stu-id="abd71-120">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="abd71-121">Значение вводится в формате "ЧЧ:ММ:СС".</span><span class="sxs-lookup"><span data-stu-id="abd71-121">The value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="abd71-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="abd71-122">Child Elements</span></span>  
  
|<span data-ttu-id="abd71-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="abd71-123">Element</span></span>|<span data-ttu-id="abd71-124">Описание</span><span class="sxs-lookup"><span data-stu-id="abd71-124">Description</span></span>|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|<span data-ttu-id="abd71-125">Содержит коллекцию параметров конфигурации для экземпляра `namedCache` .</span><span class="sxs-lookup"><span data-stu-id="abd71-125">Contains a collection of configuration settings for the `namedCache` instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="abd71-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="abd71-126">Parent Elements</span></span>  
  
|<span data-ttu-id="abd71-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="abd71-127">Element</span></span>|<span data-ttu-id="abd71-128">Описание</span><span class="sxs-lookup"><span data-stu-id="abd71-128">Description</span></span>|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|<span data-ttu-id="abd71-129">Указывает корневой элемент в каждом файле конфигурации, который используется средой CLR и .NET Framework приложениями.</span><span class="sxs-lookup"><span data-stu-id="abd71-129">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[\<system.runtime.caching>](system-runtime-caching-element-cache-settings.md)|<span data-ttu-id="abd71-130">Содержит типы, позволяющие реализовать кэширование вывода в приложениях, встроенных в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="abd71-130">Contains types that let you implement output caching in applications that are built into the .NET Framework.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="abd71-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="abd71-131">Remarks</span></span>  

 <span data-ttu-id="abd71-132">Класс <xref:System.Runtime.Caching.MemoryCache> — это конкретная реализация абстрактного класса <xref:System.Runtime.Caching.ObjectCache> .</span><span class="sxs-lookup"><span data-stu-id="abd71-132">The <xref:System.Runtime.Caching.MemoryCache> class is a concrete implementation of the abstract <xref:System.Runtime.Caching.ObjectCache> class.</span></span> <span data-ttu-id="abd71-133">Экземпляры класса <xref:System.Runtime.Caching.MemoryCache> можно снабдить сведениями о конфигурации из файлов конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="abd71-133">Instances of the <xref:System.Runtime.Caching.MemoryCache> class can be supplied with configuration information from application configuration files.</span></span> <span data-ttu-id="abd71-134">Раздел конфигурации [MemoryCache](memorycache-element-cache-settings.md) содержит коллекцию конфигураций `namedCaches` .</span><span class="sxs-lookup"><span data-stu-id="abd71-134">The [memoryCache](memorycache-element-cache-settings.md) configuration section contains a `namedCaches` configuration collection.</span></span>  
  
 <span data-ttu-id="abd71-135">При инициализации объекта кэша на базе памяти он сначала пытается найти запись `namedCaches` , которая соответствует имени в параметре, передаваемом конструктору кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="abd71-135">When a memory-based cache object is initialized, it first tries to find a `namedCaches` entry that matches the name in the parameter that is passed to the memory cache constructor.</span></span> <span data-ttu-id="abd71-136">Если запись `namedCaches` найдена, из файла конфигурации извлекаются сведения об опросах и управлении памятью.</span><span class="sxs-lookup"><span data-stu-id="abd71-136">If a `namedCaches` entry is found, the polling and memory-management information are retrieved from the configuration file.</span></span>  
  
 <span data-ttu-id="abd71-137">После этого процесс инициализации определяет, были ли переопределены какие-либо записи конфигурации, с помощью дополнительной коллекцию пар имя-значение для сведений о конфигурации в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="abd71-137">The initialization process then determines whether any configuration entries were overridden, by using the optional collection of name/value pairs of configuration information in the constructor.</span></span> <span data-ttu-id="abd71-138">Если передать в коллекцию пар имя-значение любое из следующих значений, оно переопределит сведения, полученные из файла конфигурации:</span><span class="sxs-lookup"><span data-stu-id="abd71-138">If you pass any one of the following values in the name/value pair collection, these values override information obtained from the configuration file:</span></span>  
  
- <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.CacheMemoryLimitMegabytes%2A>  
  
- <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.PhysicalMemoryLimitPercentage%2A>  
  
- <xref:System.Runtime.Caching.MemoryCache.PollingInterval%2A>  
  
## <a name="example"></a><span data-ttu-id="abd71-139">Пример</span><span class="sxs-lookup"><span data-stu-id="abd71-139">Example</span></span>  

 <span data-ttu-id="abd71-140">В следующем примере показано, как задать имя <xref:System.Runtime.Caching.MemoryCache> объекта в качестве имени объекта кэша по умолчанию, задав `name` для атрибута значение Default.</span><span class="sxs-lookup"><span data-stu-id="abd71-140">The following example shows how to set the name of the <xref:System.Runtime.Caching.MemoryCache> object to the default cache object name by setting the `name` attribute to "Default".</span></span>  
  
 <span data-ttu-id="abd71-141">Атрибутам `cacheMemoryLimitMegabytes` и `physicalMemoryLimitPercentage` присваивается нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="abd71-141">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryLimitPercentage` attribute are set to zero.</span></span> <span data-ttu-id="abd71-142">Это означает, что эвристика автомасштабирования <xref:System.Runtime.Caching.MemoryCache> используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="abd71-142">Setting these attributes to zero means that the <xref:System.Runtime.Caching.MemoryCache> autosizing heuristics are used by default.</span></span> <span data-ttu-id="abd71-143">Реализация кэша должна каждые две минуты сравнивать текущую загрузку памяти с абсолютными и процентными ограничениями по памяти.</span><span class="sxs-lookup"><span data-stu-id="abd71-143">The cache implementation should compare the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
```xml  
<configuration>  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="Default"
               cacheMemoryLimitMegabytes="0"
               physicalMemoryLimitPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="abd71-144">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="abd71-144">See also</span></span>

- <xref:System.Runtime.Caching.MemoryCache>
- [<span data-ttu-id="abd71-145">\<system.runtime.caching> Элемент (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="abd71-145">\<system.runtime.caching> Element (Cache Settings)</span></span>](system-runtime-caching-element-cache-settings.md)
- [<span data-ttu-id="abd71-146">\<namedCaches> Элемент (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="abd71-146">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
