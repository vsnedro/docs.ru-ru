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
ms.openlocfilehash: e081882aa8df89c0a1bf5d4c60f1395a3319c417
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190375"
---
# <a name="defaultftpcachepolicy-element-network-settings"></a><span data-ttu-id="64613-102">Элемент \<defaultFtpCachePolicy> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="64613-102">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>

<span data-ttu-id="64613-103">Описывает, активно ли кэширование FTP и описывает политику кэширования по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="64613-103">Describes whether FTP caching is active and describes the default caching policy.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<requestCaching>**](requestcaching-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultFtpCachePolicy>**

## <a name="syntax"></a><span data-ttu-id="64613-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="64613-104">Syntax</span></span>  
  
```xml  
<defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="64613-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="64613-105">Attributes and Elements</span></span>  

 <span data-ttu-id="64613-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="64613-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="64613-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="64613-107">Attributes</span></span>  
  
|<span data-ttu-id="64613-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="64613-108">Attribute</span></span>|<span data-ttu-id="64613-109">Описание</span><span class="sxs-lookup"><span data-stu-id="64613-109">Description</span></span>|  
|---------------|-----------------|  
|`policyLevel`|<span data-ttu-id="64613-110">Указывает политику кэширования FTP.</span><span class="sxs-lookup"><span data-stu-id="64613-110">Specifies the FTP caching policy.</span></span> <span data-ttu-id="64613-111">Значение по умолчанию — `Default`.</span><span class="sxs-lookup"><span data-stu-id="64613-111">The default value is `Default`.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="64613-112">Атрибут Полицилевел</span><span class="sxs-lookup"><span data-stu-id="64613-112">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="64613-113">Значение</span><span class="sxs-lookup"><span data-stu-id="64613-113">Value</span></span>|<span data-ttu-id="64613-114">Описание</span><span class="sxs-lookup"><span data-stu-id="64613-114">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="64613-115">Возвращает кэшированный ресурс, если ресурс является актуальным, длина содержимого является точной, а атрибуты срока действия, изменения и длины содержимого существуют.</span><span class="sxs-lookup"><span data-stu-id="64613-115">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="64613-116">Возвращает ресурс с сервера.</span><span class="sxs-lookup"><span data-stu-id="64613-116">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="64613-117">Возвращает кэшированный ресурс, если длина содержимого имеется и соответствует размеру записи.</span><span class="sxs-lookup"><span data-stu-id="64613-117">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="64613-118">Возвращает кэшированный ресурс, если длина содержимого указана и соответствует размеру записи. в противном случае ресурс загружается с сервера и возвращается вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="64613-118">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="64613-119">Возвращает кэшированный ресурс, если метка времени кэшированного ресурса совпадает с меткой времени ресурса на сервере. в противном случае ресурс загружается с сервера, хранится в кэше и возвращается вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="64613-119">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="64613-120">Скачивает ресурс с сервера, сохраняет его в кэше и возвращает ресурс вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="64613-120">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="64613-121">Если кэшированный ресурс существует, он удаляется.</span><span class="sxs-lookup"><span data-stu-id="64613-121">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="64613-122">Ресурс загружается с сервера и возвращается вызывающему.</span><span class="sxs-lookup"><span data-stu-id="64613-122">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="64613-123">Выполняет запрос, используя кэшированную копию ресурса, если метка времени ресурса совпадает с меткой времени ресурса на сервере, в противном случае ресурс загружается с сервера, представляется вызывающему объекту и сохраняется в кэше.</span><span class="sxs-lookup"><span data-stu-id="64613-123">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and stored in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="64613-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="64613-124">Child Elements</span></span>  

 <span data-ttu-id="64613-125">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="64613-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="64613-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="64613-126">Parent Elements</span></span>  
  
|<span data-ttu-id="64613-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="64613-127">Element</span></span>|<span data-ttu-id="64613-128">Описание</span><span class="sxs-lookup"><span data-stu-id="64613-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="64613-129">requestCaching</span><span class="sxs-lookup"><span data-stu-id="64613-129">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="64613-130">Управляет механизмом кэширования для сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="64613-130">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64613-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="64613-131">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="64613-132">Пример</span><span class="sxs-lookup"><span data-stu-id="64613-132">Example</span></span>  

 <span data-ttu-id="64613-133">В следующем примере показано, как задать политику кэширования FTP для `NoCacheNoStore` .</span><span class="sxs-lookup"><span data-stu-id="64613-133">The following example shows how to specify an FTP caching policy of `NoCacheNoStore`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="64613-134">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="64613-134">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="64613-135">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="64613-135">Network Settings Schema</span></span>](index.md)
