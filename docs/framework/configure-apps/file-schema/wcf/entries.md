---
title: <entries>
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: d3dae510ac62735138a24b8fb97a8acfffde1a98
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189972"
---
# \<entries>

<span data-ttu-id="29704-101">Запись маршрутизации, содержащая сопоставление между фильтрами маршрутизации и целевыми конечными точками (которые будут использованы при отправке сообщений при условии совпадения с критериями фильтров).</span><span class="sxs-lookup"><span data-stu-id="29704-101">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTable>**](filtertable.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<entries>**  
  
## <a name="syntax"></a><span data-ttu-id="29704-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="29704-102">Syntax</span></span>  
  
```xml  
<routing>
  <filterTables>
    <filterTable name="String">
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="29704-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="29704-103">Attributes and Elements</span></span>  

 <span data-ttu-id="29704-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="29704-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="29704-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="29704-105">Attributes</span></span>  

 <span data-ttu-id="29704-106">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="29704-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="29704-107">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="29704-107">Child Elements</span></span>  
  
|<span data-ttu-id="29704-108">Элемент</span><span class="sxs-lookup"><span data-stu-id="29704-108">Element</span></span>|<span data-ttu-id="29704-109">Описание</span><span class="sxs-lookup"><span data-stu-id="29704-109">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|<span data-ttu-id="29704-110">Сопоставляет фильтр с ранее определенной конечной точкой клиента.</span><span class="sxs-lookup"><span data-stu-id="29704-110">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="29704-111">Сообщения, соответствующие этому фильтру, будут отправлены по данному назначению.</span><span class="sxs-lookup"><span data-stu-id="29704-111">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="29704-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="29704-112">Parent Elements</span></span>  
  
|<span data-ttu-id="29704-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="29704-113">Element</span></span>|<span data-ttu-id="29704-114">Описание</span><span class="sxs-lookup"><span data-stu-id="29704-114">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="29704-115">Раздел конфигурации, содержащий таблицу маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="29704-115">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="29704-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="29704-116">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
