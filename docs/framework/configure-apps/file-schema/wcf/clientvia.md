---
title: <clientVia>
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: 5e62201a38dc4dc251996531a4af5f294dd2395f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151107"
---
# \<clientVia>

<span data-ttu-id="3e1bd-101">Задает универсальный код ресурса (URI), для которого необходимо создать канал транспорта.</span><span class="sxs-lookup"><span data-stu-id="3e1bd-101">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="3e1bd-102">Для получения дополнительной информации см. <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="3e1bd-102">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientVia>**  
  
## <a name="syntax"></a><span data-ttu-id="3e1bd-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3e1bd-103">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3e1bd-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3e1bd-104">Attributes and Elements</span></span>  

 <span data-ttu-id="3e1bd-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3e1bd-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3e1bd-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3e1bd-106">Attributes</span></span>  
  
|<span data-ttu-id="3e1bd-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3e1bd-107">Attribute</span></span>|<span data-ttu-id="3e1bd-108">Описание</span><span class="sxs-lookup"><span data-stu-id="3e1bd-108">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="3e1bd-109">Строка, задающая универсальный код ресурса (URI), который указывает маршрут для сообщения.</span><span class="sxs-lookup"><span data-stu-id="3e1bd-109">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3e1bd-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3e1bd-110">Child Elements</span></span>  

 <span data-ttu-id="3e1bd-111">Нет</span><span class="sxs-lookup"><span data-stu-id="3e1bd-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3e1bd-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3e1bd-112">Parent Elements</span></span>  
  
|<span data-ttu-id="3e1bd-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="3e1bd-113">Element</span></span>|<span data-ttu-id="3e1bd-114">Описание</span><span class="sxs-lookup"><span data-stu-id="3e1bd-114">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="3e1bd-115">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="3e1bd-115">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3e1bd-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3e1bd-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
