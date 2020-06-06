---
title: Элемент <remove> для <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
ms.openlocfilehash: 991ad0eb9c04c27ded4d566115107ac7b47a71e1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252340"
---
# <a name="remove-element-for-namedcaches"></a><span data-ttu-id="0c391-102">Элемент \<remove> для \<namedCaches></span><span class="sxs-lookup"><span data-stu-id="0c391-102">\<remove> Element for \<namedCaches></span></span>
<span data-ttu-id="0c391-103">Удаляет элемент именованного кэша из коллекции `namedCaches` для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="0c391-103">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  
  
## <a name="syntax"></a><span data-ttu-id="0c391-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0c391-104">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="0c391-105">Type</span><span class="sxs-lookup"><span data-stu-id="0c391-105">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0c391-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0c391-106">Attributes and Elements</span></span>  
 <span data-ttu-id="0c391-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0c391-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0c391-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0c391-108">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="0c391-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0c391-109">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="0c391-110">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0c391-110">Parent Elements</span></span>  
  
|<span data-ttu-id="0c391-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="0c391-111">Element</span></span>|<span data-ttu-id="0c391-112">Описание</span><span class="sxs-lookup"><span data-stu-id="0c391-112">Description</span></span>|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|<span data-ttu-id="0c391-113">Содержит коллекцию параметров конфигурации для именованных <xref:System.Runtime.Caching.MemoryCache> экземпляров.</span><span class="sxs-lookup"><span data-stu-id="0c391-113">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c391-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="0c391-114">Remarks</span></span>  
 <span data-ttu-id="0c391-115">`remove`Элемент удаляет `namedCache` запись из именованной коллекции кэша для кэша памяти.</span><span class="sxs-lookup"><span data-stu-id="0c391-115">The `remove` element removes a `namedCache` entry from the named cache collection for a memory cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c391-116">См. также</span><span class="sxs-lookup"><span data-stu-id="0c391-116">See also</span></span>

- [<span data-ttu-id="0c391-117">\<namedCaches>Элемент (параметры кэша)</span><span class="sxs-lookup"><span data-stu-id="0c391-117">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
