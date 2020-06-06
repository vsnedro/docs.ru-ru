---
title: <serviceDiscovery>
ms.date: 03/30/2017
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
ms.openlocfilehash: 7ac067e84f2a4d2724e3d8f2d0af9b220fd15538
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399660"
---
# \<serviceDiscovery>
<span data-ttu-id="15c8e-101">Указывает возможность обнаружения конечных точек службы.</span><span class="sxs-lookup"><span data-stu-id="15c8e-101">Specifies the discoverability of service endpoints.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceDiscovery>**  
  
## <a name="syntax"></a><span data-ttu-id="15c8e-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="15c8e-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceDiscovery>
        <announcementEndpoints>
          <endpoint name="String"
                    kind="Type" />
        </announcementEndpoints>
        <discoveryEndpoints>
          <endpoint name="String"
                    kind="Type" />
        </discoveryEndpoints>
      </serviceDiscovery>
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="15c8e-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="15c8e-103">Attributes and Elements</span></span>  
 <span data-ttu-id="15c8e-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="15c8e-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="15c8e-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="15c8e-105">Attributes</span></span>  
 <span data-ttu-id="15c8e-106">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="15c8e-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="15c8e-107">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="15c8e-107">Child Elements</span></span>  
  
|<span data-ttu-id="15c8e-108">Элемент</span><span class="sxs-lookup"><span data-stu-id="15c8e-108">Element</span></span>|<span data-ttu-id="15c8e-109">Описание</span><span class="sxs-lookup"><span data-stu-id="15c8e-109">Description</span></span>|  
|-------------|-----------------|  
|[\<announcementEndpoint>](announcementendpoint.md)|<span data-ttu-id="15c8e-110">Коллекция конечных точек объявления.</span><span class="sxs-lookup"><span data-stu-id="15c8e-110">A collection of announcement endpoints.</span></span> <span data-ttu-id="15c8e-111">Используйте этот раздел, чтобы задать конечные точки, которые будут использоваться для отправки сообщений с объявлениями.</span><span class="sxs-lookup"><span data-stu-id="15c8e-111">Use this section to specify the endpoints to use for sending announcement messages.</span></span>|  
|[\<discoveryEndpoint>](discoveryendpoint.md)|<span data-ttu-id="15c8e-112">Коллекция конечных точек обнаружения.</span><span class="sxs-lookup"><span data-stu-id="15c8e-112">A collection of discovery endpoints.</span></span> <span data-ttu-id="15c8e-113">Используйте этот раздел, чтобы задать конечные точки, которые будут прослушиваться на предмет сообщений об обнаружении.</span><span class="sxs-lookup"><span data-stu-id="15c8e-113">Use this section to specify the endpoints on which to listen for the discovery messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="15c8e-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="15c8e-114">Parent Elements</span></span>  
  
|<span data-ttu-id="15c8e-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="15c8e-115">Element</span></span>|<span data-ttu-id="15c8e-116">Описание</span><span class="sxs-lookup"><span data-stu-id="15c8e-116">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="15c8e-117">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="15c8e-117">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15c8e-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="15c8e-118">Remarks</span></span>  
 <span data-ttu-id="15c8e-119">При добавлении к конфигурации поведения службы этот элемент конфигурации делает все конечные точки этой службы обнаруживаемыми.</span><span class="sxs-lookup"><span data-stu-id="15c8e-119">When added to the service’s behavior configuration, this configuration element makes all of the endpoints of that service discoverable.</span></span> <span data-ttu-id="15c8e-120">Можно дополнительно настроить функции обнаружения таких конечных точек с помощью [\<discoveryEndpoint>](discoveryendpoint.md) [\<announcementEndpoint>](announcementendpoint.md) дочерних элементов или.</span><span class="sxs-lookup"><span data-stu-id="15c8e-120">You can further configure the discovery features of such endpoints by using the [\<discoveryEndpoint>](discoveryendpoint.md) or [\<announcementEndpoint>](announcementendpoint.md) child elements.</span></span> <span data-ttu-id="15c8e-121">Используйте [\<announcementEndpoint>](announcementendpoint.md) раздел для настройки объявлений, указав конфигурацию конечной точки, которая будет использоваться для отправки объявлений службы (в сети, Hello и offline/Bye).</span><span class="sxs-lookup"><span data-stu-id="15c8e-121">Use the [\<announcementEndpoint>](announcementendpoint.md) section to configure the announcements by specifying the endpoint configuration to be use to send service announcements (online/Hello and offline/Bye).</span></span> <span data-ttu-id="15c8e-122">Используйте [\<discoveryEndpoint>](discoveryendpoint.md) раздел, чтобы вручную указать конечную точку для прослушивания сообщений обнаружения.</span><span class="sxs-lookup"><span data-stu-id="15c8e-122">Use the [\<discoveryEndpoint>](discoveryendpoint.md) section to manually specify the endpoint on which to listen for the discovery messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15c8e-123">Пример</span><span class="sxs-lookup"><span data-stu-id="15c8e-123">Example</span></span>  
 <span data-ttu-id="15c8e-124">В следующем примере конфигурации указано, что объект CalculatorService является обнаруживаемым. Дополнительно также указана конечная точка, используемая для объявления.</span><span class="sxs-lookup"><span data-stu-id="15c8e-124">The following configuration example specifies that the CalculatorService to be discoverable, and optionally specifies the announcement endpoint to be used.</span></span>  
  
```xml  
<services>
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    ...
  </service>
</services>
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <serviceDiscovery>
        <announcementEndpoints>
          <endpoint name="udpEndpoint"
                    kind="udpAnnouncementEndpoint" />
        </announcementEndpoints>
      </serviceDiscovery>
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="15c8e-125">См. также</span><span class="sxs-lookup"><span data-stu-id="15c8e-125">See also</span></span>

- <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>
