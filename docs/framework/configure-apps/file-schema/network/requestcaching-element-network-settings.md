---
title: Элемент <requestCaching> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requestCaching
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching
helpviewer_keywords:
- requestCaching element
- <requestCaching> element
ms.assetid: 9962a2fe-cbda-41a6-9377-571811eaea84
ms.openlocfilehash: afee69eb894518b1c88483e34a1d64d452019244
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "74802131"
---
# <a name="requestcaching-element-network-settings"></a><span data-ttu-id="44819-102">Элемент \<requestCaching> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="44819-102">\<requestCaching> Element (Network Settings)</span></span>
<span data-ttu-id="44819-103">Управляет механизмом кэширования для сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="44819-103">Controls the caching mechanism for network requests.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<requestCaching>**  
  
## <a name="syntax"></a><span data-ttu-id="44819-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="44819-104">Syntax</span></span>  
  
```xml  
<requestCaching  
  isPrivateCache ="true|false"  
  disableAllCaching="true|false"  
  defaultPolicyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
  unspecifiedMaximumAge= "d.hh:mm:ss">  
    <defaultHttpCachePolicy>...</defaultHttpCachePolicy>  
    <defaultFtpCachePolicy>...</defaultFtpCachePolicy>  
</requestCaching>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="44819-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="44819-105">Attributes and Elements</span></span>  
 <span data-ttu-id="44819-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="44819-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="44819-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="44819-107">Attributes</span></span>  
  
|<span data-ttu-id="44819-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="44819-108">Attribute</span></span>|<span data-ttu-id="44819-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="44819-109">Description</span></span>|  
|---------------|-----------------|  
|`isPrivateCache`|<span data-ttu-id="44819-110">Указывает, обеспечивает ли кэш изоляцию между данными разных пользователей.</span><span class="sxs-lookup"><span data-stu-id="44819-110">Specifies whether the cache provides isolation between the information of different users.</span></span> <span data-ttu-id="44819-111">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="44819-111">The default value is `true`.</span></span> <span data-ttu-id="44819-112">Это значение должно быть `false` для приложений среднего уровня.</span><span class="sxs-lookup"><span data-stu-id="44819-112">This value should be `false` for middle tier applications.</span></span>|  
|`disableAllCaching`|<span data-ttu-id="44819-113">Указывает, что кэширование отключено для всех веб-ответов и не может быть переопределено программным способом.</span><span class="sxs-lookup"><span data-stu-id="44819-113">Specifies that caching is disabled for all Web responses, and cannot be overridden programmatically.</span></span>|  
|`defaultPolicyLevel`|<span data-ttu-id="44819-114">Одно из значений в перечислении <xref:System.Net.Cache.RequestCacheLevel>.</span><span class="sxs-lookup"><span data-stu-id="44819-114">One of the values in the <xref:System.Net.Cache.RequestCacheLevel> enumeration.</span></span> <span data-ttu-id="44819-115">Значение по умолчанию — `BypassCache`.</span><span class="sxs-lookup"><span data-stu-id="44819-115">The default value is `BypassCache`.</span></span>|  
|`unspecifiedMaximumAge`|<span data-ttu-id="44819-116">Задает время по умолчанию, по истечении которого содержимое помечается как просроченное.</span><span class="sxs-lookup"><span data-stu-id="44819-116">Specifies the default time after which content is marked as expired.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="44819-117">Атрибут Полицилевел</span><span class="sxs-lookup"><span data-stu-id="44819-117">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="44819-118">Значение</span><span class="sxs-lookup"><span data-stu-id="44819-118">Value</span></span>|<span data-ttu-id="44819-119">Описание</span><span class="sxs-lookup"><span data-stu-id="44819-119">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="44819-120">Возвращает кэшированный ресурс, если ресурс является актуальным, длина содержимого является точной, а атрибуты срока действия, изменения и длины содержимого существуют.</span><span class="sxs-lookup"><span data-stu-id="44819-120">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="44819-121">Возвращает ресурс с сервера.</span><span class="sxs-lookup"><span data-stu-id="44819-121">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="44819-122">Возвращает кэшированный ресурс, если длина содержимого имеется и соответствует размеру записи.</span><span class="sxs-lookup"><span data-stu-id="44819-122">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="44819-123">Возвращает кэшированный ресурс, если длина содержимого указана и соответствует размеру записи. в противном случае ресурс загружается с сервера и возвращается вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="44819-123">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="44819-124">Возвращает кэшированный ресурс, если метка времени кэшированного ресурса совпадает с меткой времени ресурса на сервере. в противном случае ресурс загружается с сервера, хранится в кэше, и возвращается вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="44819-124">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and is returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="44819-125">Скачивает ресурс с сервера, сохраняет его в кэше и возвращает ресурс вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="44819-125">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="44819-126">Если кэшированный ресурс существует, он удаляется.</span><span class="sxs-lookup"><span data-stu-id="44819-126">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="44819-127">Ресурс загружается с сервера и возвращается вызывающему.</span><span class="sxs-lookup"><span data-stu-id="44819-127">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="44819-128">Удовлетворяет запросу, используя кэшированную копию ресурса, если отметка времени совпадает с меткой времени ресурса на сервере. в противном случае ресурс загружается с сервера, представленного вызывающему объекту, и хранится в кэше.</span><span class="sxs-lookup"><span data-stu-id="44819-128">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and is stored in the cache,</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="44819-129">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="44819-129">Child Elements</span></span>  
  
|<span data-ttu-id="44819-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="44819-130">Element</span></span>|<span data-ttu-id="44819-131">Описание</span><span class="sxs-lookup"><span data-stu-id="44819-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="44819-132">дефаулсттпкачеполици</span><span class="sxs-lookup"><span data-stu-id="44819-132">defaultHttpCachePolicy</span></span>](defaulthttpcachepolicy-element-network-settings.md)|<span data-ttu-id="44819-133">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="44819-133">Optional element.</span></span><br /><br /> <span data-ttu-id="44819-134">Описывает, активно ли кэширование HTTP и описывает политику кэширования по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="44819-134">Describes whether HTTP caching is active and describes the default caching policy.</span></span>|  
|[<span data-ttu-id="44819-135">\<defaultFtpCachePolicy>Элемент (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="44819-135">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>](defaultftpcachepolicy-element-network-settings.md)|<span data-ttu-id="44819-136">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="44819-136">Optional element.</span></span><br /><br /> <span data-ttu-id="44819-137">Описывает, активно ли кэширование FTP и описывает политику кэширования по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="44819-137">Describes whether FTP caching is active and describes the default caching policy.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="44819-138">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="44819-138">Parent Elements</span></span>  
  
|<span data-ttu-id="44819-139">Элемент</span><span class="sxs-lookup"><span data-stu-id="44819-139">Element</span></span>|<span data-ttu-id="44819-140">Описание</span><span class="sxs-lookup"><span data-stu-id="44819-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="44819-141">system.net</span><span class="sxs-lookup"><span data-stu-id="44819-141">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="44819-142">Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="44819-142">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="44819-143">Пример</span><span class="sxs-lookup"><span data-stu-id="44819-143">Example</span></span>  
 <span data-ttu-id="44819-144">В следующем примере показано, как отключить все кэширование.</span><span class="sxs-lookup"><span data-stu-id="44819-144">The following example shows how to disable all caching.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching  
      disableAllCaching="true"  
    />  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="44819-145">См. также</span><span class="sxs-lookup"><span data-stu-id="44819-145">See also</span></span>

- <xref:System.Net.Cache?displayProperty=nameWithType>
- [<span data-ttu-id="44819-146">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="44819-146">Network Settings Schema</span></span>](index.md)
