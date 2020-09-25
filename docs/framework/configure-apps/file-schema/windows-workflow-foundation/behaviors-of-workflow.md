---
title: <behaviors> рабочего процесса
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: 21974f77526f55a47c014a285efd3bbac6fc1f7b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189608"
---
# <a name="behaviors-of-workflow"></a><span data-ttu-id="d97b1-102">\<behaviors> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="d97b1-102">\<behaviors> of workflow</span></span>

<span data-ttu-id="d97b1-103">Этот элемент содержит коллекцию **serviceBehaviors** .</span><span class="sxs-lookup"><span data-stu-id="d97b1-103">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="d97b1-104">Каждый элемент в коллекции определяет элементы поведения, используемые службами рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="d97b1-104">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="d97b1-105">Каждый элемент поведения определяется с помощью уникального атрибута **имени** .</span><span class="sxs-lookup"><span data-stu-id="d97b1-105">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<behaviors>**  
  
## <a name="syntax"></a><span data-ttu-id="d97b1-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d97b1-106">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d97b1-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d97b1-107">Attributes and Elements</span></span>  

 <span data-ttu-id="d97b1-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d97b1-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d97b1-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d97b1-109">Attributes</span></span>  

 <span data-ttu-id="d97b1-110">Нет</span><span class="sxs-lookup"><span data-stu-id="d97b1-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d97b1-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d97b1-111">Child Elements</span></span>  
  
|<span data-ttu-id="d97b1-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="d97b1-112">Element</span></span>|<span data-ttu-id="d97b1-113">Описание</span><span class="sxs-lookup"><span data-stu-id="d97b1-113">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceBehaviors>](servicebehaviors-of-workflow.md)|<span data-ttu-id="d97b1-114">В данном разделе конфигурации представлены все поведения, определенные для конкретной службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="d97b1-114">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d97b1-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d97b1-115">Parent Elements</span></span>  
  
|<span data-ttu-id="d97b1-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="d97b1-116">Element</span></span>|<span data-ttu-id="d97b1-117">Описание</span><span class="sxs-lookup"><span data-stu-id="d97b1-117">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel>](../wcf/system-servicemodel.md)|<span data-ttu-id="d97b1-118">Корневой элемент всех элементов конфигурации рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="d97b1-118">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d97b1-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d97b1-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="d97b1-120">Настройка и расширение среды выполнения с помощью поведений</span><span class="sxs-lookup"><span data-stu-id="d97b1-120">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
