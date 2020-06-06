---
title: <defaultPorts>
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 89ebad118c1c9210357d8fd281c9216b7f64b450
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398076"
---
# \<defaultPorts>
<span data-ttu-id="9648b-101">Коллекция портов по умолчанию со списком конечных точек связи по умолчанию, которые прослушивает клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="9648b-101">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<useRequestHeadersForMetadataAddress>**](userequestheadersformetadataaddress.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultPorts>**  
  
## <a name="syntax"></a><span data-ttu-id="9648b-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9648b-102">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9648b-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9648b-103">Attributes and Elements</span></span>  
 <span data-ttu-id="9648b-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9648b-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9648b-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9648b-105">Attributes</span></span>  
 <span data-ttu-id="9648b-106">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="9648b-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9648b-107">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9648b-107">Child Elements</span></span>  
  
|<span data-ttu-id="9648b-108">Элемент</span><span class="sxs-lookup"><span data-stu-id="9648b-108">Element</span></span>|<span data-ttu-id="9648b-109">Описание</span><span class="sxs-lookup"><span data-stu-id="9648b-109">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9648b-110">\<add>окна\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="9648b-110">\<add> of \<defaultPorts></span></span>](add-of-defaultports.md)|<span data-ttu-id="9648b-111">Конечная точка связи по умолчанию, которую прослушивает клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="9648b-111">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9648b-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9648b-112">Parent Elements</span></span>  
  
|<span data-ttu-id="9648b-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="9648b-113">Element</span></span>|<span data-ttu-id="9648b-114">Описание</span><span class="sxs-lookup"><span data-stu-id="9648b-114">Description</span></span>|  
|-------------|-----------------|  
|[\<useRequestHeadersForMetadataAddress>](userequestheadersformetadataaddress.md)|<span data-ttu-id="9648b-115">Список портов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9648b-115">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9648b-116">См. также</span><span class="sxs-lookup"><span data-stu-id="9648b-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
