---
title: <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 9b3ed6b39f1743249925d5b6d9a47845c87983bc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850209"
---
# \<baseAddresses>
<span data-ttu-id="87058-101">Представляет коллекцию элементов `baseAddress`, которые являются базовыми адресам для узла службы в резидентной среде.</span><span class="sxs-lookup"><span data-stu-id="87058-101">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="87058-102">Если указан базовый адрес, конечные точки можно настроить, используя относительные (по отношению к базовому адресу) адреса.</span><span class="sxs-lookup"><span data-stu-id="87058-102">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<baseAddresses>**  
  
## <a name="syntax"></a><span data-ttu-id="87058-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="87058-103">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="87058-104">Type</span><span class="sxs-lookup"><span data-stu-id="87058-104">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="87058-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="87058-105">Attributes and Elements</span></span>  
 <span data-ttu-id="87058-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="87058-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="87058-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="87058-107">Attributes</span></span>  
 <span data-ttu-id="87058-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="87058-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="87058-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="87058-109">Child Elements</span></span>  
  
|<span data-ttu-id="87058-110">Элемент</span><span class="sxs-lookup"><span data-stu-id="87058-110">Element</span></span>|<span data-ttu-id="87058-111">Описание</span><span class="sxs-lookup"><span data-stu-id="87058-111">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-baseaddresses.md)|<span data-ttu-id="87058-112">Элемент конфигурации, который задает базовые адреса, используемые узлом службы.</span><span class="sxs-lookup"><span data-stu-id="87058-112">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="87058-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="87058-113">Parent Elements</span></span>  
  
|<span data-ttu-id="87058-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="87058-114">Element</span></span>|<span data-ttu-id="87058-115">Описание</span><span class="sxs-lookup"><span data-stu-id="87058-115">Description</span></span>|  
|-------------|-----------------|  
|[\<host>](host.md)|<span data-ttu-id="87058-116">Элемент конфигурации, который задает параметры узла службы.</span><span class="sxs-lookup"><span data-stu-id="87058-116">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="87058-117">См. также</span><span class="sxs-lookup"><span data-stu-id="87058-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="87058-118">Размещение</span><span class="sxs-lookup"><span data-stu-id="87058-118">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
