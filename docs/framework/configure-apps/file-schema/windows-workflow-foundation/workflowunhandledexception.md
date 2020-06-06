---
title: <workflowUnhandledException>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: 29b6d8982e712a0fa595b3103803f1795adea892
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398565"
---
# \<workflowUnhandledException>
<span data-ttu-id="56661-101">Поведение службы, позволяющее задать действие, которое будет выполнено при появлении необработанного исключения в службе рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="56661-101">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowUnhandledException>**  
  
## <a name="syntax"></a><span data-ttu-id="56661-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="56661-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56661-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="56661-103">Attributes and Elements</span></span>  
 <span data-ttu-id="56661-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="56661-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56661-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="56661-105">Attributes</span></span>  
  
|<span data-ttu-id="56661-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="56661-106">Attribute</span></span>|<span data-ttu-id="56661-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="56661-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="56661-108">action</span><span class="sxs-lookup"><span data-stu-id="56661-108">action</span></span>|<span data-ttu-id="56661-109">Строка, указывающая действие, которое должно быть предпринято при возникновении необработанного исключения.</span><span class="sxs-lookup"><span data-stu-id="56661-109">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="56661-110">Это атрибут типа <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction>.</span><span class="sxs-lookup"><span data-stu-id="56661-110">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="56661-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="56661-111">Child Elements</span></span>  
 <span data-ttu-id="56661-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="56661-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="56661-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="56661-113">Parent Elements</span></span>  
  
|<span data-ttu-id="56661-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="56661-114">Element</span></span>|<span data-ttu-id="56661-115">Описание</span><span class="sxs-lookup"><span data-stu-id="56661-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="56661-116">\<behavior>окна\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="56661-116">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="56661-117">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="56661-117">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="56661-118">См. также</span><span class="sxs-lookup"><span data-stu-id="56661-118">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
