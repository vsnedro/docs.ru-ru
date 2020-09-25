---
title: <bufferReceive>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b23c3a54-10d4-4f13-ab6d-98b26b76f22a
ms.openlocfilehash: 16d4546bce461b55695e0deed093396ce1c2b0b6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189569"
---
# \<bufferReceive>

<span data-ttu-id="52e01-101">Поведение, позволяющее службе рабочего процесса использовать обработку буфера получения, благодаря чему можно обрабатывать неупорядоченные сообщения.</span><span class="sxs-lookup"><span data-stu-id="52e01-101">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bufferReceive>**  
  
## <a name="syntax"></a><span data-ttu-id="52e01-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="52e01-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="52e01-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="52e01-103">Attributes and Elements</span></span>  

 <span data-ttu-id="52e01-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="52e01-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="52e01-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="52e01-105">Attributes</span></span>  
  
|<span data-ttu-id="52e01-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="52e01-106">Attribute</span></span>|<span data-ttu-id="52e01-107">Описание</span><span class="sxs-lookup"><span data-stu-id="52e01-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="52e01-108">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="52e01-108">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="52e01-109">Целочисленное значение, указывающее максимальное число отложенных сообщений для каждого канала.</span><span class="sxs-lookup"><span data-stu-id="52e01-109">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="52e01-110">Значение по умолчанию — 512.</span><span class="sxs-lookup"><span data-stu-id="52e01-110">The default value is 512.</span></span> <span data-ttu-id="52e01-111">Это свойство ограничивает число внеочередных сообщений, которые могут быть получены службой рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="52e01-111">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="52e01-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="52e01-112">Child Elements</span></span>  

 <span data-ttu-id="52e01-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="52e01-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="52e01-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="52e01-114">Parent Elements</span></span>  
  
|<span data-ttu-id="52e01-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="52e01-115">Element</span></span>|<span data-ttu-id="52e01-116">Описание</span><span class="sxs-lookup"><span data-stu-id="52e01-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="52e01-117">\<behavior> из \<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="52e01-117">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="52e01-118">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="52e01-118">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="52e01-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="52e01-119">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.BufferedReceiveServiceBehavior>
- <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>
