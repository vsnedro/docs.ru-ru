---
title: <add> из <services>
ms.date: 03/30/2017
ms.assetid: 6bdc4590-aa9c-4ec8-9345-879d780cd141
ms.openlocfilehash: 26d43460f225cb57946aca80e3d1e3fde2ea1100
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557714"
---
# <a name="add-of-services"></a><span data-ttu-id="afdbd-102">\<add> из \<services></span><span class="sxs-lookup"><span data-stu-id="afdbd-102">\<add> of \<services></span></span>
<span data-ttu-id="afdbd-103">Задает параметры экземпляра <xref:System.Workflow.Runtime.WorkflowRuntime> для размещения служб Windows Communication Foundation (WCF) на основе рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="afdbd-103">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="afdbd-104">Это элемент типа <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="afdbd-104">This element is of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowRuntime>**](workflowruntime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services-of-workflowruntime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="afdbd-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="afdbd-105">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <services>
    <add type="String" />
  </services>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="afdbd-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="afdbd-106">Attributes and Elements</span></span>  
 <span data-ttu-id="afdbd-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="afdbd-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="afdbd-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="afdbd-108">Attributes</span></span>  
  
|<span data-ttu-id="afdbd-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="afdbd-109">Attribute</span></span>|<span data-ttu-id="afdbd-110">Описание</span><span class="sxs-lookup"><span data-stu-id="afdbd-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="afdbd-111">type</span><span class="sxs-lookup"><span data-stu-id="afdbd-111">type</span></span>|<span data-ttu-id="afdbd-112">Строка, задающая имя типа с указанием сборки для службы, которую необходимо инициализировать.</span><span class="sxs-lookup"><span data-stu-id="afdbd-112">A string that specifies the assembly-qualified type name of the service to be initialized.</span></span> <span data-ttu-id="afdbd-113">Заданная служба должна соответствовать определенным правилам, связанным с сигнатурами их конструкторов.</span><span class="sxs-lookup"><span data-stu-id="afdbd-113">The service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="afdbd-114">Дополнительные сведения см. в разделе <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="afdbd-114">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="afdbd-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="afdbd-115">Child Elements</span></span>  
 <span data-ttu-id="afdbd-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="afdbd-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="afdbd-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="afdbd-117">Parent Elements</span></span>  
  
|<span data-ttu-id="afdbd-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="afdbd-118">Element</span></span>|<span data-ttu-id="afdbd-119">Описание</span><span class="sxs-lookup"><span data-stu-id="afdbd-119">Description</span></span>|  
|-------------|-----------------|  
|[\<services>](services-of-workflowruntime.md)|<span data-ttu-id="afdbd-120">Коллекция служб, добавляемая в механизм <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="afdbd-120">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="afdbd-121">Элементы имеют тип <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="afdbd-121">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="afdbd-122">Службы, указанные в коллекции, инициализируются механизмом среды выполнения рабочих процессов и добавляются в службы при вызове соответствующего конструктора <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="afdbd-122">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="afdbd-123">Таким образом, службы, указанные в коллекции, должны отвечать определенным правилам в отношении сигнатур конструкторов.</span><span class="sxs-lookup"><span data-stu-id="afdbd-123">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="afdbd-124">Дополнительные сведения см. в разделе <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="afdbd-124">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="afdbd-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="afdbd-125">Remarks</span></span>  
 <span data-ttu-id="afdbd-126">Служба, указанная в данном элементе, инициализируется механизмом среды выполнения рабочих процессов и добавляется в службы при вызове соответствующего конструктора <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="afdbd-126">The service specified in this element will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="afdbd-127">Поэтому заданная служба должна соответствовать определенным правилам, относящимся к сигнатурам конструкторов.</span><span class="sxs-lookup"><span data-stu-id="afdbd-127">Therefore, the service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="afdbd-128">Дополнительные сведения см. в разделе <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="afdbd-128">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>  
  
## <a name="example"></a><span data-ttu-id="afdbd-129">Пример</span><span class="sxs-lookup"><span data-stu-id="afdbd-129">Example</span></span>  
  
```xml  
<serviceBehaviors>
  <behavior name="ServiceBehavior">
    <workflowRuntime name="WorkflowServiceHostRuntime"
                     validateOnCreate="true"
                     enablePerformanceCounters="true">
      <services>
        <add type="NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common.TestPersistenceService.FilePersistenceService, NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common" />
      </services>
    </workflowRuntime>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="afdbd-130">См. также</span><span class="sxs-lookup"><span data-stu-id="afdbd-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <span data-ttu-id="afdbd-131">[Файлы конфигурации рабочих процессов](/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="afdbd-131">[Workflow Configuration Files](/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
