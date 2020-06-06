---
title: <add> из <scopes>
ms.date: 03/30/2017
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
ms.openlocfilehash: bcde6b18c34dccf1716c809dddeb45b1b4da90f0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398305"
---
# <a name="add-of-scopes"></a><span data-ttu-id="2bdc7-102">\<add> из \<scopes></span><span class="sxs-lookup"><span data-stu-id="2bdc7-102">\<add> of \<scopes></span></span>
<span data-ttu-id="2bdc7-103">Добавляет URI пользовательский области, который при выполнении запроса можно использовать для фильтрации конечных точек службы.</span><span class="sxs-lookup"><span data-stu-id="2bdc7-103">Adds a custom scope Uri that can be used to filter service endpoints during query.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointDiscovery>**](endpointdiscovery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<scopes>**](scopes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="2bdc7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2bdc7-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2bdc7-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2bdc7-105">Attributes and Elements</span></span>  
 <span data-ttu-id="2bdc7-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2bdc7-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2bdc7-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2bdc7-107">Attributes</span></span>  
  
|<span data-ttu-id="2bdc7-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2bdc7-108">Attribute</span></span>|<span data-ttu-id="2bdc7-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="2bdc7-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2bdc7-110">область</span><span class="sxs-lookup"><span data-stu-id="2bdc7-110">scope</span></span>|<span data-ttu-id="2bdc7-111">URI, содержащий сведения об области для конечной точки, которую можно использовать в критериях соответствия при поиске служб.</span><span class="sxs-lookup"><span data-stu-id="2bdc7-111">A URI that contains scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2bdc7-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2bdc7-112">Child Elements</span></span>  
 <span data-ttu-id="2bdc7-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2bdc7-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2bdc7-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2bdc7-114">Parent Elements</span></span>  
  
|<span data-ttu-id="2bdc7-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="2bdc7-115">Element</span></span>|<span data-ttu-id="2bdc7-116">Описание</span><span class="sxs-lookup"><span data-stu-id="2bdc7-116">Description</span></span>|  
|-------------|-----------------|  
|[\<scopes>](scopes.md)|<span data-ttu-id="2bdc7-117">Содержит коллекцию элементов конфигурации, указывающие идентификаторы URI пользовательских областей, которые можно использовать для фильтрации конечных точек службы во время выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="2bdc7-117">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2bdc7-118">См. также</span><span class="sxs-lookup"><span data-stu-id="2bdc7-118">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
