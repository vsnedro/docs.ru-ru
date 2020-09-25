---
title: <filterTable>
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: fb36feedc5fb2cbdf3827cbe44242c7ac6ab8a9b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185695"
---
# \<filterTable>

<span data-ttu-id="be6c2-101">Представляет таблицу маршрутизации, которая содержит список фильтров, с помощью которых вычисляются сообщения, а также клиентскую конечную точку, которой будут направляться сообщения, если фильтр возвратит значение true.</span><span class="sxs-lookup"><span data-stu-id="be6c2-101">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filterTable>**  
  
## <a name="syntax"></a><span data-ttu-id="be6c2-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="be6c2-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="be6c2-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="be6c2-103">Attributes and Elements</span></span>  

 <span data-ttu-id="be6c2-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="be6c2-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="be6c2-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="be6c2-105">Attributes</span></span>  
  
|<span data-ttu-id="be6c2-106">Элемент</span><span class="sxs-lookup"><span data-stu-id="be6c2-106">Element</span></span>|<span data-ttu-id="be6c2-107">Описание</span><span class="sxs-lookup"><span data-stu-id="be6c2-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="be6c2-108">name</span><span class="sxs-lookup"><span data-stu-id="be6c2-108">name</span></span>|<span data-ttu-id="be6c2-109">Строка, содержащая уникальное имя этого элемента конфигурации.</span><span class="sxs-lookup"><span data-stu-id="be6c2-109">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="be6c2-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="be6c2-110">Child Elements</span></span>  
  
|<span data-ttu-id="be6c2-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="be6c2-111">Element</span></span>|<span data-ttu-id="be6c2-112">Описание</span><span class="sxs-lookup"><span data-stu-id="be6c2-112">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|<span data-ttu-id="be6c2-113">Сопоставление между фильтрами маршрутизации и целевыми конечными точками (которые будут использованы при отправке сообщений при условии совпадения с критериями фильтров).</span><span class="sxs-lookup"><span data-stu-id="be6c2-113">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="be6c2-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="be6c2-114">Parent Elements</span></span>  
  
|<span data-ttu-id="be6c2-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="be6c2-115">Element</span></span>|<span data-ttu-id="be6c2-116">Описание</span><span class="sxs-lookup"><span data-stu-id="be6c2-116">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="be6c2-117">Раздел конфигурации, содержащий таблицы маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="be6c2-117">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="be6c2-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="be6c2-118">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
