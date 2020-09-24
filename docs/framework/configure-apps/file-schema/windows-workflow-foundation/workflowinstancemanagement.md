---
title: <workflowInstanceManagement>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
ms.openlocfilehash: 532d4c31a582b2b0cd90f6f42b20e00790f9ab02
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148663"
---
# \<workflowInstanceManagement>

<span data-ttu-id="b7d90-101">Поведение службы, которое позволяет указать параметры, управляющие выполнением экземпляров рабочего процесса, включая сохраняемость, необработанное поведение исключения и неактивное поведение.</span><span class="sxs-lookup"><span data-stu-id="b7d90-101">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceManagement>**  
  
## <a name="syntax"></a><span data-ttu-id="b7d90-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b7d90-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b7d90-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b7d90-103">Attributes and Elements</span></span>  

 <span data-ttu-id="b7d90-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b7d90-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b7d90-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b7d90-105">Attributes</span></span>  
  
|<span data-ttu-id="b7d90-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b7d90-106">Attribute</span></span>|<span data-ttu-id="b7d90-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b7d90-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b7d90-108">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="b7d90-108">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="b7d90-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b7d90-109">Child Elements</span></span>  

 <span data-ttu-id="b7d90-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b7d90-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b7d90-111">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b7d90-111">Parent Elements</span></span>  
  
|<span data-ttu-id="b7d90-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="b7d90-112">Element</span></span>|<span data-ttu-id="b7d90-113">Описание</span><span class="sxs-lookup"><span data-stu-id="b7d90-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b7d90-114">\<behavior> из \<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="b7d90-114">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="b7d90-115">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="b7d90-115">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b7d90-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b7d90-116">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>
