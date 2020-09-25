---
title: <discoveryClientSettings>
ms.date: 03/30/2017
ms.assetid: 02e1b823-a8bb-4074-90d5-8599f71e8f9d
ms.openlocfilehash: 6e3f273af807eb362f005fef63246013ecc88581
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192247"
---
# \<discoveryClientSettings>

<span data-ttu-id="6b9b3-101">Содержит параметры, необходимые приложению для участия в процессе обнаружения служб в качестве клиента.</span><span class="sxs-lookup"><span data-stu-id="6b9b3-101">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryClientSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="6b9b3-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6b9b3-102">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
        <discoveryClientSettings discoveryEndpoint="String">
          <findCriteria duration="TimeSpan"
                        maxResults="Integer"
                        scopeMatchBy="Uri">
            <contractTypeNames>
              <add name="String"
                   namespace="String" />
            <contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI"/>
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6b9b3-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6b9b3-103">Attributes and Elements</span></span>  

 <span data-ttu-id="6b9b3-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6b9b3-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6b9b3-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6b9b3-105">Attributes</span></span>  
  
|<span data-ttu-id="6b9b3-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6b9b3-106">Attribute</span></span>|<span data-ttu-id="6b9b3-107">Описание</span><span class="sxs-lookup"><span data-stu-id="6b9b3-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6b9b3-108">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="6b9b3-108">discoveryEndpoint</span></span>|<span data-ttu-id="6b9b3-109">Строка, содержащая имя конечной точки обнаружения, которая позволяет клиентскому приложению выполнять автоматический поиск необходимой службы и находить ее адрес во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="6b9b3-109">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6b9b3-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6b9b3-110">Child Elements</span></span>  
  
|<span data-ttu-id="6b9b3-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="6b9b3-111">Element</span></span>|<span data-ttu-id="6b9b3-112">Описание</span><span class="sxs-lookup"><span data-stu-id="6b9b3-112">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="6b9b3-113">Элемент конфигурации, который предоставляет набор критериев, используемых клиентским приложением для поиска службы обнаружения.</span><span class="sxs-lookup"><span data-stu-id="6b9b3-113">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="6b9b3-114">Критерии могут быть сгруппированы в критерии поиска (с указанием искомых служб) и критерии прекращения поиска (как долго должен длиться поиск).</span><span class="sxs-lookup"><span data-stu-id="6b9b3-114">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6b9b3-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6b9b3-115">Parent Elements</span></span>  
  
|<span data-ttu-id="6b9b3-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="6b9b3-116">Element</span></span>|<span data-ttu-id="6b9b3-117">Описание</span><span class="sxs-lookup"><span data-stu-id="6b9b3-117">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="6b9b3-118">Определяет стандартную конечную точку, сведения которой позволяют приложению работать в качестве клиентской программы, динамически ищущей адрес конечной точки во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="6b9b3-118">Defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6b9b3-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6b9b3-119">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientSettingsElement>
