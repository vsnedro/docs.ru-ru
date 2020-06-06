---
title: <dynamicEndpoint>
ms.date: 03/30/2017
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
ms.openlocfilehash: da57ca3ba3bc0036727a749f1cab9ec3657a4fda
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855340"
---
# \<dynamicEndpoint>
<span data-ttu-id="e016f-101">Этот элемент конфигурации определяет стандартную конечную точку, содержащую сведения, позволяющие приложению работать в качестве клиентской программы, которая может найти адрес конечной точки динамически во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="e016f-101">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dynamicEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="e016f-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e016f-102">Syntax</span></span>  
  
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
              <add scope="URI" />
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e016f-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e016f-103">Attributes and Elements</span></span>  
 <span data-ttu-id="e016f-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e016f-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e016f-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e016f-105">Attributes</span></span>  
 <span data-ttu-id="e016f-106">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e016f-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e016f-107">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e016f-107">Child Elements</span></span>  
  
|<span data-ttu-id="e016f-108">Элемент</span><span class="sxs-lookup"><span data-stu-id="e016f-108">Element</span></span>|<span data-ttu-id="e016f-109">Описание</span><span class="sxs-lookup"><span data-stu-id="e016f-109">Description</span></span>|  
|-------------|-----------------|  
|[\<discoveryClientSettings>](discoveryclientsettings.md)|<span data-ttu-id="e016f-110">Содержит параметры, необходимые приложению для участия в процессе обнаружения служб в качестве клиента.</span><span class="sxs-lookup"><span data-stu-id="e016f-110">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e016f-111">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e016f-111">Parent Elements</span></span>  
  
|<span data-ttu-id="e016f-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="e016f-112">Element</span></span>|<span data-ttu-id="e016f-113">Описание</span><span class="sxs-lookup"><span data-stu-id="e016f-113">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="e016f-114">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="e016f-114">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e016f-115">См. также</span><span class="sxs-lookup"><span data-stu-id="e016f-115">See also</span></span>

- <xref:System.ServiceModel.Discovery.DynamicEndpoint>
- <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
