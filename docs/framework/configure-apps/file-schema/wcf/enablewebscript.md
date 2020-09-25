---
title: <enableWebScript>
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: 11378e6cc8cbe8e631fd77ab74c91a616099df52
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190089"
---
# \<enableWebScript>

<span data-ttu-id="29686-101">Этот элемент включает поведение конечной точки, которое позволяет использовать службу с веб-страниц ASP.NET с поддержкой технологии AJAX.</span><span class="sxs-lookup"><span data-stu-id="29686-101">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<enableWebScript>**  
  
## <a name="syntax"></a><span data-ttu-id="29686-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="29686-102">Syntax</span></span>  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="29686-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="29686-103">Attributes and Elements</span></span>  

 <span data-ttu-id="29686-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="29686-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="29686-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="29686-105">Attributes</span></span>  

 <span data-ttu-id="29686-106">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="29686-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="29686-107">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="29686-107">Child Elements</span></span>  

 <span data-ttu-id="29686-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="29686-108">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="29686-109">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="29686-109">Parent Elements</span></span>  
  
|<span data-ttu-id="29686-110">Элемент</span><span class="sxs-lookup"><span data-stu-id="29686-110">Element</span></span>|<span data-ttu-id="29686-111">Описание</span><span class="sxs-lookup"><span data-stu-id="29686-111">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="29686-112">Задает набор поведений конечной точки.</span><span class="sxs-lookup"><span data-stu-id="29686-112">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29686-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="29686-113">Remarks</span></span>  

 <span data-ttu-id="29686-114">Это поведение следует использовать только в сочетании со [\<webHttpBinding>](webhttpbinding.md) стандартной привязкой или с [\<webMessageEncoding>](webmessageencoding.md) элементом Binding.</span><span class="sxs-lookup"><span data-stu-id="29686-114">This behavior should only be used in conjunction with either the [\<webHttpBinding>](webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="29686-115">Дополнительные сведения об этом поведении см. в разделе <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span><span class="sxs-lookup"><span data-stu-id="29686-115">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29686-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="29686-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>
- <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>
- [<span data-ttu-id="29686-117">Интеграция с AJAX и поддержка JSON</span><span class="sxs-lookup"><span data-stu-id="29686-117">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [\<webHttp>](webhttp.md)
