---
title: <filter>
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: 6e78275aaeb202405e327302455d56fa431d7f27
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855256"
---
# \<filter>

<span data-ttu-id="bef78-101">Определяет фильтр маршрутизации, определяющий тип Windows Communication Foundation (WCF), который <xref:System.ServiceModel.Dispatcher.MessageFilter> будет использоваться при оценке входящих сообщений, а также любые вспомогательные данные или параметры, необходимые для фильтра.</span><span class="sxs-lookup"><span data-stu-id="bef78-101">Defines a routing filter, which determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<filters>**](filters-of-routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**  
  
## <a name="syntax"></a><span data-ttu-id="bef78-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bef78-102">Syntax</span></span>  
  
```xml  
<routing>
  <filters>
    <filter customType="String"
            filterData="String"
            filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath"
            name="String" />
  </filters>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bef78-103">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="bef78-103">Attributes and elements</span></span>

<span data-ttu-id="bef78-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bef78-104">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="bef78-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bef78-105">Attributes</span></span>

| <span data-ttu-id="bef78-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="bef78-106">Attribute</span></span>  | <span data-ttu-id="bef78-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="bef78-107">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="bef78-108">customType</span><span class="sxs-lookup"><span data-stu-id="bef78-108">customType</span></span> | <span data-ttu-id="bef78-109">Строка, содержащая полное имя для пользовательского типа, используемого в качестве фильтра.</span><span class="sxs-lookup"><span data-stu-id="bef78-109">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="bef78-110">Если параметр `filterType` имеет значение `custom` , этот атрибут содержит полное имя типа создаваемого класса.</span><span class="sxs-lookup"><span data-stu-id="bef78-110">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="bef78-111">`filterData`может также содержать значения, используемые при вычислении настраиваемого фильтра типов.</span><span class="sxs-lookup"><span data-stu-id="bef78-111">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="bef78-112">filterData</span><span class="sxs-lookup"><span data-stu-id="bef78-112">filterData</span></span> | <span data-ttu-id="bef78-113">Строка, содержащая данные фильтра.</span><span class="sxs-lookup"><span data-stu-id="bef78-113">A string containing the filter data.</span></span> <span data-ttu-id="bef78-114">Дополнительные сведения об указании этого атрибута см. в разделе <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="bef78-114">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="bef78-115">filterType</span><span class="sxs-lookup"><span data-stu-id="bef78-115">filterType</span></span> | <span data-ttu-id="bef78-116">Строка, содержащая тип фильтра.</span><span class="sxs-lookup"><span data-stu-id="bef78-116">A string containing the filter type.</span></span> <span data-ttu-id="bef78-117">Этот атрибут имеет тип <xref:System.ServiceModel.Routing.Configuration.FilterType>.</span><span class="sxs-lookup"><span data-stu-id="bef78-117">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="bef78-118">Дополнительные сведения о том, как это работает с атрибутом `filterData`, см. в разделе <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="bef78-118">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="bef78-119">name</span><span class="sxs-lookup"><span data-stu-id="bef78-119">name</span></span>       | <span data-ttu-id="bef78-120">Строка, содержащая уникальное имя этого элемента фильтра.</span><span class="sxs-lookup"><span data-stu-id="bef78-120">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="bef78-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bef78-121">Child elements</span></span>

<span data-ttu-id="bef78-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="bef78-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="bef78-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bef78-123">Parent elements</span></span>

| <span data-ttu-id="bef78-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="bef78-124">Element</span></span> | <span data-ttu-id="bef78-125">Описание</span><span class="sxs-lookup"><span data-stu-id="bef78-125">Description</span></span> |
| ------- | ----------- |
| [\<routing>](routing.md) | <span data-ttu-id="bef78-126">Раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF), <xref:System.ServiceModel.Dispatcher.MessageFilter> используемый при оценке входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="bef78-126">A configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="bef78-127">См. также</span><span class="sxs-lookup"><span data-stu-id="bef78-127">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>
