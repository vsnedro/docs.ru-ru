---
title: <filterTables>
ms.date: 03/30/2017
ms.assetid: 41f1ac35-f559-473a-b2c3-8cc83a6a3831
ms.openlocfilehash: c68479737cefe542a10a404a8b31a4820a430ffb
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855199"
---
# \<filterTables>
<span data-ttu-id="2a77a-101">Представляет раздел конфигурации, в котором определены таблицы маршрутизации, содержащие сопоставление между фильтрами маршрутизации и целевыми конечными точками (которые будут использованы при отправке сообщений при совпадении с критериями фильтров).</span><span class="sxs-lookup"><span data-stu-id="2a77a-101">Represents a configuration section for defining routing tables that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filterTables>**  
  
## <a name="syntax"></a><span data-ttu-id="2a77a-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2a77a-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2a77a-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2a77a-103">Attributes and Elements</span></span>  
 <span data-ttu-id="2a77a-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2a77a-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2a77a-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2a77a-105">Attributes</span></span>  
 <span data-ttu-id="2a77a-106">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2a77a-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2a77a-107">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2a77a-107">Child Elements</span></span>  
  
|<span data-ttu-id="2a77a-108">Элемент</span><span class="sxs-lookup"><span data-stu-id="2a77a-108">Element</span></span>|<span data-ttu-id="2a77a-109">Описание</span><span class="sxs-lookup"><span data-stu-id="2a77a-109">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|<span data-ttu-id="2a77a-110">Таблица маршрутизации, содержащая сопоставление между фильтрами маршрутизации и целевыми конечными точками (которые будут использованы при отправке сообщений при условии совпадения с критериями фильтров).</span><span class="sxs-lookup"><span data-stu-id="2a77a-110">A routing table that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2a77a-111">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2a77a-111">Parent Elements</span></span>  
  
|<span data-ttu-id="2a77a-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="2a77a-112">Element</span></span>|<span data-ttu-id="2a77a-113">Описание</span><span class="sxs-lookup"><span data-stu-id="2a77a-113">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="2a77a-114">Раздел конфигурации, содержащий фильтры и таблицы маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="2a77a-114">A configuration section that contains routing filters and routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2a77a-115">См. также</span><span class="sxs-lookup"><span data-stu-id="2a77a-115">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>
