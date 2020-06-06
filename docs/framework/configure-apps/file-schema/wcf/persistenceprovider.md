---
title: <persistenceProvider>
ms.date: 03/30/2017
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
ms.openlocfilehash: 7c4d9ae29ca1e543217d444e05a661b48e2cbb62
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400068"
---
# \<persistenceProvider>
<span data-ttu-id="4a2e1-101">Задает тип используемой реализации поставщика сохраняемости, а также время ожидания операций сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="4a2e1-101">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<persistenceProvider>**  
  
## <a name="syntax"></a><span data-ttu-id="4a2e1-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4a2e1-102">Syntax</span></span>  
  
```xml  
<persistenceProvider persistenceOperationTimeout="TimeSpan"
                     type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4a2e1-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4a2e1-103">Attributes and Elements</span></span>  
 <span data-ttu-id="4a2e1-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4a2e1-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4a2e1-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4a2e1-105">Attributes</span></span>  
  
|<span data-ttu-id="4a2e1-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4a2e1-106">Attribute</span></span>|<span data-ttu-id="4a2e1-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="4a2e1-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4a2e1-108">persistenceOperationTimeout</span><span class="sxs-lookup"><span data-stu-id="4a2e1-108">persistenceOperationTimeout</span></span>|<span data-ttu-id="4a2e1-109">Значение <xref:System.TimeSpan>, которое задает время ожидания, используемое для операций сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="4a2e1-109">A <xref:System.TimeSpan> value that specifies the time-out used for persistence operations.</span></span> <span data-ttu-id="4a2e1-110">Значение по умолчанию — "00:00:30".</span><span class="sxs-lookup"><span data-stu-id="4a2e1-110">The default is "00:00:30".</span></span>|  
|<span data-ttu-id="4a2e1-111">тип</span><span class="sxs-lookup"><span data-stu-id="4a2e1-111">type</span></span>|<span data-ttu-id="4a2e1-112">Строка, указывающая тип используемой фабрики поставщика сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="4a2e1-112">A string that specifies the type of the persistence provider factory to use.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4a2e1-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4a2e1-113">Child Elements</span></span>  
 <span data-ttu-id="4a2e1-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="4a2e1-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4a2e1-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4a2e1-115">Parent Elements</span></span>  
  
|<span data-ttu-id="4a2e1-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="4a2e1-116">Element</span></span>|<span data-ttu-id="4a2e1-117">Описание</span><span class="sxs-lookup"><span data-stu-id="4a2e1-117">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="4a2e1-118">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="4a2e1-118">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a2e1-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="4a2e1-119">Remarks</span></span>  
 <span data-ttu-id="4a2e1-120">Этот элемент задает поставщика сохраняемости, используемого для сериализации состояния службы WCF.</span><span class="sxs-lookup"><span data-stu-id="4a2e1-120">This element specifies the persistence provider to be used to serialize the state of a WCF service.</span></span> <span data-ttu-id="4a2e1-121">Он должен использоваться вместе с атрибутом `wsHttpContextBinding`, который передает сведения о состоянии в HTTP-заголовки.</span><span class="sxs-lookup"><span data-stu-id="4a2e1-121">It should be used together with the `wsHttpContextBinding` which passes state information in HTTP headers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a2e1-122">См. также</span><span class="sxs-lookup"><span data-stu-id="4a2e1-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.PersistenceProviderElement>
- <xref:System.ServiceModel.Persistence.PersistenceProvider>
