---
title: <enableWebScript>
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: 20c0057c80b668df97379d0168bb7c005d9927ce
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400386"
---
# \<enableWebScript>
<span data-ttu-id="51511-101">Этот элемент включает поведение конечной точки, которое позволяет использовать службу с веб-страниц ASP.NET с поддержкой технологии AJAX.</span><span class="sxs-lookup"><span data-stu-id="51511-101">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<enableWebScript>**  
  
## <a name="syntax"></a><span data-ttu-id="51511-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="51511-102">Syntax</span></span>  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="51511-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="51511-103">Attributes and Elements</span></span>  
 <span data-ttu-id="51511-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="51511-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="51511-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="51511-105">Attributes</span></span>  
 <span data-ttu-id="51511-106">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="51511-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="51511-107">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="51511-107">Child Elements</span></span>  
 <span data-ttu-id="51511-108">Нет.</span><span class="sxs-lookup"><span data-stu-id="51511-108">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="51511-109">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="51511-109">Parent Elements</span></span>  
  
|<span data-ttu-id="51511-110">Элемент</span><span class="sxs-lookup"><span data-stu-id="51511-110">Element</span></span>|<span data-ttu-id="51511-111">Описание</span><span class="sxs-lookup"><span data-stu-id="51511-111">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="51511-112">Задает набор поведений конечной точки.</span><span class="sxs-lookup"><span data-stu-id="51511-112">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51511-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="51511-113">Remarks</span></span>  
 <span data-ttu-id="51511-114">Это поведение следует использовать только в сочетании со [\<webHttpBinding>](webhttpbinding.md) стандартной привязкой или с [\<webMessageEncoding>](webmessageencoding.md) элементом Binding.</span><span class="sxs-lookup"><span data-stu-id="51511-114">This behavior should only be used in conjunction with either the [\<webHttpBinding>](webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="51511-115">Дополнительные сведения об этом поведении см. в разделе <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span><span class="sxs-lookup"><span data-stu-id="51511-115">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51511-116">См. также</span><span class="sxs-lookup"><span data-stu-id="51511-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>
- <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>
- [<span data-ttu-id="51511-117">Интеграция с AJAX и поддержка JSON</span><span class="sxs-lookup"><span data-stu-id="51511-117">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [\<webHttp>](webhttp.md)
