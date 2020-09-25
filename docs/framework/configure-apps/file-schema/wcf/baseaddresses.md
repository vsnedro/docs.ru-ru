---
title: <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 3b6cebd178ac5cd30fa034bd961d2d08075771d2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201542"
---
# \<baseAddresses>

<span data-ttu-id="75fac-101">Представляет коллекцию элементов `baseAddress`, которые являются базовыми адресам для узла службы в резидентной среде.</span><span class="sxs-lookup"><span data-stu-id="75fac-101">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="75fac-102">Если указан базовый адрес, конечные точки можно настроить, используя относительные (по отношению к базовому адресу) адреса.</span><span class="sxs-lookup"><span data-stu-id="75fac-102">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<baseAddresses>**  
  
## <a name="syntax"></a><span data-ttu-id="75fac-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="75fac-103">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="75fac-104">Type</span><span class="sxs-lookup"><span data-stu-id="75fac-104">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="75fac-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="75fac-105">Attributes and Elements</span></span>  

 <span data-ttu-id="75fac-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="75fac-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="75fac-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="75fac-107">Attributes</span></span>  

 <span data-ttu-id="75fac-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="75fac-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="75fac-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="75fac-109">Child Elements</span></span>  
  
|<span data-ttu-id="75fac-110">Элемент</span><span class="sxs-lookup"><span data-stu-id="75fac-110">Element</span></span>|<span data-ttu-id="75fac-111">Описание</span><span class="sxs-lookup"><span data-stu-id="75fac-111">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-baseaddresses.md)|<span data-ttu-id="75fac-112">Элемент конфигурации, который задает базовые адреса, используемые узлом службы.</span><span class="sxs-lookup"><span data-stu-id="75fac-112">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="75fac-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="75fac-113">Parent Elements</span></span>  
  
|<span data-ttu-id="75fac-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="75fac-114">Element</span></span>|<span data-ttu-id="75fac-115">Описание</span><span class="sxs-lookup"><span data-stu-id="75fac-115">Description</span></span>|  
|-------------|-----------------|  
|[\<host>](host.md)|<span data-ttu-id="75fac-116">Элемент конфигурации, который задает параметры узла службы.</span><span class="sxs-lookup"><span data-stu-id="75fac-116">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="75fac-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="75fac-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="75fac-118">Размещение</span><span class="sxs-lookup"><span data-stu-id="75fac-118">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
