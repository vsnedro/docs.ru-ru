---
title: <serviceTimeouts>
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: 801a7aaf1f0d0fa267fa8cca3d2e7fd02919c475
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399552"
---
# \<serviceTimeouts>
<span data-ttu-id="0667a-101">Задает время ожидания для службы.</span><span class="sxs-lookup"><span data-stu-id="0667a-101">Specifies the timeout for a service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTimeouts>**  
  
## <a name="syntax"></a><span data-ttu-id="0667a-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0667a-102">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="0667a-103">Type</span><span class="sxs-lookup"><span data-stu-id="0667a-103">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0667a-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0667a-104">Attributes and Elements</span></span>  
 <span data-ttu-id="0667a-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0667a-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0667a-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0667a-106">Attributes</span></span>  
  
|<span data-ttu-id="0667a-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0667a-107">Attribute</span></span>|<span data-ttu-id="0667a-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="0667a-108">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="0667a-109">Значение <xref:System.TimeSpan>, задающее интервал времени, в течение которого транзакция должна дойти от клиента до сервера.</span><span class="sxs-lookup"><span data-stu-id="0667a-109">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="0667a-110">Значение по умолчанию — "00:00:00".</span><span class="sxs-lookup"><span data-stu-id="0667a-110">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0667a-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0667a-111">Child Elements</span></span>  
 <span data-ttu-id="0667a-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0667a-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0667a-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0667a-113">Parent Elements</span></span>  
  
|<span data-ttu-id="0667a-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="0667a-114">Element</span></span>|<span data-ttu-id="0667a-115">Описание</span><span class="sxs-lookup"><span data-stu-id="0667a-115">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="0667a-116">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="0667a-116">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0667a-117">См. также</span><span class="sxs-lookup"><span data-stu-id="0667a-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
