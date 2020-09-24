---
title: <services>
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: b8cb5075ba41bed5a22b152a231c7213b326a62f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153720"
---
# \<services>

<span data-ttu-id="94537-101">Службы задаются в разделе `services` файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="94537-101">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="94537-102">Для каждой службы используется собственный раздел конфигурации `service`.</span><span class="sxs-lookup"><span data-stu-id="94537-102">Each service has its own `service` configuration section.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<services>**  
  
## <a name="syntax"></a><span data-ttu-id="94537-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="94537-103">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="94537-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="94537-104">Attributes and Elements</span></span>  

 <span data-ttu-id="94537-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="94537-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="94537-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="94537-106">Attributes</span></span>  

 <span data-ttu-id="94537-107">Нет</span><span class="sxs-lookup"><span data-stu-id="94537-107">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="94537-108">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="94537-108">Child Elements</span></span>  
  
|<span data-ttu-id="94537-109">Элемент</span><span class="sxs-lookup"><span data-stu-id="94537-109">Element</span></span>|<span data-ttu-id="94537-110">Описание</span><span class="sxs-lookup"><span data-stu-id="94537-110">Description</span></span>|  
|-------------|-----------------|  
|[\<service>](service.md)|<span data-ttu-id="94537-111">Определяет контракт службы, поведение и конечные точки конкретной службы.</span><span class="sxs-lookup"><span data-stu-id="94537-111">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="94537-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="94537-112">Parent Elements</span></span>  
  
|<span data-ttu-id="94537-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="94537-113">Element</span></span>|<span data-ttu-id="94537-114">Описание</span><span class="sxs-lookup"><span data-stu-id="94537-114">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel>](system-servicemodel.md)|<span data-ttu-id="94537-115">Корневой элемент всех элементов конфигурации Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="94537-115">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="94537-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="94537-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServicesSection>
