---
title: <serviceTimeouts>
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: 92d3de42daf6f7baf288e3e74242381a60e76618
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153603"
---
# \<serviceTimeouts>

<span data-ttu-id="72456-101">Задает время ожидания для службы.</span><span class="sxs-lookup"><span data-stu-id="72456-101">Specifies the timeout for a service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTimeouts>**  
  
## <a name="syntax"></a><span data-ttu-id="72456-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="72456-102">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="72456-103">Type</span><span class="sxs-lookup"><span data-stu-id="72456-103">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="72456-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="72456-104">Attributes and Elements</span></span>  

 <span data-ttu-id="72456-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="72456-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="72456-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="72456-106">Attributes</span></span>  
  
|<span data-ttu-id="72456-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="72456-107">Attribute</span></span>|<span data-ttu-id="72456-108">Описание</span><span class="sxs-lookup"><span data-stu-id="72456-108">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="72456-109">Значение <xref:System.TimeSpan>, задающее интервал времени, в течение которого транзакция должна дойти от клиента до сервера.</span><span class="sxs-lookup"><span data-stu-id="72456-109">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="72456-110">Значение по умолчанию — "00:00:00".</span><span class="sxs-lookup"><span data-stu-id="72456-110">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="72456-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="72456-111">Child Elements</span></span>  

 <span data-ttu-id="72456-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="72456-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="72456-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="72456-113">Parent Elements</span></span>  
  
|<span data-ttu-id="72456-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="72456-114">Element</span></span>|<span data-ttu-id="72456-115">Описание</span><span class="sxs-lookup"><span data-stu-id="72456-115">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="72456-116">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="72456-116">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="72456-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="72456-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
