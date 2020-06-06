---
title: <webScriptEndpoint>
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: b4bc33cf8ff4e703973efe7df49e9f1d2189302e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854818"
---
# \<webScriptEndpoint>
<span data-ttu-id="ea3e7-101">Этот элемент конфигурации определяет стандартную конечную точку с фиксированной [\<webHttpBinding>](webhttpbinding.md) привязкой, которая автоматически добавляет [\<enableWebScript>](enablewebscript.md) поведение.</span><span class="sxs-lookup"><span data-stu-id="ea3e7-101">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](enablewebscript.md) behavior.</span></span> <span data-ttu-id="ea3e7-102">Используйте эту конечную точку при написании службы, вызываемой из приложения ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="ea3e7-102">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webScriptEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="ea3e7-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ea3e7-103">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String" />
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ea3e7-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ea3e7-104">Attributes and Elements</span></span>  
 <span data-ttu-id="ea3e7-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ea3e7-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ea3e7-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ea3e7-106">Attributes</span></span>  
  
|<span data-ttu-id="ea3e7-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ea3e7-107">Attribute</span></span>|<span data-ttu-id="ea3e7-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="ea3e7-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ea3e7-109">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="ea3e7-109">webEndpointType</span></span>|<span data-ttu-id="ea3e7-110">Строка, указывающая тип конечной точки.</span><span class="sxs-lookup"><span data-stu-id="ea3e7-110">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ea3e7-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ea3e7-111">Child Elements</span></span>  
 <span data-ttu-id="ea3e7-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ea3e7-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ea3e7-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ea3e7-113">Parent Elements</span></span>  
  
|<span data-ttu-id="ea3e7-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="ea3e7-114">Element</span></span>|<span data-ttu-id="ea3e7-115">Описание</span><span class="sxs-lookup"><span data-stu-id="ea3e7-115">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="ea3e7-116">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="ea3e7-116">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ea3e7-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ea3e7-117">See also</span></span>

- <xref:System.ServiceModel.Description.WebScriptEndpoint>
- <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>
