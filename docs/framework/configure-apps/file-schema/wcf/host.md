---
title: <host>
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: 524226cbb826486def18c1b3b66c5b4a3c456dec
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185682"
---
# \<host>

<span data-ttu-id="aad2a-101">Задает параметры узла службы.</span><span class="sxs-lookup"><span data-stu-id="aad2a-101">Specifies settings for a service host.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<host>**  
  
## <a name="syntax"></a><span data-ttu-id="aad2a-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aad2a-102">Syntax</span></span>  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a><span data-ttu-id="aad2a-103">Type</span><span class="sxs-lookup"><span data-stu-id="aad2a-103">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aad2a-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="aad2a-104">Attributes and Elements</span></span>  

 <span data-ttu-id="aad2a-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="aad2a-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aad2a-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="aad2a-106">Attributes</span></span>  

 <span data-ttu-id="aad2a-107">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="aad2a-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="aad2a-108">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="aad2a-108">Child Elements</span></span>  
  
|<span data-ttu-id="aad2a-109">Элемент</span><span class="sxs-lookup"><span data-stu-id="aad2a-109">Element</span></span>|<span data-ttu-id="aad2a-110">Описание</span><span class="sxs-lookup"><span data-stu-id="aad2a-110">Description</span></span>|  
|-------------|-----------------|  
|[\<baseAddresses>](baseaddresses.md)|<span data-ttu-id="aad2a-111">Коллекция элементов`baseAddress`, которая задает базовые адреса, используемые узлом службы.</span><span class="sxs-lookup"><span data-stu-id="aad2a-111">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[\<timeOuts>](timeouts.md)|<span data-ttu-id="aad2a-112">Элемент конфигурации, задающий допустимый интервал времени для открытия или закрытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="aad2a-112">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aad2a-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="aad2a-113">Parent Elements</span></span>  
  
|<span data-ttu-id="aad2a-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="aad2a-114">Element</span></span>|<span data-ttu-id="aad2a-115">Описание</span><span class="sxs-lookup"><span data-stu-id="aad2a-115">Description</span></span>|  
|-------------|-----------------|  
|[\<service>](service.md)|<span data-ttu-id="aad2a-116">Задает параметры для службы Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="aad2a-116">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aad2a-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="aad2a-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="aad2a-118">Размещение</span><span class="sxs-lookup"><span data-stu-id="aad2a-118">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
