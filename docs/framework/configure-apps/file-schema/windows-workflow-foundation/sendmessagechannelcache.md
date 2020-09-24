---
title: <sendMessageChannelCache>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 241e428e-5030-4b13-8a0a-69f05288d3d9
ms.openlocfilehash: c1775ddabffda58c7529a64b89c9c53ff3da7b99
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164926"
---
# \<sendMessageChannelCache>

<span data-ttu-id="3f4a9-101">Поведение службы, которое позволяет изменить уровни доступа к кэшу, параметры кэша фабрики канала и параметры кэша канала для рабочих процессов, которые отправляют сообщения в конечные точки служб с использованием действий отправки сообщений.</span><span class="sxs-lookup"><span data-stu-id="3f4a9-101">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sendMessageChannelCache>**  
  
## <a name="syntax"></a><span data-ttu-id="3f4a9-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3f4a9-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <sendMessageChannelCache allowUnsafeCaching="Boolean">
        <channelSettings idleTimeout="TimeSpan"
                         leaseTimeout="TimeSpan"
                         maxItemsInCache="Integer" />
        <factorySettings idleTimeout="TimeSpan"
                         leaseTimeout="TimeSpan"
                         maxItemsInCache="Integer" />
      </sendMessageChannelCache>
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3f4a9-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3f4a9-103">Attributes and Elements</span></span>  

 <span data-ttu-id="3f4a9-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3f4a9-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3f4a9-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3f4a9-105">Attributes</span></span>  
  
