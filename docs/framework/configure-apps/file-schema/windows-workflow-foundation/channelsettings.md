---
title: <channelSettings>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 94a4457f-f43f-458d-a47e-2d11103ee75e
ms.openlocfilehash: f6a57e2cc1e7c5e114fd38ee3534ab7c4e629b36
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152278"
---
# \<channelSettings>
<span data-ttu-id="049b1-101">Указывает параметры кэша канала.</span><span class="sxs-lookup"><span data-stu-id="049b1-101">Specifies the settings of the channel cache.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<sendMessageChannelCache>**](sendmessagechannelcache.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<channelSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="049b1-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="049b1-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <sendMessageChannelCache allowUnsafeCaching="Boolean">
        <channelSettings idleTimeout="TimeSpan"
                         leaseTimeout="TimeSpan"
                         maxItemsInCache="Integer" />
      </sendMessageChannelCache>
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="049b1-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="049b1-103">Attributes and Elements</span></span>  
 <span data-ttu-id="049b1-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="049b1-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="049b1-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="049b1-105">Attributes</span></span>  
  
|<span data-ttu-id="049b1-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="049b1-106">Attribute</span></span>|<span data-ttu-id="049b1-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="049b1-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="049b1-108">idleTimeout</span><span class="sxs-lookup"><span data-stu-id="049b1-108">idleTimeout</span></span>|<span data-ttu-id="049b1-109">Значение TimeSpan, указывающее максимальный интервал времени, в течение которого объект может оставаться неактивным в кэше, прежде чем будет удален.</span><span class="sxs-lookup"><span data-stu-id="049b1-109">A TimeSpan value that specifies the maximum interval of time for which the object can remain idle in the cache before being disposed.</span></span>|  
|<span data-ttu-id="049b1-110">leaseTimeout</span><span class="sxs-lookup"><span data-stu-id="049b1-110">leaseTimeout</span></span>|<span data-ttu-id="049b1-111">Значение TimeSpan, указывающее интервал времени, по истечении которого объект удаляется из кэша.</span><span class="sxs-lookup"><span data-stu-id="049b1-111">A TimeSpan value that specifies  the interval of time after which an object is removed from the cache.</span></span>|  
|<span data-ttu-id="049b1-112">maxItemsInCache</span><span class="sxs-lookup"><span data-stu-id="049b1-112">maxItemsInCache</span></span>|<span data-ttu-id="049b1-113">Целое число, указывающее максимальное количество объектов, которые могут находиться в кэше.</span><span class="sxs-lookup"><span data-stu-id="049b1-113">An integer that specifies the maximum number of objects that can be in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="049b1-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="049b1-114">Child Elements</span></span>  
 <span data-ttu-id="049b1-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="049b1-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="049b1-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="049b1-116">Parent Elements</span></span>  
  
|<span data-ttu-id="049b1-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="049b1-117">Element</span></span>|<span data-ttu-id="049b1-118">Описание</span><span class="sxs-lookup"><span data-stu-id="049b1-118">Description</span></span>|  
|-------------|-----------------|  
|[\<sendMessageChannelCache>](sendmessagechannelcache.md)|<span data-ttu-id="049b1-119">Поведение службы, которое позволяет изменить уровни доступа к кэшу, параметры кэша фабрики канала и параметры кэша канала для рабочих процессов, которые отправляют сообщения в конечные точки служб с использованием действий отправки сообщений.</span><span class="sxs-lookup"><span data-stu-id="049b1-119">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="049b1-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="049b1-120">Remarks</span></span>  
 <span data-ttu-id="049b1-121">Это поведение службы предназначено для рабочих процессов, отправляющих сообщения в конечные точки служб.</span><span class="sxs-lookup"><span data-stu-id="049b1-121">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="049b1-122">Эти рабочие процессы обычно являются клиентскими, но также могут быть службами рабочих процессов, размещенными в <xref:System.ServiceModel.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="049b1-122">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="049b1-123">По умолчанию в рабочем процессе, размещенном в <xref:System.ServiceModel.WorkflowServiceHost>, кэш, используемый действиями обмена сообщениями <xref:System.ServiceModel.Activities.Send>, совместно используется всеми экземплярами рабочих процессов в <xref:System.ServiceModel.WorkflowServiceHost> (кэширование уровня узла).</span><span class="sxs-lookup"><span data-stu-id="049b1-123">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="049b1-124">Для клиентского рабочего процесса, не размещенного в <xref:System.ServiceModel.WorkflowServiceHost>, кэш доступен только для экземпляра рабочего процесса (кэширование уровня экземпляра).</span><span class="sxs-lookup"><span data-stu-id="049b1-124">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="049b1-125">По умолчанию кэширование отключено для всех действий отправки в рабочем процессе, в конфигурации которого определены конечные точки.</span><span class="sxs-lookup"><span data-stu-id="049b1-125">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="049b1-126">Дополнительные сведения о том, как изменить уровни общего доступа к кэшу по умолчанию и параметры кэша для фабрики каналов и кэша каналов, см. [в разделе изменение уровней общего доступа к кэшу для действий отправки](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span><span class="sxs-lookup"><span data-stu-id="049b1-126">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="049b1-127">Пример</span><span class="sxs-lookup"><span data-stu-id="049b1-127">Example</span></span>  
 <span data-ttu-id="049b1-128">В размещенной службе рабочего процесса в файле конфигурации приложения можно указать параметры кэша фабрики и канала.</span><span class="sxs-lookup"><span data-stu-id="049b1-128">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="049b1-129">Для этого необходимо создать поведение службы, содержащее параметры для кэша фабрики и канала, и добавить это поведение в службу.</span><span class="sxs-lookup"><span data-stu-id="049b1-129">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="049b1-130">В следующем примере показано содержимое файла конфигурации, содержащего `MyChannelCacheBehavior` поведение службы с настройками кэша настраиваемой фабрики и канала.</span><span class="sxs-lookup"><span data-stu-id="049b1-130">The following example shows the contents of a configuration file that contains the `MyChannelCacheBehavior`  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="049b1-131">Это поведение службы добавляется в службу с помощью `behaviorConfiguration` атрибута.</span><span class="sxs-lookup"><span data-stu-id="049b1-131">This service behavior is added to the service through the `behaviorConfiguration` attribute.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="049b1-132">См. также</span><span class="sxs-lookup"><span data-stu-id="049b1-132">See also</span></span>

- <xref:System.ServiceModel.Activities.SendMessageChannelCache>
- <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>
- <xref:System.ServiceModel.Activities.Send>
- <xref:System.ServiceModel.Activities.ChannelCacheSettings>
- [<span data-ttu-id="049b1-133">Изменение уровней совместного использования кэша для действий «Send»</span><span class="sxs-lookup"><span data-stu-id="049b1-133">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
