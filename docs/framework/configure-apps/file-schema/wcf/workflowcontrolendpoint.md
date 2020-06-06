---
title: <workflowControlEndpoint>
ms.date: 03/30/2017
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
ms.openlocfilehash: 670c1573fe4378a18c19d0a58fe58241745725bd
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854780"
---
# \<workflowControlEndpoint>
<span data-ttu-id="aecbf-101">Этот элемент конфигурации определяет стандартную конечную точку для управления выполнением экземпляров рабочего процесса (создание, выполнение, приостановка, завершение и т. д.).</span><span class="sxs-lookup"><span data-stu-id="aecbf-101">This configuration element defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowControlEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="aecbf-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aecbf-102">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <workflowControlEndpoint>
      <standardEndpoint name="String" />
    </workflowControlEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aecbf-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="aecbf-103">Attributes and Elements</span></span>  
 <span data-ttu-id="aecbf-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="aecbf-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aecbf-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="aecbf-105">Attributes</span></span>  
  
|<span data-ttu-id="aecbf-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="aecbf-106">Attribute</span></span>|<span data-ttu-id="aecbf-107">Описание</span><span class="sxs-lookup"><span data-stu-id="aecbf-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aecbf-108">name</span><span class="sxs-lookup"><span data-stu-id="aecbf-108">name</span></span>|<span data-ttu-id="aecbf-109">Строка, указывающая имя конфигурации стандартной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="aecbf-109">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="aecbf-110">Это имя используется в атрибуте `endpointConfiguration` конечной точки службы для связывания стандартной конечной точки с ее конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="aecbf-110">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aecbf-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="aecbf-111">Child Elements</span></span>  
 <span data-ttu-id="aecbf-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="aecbf-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="aecbf-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="aecbf-113">Parent Elements</span></span>  
  
|<span data-ttu-id="aecbf-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="aecbf-114">Element</span></span>|<span data-ttu-id="aecbf-115">Описание</span><span class="sxs-lookup"><span data-stu-id="aecbf-115">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="aecbf-116">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="aecbf-116">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aecbf-117">См. также</span><span class="sxs-lookup"><span data-stu-id="aecbf-117">See also</span></span>

- <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>
