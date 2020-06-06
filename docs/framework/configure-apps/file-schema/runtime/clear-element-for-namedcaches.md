---
title: Элемент <clear> для <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
ms.openlocfilehash: bcc0e23f0c47ad3a98430e36da31d39612caa3c9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252761"
---
# <a name="clear-element-for-namedcaches"></a><span data-ttu-id="373ed-102">Элемент \<clear> для \<namedCaches></span><span class="sxs-lookup"><span data-stu-id="373ed-102">\<clear> Element for \<namedCaches></span></span>
<span data-ttu-id="373ed-103">Очищает все `namedCache` записи в `namedCaches` коллекции для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="373ed-103">Clears all `namedCache` entries in the `namedCaches` collection for a memory cache.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**  
  
## <a name="syntax"></a><span data-ttu-id="373ed-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="373ed-104">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <clear name="Default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="373ed-105">Type</span><span class="sxs-lookup"><span data-stu-id="373ed-105">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="373ed-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="373ed-106">Attributes and Elements</span></span>  
 <span data-ttu-id="373ed-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="373ed-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="373ed-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="373ed-108">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="373ed-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="373ed-109">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="373ed-110">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="373ed-110">Parent Elements</span></span>  
  
|<span data-ttu-id="373ed-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="373ed-111">Element</span></span>|<span data-ttu-id="373ed-112">Описание</span><span class="sxs-lookup"><span data-stu-id="373ed-112">Description</span></span>|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|<span data-ttu-id="373ed-113">Содержит коллекцию параметров конфигурации для именованных <xref:System.Runtime.Caching.MemoryCache> экземпляров.</span><span class="sxs-lookup"><span data-stu-id="373ed-113">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="373ed-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="373ed-114">Remarks</span></span>  
 <span data-ttu-id="373ed-115">`clear`Элемент очищает все `namedCache` записи в именованной коллекции кэша для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="373ed-115">The `clear` element clears all `namedCache` entries in the named cache collection for a memory cache.</span></span> <span data-ttu-id="373ed-116">Элемент можно использовать `clear` перед тем, как использовать `add` элемент для добавления новой именованной записи кэша, чтобы быть уверенным в том, что в коллекции нет других именованных кэшей.</span><span class="sxs-lookup"><span data-stu-id="373ed-116">You can use the `clear` element before you use the `add` element to add a new named cache entry in order to be certain there are no other named caches in the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="373ed-117">См. также</span><span class="sxs-lookup"><span data-stu-id="373ed-117">See also</span></span>

- [<span data-ttu-id="373ed-118">\<namedCaches>Элемент (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="373ed-118">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
