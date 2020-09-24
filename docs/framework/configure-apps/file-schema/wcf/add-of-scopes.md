---
title: <add> из <scopes>
ms.date: 03/30/2017
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
ms.openlocfilehash: 1f5b5ea621614880286181c7584863ea024b3d04
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149014"
---
# <a name="add-of-scopes"></a><span data-ttu-id="06f33-102">\<add> из \<scopes></span><span class="sxs-lookup"><span data-stu-id="06f33-102">\<add> of \<scopes></span></span>

<span data-ttu-id="06f33-103">Добавляет URI пользовательский области, который при выполнении запроса можно использовать для фильтрации конечных точек службы.</span><span class="sxs-lookup"><span data-stu-id="06f33-103">Adds a custom scope Uri that can be used to filter service endpoints during query.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointDiscovery>**](endpointdiscovery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<scopes>**](scopes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="06f33-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="06f33-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="06f33-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="06f33-105">Attributes and Elements</span></span>  

 <span data-ttu-id="06f33-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="06f33-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="06f33-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="06f33-107">Attributes</span></span>  
  
|<span data-ttu-id="06f33-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="06f33-108">Attribute</span></span>|<span data-ttu-id="06f33-109">Описание</span><span class="sxs-lookup"><span data-stu-id="06f33-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="06f33-110">scope</span><span class="sxs-lookup"><span data-stu-id="06f33-110">scope</span></span>|<span data-ttu-id="06f33-111">URI, содержащий сведения об области для конечной точки, которую можно использовать в критериях соответствия при поиске служб.</span><span class="sxs-lookup"><span data-stu-id="06f33-111">A URI that contains scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="06f33-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="06f33-112">Child Elements</span></span>  

 <span data-ttu-id="06f33-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="06f33-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="06f33-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="06f33-114">Parent Elements</span></span>  
  
|<span data-ttu-id="06f33-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="06f33-115">Element</span></span>|<span data-ttu-id="06f33-116">Описание</span><span class="sxs-lookup"><span data-stu-id="06f33-116">Description</span></span>|  
|-------------|-----------------|  
|[\<scopes>](scopes.md)|<span data-ttu-id="06f33-117">Содержит коллекцию элементов конфигурации, указывающие идентификаторы URI пользовательских областей, которые можно использовать для фильтрации конечных точек службы во время выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="06f33-117">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="06f33-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="06f33-118">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
