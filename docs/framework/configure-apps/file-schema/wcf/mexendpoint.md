---
title: <mexEndpoint>
ms.date: 03/30/2017
ms.assetid: c9823060-0a5d-4f9d-99d4-4d113b758247
ms.openlocfilehash: e8f0e0fa2ea1606bf980fd6fa1fcd47f12c3b540
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204753"
---
# \<mexEndpoint>

<span data-ttu-id="87ca4-101">Этот элемент конфигурации определяет стандартную конечную точку с фиксированным контрактом IMetadataExchange.</span><span class="sxs-lookup"><span data-stu-id="87ca4-101">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="87ca4-102">Поскольку все конечные точки обмена метаданными указывают IMetadataExchange в качестве своего контракта, можно использовать эту стандартную точку вместо определения собственной точки.</span><span class="sxs-lookup"><span data-stu-id="87ca4-102">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="87ca4-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="87ca4-103">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="87ca4-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="87ca4-104">Attributes and Elements</span></span>  

 <span data-ttu-id="87ca4-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="87ca4-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="87ca4-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="87ca4-106">Attributes</span></span>  
  
|<span data-ttu-id="87ca4-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="87ca4-107">Attribute</span></span>|<span data-ttu-id="87ca4-108">Описание</span><span class="sxs-lookup"><span data-stu-id="87ca4-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="87ca4-109">name</span><span class="sxs-lookup"><span data-stu-id="87ca4-109">name</span></span>|<span data-ttu-id="87ca4-110">Строка, указывающая имя конфигурации стандартной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="87ca4-110">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="87ca4-111">Это имя используется в атрибуте `endpointConfiguration` конечной точки службы для связывания стандартной конечной точки с ее конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="87ca4-111">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="87ca4-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="87ca4-112">Child Elements</span></span>  

 <span data-ttu-id="87ca4-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="87ca4-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="87ca4-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="87ca4-114">Parent Elements</span></span>  
  
|<span data-ttu-id="87ca4-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="87ca4-115">Element</span></span>|<span data-ttu-id="87ca4-116">Описание</span><span class="sxs-lookup"><span data-stu-id="87ca4-116">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="87ca4-117">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="87ca4-117">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|
