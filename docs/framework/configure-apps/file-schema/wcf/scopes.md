---
title: <scopes>
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: 63f46753da13469147b378f373de9888a007bf52
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162222"
---
# \<scopes>

<span data-ttu-id="aa491-101">Содержит коллекцию элементов конфигурации, указывающие идентификаторы URI пользовательских областей, которые можно использовать для фильтрации конечных точек службы во время выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="aa491-101">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointDiscovery>**](endpointdiscovery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<scopes>**  
  
## <a name="syntax"></a><span data-ttu-id="aa491-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aa491-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enable="Boolean">
        <scopes>
          <add scope="URI" />
        </scopes>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aa491-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="aa491-103">Attributes and Elements</span></span>  

 <span data-ttu-id="aa491-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="aa491-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aa491-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="aa491-105">Attributes</span></span>  

 <span data-ttu-id="aa491-106">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="aa491-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="aa491-107">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="aa491-107">Child Elements</span></span>  
  
|<span data-ttu-id="aa491-108">attribute</span><span class="sxs-lookup"><span data-stu-id="aa491-108">Attribute</span></span>|<span data-ttu-id="aa491-109">Описание</span><span class="sxs-lookup"><span data-stu-id="aa491-109">Description</span></span>|  
|---------------|-----------------|  
|[\<add>](add-of-scopes.md)|<span data-ttu-id="aa491-110">Добавляет данные об области для конечной точки, которая может использоваться в критериях соответствия при поиске служб.</span><span class="sxs-lookup"><span data-stu-id="aa491-110">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aa491-111">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="aa491-111">Parent Elements</span></span>  
  
|<span data-ttu-id="aa491-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="aa491-112">Element</span></span>|<span data-ttu-id="aa491-113">Описание</span><span class="sxs-lookup"><span data-stu-id="aa491-113">Description</span></span>|  
|-------------|-----------------|  
|[\<endpointDiscovery>](endpointdiscovery.md)|<span data-ttu-id="aa491-114">Указывает различные параметры обнаружения для конечной точки, такие как возможность обнаружения, области и любые пользовательские модули для ее метаданных.</span><span class="sxs-lookup"><span data-stu-id="aa491-114">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aa491-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="aa491-115">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
