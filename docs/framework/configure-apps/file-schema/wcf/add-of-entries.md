---
title: <add> из <entries>
ms.date: 03/30/2017
ms.assetid: 3af4805b-dc72-4f68-b168-da4fba8c6170
ms.openlocfilehash: 156d8b8d9d0eb05efbf306434ab4555a98bc317e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149053"
---
# <a name="add-of-entries"></a><span data-ttu-id="5f697-102">\<add> из \<entries></span><span class="sxs-lookup"><span data-stu-id="5f697-102">\<add> of \<entries></span></span>

<span data-ttu-id="5f697-103">Представляет запись маршрутизации, которая сопоставляет фильтр с ранее определенной конечной точкой клиента.</span><span class="sxs-lookup"><span data-stu-id="5f697-103">Represents a routing entry that maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="5f697-104">Сообщения, соответствующие этому фильтру, будут отправлены по данному назначению.</span><span class="sxs-lookup"><span data-stu-id="5f697-104">Messages matching this filter will be sent to this destination.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTable>**](filtertable.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<entries>**](entries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="5f697-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5f697-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5f697-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5f697-106">Attributes and Elements</span></span>  

 <span data-ttu-id="5f697-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5f697-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5f697-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5f697-108">Attributes</span></span>  
  
|<span data-ttu-id="5f697-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5f697-109">Attribute</span></span>|<span data-ttu-id="5f697-110">Описание</span><span class="sxs-lookup"><span data-stu-id="5f697-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5f697-111">backupList</span><span class="sxs-lookup"><span data-stu-id="5f697-111">backupList</span></span>|<span data-ttu-id="5f697-112">Строка, указывающая ссылку на резервный список конечных точек.</span><span class="sxs-lookup"><span data-stu-id="5f697-112">A string that specifies a reference to a backup list of endpoints.</span></span>|  
|<span data-ttu-id="5f697-113">endpoint</span><span class="sxs-lookup"><span data-stu-id="5f697-113">endpoint</span></span>|<span data-ttu-id="5f697-114">Строка, в которой указана ссылка на конечную точку клиента, получающую сообщения, которые соответствуют критериям фильтра, указанного в атрибуте `filterName`.</span><span class="sxs-lookup"><span data-stu-id="5f697-114">A string that specifies a reference to a client endpoint that will receive messages that match the filter specified by the `filterName` attribute.</span></span>|  
|<span data-ttu-id="5f697-115">filterName</span><span class="sxs-lookup"><span data-stu-id="5f697-115">filterName</span></span>|<span data-ttu-id="5f697-116">Строка, в которой указана ссылка на элемент фильтра.</span><span class="sxs-lookup"><span data-stu-id="5f697-116">A string that specifies a reference to a filter element.</span></span>|  
|<span data-ttu-id="5f697-117">priority</span><span class="sxs-lookup"><span data-stu-id="5f697-117">priority</span></span>|<span data-ttu-id="5f697-118">Целое число, задающее приоритет этой записи.</span><span class="sxs-lookup"><span data-stu-id="5f697-118">An integer that specifies the priority of this entry.</span></span><br /><br /> <span data-ttu-id="5f697-119">Записи в таблице маршрутизации обрабатываются исходя из приоритета, причем 0 является самым низким приоритетом.</span><span class="sxs-lookup"><span data-stu-id="5f697-119">Entries in the routing table will be evaluated based on priority, with 0 being the lowest priority.</span></span> <span data-ttu-id="5f697-120">Все записи определенного приоритета обрабатываются одновременно, и, если для текущего приоритета не находится совпадающая запись, вычисляется следующий уровень приоритета.</span><span class="sxs-lookup"><span data-stu-id="5f697-120">All entries for a specific priority are evaluated simultaneously, if no matching entry is found for the current priority, the next priority level will be evaluated.</span></span><br /><br /> <span data-ttu-id="5f697-121">Это необязательное значение.</span><span class="sxs-lookup"><span data-stu-id="5f697-121">This value is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5f697-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5f697-122">Child Elements</span></span>  

 <span data-ttu-id="5f697-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5f697-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5f697-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5f697-124">Parent Elements</span></span>  
  
|<span data-ttu-id="5f697-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="5f697-125">Element</span></span>|<span data-ttu-id="5f697-126">Описание</span><span class="sxs-lookup"><span data-stu-id="5f697-126">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="5f697-127">Раздел конфигурации, в котором содержатся записи сопоставления маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="5f697-127">A configuration section that contains routing mapping entries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5f697-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5f697-128">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
