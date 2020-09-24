---
title: Элемент <remove> для <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
ms.openlocfilehash: c8ad5a0ce6d7a3059943b3962b9255385cea6e15
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183992"
---
# <a name="remove-element-for-namedcaches"></a><span data-ttu-id="57f50-102">Элемент \<remove> для \<namedCaches></span><span class="sxs-lookup"><span data-stu-id="57f50-102">\<remove> Element for \<namedCaches></span></span>

<span data-ttu-id="57f50-103">Удаляет элемент именованного кэша из коллекции `namedCaches` для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="57f50-103">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  
  
## <a name="syntax"></a><span data-ttu-id="57f50-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="57f50-104">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="57f50-105">Type</span><span class="sxs-lookup"><span data-stu-id="57f50-105">Type</span></span>  

 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="57f50-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="57f50-106">Attributes and Elements</span></span>  

 <span data-ttu-id="57f50-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="57f50-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="57f50-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="57f50-108">Attributes</span></span>  

 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="57f50-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="57f50-109">Child Elements</span></span>  

 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="57f50-110">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="57f50-110">Parent Elements</span></span>  
  
|<span data-ttu-id="57f50-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="57f50-111">Element</span></span>|<span data-ttu-id="57f50-112">Описание</span><span class="sxs-lookup"><span data-stu-id="57f50-112">Description</span></span>|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|<span data-ttu-id="57f50-113">Содержит коллекцию параметров конфигурации для именованных <xref:System.Runtime.Caching.MemoryCache> экземпляров.</span><span class="sxs-lookup"><span data-stu-id="57f50-113">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="57f50-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="57f50-114">Remarks</span></span>  

 <span data-ttu-id="57f50-115">`remove`Элемент удаляет `namedCache` запись из именованной коллекции кэша для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="57f50-115">The `remove` element removes a `namedCache` entry from the named cache collection for a memory cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57f50-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="57f50-116">See also</span></span>

- [<span data-ttu-id="57f50-117">\<namedCaches> Элемент (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="57f50-117">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
