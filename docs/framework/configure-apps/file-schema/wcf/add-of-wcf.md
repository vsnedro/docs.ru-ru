---
title: <add> WCF
ms.date: 03/30/2017
ms.assetid: c196f6d7-77f6-4266-973c-305b2b4dd8a2
ms.openlocfilehash: b3b2883e711cea036ed8a61631e698a9d41fcadd
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172935"
---
# <a name="add-of-wcf"></a><span data-ttu-id="55f0a-102">\<add> WCF</span><span class="sxs-lookup"><span data-stu-id="55f0a-102">\<add> of WCF</span></span>

<span data-ttu-id="55f0a-103">Настройте участника отслеживания, который будет прослушивать записи отслеживания, прямо исходящие из среды выполнения, и обрабатывать их (в зависимости от настройки).</span><span class="sxs-lookup"><span data-stu-id="55f0a-103">Configure a tracking participant that listens to the tracking records being emitted from the runtime directly and process them in whatever way it was configured.</span></span> <span data-ttu-id="55f0a-104">Включает запись результата в определенном виде (например, в виде файла, консоли, ETW), обработку или сбор записей или любое другое требуемое сочетание.</span><span class="sxs-lookup"><span data-stu-id="55f0a-104">This includes writing to a specific output (e.g., file, Console, ETW), processing/aggregating the records, or any other combination that might be required.</span></span>  
  
 <span data-ttu-id="55f0a-105">Дополнительные сведения об участниках отслеживания и отслеживания рабочих процессов см. в статье участники [отслеживания рабочих процессов и трассировки](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) и [отслеживания](../../../windows-workflow-foundation/tracking-participants.md).</span><span class="sxs-lookup"><span data-stu-id="55f0a-105">For more information in workflow tracking and tracking participants, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Participants](../../../windows-workflow-foundation/tracking-participants.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<participants>**](participants-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="55f0a-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="55f0a-106">Syntax</span></span>  
  
```xml  
<tracking>
  <participants>
    <add name="String"
         profileName="String"
         type="String" />
  </participants>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="55f0a-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="55f0a-107">Attributes and Elements</span></span>  

 <span data-ttu-id="55f0a-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="55f0a-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="55f0a-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="55f0a-109">Attributes</span></span>  
  
|<span data-ttu-id="55f0a-110">Элемент</span><span class="sxs-lookup"><span data-stu-id="55f0a-110">Element</span></span>|<span data-ttu-id="55f0a-111">Описание</span><span class="sxs-lookup"><span data-stu-id="55f0a-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="55f0a-112">name</span><span class="sxs-lookup"><span data-stu-id="55f0a-112">name</span></span>|<span data-ttu-id="55f0a-113">Строка, задающая имя участника отслеживания.</span><span class="sxs-lookup"><span data-stu-id="55f0a-113">A string that specifies the name of a tracking participant.</span></span>|  
|<span data-ttu-id="55f0a-114">profileName</span><span class="sxs-lookup"><span data-stu-id="55f0a-114">profileName</span></span>|<span data-ttu-id="55f0a-115">Строка, задающая имя профиля отслеживания, который определяет, на какие записи отслеживания подписан участник.</span><span class="sxs-lookup"><span data-stu-id="55f0a-115">A string that specifies the name of the tracking profile which defines the tracking records the tracking participant has subscribed to.</span></span>|  
|<span data-ttu-id="55f0a-116">тип</span><span class="sxs-lookup"><span data-stu-id="55f0a-116">type</span></span>|<span data-ttu-id="55f0a-117">Строка, задающая тип участника отслеживания.</span><span class="sxs-lookup"><span data-stu-id="55f0a-117">A string that specifies the type of a tracking participant.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="55f0a-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="55f0a-118">Child Elements</span></span>  

 <span data-ttu-id="55f0a-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="55f0a-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="55f0a-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="55f0a-120">Parent Elements</span></span>  
  
|<span data-ttu-id="55f0a-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="55f0a-121">Element</span></span>|<span data-ttu-id="55f0a-122">Описание</span><span class="sxs-lookup"><span data-stu-id="55f0a-122">Description</span></span>|  
|-------------|-----------------|  
|[\<participants>](../windows-workflow-foundation/participants.md)|<span data-ttu-id="55f0a-123">Список участников отслеживания</span><span class="sxs-lookup"><span data-stu-id="55f0a-123">A list of tracking participants</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55f0a-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="55f0a-124">Remarks</span></span>  

 <span data-ttu-id="55f0a-125">Участники отслеживания используются для выдачи данных отслеживания из рабочего процесса и их сохранения на различные носители.</span><span class="sxs-lookup"><span data-stu-id="55f0a-125">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="55f0a-126">Подобным образом любая последующая обработка записей отслеживания также может быть выполнена внутри участника отслеживания.</span><span class="sxs-lookup"><span data-stu-id="55f0a-126">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
 <span data-ttu-id="55f0a-127">События отслеживания могут использоваться несколькими участниками отслеживания одновременно.</span><span class="sxs-lookup"><span data-stu-id="55f0a-127">Multiple tracking participants can consume the tracking events simultaneously.</span></span> <span data-ttu-id="55f0a-128">Каждый участник отслеживания может быть связан с отдельным профилем отслеживания.</span><span class="sxs-lookup"><span data-stu-id="55f0a-128">Each tracking participant can be associated with a different tracking profile.</span></span>  
  
 <span data-ttu-id="55f0a-129">Имеется стандартный участник отслеживания, который вносит записи отслеживания в сеанс ETW.</span><span class="sxs-lookup"><span data-stu-id="55f0a-129">A standard tracking participant is provided which writes the tracking records to an ETW session.</span></span> <span data-ttu-id="55f0a-130">Участник настраивается в службе рабочего процесса путем добавления в файл конфигурации поведения, связанного с отслеживанием.</span><span class="sxs-lookup"><span data-stu-id="55f0a-130">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="55f0a-131">Включив участника отслеживания ETW, можно будет просматривать записи отслеживания в обозревателе событий.</span><span class="sxs-lookup"><span data-stu-id="55f0a-131">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="55f0a-132">Если это не отвечает заданным требованиям, то можно создать своего собственного участника отслеживания.</span><span class="sxs-lookup"><span data-stu-id="55f0a-132">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="55f0a-133">Пример</span><span class="sxs-lookup"><span data-stu-id="55f0a-133">Example</span></span>  

 <span data-ttu-id="55f0a-134">В следующем примере конфигурации показан стандартный участник отслеживания ETW, который настраивается в файле Web.config.</span><span class="sxs-lookup"><span data-stu-id="55f0a-134">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="55f0a-135">Идентификатор поставщика, который используется участником отслеживания ETW для внесения записей отслеживания в ETW, задан в разделе `<diagnostics>`.</span><span class="sxs-lookup"><span data-stu-id="55f0a-135">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the `<diagnostics>` section.</span></span> <span data-ttu-id="55f0a-136">Участник отслеживания имеет связанный с ним профиль для указания записей отслеживания, на которые он подписан.</span><span class="sxs-lookup"><span data-stu-id="55f0a-136">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="55f0a-137">Это определяется атрибутом `profileName` элемента `<add>`.</span><span class="sxs-lookup"><span data-stu-id="55f0a-137">This is defined by the `profileName` attribute of the `<add>` element.</span></span> <span data-ttu-id="55f0a-138">После их определения участник отслеживания добавляется к поведению службы `<etwTracking>`.</span><span class="sxs-lookup"><span data-stu-id="55f0a-138">Once these are defined, the Tracking Participant is added to the `<etwTracking>` service behavior.</span></span> <span data-ttu-id="55f0a-139">При этом выбранные участники отслеживания добавляются в расширения экземпляра рабочего процесса, чтобы они начали получать записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="55f0a-139">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
```xml  
<configuration>
  <system.web>
    <compilation targetFrameworkMoniker=".NETFramework,Version=v4.0" />
  </system.web>
  <system.serviceModel>
    <diagnostics etwProviderId="52A3165D-4AD9-405C-B1E8-7D9A257EAC9F" />
    <tracking>
      <participants>
        <add name="EtwTrackingParticipant"
             type="System.Activities.Tracking.EtwTrackingParticipant, System.Activities, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
             profileName="HealthMonitoring_Tracking_Profile" />
      </participants>
    </tracking>
    <behaviors>
      <serviceBehaviors>
        <behavior>
          <etwTracking profileName="Sample Tracking Profile" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="55f0a-140">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="55f0a-140">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="55f0a-141">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="55f0a-141">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="55f0a-142">Участники отслеживания</span><span class="sxs-lookup"><span data-stu-id="55f0a-142">Tracking Participants</span></span>](../../../windows-workflow-foundation/tracking-participants.md)
