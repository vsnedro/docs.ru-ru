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
# <a name="defaultftpcachepolicy-element-network-settings"></a><span data-ttu-id="62fea-102">Элемент \<defaultFtpCachePolicy> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="62fea-102">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>
<span data-ttu-id="62fea-103">Описывает, активно ли кэширование FTP и описывает политику кэширования по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="62fea-103">Describes whether FTP caching is active and describes the default caching policy.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<requestCaching>**](requestcaching-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultFtpCachePolicy>**

## <a name="syntax"></a><span data-ttu-id="62fea-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="62fea-104">Syntax</span></span>  
  
```xml  
<defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="62fea-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="62fea-105">Attributes and Elements</span></span>  
 <span data-ttu-id="62fea-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="62fea-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="62fea-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="62fea-107">Attributes</span></span>  
  
|<span data-ttu-id="62fea-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="62fea-108">Attribute</span></span>|<span data-ttu-id="62fea-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="62fea-109">Description</span></span>|  
|---------------|-----------------|  
|`policyLevel`|<span data-ttu-id="62fea-110">Указывает политику кэширования FTP.</span><span class="sxs-lookup"><span data-stu-id="62fea-110">Specifies the FTP caching policy.</span></span> <span data-ttu-id="62fea-111">Значение по умолчанию — `Default`.</span><span class="sxs-lookup"><span data-stu-id="62fea-111">The default value is `Default`.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="62fea-112">Атрибут Полицилевел</span><span class="sxs-lookup"><span data-stu-id="62fea-112">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="62fea-113">Значение</span><span class="sxs-lookup"><span data-stu-id="62fea-113">Value</span></span>|<span data-ttu-id="62fea-114">Описание</span><span class="sxs-lookup"><span data-stu-id="62fea-114">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="62fea-115">Возвращает кэшированный ресурс, если ресурс является актуальным, длина содержимого является точной, а атрибуты срока действия, изменения и длины содержимого существуют.</span><span class="sxs-lookup"><span data-stu-id="62fea-115">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="62fea-116">Возвращает ресурс с сервера.</span><span class="sxs-lookup"><span data-stu-id="62fea-116">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="62fea-117">Возвращает кэшированный ресурс, если длина содержимого имеется и соответствует размеру записи.</span><span class="sxs-lookup"><span data-stu-id="62fea-117">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="62fea-118">Возвращает кэшированный ресурс, если длина содержимого указана и соответствует размеру записи. в противном случае ресурс загружается с сервера и возвращается вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="62fea-118">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="62fea-119">Возвращает кэшированный ресурс, если метка времени кэшированного ресурса совпадает с меткой времени ресурса на сервере. в противном случае ресурс загружается с сервера, хранится в кэше и возвращается вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="62fea-119">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="62fea-120">Скачивает ресурс с сервера, сохраняет его в кэше и возвращает ресурс вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="62fea-120">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="62fea-121">Если кэшированный ресурс существует, он удаляется.</span><span class="sxs-lookup"><span data-stu-id="62fea-121">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="62fea-122">Ресурс загружается с сервера и возвращается вызывающему.</span><span class="sxs-lookup"><span data-stu-id="62fea-122">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="62fea-123">Выполняет запрос, используя кэшированную копию ресурса, если метка времени ресурса совпадает с меткой времени ресурса на сервере, в противном случае ресурс загружается с сервера, представляется вызывающему объекту и сохраняется в кэше.</span><span class="sxs-lookup"><span data-stu-id="62fea-123">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and stored in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="62fea-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="62fea-124">Child Elements</span></span>  
 <span data-ttu-id="62fea-125">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="62fea-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="62fea-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="62fea-126">Parent Elements</span></span>  
  
|<span data-ttu-id="62fea-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="62fea-127">Element</span></span>|<span data-ttu-id="62fea-128">Описание</span><span class="sxs-lookup"><span data-stu-id="62fea-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="62fea-129">requestCaching</span><span class="sxs-lookup"><span data-stu-id="62fea-129">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="62fea-130">Управляет механизмом кэширования для сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="62fea-130">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62fea-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="62fea-131">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="62fea-132">Пример</span><span class="sxs-lookup"><span data-stu-id="62fea-132">Example</span></span>  
 <span data-ttu-id="62fea-133">В следующем примере показано, как задать политику кэширования FTP для `NoCacheNoStore` .</span><span class="sxs-lookup"><span data-stu-id="62fea-133">The following example shows how to specify an FTP caching policy of `NoCacheNoStore`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="62fea-134">См. также</span><span class="sxs-lookup"><span data-stu-id="62fea-134">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="62fea-135">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="62fea-135">Network Settings Schema</span></span>](index.md)
