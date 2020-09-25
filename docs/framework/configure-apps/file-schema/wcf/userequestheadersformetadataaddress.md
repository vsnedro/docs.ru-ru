---
title: <useRequestHeadersForMetadataAddress>
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: a323e6da0eb173e303d70cc3b7309b898a805573
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172818"
---
# \<useRequestHeadersForMetadataAddress>

<span data-ttu-id="f5568-101">Включает получение сведений об адресе метаданных из заголовков сообщений запросов.</span><span class="sxs-lookup"><span data-stu-id="f5568-101">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<useRequestHeadersForMetadataAddress>**  
  
## <a name="syntax"></a><span data-ttu-id="f5568-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f5568-102">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f5568-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f5568-103">Attributes and Elements</span></span>  

 <span data-ttu-id="f5568-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f5568-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f5568-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f5568-105">Attributes</span></span>  

 <span data-ttu-id="f5568-106">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f5568-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f5568-107">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f5568-107">Child Elements</span></span>  
  
|<span data-ttu-id="f5568-108">Элемент</span><span class="sxs-lookup"><span data-stu-id="f5568-108">Element</span></span>|<span data-ttu-id="f5568-109">Описание</span><span class="sxs-lookup"><span data-stu-id="f5568-109">Description</span></span>|  
|-------------|-----------------|  
|[\<defaultPorts>](defaultports.md)|<span data-ttu-id="f5568-110">Коллекция портов по умолчанию со списком конечных точек связи по умолчанию, которые прослушивает клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="f5568-110">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f5568-111">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f5568-111">Parent Elements</span></span>  
  
|<span data-ttu-id="f5568-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="f5568-112">Element</span></span>|<span data-ttu-id="f5568-113">Описание</span><span class="sxs-lookup"><span data-stu-id="f5568-113">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="f5568-114">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="f5568-114">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f5568-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f5568-115">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
