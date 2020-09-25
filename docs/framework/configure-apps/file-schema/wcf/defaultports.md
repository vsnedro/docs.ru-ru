---
title: <defaultPorts>
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 08ca8a2bfcf5b905152f7e64a45cbae4992a7b78
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192377"
---
# \<defaultPorts>

<span data-ttu-id="8884f-101">Коллекция портов по умолчанию со списком конечных точек связи по умолчанию, которые прослушивает клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="8884f-101">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<useRequestHeadersForMetadataAddress>**](userequestheadersformetadataaddress.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultPorts>**  
  
## <a name="syntax"></a><span data-ttu-id="8884f-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8884f-102">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8884f-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8884f-103">Attributes and Elements</span></span>  

 <span data-ttu-id="8884f-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8884f-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8884f-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8884f-105">Attributes</span></span>  

 <span data-ttu-id="8884f-106">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8884f-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8884f-107">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8884f-107">Child Elements</span></span>  
  
|<span data-ttu-id="8884f-108">Элемент</span><span class="sxs-lookup"><span data-stu-id="8884f-108">Element</span></span>|<span data-ttu-id="8884f-109">Описание</span><span class="sxs-lookup"><span data-stu-id="8884f-109">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8884f-110">\<add> из \<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="8884f-110">\<add> of \<defaultPorts></span></span>](add-of-defaultports.md)|<span data-ttu-id="8884f-111">Конечная точка связи по умолчанию, которую прослушивает клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="8884f-111">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8884f-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8884f-112">Parent Elements</span></span>  
  
|<span data-ttu-id="8884f-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="8884f-113">Element</span></span>|<span data-ttu-id="8884f-114">Описание</span><span class="sxs-lookup"><span data-stu-id="8884f-114">Description</span></span>|  
|-------------|-----------------|  
|[\<useRequestHeadersForMetadataAddress>](userequestheadersformetadataaddress.md)|<span data-ttu-id="8884f-115">Список портов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8884f-115">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8884f-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8884f-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
