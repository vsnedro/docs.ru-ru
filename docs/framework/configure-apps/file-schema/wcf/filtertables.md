---
title: <filterTables>
ms.date: 03/30/2017
ms.assetid: 41f1ac35-f559-473a-b2c3-8cc83a6a3831
ms.openlocfilehash: faa26ca108010330475725f83dfd0c6668cfc6b1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178207"
---
# \<filterTables>

<span data-ttu-id="e23d9-101">Представляет раздел конфигурации, в котором определены таблицы маршрутизации, содержащие сопоставление между фильтрами маршрутизации и целевыми конечными точками (которые будут использованы при отправке сообщений при совпадении с критериями фильтров).</span><span class="sxs-lookup"><span data-stu-id="e23d9-101">Represents a configuration section for defining routing tables that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filterTables>**  
  
## <a name="syntax"></a><span data-ttu-id="e23d9-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e23d9-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e23d9-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e23d9-103">Attributes and Elements</span></span>  

 <span data-ttu-id="e23d9-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e23d9-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e23d9-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e23d9-105">Attributes</span></span>  

 <span data-ttu-id="e23d9-106">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e23d9-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e23d9-107">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e23d9-107">Child Elements</span></span>  
  
|<span data-ttu-id="e23d9-108">Элемент</span><span class="sxs-lookup"><span data-stu-id="e23d9-108">Element</span></span>|<span data-ttu-id="e23d9-109">Описание</span><span class="sxs-lookup"><span data-stu-id="e23d9-109">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|<span data-ttu-id="e23d9-110">Таблица маршрутизации, содержащая сопоставление между фильтрами маршрутизации и целевыми конечными точками (которые будут использованы при отправке сообщений при условии совпадения с критериями фильтров).</span><span class="sxs-lookup"><span data-stu-id="e23d9-110">A routing table that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e23d9-111">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e23d9-111">Parent Elements</span></span>  
  
|<span data-ttu-id="e23d9-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="e23d9-112">Element</span></span>|<span data-ttu-id="e23d9-113">Описание</span><span class="sxs-lookup"><span data-stu-id="e23d9-113">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="e23d9-114">Раздел конфигурации, содержащий фильтры и таблицы маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="e23d9-114">A configuration section that contains routing filters and routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e23d9-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e23d9-115">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>
