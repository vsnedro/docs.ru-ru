---
title: <webHttp>
ms.date: 03/30/2017
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
ms.openlocfilehash: 716d960e2d5f896976c22a60d419d9b165b36178
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202465"
---
# \<webHttp>

<span data-ttu-id="5a1db-101">Данный элемент задает <xref:System.ServiceModel.Description.WebHttpBehavior> на конечной точке в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5a1db-101">This element specifies the <xref:System.ServiceModel.Description.WebHttpBehavior> on an endpoint through configuration.</span></span> <span data-ttu-id="5a1db-102">Такое поведение при использовании в сочетании со [\<webHttpBinding>](webhttpbinding.md) стандартной привязкой позволяет использовать модель веб-программирования для службы Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="5a1db-102">This behavior, when used in conjunction with the [\<webHttpBinding>](webhttpbinding.md) standard binding, enables the Web programming model for a Windows Communication Foundation (WCF) service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webHttp>**  
  
## <a name="syntax"></a><span data-ttu-id="5a1db-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5a1db-103">Syntax</span></span>  
  
```xml  
<webHttp />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5a1db-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5a1db-104">Attributes and Elements</span></span>  

 <span data-ttu-id="5a1db-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5a1db-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5a1db-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5a1db-106">Attributes</span></span>  
  
|<span data-ttu-id="5a1db-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5a1db-107">Attribute</span></span>|<span data-ttu-id="5a1db-108">Описание</span><span class="sxs-lookup"><span data-stu-id="5a1db-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5a1db-109">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="5a1db-109">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="5a1db-110">Если это свойство имеет значение `true`, то инфраструктура WCF определяет лучший формат для использования.</span><span class="sxs-lookup"><span data-stu-id="5a1db-110">When this property is set to `true`, the WCF infrastructure determines the best format to use.</span></span> <span data-ttu-id="5a1db-111">Автоматический выбор формата отключен по умолчанию в целях обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="5a1db-111">Automatic format selection is disabled by default for backwards compatibility.</span></span> <span data-ttu-id="5a1db-112">Автоматический выбор формата можно включить программно или через конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="5a1db-112">Automatic format selection can be enabled programmatically or through configuration.</span></span>|  
|<span data-ttu-id="5a1db-113">defaultBodyStyle</span><span class="sxs-lookup"><span data-stu-id="5a1db-113">defaultBodyStyle</span></span>|<span data-ttu-id="5a1db-114">Задает стиль по умолчанию для текста возвращаемых сообщений.</span><span class="sxs-lookup"><span data-stu-id="5a1db-114">Specifies the default body style of returned messages.</span></span> <span data-ttu-id="5a1db-115">Дополнительные сведения см. в разделе <xref:System.ServiceModel.Web.WebMessageBodyStyle> и [веб-форматирование WCF](../../../wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="5a1db-115">For more information, see <xref:System.ServiceModel.Web.WebMessageBodyStyle> and [WCF Web HTTP Formatting](../../../wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="5a1db-116">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="5a1db-116">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="5a1db-117">Определяет формат ответа по умолчанию для исходящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="5a1db-117">Specifies the default outgoing response format for messages.</span></span> <span data-ttu-id="5a1db-118">Дополнительные сведения см. в разделе [веб-форматирование WCF](../../../wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="5a1db-118">For more information, see [WCF Web HTTP Formatting](../../../wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="5a1db-119">faultExceptionEnabled</span><span class="sxs-lookup"><span data-stu-id="5a1db-119">faultExceptionEnabled</span></span>|<span data-ttu-id="5a1db-120">Возвращает или задает флаг, указывающий, будет ли создаваться исключение FaultException при возникновении внутренней ошибки сервера (код состояния HTTP: 500).</span><span class="sxs-lookup"><span data-stu-id="5a1db-120">Gets or sets the flag that specifies whether a FaultException is generated when an internal server error (HTTP status code: 500) occurs.</span></span>|  
|<span data-ttu-id="5a1db-121">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="5a1db-121">helpEnabled</span></span>|<span data-ttu-id="5a1db-122">Возвращает или задает значение, определяющее, будет ли включена страница справки.</span><span class="sxs-lookup"><span data-stu-id="5a1db-122">Gets or sets a value that determines if the Help page is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5a1db-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5a1db-123">Child Elements</span></span>  

 <span data-ttu-id="5a1db-124">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5a1db-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5a1db-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5a1db-125">Parent Elements</span></span>  
  
|<span data-ttu-id="5a1db-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="5a1db-126">Element</span></span>|<span data-ttu-id="5a1db-127">Описание</span><span class="sxs-lookup"><span data-stu-id="5a1db-127">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="5a1db-128">Задает набор поведений конечной точки.</span><span class="sxs-lookup"><span data-stu-id="5a1db-128">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5a1db-129">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5a1db-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpElement>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [<span data-ttu-id="5a1db-130">Интеграция с AJAX и поддержка JSON</span><span class="sxs-lookup"><span data-stu-id="5a1db-130">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [\<webHttpBinding>](webhttpbinding.md)
