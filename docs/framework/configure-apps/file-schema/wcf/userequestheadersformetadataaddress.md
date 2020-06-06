---
title: <useRequestHeadersForMetadataAddress>
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: e0b46953924a3825420b719085e1210981da643a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399206"
---
# \<useRequestHeadersForMetadataAddress>
<span data-ttu-id="88144-101">Включает получение сведений об адресе метаданных из заголовков сообщений запросов.</span><span class="sxs-lookup"><span data-stu-id="88144-101">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<useRequestHeadersForMetadataAddress>**  
  
## <a name="syntax"></a><span data-ttu-id="88144-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="88144-102">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="88144-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="88144-103">Attributes and Elements</span></span>  
 <span data-ttu-id="88144-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="88144-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="88144-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="88144-105">Attributes</span></span>  
 <span data-ttu-id="88144-106">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="88144-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="88144-107">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="88144-107">Child Elements</span></span>  
  
|<span data-ttu-id="88144-108">Элемент</span><span class="sxs-lookup"><span data-stu-id="88144-108">Element</span></span>|<span data-ttu-id="88144-109">Описание</span><span class="sxs-lookup"><span data-stu-id="88144-109">Description</span></span>|  
|-------------|-----------------|  
|[\<defaultPorts>](defaultports.md)|<span data-ttu-id="88144-110">Коллекция портов по умолчанию со списком конечных точек связи по умолчанию, которые прослушивает клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="88144-110">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="88144-111">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="88144-111">Parent Elements</span></span>  
  
|<span data-ttu-id="88144-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="88144-112">Element</span></span>|<span data-ttu-id="88144-113">Описание</span><span class="sxs-lookup"><span data-stu-id="88144-113">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="88144-114">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="88144-114">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="88144-115">См. также</span><span class="sxs-lookup"><span data-stu-id="88144-115">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
