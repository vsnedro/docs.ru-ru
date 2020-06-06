---
title: <entries>
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: ffe2538fa2c3cb680285cfaa68c975c0f9d4b1bd
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855276"
---
# \<entries>
<span data-ttu-id="86b1b-101">Запись маршрутизации, содержащая сопоставление между фильтрами маршрутизации и целевыми конечными точками (которые будут использованы при отправке сообщений при условии совпадения с критериями фильтров).</span><span class="sxs-lookup"><span data-stu-id="86b1b-101">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTable>**](filtertable.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<entries>**  
  
## <a name="syntax"></a><span data-ttu-id="86b1b-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="86b1b-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="86b1b-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="86b1b-103">Attributes and Elements</span></span>  
 <span data-ttu-id="86b1b-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="86b1b-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="86b1b-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="86b1b-105">Attributes</span></span>  
 <span data-ttu-id="86b1b-106">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="86b1b-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="86b1b-107">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="86b1b-107">Child Elements</span></span>  
  
|<span data-ttu-id="86b1b-108">Элемент</span><span class="sxs-lookup"><span data-stu-id="86b1b-108">Element</span></span>|<span data-ttu-id="86b1b-109">Описание</span><span class="sxs-lookup"><span data-stu-id="86b1b-109">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|<span data-ttu-id="86b1b-110">Сопоставляет фильтр с ранее определенной конечной точкой клиента.</span><span class="sxs-lookup"><span data-stu-id="86b1b-110">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="86b1b-111">Сообщения, соответствующие этому фильтру, будут отправлены по данному назначению.</span><span class="sxs-lookup"><span data-stu-id="86b1b-111">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="86b1b-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="86b1b-112">Parent Elements</span></span>  
  
|<span data-ttu-id="86b1b-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="86b1b-113">Element</span></span>|<span data-ttu-id="86b1b-114">Описание</span><span class="sxs-lookup"><span data-stu-id="86b1b-114">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="86b1b-115">Раздел конфигурации, содержащий таблицу маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="86b1b-115">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="86b1b-116">См. также</span><span class="sxs-lookup"><span data-stu-id="86b1b-116">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
