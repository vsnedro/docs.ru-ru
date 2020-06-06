---
title: <host>
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: b764bc21e9c4555b39c3d096212b6e6bcabb62ff
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855209"
---
# \<host>
<span data-ttu-id="8ad8b-101">Задает параметры узла службы.</span><span class="sxs-lookup"><span data-stu-id="8ad8b-101">Specifies settings for a service host.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<host>**  
  
## <a name="syntax"></a><span data-ttu-id="8ad8b-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8ad8b-102">Syntax</span></span>  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a><span data-ttu-id="8ad8b-103">Type</span><span class="sxs-lookup"><span data-stu-id="8ad8b-103">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8ad8b-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8ad8b-104">Attributes and Elements</span></span>  
 <span data-ttu-id="8ad8b-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8ad8b-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8ad8b-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8ad8b-106">Attributes</span></span>  
 <span data-ttu-id="8ad8b-107">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8ad8b-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8ad8b-108">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8ad8b-108">Child Elements</span></span>  
  
|<span data-ttu-id="8ad8b-109">Элемент</span><span class="sxs-lookup"><span data-stu-id="8ad8b-109">Element</span></span>|<span data-ttu-id="8ad8b-110">Описание</span><span class="sxs-lookup"><span data-stu-id="8ad8b-110">Description</span></span>|  
|-------------|-----------------|  
|[\<baseAddresses>](baseaddresses.md)|<span data-ttu-id="8ad8b-111">Коллекция элементов`baseAddress`, которая задает базовые адреса, используемые узлом службы.</span><span class="sxs-lookup"><span data-stu-id="8ad8b-111">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[\<timeOuts>](timeouts.md)|<span data-ttu-id="8ad8b-112">Элемент конфигурации, задающий допустимый интервал времени для открытия или закрытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="8ad8b-112">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8ad8b-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8ad8b-113">Parent Elements</span></span>  
  
|<span data-ttu-id="8ad8b-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="8ad8b-114">Element</span></span>|<span data-ttu-id="8ad8b-115">Описание</span><span class="sxs-lookup"><span data-stu-id="8ad8b-115">Description</span></span>|  
|-------------|-----------------|  
|[\<service>](service.md)|<span data-ttu-id="8ad8b-116">Задает параметры для службы Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="8ad8b-116">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8ad8b-117">См. также</span><span class="sxs-lookup"><span data-stu-id="8ad8b-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="8ad8b-118">Размещение</span><span class="sxs-lookup"><span data-stu-id="8ad8b-118">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
