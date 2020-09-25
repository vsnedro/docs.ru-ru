---
title: <etwTracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: cb45c82e-6ea1-4c4d-924c-118a25ae1f35
ms.openlocfilehash: e1048cf3a9f56e4177f3ffe2dcd561a1babadacd
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198773"
---
# \<etwTracking>

<span data-ttu-id="7740a-101">Поведение службы позволяет ей использовать отслеживание ETW совместно с <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span><span class="sxs-lookup"><span data-stu-id="7740a-101">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<etwTracking>**  
  
## <a name="syntax"></a><span data-ttu-id="7740a-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7740a-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <etwTracking profileName="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7740a-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7740a-103">Attributes and Elements</span></span>  

 <span data-ttu-id="7740a-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7740a-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7740a-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7740a-105">Attributes</span></span>  
  
|<span data-ttu-id="7740a-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7740a-106">Attribute</span></span>|<span data-ttu-id="7740a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="7740a-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7740a-108">profileName</span><span class="sxs-lookup"><span data-stu-id="7740a-108">profileName</span></span>|<span data-ttu-id="7740a-109">Строка, указывающая имя профиля отслеживания, связанного с этим поведением.</span><span class="sxs-lookup"><span data-stu-id="7740a-109">A string that specifies the name of the tracking profile associated with this behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7740a-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7740a-110">Child Elements</span></span>  

 <span data-ttu-id="7740a-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7740a-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7740a-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7740a-112">Parent Elements</span></span>  
  
|<span data-ttu-id="7740a-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="7740a-113">Element</span></span>|<span data-ttu-id="7740a-114">Описание</span><span class="sxs-lookup"><span data-stu-id="7740a-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7740a-115">\<behavior> из \<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="7740a-115">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="7740a-116">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="7740a-116">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7740a-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="7740a-117">Remarks</span></span>  

 <span data-ttu-id="7740a-118">Если добавить этот элемент к конфигурации поведения службы, то для службы рабочего процесса будет настроен участник отслеживания.</span><span class="sxs-lookup"><span data-stu-id="7740a-118">When added to the service’s behavior configuration, this configuration element configures a tracking participant on a workflow service.</span></span>  
  
 <span data-ttu-id="7740a-119">Участники отслеживания используются для выдачи данных отслеживания из рабочего процесса и их сохранения на различные носители.</span><span class="sxs-lookup"><span data-stu-id="7740a-119">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="7740a-120">Подобным образом любая последующая обработка записей отслеживания также может быть выполнена внутри участника отслеживания.</span><span class="sxs-lookup"><span data-stu-id="7740a-120">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7740a-121">Пример</span><span class="sxs-lookup"><span data-stu-id="7740a-121">Example</span></span>  

 <span data-ttu-id="7740a-122">В следующем примере конфигурации показан стандартный участник отслеживания ETW, который настраивается в файле Web.config.</span><span class="sxs-lookup"><span data-stu-id="7740a-122">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="7740a-123">Идентификатор поставщика, используемый участником отслеживания ETW для записи записей отслеживания в ETW, определяется в **\<diagnostics>** разделе.</span><span class="sxs-lookup"><span data-stu-id="7740a-123">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="7740a-124">Участник отслеживания имеет связанный с ним профиль для указания записей отслеживания, на которые он подписан.</span><span class="sxs-lookup"><span data-stu-id="7740a-124">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="7740a-125">Это определяется атрибутом **filename** **\<add>** элемента.</span><span class="sxs-lookup"><span data-stu-id="7740a-125">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="7740a-126">После того как они определены, участник отслеживания добавляется к **\<etwTracking>** поведению службы.</span><span class="sxs-lookup"><span data-stu-id="7740a-126">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="7740a-127">При этом выбранные участники отслеживания добавляются в расширения экземпляра рабочего процесса, чтобы они начали получать записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="7740a-127">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
```xml  
<configuration>
  <system.web>
    <compilation targetFrameworkMoniker=".NETFramework,Version=v4.0"/>
  </system.web>
  <system.serviceModel>
    <diagnostics etwProviderId="52A3165D-4AD9-405C-B1E8-7D9A257EAC9F" />
    <tracking>
      <participants>
        <add name="EtwTrackingParticipant"
             type="System.Activities.Tracking.EtwTrackingParticipant, System.Activities, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
             profileName="HealthMonitoring_Tracking_Profile"/>
      </participants>
    </tracking>
    <behaviors>
      <serviceBehaviors>
        <behavior>
          <etwTracking profileName="Sample Tracking Profile"/>  
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7740a-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7740a-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="7740a-129">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="7740a-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="7740a-130">Участники отслеживания</span><span class="sxs-lookup"><span data-stu-id="7740a-130">Tracking Participants</span></span>](../../../windows-workflow-foundation/tracking-participants.md)
