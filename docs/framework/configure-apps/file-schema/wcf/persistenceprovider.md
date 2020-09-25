---
title: <persistenceProvider>
ms.date: 03/30/2017
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
ms.openlocfilehash: dbf0ba565d4e3e2d65b4a81eb5d345fa90fb43c7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181431"
---
# \<persistenceProvider>

<span data-ttu-id="d0315-101">Задает тип используемой реализации поставщика сохраняемости, а также время ожидания операций сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="d0315-101">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<persistenceProvider>**  
  
## <a name="syntax"></a><span data-ttu-id="d0315-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d0315-102">Syntax</span></span>  
  
```xml  
<persistenceProvider persistenceOperationTimeout="TimeSpan"
                     type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d0315-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d0315-103">Attributes and Elements</span></span>  

 <span data-ttu-id="d0315-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d0315-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d0315-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d0315-105">Attributes</span></span>  
  
|<span data-ttu-id="d0315-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d0315-106">Attribute</span></span>|<span data-ttu-id="d0315-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d0315-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d0315-108">persistenceOperationTimeout</span><span class="sxs-lookup"><span data-stu-id="d0315-108">persistenceOperationTimeout</span></span>|<span data-ttu-id="d0315-109">Значение <xref:System.TimeSpan>, которое задает время ожидания, используемое для операций сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="d0315-109">A <xref:System.TimeSpan> value that specifies the time-out used for persistence operations.</span></span> <span data-ttu-id="d0315-110">Значение по умолчанию — "00:00:30".</span><span class="sxs-lookup"><span data-stu-id="d0315-110">The default is "00:00:30".</span></span>|  
|<span data-ttu-id="d0315-111">тип</span><span class="sxs-lookup"><span data-stu-id="d0315-111">type</span></span>|<span data-ttu-id="d0315-112">Строка, указывающая тип используемой фабрики поставщика сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="d0315-112">A string that specifies the type of the persistence provider factory to use.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d0315-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d0315-113">Child Elements</span></span>  

 <span data-ttu-id="d0315-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d0315-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d0315-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d0315-115">Parent Elements</span></span>  
  
|<span data-ttu-id="d0315-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="d0315-116">Element</span></span>|<span data-ttu-id="d0315-117">Описание</span><span class="sxs-lookup"><span data-stu-id="d0315-117">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="d0315-118">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="d0315-118">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0315-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="d0315-119">Remarks</span></span>  

 <span data-ttu-id="d0315-120">Этот элемент задает поставщика сохраняемости, используемого для сериализации состояния службы WCF.</span><span class="sxs-lookup"><span data-stu-id="d0315-120">This element specifies the persistence provider to be used to serialize the state of a WCF service.</span></span> <span data-ttu-id="d0315-121">Он должен использоваться вместе с атрибутом `wsHttpContextBinding`, который передает сведения о состоянии в HTTP-заголовки.</span><span class="sxs-lookup"><span data-stu-id="d0315-121">It should be used together with the `wsHttpContextBinding` which passes state information in HTTP headers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0315-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d0315-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.PersistenceProviderElement>
- <xref:System.ServiceModel.Persistence.PersistenceProvider>
