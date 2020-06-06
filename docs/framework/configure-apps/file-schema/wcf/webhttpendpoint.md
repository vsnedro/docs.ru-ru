---
title: <webHttpEndpoint>
ms.date: 03/30/2017
ms.assetid: ecaaeb6f-ebd0-411d-8b53-92477cd45347
ms.openlocfilehash: 8d4f55fd5b51ea77839b7fdbb930e937f5700417
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854798"
---
# \<webHttpEndpoint>
<span data-ttu-id="50e5b-101">Этот элемент конфигурации определяет стандартную конечную точку с фиксированной [\<webHttpBinding>](webhttpbinding.md) привязкой, которая автоматически добавляет [\<webHttp>](webhttp.md) поведение.</span><span class="sxs-lookup"><span data-stu-id="50e5b-101">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<webHttp>](webhttp.md) behavior.</span></span> <span data-ttu-id="50e5b-102">Используйте эту конечную точку при написании службы REST.</span><span class="sxs-lookup"><span data-stu-id="50e5b-102">Use this endpoint when writing a REST service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webHttpEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="50e5b-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="50e5b-103">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webHttpEndpoint>
      <standardEndpoint automaticFormatSelectionEnabled="String"
                        defaultOutgoingResponseFormat="Xml/Json"
                        helpEnabled="Boolean"
                        webEndpointType="String" />
    </webHttpEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="50e5b-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="50e5b-104">Attributes and Elements</span></span>  
 <span data-ttu-id="50e5b-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="50e5b-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="50e5b-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="50e5b-106">Attributes</span></span>  
  
|<span data-ttu-id="50e5b-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="50e5b-107">Attribute</span></span>|<span data-ttu-id="50e5b-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="50e5b-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="50e5b-109">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="50e5b-109">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="50e5b-110">Логическое значение, указывающее, включен ли автоматический выбор формата.</span><span class="sxs-lookup"><span data-stu-id="50e5b-110">A Boolean value that indicates whether automatic format selection is enabled.</span></span><br /><br /> <span data-ttu-id="50e5b-111">Если автоматический выбор формата включен, инфраструктура выполняет синтаксический анализ заголовка `Accept` сообщения запроса и определяет наиболее подходящий формат ответа.</span><span class="sxs-lookup"><span data-stu-id="50e5b-111">When automatic format selection is enabled, the infrastructure parses the `Accept` header of the request message and determines the most appropriate response format.</span></span> <span data-ttu-id="50e5b-112">Если в заголовке `Accept` не указан подходящий формат ответа, инфраструктура использует тип `Content-Type` сообщения запроса или формат ответа, заданный для этой операции по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="50e5b-112">If the `Accept` header does not specify a suitable response format, the infrastructure uses the `Content-Type` of the request message or the default response format of the operation.</span></span>|  
|<span data-ttu-id="50e5b-113">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="50e5b-113">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="50e5b-114">Атрибут, определяющий формат исходящего ответа по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="50e5b-114">An attribute that specifies the default outgoing response format.</span></span> <span data-ttu-id="50e5b-115">Это атрибут типа <xref:System.ServiceModel.Web.WebMessageFormat>.</span><span class="sxs-lookup"><span data-stu-id="50e5b-115">This attribute is of the <xref:System.ServiceModel.Web.WebMessageFormat> type</span></span>|  
|<span data-ttu-id="50e5b-116">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="50e5b-116">helpEnabled</span></span>|<span data-ttu-id="50e5b-117">Логическое значение, указывающее, включена ли страница справки HTTP для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="50e5b-117">A Boolean value that indicates whether the HTTP help page is enabled for the endpoint.</span></span>|  
|<span data-ttu-id="50e5b-118">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="50e5b-118">webEndpointType</span></span>|<span data-ttu-id="50e5b-119">Строка, указывающая тип конечной точки.</span><span class="sxs-lookup"><span data-stu-id="50e5b-119">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="50e5b-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="50e5b-120">Child Elements</span></span>  
 <span data-ttu-id="50e5b-121">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="50e5b-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="50e5b-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="50e5b-122">Parent Elements</span></span>  
  
|<span data-ttu-id="50e5b-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="50e5b-123">Element</span></span>|<span data-ttu-id="50e5b-124">Описание</span><span class="sxs-lookup"><span data-stu-id="50e5b-124">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="50e5b-125">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="50e5b-125">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="50e5b-126">См. также</span><span class="sxs-lookup"><span data-stu-id="50e5b-126">See also</span></span>

- <xref:System.ServiceModel.Description.WebHttpEndpoint>
- <xref:System.ServiceModel.Configuration.WebHttpEndpointElement>
