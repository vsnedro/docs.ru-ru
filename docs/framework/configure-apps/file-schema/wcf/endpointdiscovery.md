---
title: <endpointDiscovery>
ms.date: 03/30/2017
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
ms.openlocfilehash: 621c742e3bb06ce91fa5a6b8951351295f73df9e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185812"
---
# \<endpointDiscovery>

<span data-ttu-id="14863-101">Указывает различные параметры обнаружения для конечной точки, такие как возможность обнаружения, области и любые пользовательские модули для ее метаданных.</span><span class="sxs-lookup"><span data-stu-id="14863-101">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpointDiscovery>**  
  
## <a name="syntax"></a><span data-ttu-id="14863-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="14863-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enabled="Boolean">
        <scopes>
          <add scope="URI"/>
        </scopes>
        <extensions />
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14863-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="14863-103">Attributes and Elements</span></span>  

 <span data-ttu-id="14863-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="14863-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14863-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="14863-105">Attributes</span></span>  
  
|<span data-ttu-id="14863-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="14863-106">Attribute</span></span>|<span data-ttu-id="14863-107">Описание</span><span class="sxs-lookup"><span data-stu-id="14863-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="14863-108">Включено</span><span class="sxs-lookup"><span data-stu-id="14863-108">enabled</span></span>|<span data-ttu-id="14863-109">Логическое значение, указывающее, включена ли возможность обнаружения в этой конечной точке.</span><span class="sxs-lookup"><span data-stu-id="14863-109">A Boolean value that specifies whether discoverability is enabled on this endpoint.</span></span> <span data-ttu-id="14863-110">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="14863-110">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="14863-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="14863-111">Child Elements</span></span>  
  
|<span data-ttu-id="14863-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="14863-112">Element</span></span>|<span data-ttu-id="14863-113">Описание</span><span class="sxs-lookup"><span data-stu-id="14863-113">Description</span></span>|  
|-------------|-----------------|  
|[\<scopes>](scopes.md)|<span data-ttu-id="14863-114">Коллекция URI областей для этой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="14863-114">A collection of scope URIs for the endpoint.</span></span> <span data-ttu-id="14863-115">С одной конечной точкой можно связать несколько URI областей.</span><span class="sxs-lookup"><span data-stu-id="14863-115">More than one scope Uris can be associated with a single endpoint.</span></span>|  
|<span data-ttu-id="14863-116">[\<extensions>](extensions.md) [из \<endpointDiscovery> ]</span><span class="sxs-lookup"><span data-stu-id="14863-116">[\<extensions>](extensions.md) [of \<endpointDiscovery>]</span></span>|<span data-ttu-id="14863-117">Коллекция элементов XML, позволяющая указывать пользовательские метаданные, публикуемые для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="14863-117">A collection of XML elements that allows you to specify custom metadata to be published for an endpoint.</span></span>|  
|\<types>|<span data-ttu-id="14863-118">Коллекция интерфейсов, которые нужно найти.</span><span class="sxs-lookup"><span data-stu-id="14863-118">A collection of interfaces to search for.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="14863-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="14863-119">Parent Elements</span></span>  
  
|<span data-ttu-id="14863-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="14863-120">Element</span></span>|<span data-ttu-id="14863-121">Описание</span><span class="sxs-lookup"><span data-stu-id="14863-121">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="14863-122">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="14863-122">Specifies a behavior element.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="14863-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="14863-123">Remarks</span></span>  

 <span data-ttu-id="14863-124">Если добавить этот элемент конфигурации в конфигурацию поведения конечной точки и присвоить атрибуту `enabled` значение `true`, то будет включена возможность обнаружения.</span><span class="sxs-lookup"><span data-stu-id="14863-124">When added to the endpoint’s behavior configuration and with the `enabled` attribute set to `true`, this configuration element enables its discoverability.</span></span> <span data-ttu-id="14863-125">Кроме того, можно использовать [\<scopes>](scopes.md) дочерний элемент для указания универсальных кодов ресурсов (URI) настраиваемой области, которые можно использовать для фильтрации конечных точек службы во время запроса, а также [\<extensions>](extensions.md) дочерний элемент для указания пользовательских метаданных, которые должны быть опубликованы вместе со стандартными обнаруживаемыми метаданными (EPR, Контракттипенаме, Биндингнаме, Scope и ListenUri).</span><span class="sxs-lookup"><span data-stu-id="14863-125">In addition, you can use the [\<scopes>](scopes.md)child element to specifying custom scope Uris that can be used to filter service endpoints during query, as well as the [\<extensions>](extensions.md) child element to specify custom metadata that should be published along with the standard discoverable metadata (EPR, ContractTypeName, BindingName, Scope and ListenURI).</span></span>  
  
 <span data-ttu-id="14863-126">Этот элемент конфигурации зависит от [\<serviceDiscovery>](servicediscovery.md) элемента, который обеспечивает контроль уровня обслуживания для обнаружения.</span><span class="sxs-lookup"><span data-stu-id="14863-126">This configuration element is dependent on the [\<serviceDiscovery>](servicediscovery.md) element that provides the service level control of discoverability.</span></span> <span data-ttu-id="14863-127">Это означает, что параметры этого элемента игнорируются, если они отсутствуют [\<serviceDiscovery>](servicediscovery.md) в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="14863-127">This means that this element’s settings are ignored if [\<serviceDiscovery>](servicediscovery.md) is not present in the configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14863-128">Пример</span><span class="sxs-lookup"><span data-stu-id="14863-128">Example</span></span>  

 <span data-ttu-id="14863-129">В следующем примере конфигурации определены области фильтрации и метаданные расширения, которые будут опубликованы для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="14863-129">The following configuration example specifies filtering scopes and extension metadata to be published for an endpoint.</span></span>  
  
```xml  
<services>
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <endpoint binding="basicHttpBinding"
              address="calculator"
              contract="ICalculatorService"
              behaviorConfiguration="calculatorEndpointBehavior" />
  </service>
</services>
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <serviceDiscovery />
    </behavior>
  </serviceBehaviors>
  <endpointBehaviors>
    <behavior name="calculatorEndpointBehavior">
      <endpointDiscovery enabled="true">
        <scopes>
          <add scope="http://contoso/test1" />
          <add scope="http://contoso/test2" />
        </scopes>
        <extensions>
          <e:Publisher xmlns:e="http://example.org">
            <e:Name>The Example Organization</e:Name>
            <e:Address>One Example Way, ExampleTown, EX 12345</e:Address>
            <e:Contact>support@example.org</e:Contact>
          </e:Publisher>
          <AnotherCustomMetadata>Custom Metadata</AnotherCustomMetadata>
        </extensions>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="14863-130">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="14863-130">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
