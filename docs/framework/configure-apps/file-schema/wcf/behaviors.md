---
title: <behaviors>
ms.date: 03/30/2017
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
ms.openlocfilehash: bcdd26f038b343040d81b0add83bf166a5e3151f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "74139688"
---
# \<behaviors>
<span data-ttu-id="10db7-101">Данный элемент определяет две дочерние коллекции с именами `endpointBehaviors` и `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="10db7-101">This element defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="10db7-102">Каждая коллекция определяет элементы поведений, используемые конечными точками и службами соответственно.</span><span class="sxs-lookup"><span data-stu-id="10db7-102">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="10db7-103">Каждый элемент поведения идентифицируется по уникальному атрибуту `name`.</span><span class="sxs-lookup"><span data-stu-id="10db7-103">Each behavior element is identified by its unique `name` attribute.</span></span> <span data-ttu-id="10db7-104">Начиная с .NET Framework 4, привязки и поведения не обязательно должны иметь имя.</span><span class="sxs-lookup"><span data-stu-id="10db7-104">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="10db7-105">Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="10db7-105">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<behaviors>**  
  
## <a name="syntax"></a><span data-ttu-id="10db7-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="10db7-106">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
  </serviceBehaviors>
  <endpointBehaviors>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="10db7-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="10db7-107">Attributes and Elements</span></span>  
 <span data-ttu-id="10db7-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="10db7-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="10db7-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="10db7-109">Attributes</span></span>  
 <span data-ttu-id="10db7-110">Нет</span><span class="sxs-lookup"><span data-stu-id="10db7-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="10db7-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="10db7-111">Child Elements</span></span>  
  
|<span data-ttu-id="10db7-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="10db7-112">Element</span></span>|<span data-ttu-id="10db7-113">Описание</span><span class="sxs-lookup"><span data-stu-id="10db7-113">Description</span></span>|  
|-------------|-----------------|  
|[\<endpointBehaviors>](endpointbehaviors.md)|<span data-ttu-id="10db7-114">Данный раздел конфигурации представляет все типы поведения, определенные для конкретной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="10db7-114">This configuration section represents all the behaviors defined for a specific endpoint.</span></span>|  
|[\<serviceBehaviors>](servicebehaviors.md)|<span data-ttu-id="10db7-115">В данном разделе конфигурации представлены все поведения, определенные для конкретной службы.</span><span class="sxs-lookup"><span data-stu-id="10db7-115">This configuration section represents all the behaviors defined for a specific service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="10db7-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="10db7-116">Parent Elements</span></span>  
  
|<span data-ttu-id="10db7-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="10db7-117">Element</span></span>|<span data-ttu-id="10db7-118">Описание</span><span class="sxs-lookup"><span data-stu-id="10db7-118">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel>](system-servicemodel.md)|<span data-ttu-id="10db7-119">Корневой элемент всех элементов конфигурации Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="10db7-119">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10db7-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="10db7-120">Remarks</span></span>  
 <span data-ttu-id="10db7-121">Элемент `<remove>` можно использовать для удаления определенного поведения из коллекции.</span><span class="sxs-lookup"><span data-stu-id="10db7-121">You can use the `<remove>` element to remove a particular behavior from the collection.</span></span> <span data-ttu-id="10db7-122">Для этого нужно просто указать имя удаляемого поведения в атрибуте `name` элемента `<remove>`.</span><span class="sxs-lookup"><span data-stu-id="10db7-122">To do so, simply supply the name of the behavior to remove in the `name` attribute of the `<remove>` element.</span></span>  <span data-ttu-id="10db7-123">Также можно использовать элемент `<clear>`, очищающий все содержимое коллекции, чтобы обеспечить запуск пустой коллекции.</span><span class="sxs-lookup"><span data-stu-id="10db7-123">You can also use the `<clear>` element to insure that a behavior collection starts empty by clearing out all the content of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10db7-124">См. также</span><span class="sxs-lookup"><span data-stu-id="10db7-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElement>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="10db7-125">Настройка и расширение среды выполнения с помощью поведений</span><span class="sxs-lookup"><span data-stu-id="10db7-125">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
- [<span data-ttu-id="10db7-126">Настройка поведений клиентов</span><span class="sxs-lookup"><span data-stu-id="10db7-126">Configuring Client Behaviors</span></span>](../../../wcf/configuring-client-behaviors.md)
- [<span data-ttu-id="10db7-127">Задание поведения клиента во время выполнения</span><span class="sxs-lookup"><span data-stu-id="10db7-127">Specifying Client Run-Time Behavior</span></span>](../../../wcf/specifying-client-run-time-behavior.md)
- [<span data-ttu-id="10db7-128">Указание поведения службы во время выполнения</span><span class="sxs-lookup"><span data-stu-id="10db7-128">Specifying Service Run-Time Behavior</span></span>](../../../wcf/specifying-service-run-time-behavior.md)
- [<span data-ttu-id="10db7-129">Поведение безопасности</span><span class="sxs-lookup"><span data-stu-id="10db7-129">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
