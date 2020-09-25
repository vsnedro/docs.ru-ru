---
title: <behavior> из <serviceBehaviors> рабочего процесса
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a4b718a-1b40-4957-935a-f6122819ab3c
ms.openlocfilehash: 14c528746963a3078e0ab377d095414d2fca0dbe
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189621"
---
# <a name="behavior-of-servicebehaviors-of-workflow"></a><span data-ttu-id="c433c-102">\<behavior> из \<serviceBehaviors> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="c433c-102">\<behavior> of \<serviceBehaviors> of workflow</span></span>

<span data-ttu-id="c433c-103">Элемент **Behavior** содержит коллекцию параметров для поведения службы.</span><span class="sxs-lookup"><span data-stu-id="c433c-103">The **behavior** element contains a collection of settings for the behavior of a service.</span></span> <span data-ttu-id="c433c-104">Каждое поведение индексируется по **имени**.</span><span class="sxs-lookup"><span data-stu-id="c433c-104">Each behavior is indexed by its **name**.</span></span> <span data-ttu-id="c433c-105">Службы могут ссылаться на каждое поведение с помощью этого имени, используя атрибут **behaviorConfiguration** [\<endpoint>](../wcf/endpoint-element.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="c433c-105">Services can link to each behavior through this name using the **behaviorConfiguration** attribute of the [\<endpoint>](../wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="c433c-106">Это позволяет конечным точкам иметь общие конфигурации поведений без переопределения параметров.</span><span class="sxs-lookup"><span data-stu-id="c433c-106">This allows endpoints to share common behavior configurations without redefining the settings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<behavior>**  
  
## <a name="syntax"></a><span data-ttu-id="c433c-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c433c-107">Syntax</span></span>  
  
```xml  
<system.ServiceModel>  
  <behaviors>  
    <serviceBehaviors>  
      <behavior name="String">
        <bufferReceive maxPendingMessagesPerChannel="Integer" />
        <etwTracking profileName="String" />
        <sendMessageChannelCache allowUnsafeCaching="Boolean">
          <channelSettings idleTimeout="TimeSpan"
                           leaseTimeout="TimeSpan"
                           maxItemsInCache="Integer" />
          <factorySettings idleTimeout="TimeSpan"
                           leaseTimeout="TimeSpan"
                           maxItemsInCache="Integer" />
        </sendMessageChannelCache>
        <sqlWorkflowInstanceStore connectionStringName="String"
                                  hostLockRenewalPeriod="TimeSpan"
                                  instanceCompletionAction="DeleteNothing/DeleteAll"
                                  instanceEncodingAction="None/GZip"
                                  instanceLockedExceptionAction="NoRetry/BasicRetry/AggressiveRetry"
                                  runnableInstancesDetectionPeriod="TimeSpan" />
        <workflowIdle timeToPersist="TimeSpan"
                      timeToUnload="TimeSpan" />
        <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
      </behavior>
    </serviceBehaviors>  
  </behaviors>  
</system.ServiceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c433c-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c433c-108">Attributes and Elements</span></span>  

 <span data-ttu-id="c433c-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c433c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c433c-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c433c-110">Attributes</span></span>  
  
|<span data-ttu-id="c433c-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c433c-111">Attribute</span></span>|<span data-ttu-id="c433c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="c433c-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c433c-113">name</span><span class="sxs-lookup"><span data-stu-id="c433c-113">name</span></span>|<span data-ttu-id="c433c-114">Уникальная строка, содержащая имя конфигурации поведения.</span><span class="sxs-lookup"><span data-stu-id="c433c-114">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="c433c-115">Это значение является заданной пользователем строкой, которая должна быть уникальной, поскольку она действует как строка идентификации для элемента.</span><span class="sxs-lookup"><span data-stu-id="c433c-115">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c433c-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c433c-116">Child Elements</span></span>  
  
|<span data-ttu-id="c433c-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="c433c-117">Element</span></span>|<span data-ttu-id="c433c-118">Описание</span><span class="sxs-lookup"><span data-stu-id="c433c-118">Description</span></span>|  
|-------------|-----------------|  
|[\<bufferReceive>](bufferreceive.md)|<span data-ttu-id="c433c-119">Поведение, позволяющее службе рабочего процесса использовать обработку буфера получения, благодаря чему можно обрабатывать неупорядоченные сообщения.</span><span class="sxs-lookup"><span data-stu-id="c433c-119">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>|  
|[\<routing>](../wcf/routing-of-servicebehavior.md)|<span data-ttu-id="c433c-120">Поведение службы позволяет ей использовать отслеживание ETW совместно с <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span><span class="sxs-lookup"><span data-stu-id="c433c-120">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>|  
|[\<sendMessageChannelCache>](sendmessagechannelcache.md)|<span data-ttu-id="c433c-121">Поведение службы, которое позволяет изменить уровни доступа к кэшу, параметры кэша фабрики канала и параметры кэша канала для рабочих процессов, которые отправляют сообщения в конечные точки служб с использованием действий отправки сообщений.</span><span class="sxs-lookup"><span data-stu-id="c433c-121">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
|[\<sqlWorkflowInstanceStore>](sqlworkflowinstancestore.md)|<span data-ttu-id="c433c-122">Поведение службы, позволяющее настроить функцию <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, поддерживающую сохранение сведений о состоянии для экземпляров службы рабочего процесса в базу данных SQL Server 2005 или SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="c433c-122">A service behavior that allows you to configure the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> feature, which supports persisting state information for workflow service instances into an SQL Server 2005 or SQL Server 2008 database.</span></span>|  
|[\<workflowIdle>](workflowidle.md)|<span data-ttu-id="c433c-123">Поведение службы, управляющее выгрузкой и сохранением простаивающих экземпляров рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="c433c-123">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>|  
|[\<workflowInstanceManagement>](workflowinstancemanagement.md)|<span data-ttu-id="c433c-124">Поведение службы, которое позволяет указать параметры, управляющие выполнением экземпляров рабочего процесса, включая сохраняемость, необработанное поведение исключения и неактивное поведение.</span><span class="sxs-lookup"><span data-stu-id="c433c-124">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>|  
|[\<workflowUnhandledException>](workflowunhandledexception.md)|<span data-ttu-id="c433c-125">Поведение службы, позволяющее задать действие, которое будет выполнено при появлении необработанного исключения в службе рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="c433c-125">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c433c-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c433c-126">Parent Elements</span></span>  
  
|<span data-ttu-id="c433c-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="c433c-127">Element</span></span>|<span data-ttu-id="c433c-128">Описание</span><span class="sxs-lookup"><span data-stu-id="c433c-128">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceBehaviors>](servicebehaviors-of-workflow.md)|<span data-ttu-id="c433c-129">Коллекция элементов поведений службы.</span><span class="sxs-lookup"><span data-stu-id="c433c-129">A collection of service behavior elements.</span></span>|
