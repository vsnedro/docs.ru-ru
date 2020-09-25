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
# <a name="add-element-for-namedcaches"></a><span data-ttu-id="d3849-102">Элемент \<add> для \<namedCaches></span><span class="sxs-lookup"><span data-stu-id="d3849-102">\<add> Element for \<namedCaches></span></span>

<span data-ttu-id="d3849-103">Добавляет `namedCache` запись в `namedCaches` коллекцию для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="d3849-103">Adds a `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="d3849-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d3849-104">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <add name="Default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="d3849-105">Type</span><span class="sxs-lookup"><span data-stu-id="d3849-105">Type</span></span>  

 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d3849-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d3849-106">Attributes and Elements</span></span>  

 <span data-ttu-id="d3849-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d3849-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d3849-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d3849-108">Attributes</span></span>  
  
|<span data-ttu-id="d3849-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d3849-109">Attribute</span></span>|<span data-ttu-id="d3849-110">Описание</span><span class="sxs-lookup"><span data-stu-id="d3849-110">Description</span></span>|  
|-|-|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="d3849-111">Целочисленное значение, указывающее максимально допустимый размер (в мегабайтах), <xref:System.Runtime.Caching.MemoryCache> до которого может увеличиваться экземпляр.</span><span class="sxs-lookup"><span data-stu-id="d3849-111">An integer value that specifies the maximum allowed size (in megabytes) that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="d3849-112">Значение по умолчанию — 0. Это означает, что <xref:System.Runtime.Caching.MemoryCache> по умолчанию используется эвристика автоопределения размеров класса.</span><span class="sxs-lookup"><span data-stu-id="d3849-112">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="d3849-113">Имя кэша.</span><span class="sxs-lookup"><span data-stu-id="d3849-113">The name of the cache.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="d3849-114">Целочисленное значение от 0 до 100, которое указывает максимальный процент физической памяти компьютера, который может потребляться кэшем.</span><span class="sxs-lookup"><span data-stu-id="d3849-114">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="d3849-115">Значение по умолчанию — 0. Это означает, что <xref:System.Runtime.Caching.MemoryCache> по умолчанию используется эвристика автоопределения размеров класса.</span><span class="sxs-lookup"><span data-stu-id="d3849-115">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="d3849-116">Значение, указывающее интервал, по истечении которого реализация кэша сравнивает текущую загрузку памяти с абсолютными и процентными ограничениями по памяти, заданными для данного экземпляра кэша.</span><span class="sxs-lookup"><span data-stu-id="d3849-116">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="d3849-117">Это значение указывается в формате "чч: мм: СС".</span><span class="sxs-lookup"><span data-stu-id="d3849-117">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d3849-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d3849-118">Child Elements</span></span>  

 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="d3849-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d3849-119">Parent Elements</span></span>  
  
|<span data-ttu-id="d3849-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="d3849-120">Element</span></span>|<span data-ttu-id="d3849-121">Описание</span><span class="sxs-lookup"><span data-stu-id="d3849-121">Description</span></span>|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|<span data-ttu-id="d3849-122">Содержит коллекцию параметров конфигурации для именованных <xref:System.Runtime.Caching.MemoryCache> экземпляров.</span><span class="sxs-lookup"><span data-stu-id="d3849-122">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3849-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="d3849-123">Remarks</span></span>  

 <span data-ttu-id="d3849-124">`add`Элемент добавляет запись в `namedCaches` коллекцию для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="d3849-124">The `add` element adds an entry to the `namedCaches` collection for a memory cache.</span></span> <span data-ttu-id="d3849-125">Элемент [clear](clear-element-for-namedcaches.md) можно использовать перед тем, как использовать `add` элемент, чтобы убедиться в отсутствии других именованных кэшей в коллекции.</span><span class="sxs-lookup"><span data-stu-id="d3849-125">You can use the [clear](clear-element-for-namedcaches.md) element before you use the `add` element to be certain that there are no other named caches in the collection.</span></span> <span data-ttu-id="d3849-126">Этот элемент можно использовать в файле machine.config и в файле Web.config.</span><span class="sxs-lookup"><span data-stu-id="d3849-126">This element can be used in the machine.config file and in the Web.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3849-127">Пример</span><span class="sxs-lookup"><span data-stu-id="d3849-127">Example</span></span>  

 <span data-ttu-id="d3849-128">В следующем примере показано, как определить параметры для записи по умолчанию в `namedCache` `namedCaches` коллекцию для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="d3849-128">The following example shows how to define settings for the default `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d3849-129">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d3849-129">See also</span></span>

- [<span data-ttu-id="d3849-130">\<namedCaches> Элемент (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="d3849-130">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
