---
title: <filters> из <routing>
ms.date: 03/30/2017
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
ms.openlocfilehash: c9bc3a2c379e14d8cf687676a3ec40702d150e1e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855236"
---
# <a name="filters-of-routing"></a><span data-ttu-id="1e389-102">\<filters> из \<routing></span><span class="sxs-lookup"><span data-stu-id="1e389-102">\<filters> of \<routing></span></span>

<span data-ttu-id="1e389-103">Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF), <xref:System.ServiceModel.Dispatcher.MessageFilter> используемый при оценке входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="1e389-103">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span>

[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<filters>**  
  
## <a name="syntax"></a><span data-ttu-id="1e389-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1e389-104">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <routing>
    <filters>
      <filter customType="String"
              filterData="String"
              filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath"
              name="String" />
    </filters>
  </routing>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1e389-105">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="1e389-105">Attributes and elements</span></span>

<span data-ttu-id="1e389-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1e389-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="1e389-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1e389-107">Attributes</span></span>

<span data-ttu-id="1e389-108">Нет</span><span class="sxs-lookup"><span data-stu-id="1e389-108">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="1e389-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1e389-109">Child elements</span></span>

|     | <span data-ttu-id="1e389-110">Описание</span><span class="sxs-lookup"><span data-stu-id="1e389-110">Description</span></span> |
| --- | ----------- |
| [**\<filter>**](filter.md) | <span data-ttu-id="1e389-111">Содержит фильтр маршрутизации, определяющий тип Windows Communication Foundation (WCF), который <xref:System.ServiceModel.Dispatcher.MessageFilter> будет использоваться при оценке входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="1e389-111">Contains a routing filter that determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> will be used when evaluating incoming messages.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="1e389-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1e389-112">Parent elements</span></span>

|     | <span data-ttu-id="1e389-113">Описание</span><span class="sxs-lookup"><span data-stu-id="1e389-113">Description</span></span> |
| --- | ----------- |
| [**\<routing>**](routing.md) | <span data-ttu-id="1e389-114">Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF), <xref:System.ServiceModel.Dispatcher.MessageFilter> используемый при оценке входящих сообщений, а также таблицы маршрутизации, определяющие целевые конечные точки для отправки сообщений при совпадении фильтра.</span><span class="sxs-lookup"><span data-stu-id="1e389-114">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="1e389-115">См. также</span><span class="sxs-lookup"><span data-stu-id="1e389-115">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
