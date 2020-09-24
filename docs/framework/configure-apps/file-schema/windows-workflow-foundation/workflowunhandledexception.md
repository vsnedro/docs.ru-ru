---
title: <workflowUnhandledException>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: 6e3993e43aac746f380a30341fe4ebffcd257c5f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148520"
---
# \<workflowUnhandledException>

<span data-ttu-id="c4090-101">Поведение службы, позволяющее задать действие, которое будет выполнено при появлении необработанного исключения в службе рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="c4090-101">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowUnhandledException>**  
  
## <a name="syntax"></a><span data-ttu-id="c4090-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c4090-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c4090-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c4090-103">Attributes and Elements</span></span>  

 <span data-ttu-id="c4090-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c4090-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c4090-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c4090-105">Attributes</span></span>  
  
|<span data-ttu-id="c4090-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c4090-106">Attribute</span></span>|<span data-ttu-id="c4090-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c4090-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c4090-108">action</span><span class="sxs-lookup"><span data-stu-id="c4090-108">action</span></span>|<span data-ttu-id="c4090-109">Строка, указывающая действие, которое должно быть предпринято при возникновении необработанного исключения.</span><span class="sxs-lookup"><span data-stu-id="c4090-109">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="c4090-110">Это атрибут типа <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction>.</span><span class="sxs-lookup"><span data-stu-id="c4090-110">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c4090-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c4090-111">Child Elements</span></span>  

 <span data-ttu-id="c4090-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c4090-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c4090-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c4090-113">Parent Elements</span></span>  
  
|<span data-ttu-id="c4090-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="c4090-114">Element</span></span>|<span data-ttu-id="c4090-115">Описание</span><span class="sxs-lookup"><span data-stu-id="c4090-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c4090-116">\<behavior> из \<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="c4090-116">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="c4090-117">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="c4090-117">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c4090-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c4090-118">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
