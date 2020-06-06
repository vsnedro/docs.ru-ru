---
title: <dispatcherSynchronization>
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: b95f25217c2a3558846cc7a0ef43e21aacd2ee2a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398005"
---
# \<dispatcherSynchronization>
  
<span data-ttu-id="7da68-101">Указывает поведение конечной точки, которое позволяет службе отправлять ответы в асинхронном режиме.</span><span class="sxs-lookup"><span data-stu-id="7da68-101">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dispatcherSynchronization>**  
  
## <a name="syntax"></a><span data-ttu-id="7da68-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7da68-102">Syntax</span></span>  
  
```xml  
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean"
                                   maxPendingReceives="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="7da68-103">Type</span><span class="sxs-lookup"><span data-stu-id="7da68-103">Type</span></span>  
  
`Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7da68-104">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="7da68-104">Attributes and elements</span></span>  
  
<span data-ttu-id="7da68-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7da68-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7da68-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7da68-106">Attributes</span></span>

| <span data-ttu-id="7da68-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7da68-107">Attribute</span></span>               | <span data-ttu-id="7da68-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="7da68-108">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="7da68-109">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="7da68-109">asynchronousSendEnabled</span></span> | <span data-ttu-id="7da68-110">Логическое значение, указывающее, включено ли поведение, которое позволяет отправлять ответы в асинхронном режиме.</span><span class="sxs-lookup"><span data-stu-id="7da68-110">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="7da68-111">Целочисленное значение, которое указывает число возможных получений по одному каналу.</span><span class="sxs-lookup"><span data-stu-id="7da68-111">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="7da68-112">Это значение должно настраиваться только после правильной настройки поведения регулирования службы.</span><span class="sxs-lookup"><span data-stu-id="7da68-112">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="7da68-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7da68-113">Child elements</span></span>

<span data-ttu-id="7da68-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7da68-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7da68-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7da68-115">Parent elements</span></span>

| <span data-ttu-id="7da68-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="7da68-116">Element</span></span> | <span data-ttu-id="7da68-117">Описание</span><span class="sxs-lookup"><span data-stu-id="7da68-117">Description</span></span> |  
| ------- | ----------- |  
| [\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="7da68-118">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="7da68-118">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="7da68-119">См. также</span><span class="sxs-lookup"><span data-stu-id="7da68-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement>
- <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
