---
title: <filterTable>
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: 918a365004efea82f4ef4c8868f6821d4bb6da18
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855192"
---
# \<filterTable>
<span data-ttu-id="e8164-101">Представляет таблицу маршрутизации, которая содержит список фильтров, с помощью которых вычисляются сообщения, а также клиентскую конечную точку, которой будут направляться сообщения, если фильтр возвратит значение true.</span><span class="sxs-lookup"><span data-stu-id="e8164-101">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filterTable>**  
  
## <a name="syntax"></a><span data-ttu-id="e8164-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e8164-102">Syntax</span></span>  
  
```xml  
<routing>
  <filterTables>
     name="String">
      <entries>
        <add backupList="String"
             endpointName="String"
             filterName="String"
             priority="Integer" />
      </entries>
    </filterTable>
  </filterTables>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e8164-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e8164-103">Attributes and Elements</span></span>  
 <span data-ttu-id="e8164-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e8164-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e8164-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e8164-105">Attributes</span></span>  
  
|<span data-ttu-id="e8164-106">Элемент</span><span class="sxs-lookup"><span data-stu-id="e8164-106">Element</span></span>|<span data-ttu-id="e8164-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e8164-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e8164-108">name</span><span class="sxs-lookup"><span data-stu-id="e8164-108">name</span></span>|<span data-ttu-id="e8164-109">Строка, содержащая уникальное имя этого элемента конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e8164-109">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e8164-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e8164-110">Child Elements</span></span>  
  
|<span data-ttu-id="e8164-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="e8164-111">Element</span></span>|<span data-ttu-id="e8164-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e8164-112">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|<span data-ttu-id="e8164-113">Сопоставление между фильтрами маршрутизации и целевыми конечными точками (которые будут использованы при отправке сообщений при условии совпадения с критериями фильтров).</span><span class="sxs-lookup"><span data-stu-id="e8164-113">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e8164-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e8164-114">Parent Elements</span></span>  
  
|<span data-ttu-id="e8164-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="e8164-115">Element</span></span>|<span data-ttu-id="e8164-116">Описание</span><span class="sxs-lookup"><span data-stu-id="e8164-116">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="e8164-117">Раздел конфигурации, содержащий таблицы маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="e8164-117">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e8164-118">См. также</span><span class="sxs-lookup"><span data-stu-id="e8164-118">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
