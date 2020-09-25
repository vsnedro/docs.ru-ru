---
title: <callbackTimeouts>
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: 98523489aacebf910bcf5d81c479819183887dff
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198890"
---
# \<callbackTimeouts>

<span data-ttu-id="04270-101">Задает значение времени ожидания при потоке транзакций от сервера к клиенту в сценарии с дуплексным контрактом обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="04270-101">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<callbackTimeOuts>**  
  
## <a name="syntax"></a><span data-ttu-id="04270-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="04270-102">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="04270-103">Type</span><span class="sxs-lookup"><span data-stu-id="04270-103">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="04270-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="04270-104">Attributes and Elements</span></span>  

 <span data-ttu-id="04270-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="04270-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="04270-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="04270-106">Attributes</span></span>  
  
|<span data-ttu-id="04270-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="04270-107">Attribute</span></span>|<span data-ttu-id="04270-108">Описание</span><span class="sxs-lookup"><span data-stu-id="04270-108">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="04270-109">Значение <xref:System.TimeSpan>, задающее интервал времени, в течение которого транзакции должны завершаться или автоматически прерываться.</span><span class="sxs-lookup"><span data-stu-id="04270-109">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="04270-110">Значение по умолчанию — "00:00:00".</span><span class="sxs-lookup"><span data-stu-id="04270-110">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="04270-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="04270-111">Child Elements</span></span>  

 <span data-ttu-id="04270-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="04270-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="04270-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="04270-113">Parent Elements</span></span>  
  
|<span data-ttu-id="04270-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="04270-114">Element</span></span>|<span data-ttu-id="04270-115">Описание</span><span class="sxs-lookup"><span data-stu-id="04270-115">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="04270-116">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="04270-116">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="04270-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="04270-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
