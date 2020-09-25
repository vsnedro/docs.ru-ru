---
title: <announcementEndpoint>
ms.date: 03/30/2017
ms.assetid: 034b7c69-a770-4502-8cef-38007bbcd025
ms.openlocfilehash: f68972cdf0e55f92fd4856aff912f00db7c62be4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201620"
---
# \<announcementEndpoint>

<span data-ttu-id="73e2d-101">Этот элемент конфигурации определяет стандартную конечную точку с фиксированным контрактом объявления.</span><span class="sxs-lookup"><span data-stu-id="73e2d-101">This configuration element defines a standard endpoint with a fixed announcement contract.</span></span> <span data-ttu-id="73e2d-102">Служба может также объявлять свою доступность путем отправки сообщения в режимах «в сети» и «не в сети» соответственно при открытии и закрытии службы.</span><span class="sxs-lookup"><span data-stu-id="73e2d-102">A service can optionally announce its availability by sending an online and offline announcement message when it is opened or closed respectively.</span></span> <span data-ttu-id="73e2d-103">Служба Windows Communication Foundation (WCF) указывает конечные точки объявления в [\<serviceDiscovery>](servicediscovery.md) элементе и использует аннаунцементклиент для выполнения объявлений.</span><span class="sxs-lookup"><span data-stu-id="73e2d-103">A Windows Communication Foundation (WCF) service specifies the announcement endpoints in the [\<serviceDiscovery>](servicediscovery.md) element and uses the AnnouncementClient to perform the announcements.</span></span> <span data-ttu-id="73e2d-104">Клиент, желающий прослушивать объявление от другой службы, фактически выступает в роли службы WCF. Поэтому необходимо настроить конечные точки объявления для этого клиента в [\<services>](services.md) разделе.</span><span class="sxs-lookup"><span data-stu-id="73e2d-104">A client wishing to listen for the announcement from other service is actually acting as a WCF service; thus you have to configure the announcement endpoints for that client in the [\<services>](services.md) section.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<announcementEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="73e2d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="73e2d-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <announcementEndpoint>
      <standardEndpoint discoveryVersion="WSDiscovery11/WSDiscoveryApril2005"
                        maxAnnouncementDelay="Timespan"
                        name="String" />
    </announcementEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73e2d-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="73e2d-106">Attributes and Elements</span></span>  

 <span data-ttu-id="73e2d-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="73e2d-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73e2d-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="73e2d-108">Attributes</span></span>  
  
|<span data-ttu-id="73e2d-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="73e2d-109">Attribute</span></span>|<span data-ttu-id="73e2d-110">Описание</span><span class="sxs-lookup"><span data-stu-id="73e2d-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="73e2d-111">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="73e2d-111">discoveryVersion</span></span>|<span data-ttu-id="73e2d-112">Строка, указывающая одну из двух версий протокола WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="73e2d-112">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="73e2d-113">Допустимые значения: WSDiscovery11 и WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="73e2d-113">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="73e2d-114">Это значение имеет тип <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="73e2d-114">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="73e2d-115">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="73e2d-115">maxAnnouncementDelay</span></span>|<span data-ttu-id="73e2d-116">Значение «Timespan», указывающее максимальную задержку, в течение которой протокол Discovery не будет отправлять сообщение Hello.</span><span class="sxs-lookup"><span data-stu-id="73e2d-116">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="73e2d-117">Перед отправкой сообщения ожидают произвольное время в диапазоне от 0 до значения этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="73e2d-117">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="73e2d-118">Этот атрибут используется для назначения короткой произвольной задержки для предотвращения перегрузки сети, когда сеть становится недоступной, а все службы входят в сеть одновременно.</span><span class="sxs-lookup"><span data-stu-id="73e2d-118">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="73e2d-119">name</span><span class="sxs-lookup"><span data-stu-id="73e2d-119">name</span></span>|<span data-ttu-id="73e2d-120">Строка, указывающая имя конфигурации стандартной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="73e2d-120">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="73e2d-121">Это имя используется в атрибуте `endpointConfiguration` конечной точки службы для связывания стандартной конечной точки с ее конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="73e2d-121">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="73e2d-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="73e2d-122">Child Elements</span></span>  

 <span data-ttu-id="73e2d-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="73e2d-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="73e2d-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="73e2d-124">Parent Elements</span></span>  
  
|<span data-ttu-id="73e2d-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="73e2d-125">Element</span></span>|<span data-ttu-id="73e2d-126">Описание</span><span class="sxs-lookup"><span data-stu-id="73e2d-126">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="73e2d-127">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="73e2d-127">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="73e2d-128">Пример</span><span class="sxs-lookup"><span data-stu-id="73e2d-128">Example</span></span>  

 <span data-ttu-id="73e2d-129">В следующем примере показано прослушивание клиентом сообщений с объявлениями по протоколам http и peernet.</span><span class="sxs-lookup"><span data-stu-id="73e2d-129">The following example demonstrates a client listening for announcements messages over http and peernet.</span></span>  
  
```xml  
<services>
  <service name="ServiceAnnouncementListener">
    <endpoint name="httpAnnouncementEndpoint"
              kind="announcementEndpoint"
              binding="basicHttpBinding"
              address="announcements" />
    <endpoint name="peerNetAnnouncementEndpoint"
              kind="announcementEndpoint"
              binding="peerTcpBinding"
              address="net.p2p://discoveryMesh/multicast"
              bindingConfiguration="discoveryPeerTcpBindingConfig" />
  ...
  </service>
</services>

<standardEndpoints>
  <announcementEndpoint>
    <standardEndpoint name="httpAnnouncementEndpoint"
                      version="WSDiscoveryApril2005" />
    <standardEndpoint name="peerNetAnnouncementEndpoint"
                      version="WSDiscoveryApril2005" />
  </announcementEndpoint>
</standardEndpoints>
```  
  
## <a name="see-also"></a><span data-ttu-id="73e2d-130">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="73e2d-130">See also</span></span>

- <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>
