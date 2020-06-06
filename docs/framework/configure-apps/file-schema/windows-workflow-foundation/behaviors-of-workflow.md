---
title: <behaviors>рабочего процесса
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: 05a15cdf5c043eb5d94b36028324310d2b7a8413
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398879"
---
# <a name="behaviors-of-workflow"></a><span data-ttu-id="0d7cf-102">\<behaviors>рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="0d7cf-102">\<behaviors> of workflow</span></span>
<span data-ttu-id="0d7cf-103">Этот элемент содержит коллекцию **serviceBehaviors** .</span><span class="sxs-lookup"><span data-stu-id="0d7cf-103">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="0d7cf-104">Каждый элемент в коллекции определяет элементы поведения, используемые службами рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="0d7cf-104">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="0d7cf-105">Каждый элемент поведения определяется с помощью уникального атрибута **имени** .</span><span class="sxs-lookup"><span data-stu-id="0d7cf-105">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<behaviors>**  
  
## <a name="syntax"></a><span data-ttu-id="0d7cf-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0d7cf-106">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0d7cf-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0d7cf-107">Attributes and Elements</span></span>  
 <span data-ttu-id="0d7cf-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0d7cf-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0d7cf-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0d7cf-109">Attributes</span></span>  
 <span data-ttu-id="0d7cf-110">Нет</span><span class="sxs-lookup"><span data-stu-id="0d7cf-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0d7cf-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0d7cf-111">Child Elements</span></span>  
  
|<span data-ttu-id="0d7cf-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="0d7cf-112">Element</span></span>|<span data-ttu-id="0d7cf-113">Описание</span><span class="sxs-lookup"><span data-stu-id="0d7cf-113">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceBehaviors>](servicebehaviors-of-workflow.md)|<span data-ttu-id="0d7cf-114">В данном разделе конфигурации представлены все поведения, определенные для конкретной службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="0d7cf-114">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0d7cf-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0d7cf-115">Parent Elements</span></span>  
  
|<span data-ttu-id="0d7cf-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="0d7cf-116">Element</span></span>|<span data-ttu-id="0d7cf-117">Описание</span><span class="sxs-lookup"><span data-stu-id="0d7cf-117">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel>](../wcf/system-servicemodel.md)|<span data-ttu-id="0d7cf-118">Корневой элемент всех элементов конфигурации рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="0d7cf-118">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0d7cf-119">См. также</span><span class="sxs-lookup"><span data-stu-id="0d7cf-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="0d7cf-120">Настройка и расширение среды выполнения с помощью поведений</span><span class="sxs-lookup"><span data-stu-id="0d7cf-120">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
