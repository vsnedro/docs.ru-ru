---
title: <mexEndpoint>
ms.date: 03/30/2017
ms.assetid: c9823060-0a5d-4f9d-99d4-4d113b758247
ms.openlocfilehash: 7760ee4d3b118e339944317e8ec8d8217b5d909d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855108"
---
# \<mexEndpoint>
<span data-ttu-id="6aa2d-101">Этот элемент конфигурации определяет стандартную конечную точку с фиксированным контрактом IMetadataExchange.</span><span class="sxs-lookup"><span data-stu-id="6aa2d-101">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="6aa2d-102">Поскольку все конечные точки обмена метаданными указывают IMetadataExchange в качестве своего контракта, можно использовать эту стандартную точку вместо определения собственной точки.</span><span class="sxs-lookup"><span data-stu-id="6aa2d-102">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="6aa2d-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6aa2d-103">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6aa2d-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6aa2d-104">Attributes and Elements</span></span>  
 <span data-ttu-id="6aa2d-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6aa2d-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6aa2d-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6aa2d-106">Attributes</span></span>  
  
|<span data-ttu-id="6aa2d-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6aa2d-107">Attribute</span></span>|<span data-ttu-id="6aa2d-108">Описание</span><span class="sxs-lookup"><span data-stu-id="6aa2d-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6aa2d-109">name</span><span class="sxs-lookup"><span data-stu-id="6aa2d-109">name</span></span>|<span data-ttu-id="6aa2d-110">Строка, указывающая имя конфигурации стандартной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="6aa2d-110">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="6aa2d-111">Это имя используется в атрибуте `endpointConfiguration` конечной точки службы для связывания стандартной конечной точки с ее конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="6aa2d-111">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6aa2d-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6aa2d-112">Child Elements</span></span>  
 <span data-ttu-id="6aa2d-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="6aa2d-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6aa2d-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6aa2d-114">Parent Elements</span></span>  
  
|<span data-ttu-id="6aa2d-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="6aa2d-115">Element</span></span>|<span data-ttu-id="6aa2d-116">Описание</span><span class="sxs-lookup"><span data-stu-id="6aa2d-116">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="6aa2d-117">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="6aa2d-117">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|
