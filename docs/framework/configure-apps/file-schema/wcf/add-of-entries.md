---
title: <add> из <entries>
ms.date: 03/30/2017
ms.assetid: 3af4805b-dc72-4f68-b168-da4fba8c6170
ms.openlocfilehash: 23b0a825ea593f85ade870d5b93367571eaa3ec0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850509"
---
# <a name="add-of-entries"></a><span data-ttu-id="a77a1-102">\<add> из \<entries></span><span class="sxs-lookup"><span data-stu-id="a77a1-102">\<add> of \<entries></span></span>
<span data-ttu-id="a77a1-103">Представляет запись маршрутизации, которая сопоставляет фильтр с ранее определенной конечной точкой клиента.</span><span class="sxs-lookup"><span data-stu-id="a77a1-103">Represents a routing entry that maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="a77a1-104">Сообщения, соответствующие этому фильтру, будут отправлены по данному назначению.</span><span class="sxs-lookup"><span data-stu-id="a77a1-104">Messages matching this filter will be sent to this destination.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTable>**](filtertable.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<entries>**](entries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="a77a1-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a77a1-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a77a1-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a77a1-106">Attributes and Elements</span></span>  
 <span data-ttu-id="a77a1-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a77a1-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a77a1-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a77a1-108">Attributes</span></span>  
  
|<span data-ttu-id="a77a1-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a77a1-109">Attribute</span></span>|<span data-ttu-id="a77a1-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="a77a1-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a77a1-111">backupList</span><span class="sxs-lookup"><span data-stu-id="a77a1-111">backupList</span></span>|<span data-ttu-id="a77a1-112">Строка, указывающая ссылку на резервный список конечных точек.</span><span class="sxs-lookup"><span data-stu-id="a77a1-112">A string that specifies a reference to a backup list of endpoints.</span></span>|  
|<span data-ttu-id="a77a1-113">endpoint</span><span class="sxs-lookup"><span data-stu-id="a77a1-113">endpoint</span></span>|<span data-ttu-id="a77a1-114">Строка, в которой указана ссылка на конечную точку клиента, получающую сообщения, которые соответствуют критериям фильтра, указанного в атрибуте `filterName`.</span><span class="sxs-lookup"><span data-stu-id="a77a1-114">A string that specifies a reference to a client endpoint that will receive messages that match the filter specified by the `filterName` attribute.</span></span>|  
|<span data-ttu-id="a77a1-115">filterName</span><span class="sxs-lookup"><span data-stu-id="a77a1-115">filterName</span></span>|<span data-ttu-id="a77a1-116">Строка, в которой указана ссылка на элемент фильтра.</span><span class="sxs-lookup"><span data-stu-id="a77a1-116">A string that specifies a reference to a filter element.</span></span>|  
|<span data-ttu-id="a77a1-117">priority</span><span class="sxs-lookup"><span data-stu-id="a77a1-117">priority</span></span>|<span data-ttu-id="a77a1-118">Целое число, задающее приоритет этой записи.</span><span class="sxs-lookup"><span data-stu-id="a77a1-118">An integer that specifies the priority of this entry.</span></span><br /><br /> <span data-ttu-id="a77a1-119">Записи в таблице маршрутизации обрабатываются исходя из приоритета, причем 0 является самым низким приоритетом.</span><span class="sxs-lookup"><span data-stu-id="a77a1-119">Entries in the routing table will be evaluated based on priority, with 0 being the lowest priority.</span></span> <span data-ttu-id="a77a1-120">Все записи определенного приоритета обрабатываются одновременно, и, если для текущего приоритета не находится совпадающая запись, вычисляется следующий уровень приоритета.</span><span class="sxs-lookup"><span data-stu-id="a77a1-120">All entries for a specific priority are evaluated simultaneously, if no matching entry is found for the current priority, the next priority level will be evaluated.</span></span><br /><br /> <span data-ttu-id="a77a1-121">Это необязательное значение.</span><span class="sxs-lookup"><span data-stu-id="a77a1-121">This value is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a77a1-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a77a1-122">Child Elements</span></span>  
 <span data-ttu-id="a77a1-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a77a1-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a77a1-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a77a1-124">Parent Elements</span></span>  
  
|<span data-ttu-id="a77a1-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="a77a1-125">Element</span></span>|<span data-ttu-id="a77a1-126">Описание</span><span class="sxs-lookup"><span data-stu-id="a77a1-126">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="a77a1-127">Раздел конфигурации, в котором содержатся записи сопоставления маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="a77a1-127">A configuration section that contains routing mapping entries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a77a1-128">См. также</span><span class="sxs-lookup"><span data-stu-id="a77a1-128">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
