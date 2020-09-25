---
title: Элемент <defaultHttpCachePolicy> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultHttpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultHttpCachePolicy
helpviewer_keywords:
- defaultHttpCachePolicy element
- <defaultHttpCachePolicy> element
ms.assetid: 2c1247d0-39b0-4c12-919a-a925ce075c79
ms.openlocfilehash: 4120c57fbb65da1c124414cbe9cfba7ae64388f8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190323"
---
# <a name="defaulthttpcachepolicy-element-network-settings"></a><span data-ttu-id="4b35f-102">Элемент \<defaultHttpCachePolicy> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="4b35f-102">\<defaultHttpCachePolicy> Element (Network Settings)</span></span>

<span data-ttu-id="4b35f-103">Описывает, активно ли кэширование HTTP и описывает политику кэширования по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4b35f-103">Describes whether HTTP caching is active and describes the default caching policy.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<requestCaching>**](requestcaching-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultHttpCachePolicy>**

## <a name="syntax"></a><span data-ttu-id="4b35f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4b35f-104">Syntax</span></span>  
  
```xml  
<defaultHttpCachePolicy  
  policyLevel="BypassCache|Default"  
  minimumFresh="d.hh:mm:ss|minValue|maxValue"  
  maximumAge="d.hh:mm:ss|minValue|maxValue"  
  maximumStale="d.hh:mm:ss|minValue|maxValue"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4b35f-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4b35f-105">Attributes and Elements</span></span>  

 <span data-ttu-id="4b35f-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4b35f-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4b35f-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4b35f-107">Attributes</span></span>  
  
|<span data-ttu-id="4b35f-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4b35f-108">Attribute</span></span>|<span data-ttu-id="4b35f-109">Описание</span><span class="sxs-lookup"><span data-stu-id="4b35f-109">Description</span></span>|  
|---------------|-----------------|  
|`maximumAge`|<span data-ttu-id="4b35f-110">Указывает максимальный интервал времени, по истечении которого кэшированный объект помечается как истекший.</span><span class="sxs-lookup"><span data-stu-id="4b35f-110">Specifies the maximum time interval before a cached object is marked as expired.</span></span>|  
|`maximumStale`|<span data-ttu-id="4b35f-111">Указывает максимальное время после истечения срока действия вычисленного объекта до пометки времени, когда кэшированный объект помечается как истекший.</span><span class="sxs-lookup"><span data-stu-id="4b35f-111">Specifies the maximum time past the computed freshness time before a cached object is marked as expired.</span></span>|  
|`minimumFresh`|<span data-ttu-id="4b35f-112">Указывает минимальное время, в течение которого кэшированный объект будет считаться актуальным.</span><span class="sxs-lookup"><span data-stu-id="4b35f-112">Specifies the minimum time for a cached object to be considered fresh.</span></span>|  
|`policyLevel`|<span data-ttu-id="4b35f-113">Указывает, является ли политика кэширования автоматическим, или же кэш будет пропущен.</span><span class="sxs-lookup"><span data-stu-id="4b35f-113">Specifies whether the caching policy is automatic, or whether the cache is bypassed.</span></span> <span data-ttu-id="4b35f-114">Значение по умолчанию — `BypassCache`.</span><span class="sxs-lookup"><span data-stu-id="4b35f-114">The default value is `BypassCache`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4b35f-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4b35f-115">Child Elements</span></span>  

 <span data-ttu-id="4b35f-116">Нет</span><span class="sxs-lookup"><span data-stu-id="4b35f-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4b35f-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4b35f-117">Parent Elements</span></span>  
  
|<span data-ttu-id="4b35f-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="4b35f-118">Element</span></span>|<span data-ttu-id="4b35f-119">Описание</span><span class="sxs-lookup"><span data-stu-id="4b35f-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4b35f-120">requestCaching</span><span class="sxs-lookup"><span data-stu-id="4b35f-120">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="4b35f-121">Управляет механизмом кэширования для сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="4b35f-121">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b35f-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="4b35f-122">Remarks</span></span>  

 <span data-ttu-id="4b35f-123">Значение `policyLevel` атрибута может быть `BypassCache` или `Default` .</span><span class="sxs-lookup"><span data-stu-id="4b35f-123">The value for the `policyLevel` attribute is either `BypassCache` or `Default`.</span></span>  
  
 <span data-ttu-id="4b35f-124">Значения для `maximumAge` элементов, `maximumStale` и `minimumFresh` являются либо явным временным интервалом с форматом *d*.\* чч*:*мм*:*СС\* (дни, часы, минуты и секунды), константы `minValue` или `maxValue` (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="4b35f-124">Values for the `maximumAge`, `maximumStale`, and `minimumFresh` elements are either an explicit time interval with a format of *d*.*hh*:*mm*:*ss* (days, hours, minutes, and seconds), or the constants `minValue` or `maxValue`, as appropriate.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="4b35f-125">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="4b35f-125">Configuration Files</span></span>  

 <span data-ttu-id="4b35f-126">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="4b35f-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b35f-127">Пример</span><span class="sxs-lookup"><span data-stu-id="4b35f-127">Example</span></span>  

 <span data-ttu-id="4b35f-128">В следующем примере показано, как задать минимальное новое время в 6 часов, максимальное время существования, равное двум дням, и максимальное устаревшее время, равное четырем часам.</span><span class="sxs-lookup"><span data-stu-id="4b35f-128">The following example shows how to specify a minimum fresh time of six hours, a maximum age time of two days, and a maximum stale time of four hours.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultHttpCachePolicy  
        minimumFresh="0.06:00:00"  
        maximumAge="2.00:00:00"  
        maximumStale="0.04:00:00"
      />  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4b35f-129">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4b35f-129">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="4b35f-130">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="4b35f-130">Network Settings Schema</span></span>](index.md)
