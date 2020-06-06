---
title: <clientVia>
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: a1c2ee68fb039e24e1462148cb52daf1bb57f8ed
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398112"
---
# \<clientVia>
<span data-ttu-id="726d8-101">Задает универсальный код ресурса (URI), для которого необходимо создать канал транспорта.</span><span class="sxs-lookup"><span data-stu-id="726d8-101">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="726d8-102">Для получения дополнительной информации см. <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="726d8-102">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientVia>**  
  
## <a name="syntax"></a><span data-ttu-id="726d8-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="726d8-103">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="726d8-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="726d8-104">Attributes and Elements</span></span>  
 <span data-ttu-id="726d8-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="726d8-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="726d8-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="726d8-106">Attributes</span></span>  
  
|<span data-ttu-id="726d8-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="726d8-107">Attribute</span></span>|<span data-ttu-id="726d8-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="726d8-108">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="726d8-109">Строка, задающая универсальный код ресурса (URI), который указывает маршрут для сообщения.</span><span class="sxs-lookup"><span data-stu-id="726d8-109">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="726d8-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="726d8-110">Child Elements</span></span>  
 <span data-ttu-id="726d8-111">Нет</span><span class="sxs-lookup"><span data-stu-id="726d8-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="726d8-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="726d8-112">Parent Elements</span></span>  
  
|<span data-ttu-id="726d8-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="726d8-113">Element</span></span>|<span data-ttu-id="726d8-114">Описание</span><span class="sxs-lookup"><span data-stu-id="726d8-114">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="726d8-115">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="726d8-115">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="726d8-116">См. также</span><span class="sxs-lookup"><span data-stu-id="726d8-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
