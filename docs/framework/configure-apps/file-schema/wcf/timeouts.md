---
title: <timeOuts>
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: f7e513bb5c486fa5f7c39c9b2e3cfcd26bd7c219
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157100"
---
# \<timeOuts>

<span data-ttu-id="b4d77-101">Элемент конфигурации, который задает допустимый интервал времени для открытия или закрытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="b4d77-101">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<timeOuts>**  
  
## <a name="syntax"></a><span data-ttu-id="b4d77-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b4d77-102">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b4d77-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b4d77-103">Attributes and Elements</span></span>  

 <span data-ttu-id="b4d77-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b4d77-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b4d77-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b4d77-105">Attributes</span></span>  
  
|<span data-ttu-id="b4d77-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b4d77-106">Attribute</span></span>|<span data-ttu-id="b4d77-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b4d77-107">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="b4d77-108">Значение <xref:System.TimeSpan>, которое задает временной интервал, выделенный для операции закрытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="b4d77-108">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="b4d77-109">Значение <xref:System.TimeSpan>, которое задает временной интервал, выделенный для операции открытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="b4d77-109">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b4d77-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b4d77-110">Child Elements</span></span>  

 <span data-ttu-id="b4d77-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b4d77-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b4d77-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b4d77-112">Parent Elements</span></span>  
  
|<span data-ttu-id="b4d77-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="b4d77-113">Element</span></span>|<span data-ttu-id="b4d77-114">Описание</span><span class="sxs-lookup"><span data-stu-id="b4d77-114">Description</span></span>|  
|-------------|-----------------|  
|[\<host>](host.md)|<span data-ttu-id="b4d77-115">Элемент конфигурации, который задает параметры узла службы.</span><span class="sxs-lookup"><span data-stu-id="b4d77-115">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b4d77-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b4d77-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="b4d77-117">Размещение</span><span class="sxs-lookup"><span data-stu-id="b4d77-117">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