|<span data-ttu-id="3f4a9-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3f4a9-106">Attribute</span></span>|<span data-ttu-id="3f4a9-107">Описание</span><span class="sxs-lookup"><span data-stu-id="3f4a9-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3f4a9-108">allowUnsafeCaching</span><span class="sxs-lookup"><span data-stu-id="3f4a9-108">allowUnsafeCaching</span></span>|<span data-ttu-id="3f4a9-109">Логическое значение, указывающее, следует ли включить кэширование.</span><span class="sxs-lookup"><span data-stu-id="3f4a9-109">A Boolean value that indicates whether to turn caching on.</span></span> <span data-ttu-id="3f4a9-110">Если служба рабочего процесса имеет пользовательские привязки или поведения, то кэширование может оказаться небезопасным (и будет отключено по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="3f4a9-110">If your workflow service has custom bindings or custom behaviors, caching could be unsecure and therefore is disabled by default.</span></span> <span data-ttu-id="3f4a9-111">Однако если вы хотите включить кэширование, присвойте этому свойству значение **true**.</span><span class="sxs-lookup"><span data-stu-id="3f4a9-111">However, if you want to turn caching on set this property to **true**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3f4a9-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3f4a9-112">Child Elements</span></span>  
  
|<span data-ttu-id="3f4a9-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="3f4a9-113">Element</span></span>|<span data-ttu-id="3f4a9-114">Описание</span><span class="sxs-lookup"><span data-stu-id="3f4a9-114">Description</span></span>|  
|-------------|-----------------|  
|[\<channelSettings>](channelsettings.md)|<span data-ttu-id="3f4a9-115">Указывает параметры кэша канала.</span><span class="sxs-lookup"><span data-stu-id="3f4a9-115">Specifies the settings of the channel cache.</span></span>|  
|[\<factorySettings>](factorysettings.md)|<span data-ttu-id="3f4a9-116">Указывает параметры кэша фабрики канала.</span><span class="sxs-lookup"><span data-stu-id="3f4a9-116">Specifies the settings of the channel factory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3f4a9-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3f4a9-117">Parent Elements</span></span>  
  
|<span data-ttu-id="3f4a9-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="3f4a9-118">Element</span></span>|<span data-ttu-id="3f4a9-119">Описание</span><span class="sxs-lookup"><span data-stu-id="3f4a9-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3f4a9-120">\<behavior> из \<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="3f4a9-120">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="3f4a9-121">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="3f4a9-121">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f4a9-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="3f4a9-122">Remarks</span></span>  

 <span data-ttu-id="3f4a9-123">Это поведение службы предназначено для рабочих процессов, отправляющих сообщения в конечные точки служб.</span><span class="sxs-lookup"><span data-stu-id="3f4a9-123">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="3f4a9-124">Эти рабочие процессы обычно являются клиентскими, но также могут быть службами рабочих процессов, размещенными в <xref:System.ServiceModel.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="3f4a9-124">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="3f4a9-125">По умолчанию в рабочем процессе, размещенном в <xref:System.ServiceModel.WorkflowServiceHost>, кэш, используемый действиями обмена сообщениями <xref:System.ServiceModel.Activities.Send>, совместно используется всеми экземплярами рабочих процессов в <xref:System.ServiceModel.WorkflowServiceHost> (кэширование уровня узла).</span><span class="sxs-lookup"><span data-stu-id="3f4a9-125">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="3f4a9-126">Для клиентского рабочего процесса, не размещенного в <xref:System.ServiceModel.WorkflowServiceHost>, кэш доступен только для экземпляра рабочего процесса (кэширование уровня экземпляра).</span><span class="sxs-lookup"><span data-stu-id="3f4a9-126">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="3f4a9-127">По умолчанию кэширование отключено для всех действий отправки в рабочем процессе, в конфигурации которого определены конечные точки.</span><span class="sxs-lookup"><span data-stu-id="3f4a9-127">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="3f4a9-128">Дополнительные сведения о том, как изменить уровни общего доступа к кэшу по умолчанию и параметры кэша для фабрики каналов и кэша каналов, см. [в разделе изменение уровней общего доступа к кэшу для действий отправки](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span><span class="sxs-lookup"><span data-stu-id="3f4a9-128">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f4a9-129">Пример</span><span class="sxs-lookup"><span data-stu-id="3f4a9-129">Example</span></span>  

 <span data-ttu-id="3f4a9-130">В размещенной службе рабочего процесса в файле конфигурации приложения можно указать параметры кэша фабрики и канала.</span><span class="sxs-lookup"><span data-stu-id="3f4a9-130">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="3f4a9-131">Для этого необходимо создать поведение службы, содержащее параметры для кэша фабрики и канала, и добавить это поведение в службу.</span><span class="sxs-lookup"><span data-stu-id="3f4a9-131">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="3f4a9-132">В следующем примере показано содержимое файла конфигурации, содержащего `MyChannelCacheBehavior`  поведение службы с настройками кэша настраиваемой фабрики и канала.</span><span class="sxs-lookup"><span data-stu-id="3f4a9-132">The following example shows the contents of a configuration file that contains the `MyChannelCacheBehavior`  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="3f4a9-133">Это поведение службы добавляется в службу с помощью `behaviorConfiguration` атрибута.</span><span class="sxs-lookup"><span data-stu-id="3f4a9-133">This service behavior is added to the service through the `behaviorConfiguration` attribute.</span></span>  
  
```xml  
<configuration>
  <system.serviceModel>  
    <!-- List of other config sections here -->
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="MyChannelCacheBehavior">  
          <sendMessageChannelCache allowUnsafeCaching ="false" >  
            <!-- Control only the host level settings -->
            <factorySettings maxItemsInCache = "8" idleTimeout = "00:05:00" leaseTimeout="10:00:00" />  
            <channelSettings maxItemsInCache = "32" idleTimeout = "00:05:00" leaseTimeout="00:06:00" />  
          </sendMessageChannelCache>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service name="MyService" behaviorConfiguration="MyChannelCacheBehavior" />  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3f4a9-134">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3f4a9-134">See also</span></span>

- <xref:System.ServiceModel.Activities.SendMessageChannelCache>
- <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>
- <xref:System.ServiceModel.Activities.Send>
- [<span data-ttu-id="3f4a9-135">Изменение уровней совместного использования кэша для действий «Send»</span><span class="sxs-lookup"><span data-stu-id="3f4a9-135">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
