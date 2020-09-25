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
ms.openlocfilehash: 3eb32b7ae643efdb19892410b669c1e7ff80e0ad
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91174164"
---
# <a name="requestcaching-element-network-settings"></a><span data-ttu-id="d8f13-102">Элемент \<requestCaching> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="d8f13-102">\<requestCaching> Element (Network Settings)</span></span>

<span data-ttu-id="d8f13-103">Управляет механизмом кэширования для сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="d8f13-103">Controls the caching mechanism for network requests.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<requestCaching>**  
  
## <a name="syntax"></a><span data-ttu-id="d8f13-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d8f13-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d8f13-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d8f13-105">Attributes and Elements</span></span>  

 <span data-ttu-id="d8f13-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d8f13-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d8f13-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d8f13-107">Attributes</span></span>  
  
|<span data-ttu-id="d8f13-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d8f13-108">Attribute</span></span>|<span data-ttu-id="d8f13-109">Описание</span><span class="sxs-lookup"><span data-stu-id="d8f13-109">Description</span></span>|  
|---------------|-----------------|  
|`isPrivateCache`|<span data-ttu-id="d8f13-110">Указывает, обеспечивает ли кэш изоляцию между данными разных пользователей.</span><span class="sxs-lookup"><span data-stu-id="d8f13-110">Specifies whether the cache provides isolation between the information of different users.</span></span> <span data-ttu-id="d8f13-111">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="d8f13-111">The default value is `true`.</span></span> <span data-ttu-id="d8f13-112">Это значение должно быть `false` для приложений среднего уровня.</span><span class="sxs-lookup"><span data-stu-id="d8f13-112">This value should be `false` for middle tier applications.</span></span>|  
|`disableAllCaching`|<span data-ttu-id="d8f13-113">Указывает, что кэширование отключено для всех веб-ответов и не может быть переопределено программным способом.</span><span class="sxs-lookup"><span data-stu-id="d8f13-113">Specifies that caching is disabled for all Web responses, and cannot be overridden programmatically.</span></span>|  
|`defaultPolicyLevel`|<span data-ttu-id="d8f13-114">Одно из значений в перечислении <xref:System.Net.Cache.RequestCacheLevel>.</span><span class="sxs-lookup"><span data-stu-id="d8f13-114">One of the values in the <xref:System.Net.Cache.RequestCacheLevel> enumeration.</span></span> <span data-ttu-id="d8f13-115">Значение по умолчанию — `BypassCache`.</span><span class="sxs-lookup"><span data-stu-id="d8f13-115">The default value is `BypassCache`.</span></span>|  
|`unspecifiedMaximumAge`|<span data-ttu-id="d8f13-116">Задает время по умолчанию, по истечении которого содержимое помечается как просроченное.</span><span class="sxs-lookup"><span data-stu-id="d8f13-116">Specifies the default time after which content is marked as expired.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="d8f13-117">Атрибут Полицилевел</span><span class="sxs-lookup"><span data-stu-id="d8f13-117">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="d8f13-118">Значение</span><span class="sxs-lookup"><span data-stu-id="d8f13-118">Value</span></span>|<span data-ttu-id="d8f13-119">Описание</span><span class="sxs-lookup"><span data-stu-id="d8f13-119">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="d8f13-120">Возвращает кэшированный ресурс, если ресурс является актуальным, длина содержимого является точной, а атрибуты срока действия, изменения и длины содержимого существуют.</span><span class="sxs-lookup"><span data-stu-id="d8f13-120">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="d8f13-121">Возвращает ресурс с сервера.</span><span class="sxs-lookup"><span data-stu-id="d8f13-121">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="d8f13-122">Возвращает кэшированный ресурс, если длина содержимого имеется и соответствует размеру записи.</span><span class="sxs-lookup"><span data-stu-id="d8f13-122">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="d8f13-123">Возвращает кэшированный ресурс, если длина содержимого указана и соответствует размеру записи. в противном случае ресурс загружается с сервера и возвращается вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="d8f13-123">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="d8f13-124">Возвращает кэшированный ресурс, если метка времени кэшированного ресурса совпадает с меткой времени ресурса на сервере. в противном случае ресурс загружается с сервера, хранится в кэше, и возвращается вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="d8f13-124">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and is returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="d8f13-125">Скачивает ресурс с сервера, сохраняет его в кэше и возвращает ресурс вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="d8f13-125">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="d8f13-126">Если кэшированный ресурс существует, он удаляется.</span><span class="sxs-lookup"><span data-stu-id="d8f13-126">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="d8f13-127">Ресурс загружается с сервера и возвращается вызывающему.</span><span class="sxs-lookup"><span data-stu-id="d8f13-127">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="d8f13-128">Удовлетворяет запросу, используя кэшированную копию ресурса, если отметка времени совпадает с меткой времени ресурса на сервере. в противном случае ресурс загружается с сервера, представленного вызывающему объекту, и хранится в кэше.</span><span class="sxs-lookup"><span data-stu-id="d8f13-128">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and is stored in the cache,</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d8f13-129">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d8f13-129">Child Elements</span></span>  
  
|<span data-ttu-id="d8f13-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="d8f13-130">Element</span></span>|<span data-ttu-id="d8f13-131">Описание</span><span class="sxs-lookup"><span data-stu-id="d8f13-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d8f13-132">дефаулсттпкачеполици</span><span class="sxs-lookup"><span data-stu-id="d8f13-132">defaultHttpCachePolicy</span></span>](defaulthttpcachepolicy-element-network-settings.md)|<span data-ttu-id="d8f13-133">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d8f13-133">Optional element.</span></span><br /><br /> <span data-ttu-id="d8f13-134">Описывает, активно ли кэширование HTTP и описывает политику кэширования по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d8f13-134">Describes whether HTTP caching is active and describes the default caching policy.</span></span>|  
|[<span data-ttu-id="d8f13-135">Элемент \<defaultFtpCachePolicy> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="d8f13-135">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>](defaultftpcachepolicy-element-network-settings.md)|<span data-ttu-id="d8f13-136">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d8f13-136">Optional element.</span></span><br /><br /> <span data-ttu-id="d8f13-137">Описывает, активно ли кэширование FTP и описывает политику кэширования по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d8f13-137">Describes whether FTP caching is active and describes the default caching policy.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d8f13-138">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d8f13-138">Parent Elements</span></span>  
  
|<span data-ttu-id="d8f13-139">Элемент</span><span class="sxs-lookup"><span data-stu-id="d8f13-139">Element</span></span>|<span data-ttu-id="d8f13-140">Описание</span><span class="sxs-lookup"><span data-stu-id="d8f13-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d8f13-141">system.net</span><span class="sxs-lookup"><span data-stu-id="d8f13-141">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="d8f13-142">Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="d8f13-142">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d8f13-143">Пример</span><span class="sxs-lookup"><span data-stu-id="d8f13-143">Example</span></span>  

 <span data-ttu-id="d8f13-144">В следующем примере показано, как отключить все кэширование.</span><span class="sxs-lookup"><span data-stu-id="d8f13-144">The following example shows how to disable all caching.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching  
      disableAllCaching="true"  
    />  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d8f13-145">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d8f13-145">See also</span></span>

- <xref:System.Net.Cache?displayProperty=nameWithType>
- [<span data-ttu-id="d8f13-146">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="d8f13-146">Network Settings Schema</span></span>](index.md)
