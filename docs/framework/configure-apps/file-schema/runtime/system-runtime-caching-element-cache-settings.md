---
title: Элемент <system.runtime.caching> (параметры кэша)
ms.date: 03/30/2017
helpviewer_keywords:
- <system.runtime.caching> element
- caching [.NET Framework], configuration
- system.runtime.caching element
ms.assetid: 9b44daee-874a-4bd1-954e-83bf53565590
ms.openlocfilehash: df4887c8801dcf8af06b3826673a03cbc7dbc9b5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153858"
---
# <a name="systemruntimecaching-element-cache-settings"></a><span data-ttu-id="2368b-102">Элемент \<system.runtime.caching> (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="2368b-102">\<system.runtime.caching> Element (Cache Settings)</span></span>

<span data-ttu-id="2368b-103">Обеспечивает настройку реализации <xref:System.Runtime.Caching.ObjectCache> в памяти по умолчанию посредством записи `memoryCache` в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2368b-103">Provides configuration for the default in-memory <xref:System.Runtime.Caching.ObjectCache> implementation through the `memoryCache` entry in the configuration file.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.runtime.caching>**  
  
## <a name="syntax"></a><span data-ttu-id="2368b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2368b-104">Syntax</span></span>  
  
```xml  
<system.runtime.caching >  
   <!-- child elements -->  
</system.runtime.caching >  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2368b-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2368b-105">Attributes and Elements</span></span>

<span data-ttu-id="2368b-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2368b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2368b-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2368b-107">Attributes</span></span>

`None`  

### <a name="child-elements"></a><span data-ttu-id="2368b-108">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2368b-108">Child Elements</span></span>

|<span data-ttu-id="2368b-109">Элемент</span><span class="sxs-lookup"><span data-stu-id="2368b-109">Element</span></span>|<span data-ttu-id="2368b-110">Описание</span><span class="sxs-lookup"><span data-stu-id="2368b-110">Description</span></span>|  
|-------------|-----------------|  
|[\<memoryCache>](memorycache-element-cache-settings.md)|<span data-ttu-id="2368b-111">Определяет элемент, используемый для настройки кэша, который основан на классе <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="2368b-111">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2368b-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2368b-112">Parent Elements</span></span>  
  
|<span data-ttu-id="2368b-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="2368b-113">Element</span></span>|<span data-ttu-id="2368b-114">Описание</span><span class="sxs-lookup"><span data-stu-id="2368b-114">Description</span></span>|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|<span data-ttu-id="2368b-115">Указывает корневой элемент в каждом файле конфигурации, который используется средой CLR и .NET Framework приложениями.</span><span class="sxs-lookup"><span data-stu-id="2368b-115">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2368b-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="2368b-116">Remarks</span></span>

<span data-ttu-id="2368b-117">Классы в этом пространстве имен предоставляют способ использования средств кэширования, например таких, которые имеются в ASP.NET, но без зависимости от сборки `System.Web` .</span><span class="sxs-lookup"><span data-stu-id="2368b-117">The classes in this namespace provide a way to use caching facilities like those in ASP.NET, but without a dependency on the `System.Web` assembly.</span></span> <span data-ttu-id="2368b-118">Для получения дополнительной информации см. [Caching in .NET Framework Applications](../../../performance/caching-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="2368b-118">For more information, see [Caching in .NET Framework Applications](../../../performance/caching-in-net-framework-applications.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2368b-119">Функции кэширования вывода и типы в <xref:System.Runtime.Caching> пространстве имен являются новыми в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="2368b-119">The output caching functionality and types in the <xref:System.Runtime.Caching> namespace are new in .NET Framework 4.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2368b-120">Пример</span><span class="sxs-lookup"><span data-stu-id="2368b-120">Example</span></span>

<span data-ttu-id="2368b-121">В следующем примере кода показано, как настроить кэш, основанный на классе <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="2368b-121">The following example shows how to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span> <span data-ttu-id="2368b-122">В примере показано, как построить экземпляр записи `namedCaches` для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="2368b-122">The example shows how to configure an instance of the `namedCaches` entry for memory cache.</span></span> <span data-ttu-id="2368b-123">Для имени кэша задается имя записи кэша по умолчанию, присвоенное `name` атрибуту значения "default".</span><span class="sxs-lookup"><span data-stu-id="2368b-123">The name of the cache is set to the default cache entry name by setting the `name` attribute to "Default".</span></span>  
  
<span data-ttu-id="2368b-124">Атрибутам `cacheMemoryLimitMegabytes` и `physicalMemoryPercentage` присваивается нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="2368b-124">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="2368b-125">Это означает, что эвристика автомасштабирования <xref:System.Runtime.Caching.MemoryCache> используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2368b-125">Setting these attributes to zero means that the <xref:System.Runtime.Caching.MemoryCache> autosizing heuristics are used by default.</span></span> <span data-ttu-id="2368b-126">Реализация кэша должна каждые две минуты сравнивать текущую загрузку памяти с абсолютными и процентными ограничениями по памяти.</span><span class="sxs-lookup"><span data-stu-id="2368b-126">The cache implementation should compare the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2368b-127">См. также</span><span class="sxs-lookup"><span data-stu-id="2368b-127">See also</span></span>

- [<span data-ttu-id="2368b-128">\<memoryCache>Элемент (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="2368b-128">\<memoryCache> Element (Cache Settings)</span></span>](memorycache-element-cache-settings.md)
