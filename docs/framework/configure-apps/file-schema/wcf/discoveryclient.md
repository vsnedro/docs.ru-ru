---
title: <discoveryClient>
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: af9cf127652f1e12ae57948f9b4a6a26285af793
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192260"
---
# \<discoveryClient>

<span data-ttu-id="b7f4e-101">Элемент конфигурации для создания пользовательской привязки, которая позволяет клиентскому приложению автоматически выполнять поиск обнаруживаемой службы и определять ее адрес во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="b7f4e-101">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryClient>**  
  
## <a name="syntax"></a><span data-ttu-id="b7f4e-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b7f4e-102">Syntax</span></span>  
  
```xml  
<discoveryClient discoveryEndpoint="String">
  <findCriteria duration="TimeSpan"
                maxResults="Integer"
                scopeMatchBy="Uri">
    <contractTypeNames>
      <add name="String"
           namespace="String" />
    </contractTypeNames>
    <extensions />
    <scopes>
      <add scope="URI"/>
    </scopes>
  </findCriteria>
</discoveryClient>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b7f4e-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b7f4e-103">Attributes and Elements</span></span>  

 <span data-ttu-id="b7f4e-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b7f4e-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b7f4e-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b7f4e-105">Attributes</span></span>  
  
|<span data-ttu-id="b7f4e-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b7f4e-106">Attribute</span></span>|<span data-ttu-id="b7f4e-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b7f4e-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b7f4e-108">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="b7f4e-108">discoveryEndpoint</span></span>|<span data-ttu-id="b7f4e-109">Строка, содержащая имя конечной точки обнаружения, которая позволяет клиентскому приложению выполнять автоматический поиск необходимой службы и находить ее адрес во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="b7f4e-109">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b7f4e-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b7f4e-110">Child Elements</span></span>  
  
|<span data-ttu-id="b7f4e-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="b7f4e-111">Element</span></span>|<span data-ttu-id="b7f4e-112">Описание</span><span class="sxs-lookup"><span data-stu-id="b7f4e-112">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="b7f4e-113">Элемент конфигурации, который предоставляет набор критериев, используемых клиентским приложением для поиска службы обнаружения.</span><span class="sxs-lookup"><span data-stu-id="b7f4e-113">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="b7f4e-114">Критерии могут быть сгруппированы в критерии поиска (с указанием искомых служб) и критерии прекращения поиска (как долго должен длиться поиск).</span><span class="sxs-lookup"><span data-stu-id="b7f4e-114">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b7f4e-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b7f4e-115">Parent Elements</span></span>  
  
|<span data-ttu-id="b7f4e-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="b7f4e-116">Element</span></span>|<span data-ttu-id="b7f4e-117">Описание</span><span class="sxs-lookup"><span data-stu-id="b7f4e-117">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="b7f4e-118">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="b7f4e-118">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b7f4e-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b7f4e-119">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
