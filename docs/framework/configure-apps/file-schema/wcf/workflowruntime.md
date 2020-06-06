---
title: <workflowRuntime>
ms.date: 03/30/2017
ms.assetid: 304c70fa-78d1-4d0f-b89f-0ca23d734c6f
ms.openlocfilehash: d12656b77fa219080382603fd04a542d2fa9064a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399086"
---
# \<workflowRuntime>
<span data-ttu-id="19c78-101">Задает параметры экземпляра <xref:System.Workflow.Runtime.WorkflowRuntime> для размещения служб Windows Communication Foundation (WCF) на основе рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="19c78-101">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowRuntime>**  
  
## <a name="syntax"></a><span data-ttu-id="19c78-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="19c78-102">Syntax</span></span>  
  
```xml  
<workflowRuntime cachedInstanceExpiration="TimeSpan"
                 enablePerformanceCounters="Boolean"
                 name="String"
                 validateOnCreate="Boolean">
  <commonParameters>
    <add name="String"
         value="String" />
  </commonParameters>
  <services>
    <add type="String" />
  </services>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="19c78-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="19c78-103">Attributes and Elements</span></span>  
 <span data-ttu-id="19c78-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="19c78-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="19c78-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="19c78-105">Attributes</span></span>  
  
|<span data-ttu-id="19c78-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="19c78-106">Attribute</span></span>|<span data-ttu-id="19c78-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="19c78-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="19c78-108">cachedInstanceExpiration</span><span class="sxs-lookup"><span data-stu-id="19c78-108">cachedInstanceExpiration</span></span>|<span data-ttu-id="19c78-109">Необязательное значение <xref:System.TimeSpan>, определяющее максимальный период времени, в течение которого экземпляр рабочего процесса может оставаться в памяти в неактивном состоянии до принудительной выгрузки или прекращения.</span><span class="sxs-lookup"><span data-stu-id="19c78-109">An optional <xref:System.TimeSpan> value that specifies the maximum duration a workflow instance can stay in-memory in idle state before it is forcefully unloaded or aborted.</span></span> <span data-ttu-id="19c78-110">Если среда выполнения рабочего процесса имеет параметр `PersistenceService`, выполняющий unloadOnIdle, этот атрибут игнорируется.</span><span class="sxs-lookup"><span data-stu-id="19c78-110">If the workflowruntime has `PersistenceService` which performs unloadOnIdle, this attribute is ignored.</span></span>|  
|<span data-ttu-id="19c78-111">enablePerformanceCounters</span><span class="sxs-lookup"><span data-stu-id="19c78-111">enablePerformanceCounters</span></span>|<span data-ttu-id="19c78-112">Необязательное логическое значение, определяющее, включены ли счетчики производительности.</span><span class="sxs-lookup"><span data-stu-id="19c78-112">An optional Boolean value that specifies whether performance counters are enabled.</span></span> <span data-ttu-id="19c78-113">Счетчики производительности предоставляют статистические данные о различных рабочих процессах, но они могут вызывать снижение производительности при запуске подсистемы среды выполнения рабочего процесса и при выполнении экземпляров рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="19c78-113">Performance counters provide information on various workflow-related statistics, but they cause a performance penalty when the workflow runtime engine starts, and when workflow instances are running.</span></span> <span data-ttu-id="19c78-114">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="19c78-114">The default value is `true`.</span></span>|  
|<span data-ttu-id="19c78-115">name</span><span class="sxs-lookup"><span data-stu-id="19c78-115">name</span></span>|<span data-ttu-id="19c78-116">Строка, содержащая имя подсистемы среды выполнения рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="19c78-116">A string containing the name of the workflow runtime engine.</span></span> <span data-ttu-id="19c78-117">Имя используется в выходных данных для различения данной среды выполнения от других сред выполнения, которые могут выполняться в системе, например в счетчиках производительности.</span><span class="sxs-lookup"><span data-stu-id="19c78-117">The name is used in output to distinguish this runtime from other runtimes that may be running on the system, for example, in performance counters.</span></span><br /><br /> <span data-ttu-id="19c78-118">Значением по умолчанию является пустая строка.</span><span class="sxs-lookup"><span data-stu-id="19c78-118">The default is an empty string.</span></span>|  
|<span data-ttu-id="19c78-119">validateOnCreate</span><span class="sxs-lookup"><span data-stu-id="19c78-119">validateOnCreate</span></span>|<span data-ttu-id="19c78-120">Необязательное логическое значение, указывающее, будет ли выполняться проверка определения рабочего процесса при открытии WorkflowServiceHost.</span><span class="sxs-lookup"><span data-stu-id="19c78-120">An optional Boolean value that specifies whether validation of workflow definition will occur when the WorkflowServiceHost is opened.</span></span>  <span data-ttu-id="19c78-121">Если этому атрибуту задано значение `true`, проверка рабочего процесса выполняется при каждом вызове `WorkflowServiceHost.Open`.</span><span class="sxs-lookup"><span data-stu-id="19c78-121">When this attribute is set to `true`, the workflow validation is executed every time `WorkflowServiceHost.Open` is called.</span></span> <span data-ttu-id="19c78-122">В случае обнаружения ошибок проверки возникает ошибка <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException>.</span><span class="sxs-lookup"><span data-stu-id="19c78-122">If validation errors are found, a <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException> error is thrown.</span></span><br /><br /> <span data-ttu-id="19c78-123">Если это свойство имеет значение `false`, проверка определения рабочего процесса не выполняется.</span><span class="sxs-lookup"><span data-stu-id="19c78-123">When this property is set to `false`, no Workflow definition validation will happen.</span></span><br /><br /> <span data-ttu-id="19c78-124">Значение этого свойства по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="19c78-124">The default value for this property is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="19c78-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="19c78-125">Child Elements</span></span>  
  
|<span data-ttu-id="19c78-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="19c78-126">Element</span></span>|<span data-ttu-id="19c78-127">Описание</span><span class="sxs-lookup"><span data-stu-id="19c78-127">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="19c78-128">commonParameters</span><span class="sxs-lookup"><span data-stu-id="19c78-128">commonParameters</span></span>|<span data-ttu-id="19c78-129">Коллекция общих параметров, используемых службой.</span><span class="sxs-lookup"><span data-stu-id="19c78-129">A collection of common parameters used by services.</span></span> <span data-ttu-id="19c78-130">Эта коллекция, как правило, включает строку подключения базы данных, которая может совместно использоваться постоянными службами.</span><span class="sxs-lookup"><span data-stu-id="19c78-130">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
|<span data-ttu-id="19c78-131">services;</span><span class="sxs-lookup"><span data-stu-id="19c78-131">services</span></span>|<span data-ttu-id="19c78-132">Коллекция служб, добавляемая в механизм <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="19c78-132">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="19c78-133">Элементы имеют тип <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="19c78-133">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="19c78-134">Службы, указанные в коллекции, инициализируются механизмом среды выполнения рабочих процессов и добавляются в службы при вызове соответствующего конструктора <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="19c78-134">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="19c78-135">Таким образом, службы, указанные в коллекции, должны отвечать определенным правилам в отношении сигнатур конструкторов.</span><span class="sxs-lookup"><span data-stu-id="19c78-135">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="19c78-136">Дополнительные сведения см. в разделе <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="19c78-136">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="19c78-137">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="19c78-137">Parent Elements</span></span>  
  
|<span data-ttu-id="19c78-138">Элемент</span><span class="sxs-lookup"><span data-stu-id="19c78-138">Element</span></span>|<span data-ttu-id="19c78-139">Описание</span><span class="sxs-lookup"><span data-stu-id="19c78-139">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="19c78-140">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="19c78-140">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19c78-141">Примечания</span><span class="sxs-lookup"><span data-stu-id="19c78-141">Remarks</span></span>  
 <span data-ttu-id="19c78-142">Дополнительные сведения об использовании файла конфигурации для управления поведением <xref:System.Workflow.Runtime.WorkflowRuntime> объекта Windows Workflow Foundation ведущего приложения см. в разделе [файлы конфигурации рабочего процесса](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="19c78-142">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="19c78-143">Пример</span><span class="sxs-lookup"><span data-stu-id="19c78-143">Example</span></span>  
  
```xml  
<serviceBehaviors>
   <behavior name="ServiceBehavior">
      <workflowRuntime name="WorkflowServiceHostRuntime"
                       validateOnCreate="true"
                       enablePerformanceCounters="true">
         <commonParameters>
            <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
            <add name="EnableRetries" value="True" />
         </commonParameters>
         <services>
             <add type="NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common.TestPersistenceService.FilePersistenceService, NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common"/>
         </services>
      </workflowRuntime>
   </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="19c78-144">См. также</span><span class="sxs-lookup"><span data-stu-id="19c78-144">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <span data-ttu-id="19c78-145">[Файлы конфигурации рабочих процессов](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="19c78-145">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
