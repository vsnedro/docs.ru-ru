---
title: <timeOuts>
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: b9c67ac03f0eb73a2a4cdd43ab48fe12871a1cc3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854964"
---
# \<timeOuts>
<span data-ttu-id="5a9f6-101">Элемент конфигурации, который задает допустимый интервал времени для открытия или закрытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="5a9f6-101">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<timeOuts>**  
  
## <a name="syntax"></a><span data-ttu-id="5a9f6-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5a9f6-102">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5a9f6-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5a9f6-103">Attributes and Elements</span></span>  
 <span data-ttu-id="5a9f6-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5a9f6-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5a9f6-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5a9f6-105">Attributes</span></span>  
  
|<span data-ttu-id="5a9f6-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5a9f6-106">Attribute</span></span>|<span data-ttu-id="5a9f6-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="5a9f6-107">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="5a9f6-108">Значение <xref:System.TimeSpan>, которое задает временной интервал, выделенный для операции закрытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="5a9f6-108">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="5a9f6-109">Значение <xref:System.TimeSpan>, которое задает временной интервал, выделенный для операции открытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="5a9f6-109">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5a9f6-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5a9f6-110">Child Elements</span></span>  
 <span data-ttu-id="5a9f6-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5a9f6-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5a9f6-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5a9f6-112">Parent Elements</span></span>  
  
|<span data-ttu-id="5a9f6-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="5a9f6-113">Element</span></span>|<span data-ttu-id="5a9f6-114">Описание</span><span class="sxs-lookup"><span data-stu-id="5a9f6-114">Description</span></span>|  
|-------------|-----------------|  
|[\<host>](host.md)|<span data-ttu-id="5a9f6-115">Элемент конфигурации, который задает параметры узла службы.</span><span class="sxs-lookup"><span data-stu-id="5a9f6-115">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5a9f6-116">См. также</span><span class="sxs-lookup"><span data-stu-id="5a9f6-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="5a9f6-117">Размещение</span><span class="sxs-lookup"><span data-stu-id="5a9f6-117">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
