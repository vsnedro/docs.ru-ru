---
title: <tokenReplayDetection>
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: df512960b522f17dc9247bb5959e246c8c1f15b8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169808"
---
# \<tokenReplayDetection>

<span data-ttu-id="006db-101">Включает обнаружение воспроизведения маркеров и задает срок действия токенов.</span><span class="sxs-lookup"><span data-stu-id="006db-101">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayDetection>**  
  
## <a name="syntax"></a><span data-ttu-id="006db-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="006db-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="006db-103">Type</span><span class="sxs-lookup"><span data-stu-id="006db-103">Type</span></span>  

 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="006db-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="006db-104">Attributes and Elements</span></span>  

 <span data-ttu-id="006db-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="006db-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="006db-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="006db-106">Attributes</span></span>  
  
|<span data-ttu-id="006db-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="006db-107">Attribute</span></span>|<span data-ttu-id="006db-108">Описание</span><span class="sxs-lookup"><span data-stu-id="006db-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="006db-109">Включено</span><span class="sxs-lookup"><span data-stu-id="006db-109">enabled</span></span>|<span data-ttu-id="006db-110">Значение типа, указывающее, включено ли обнаружение воспроизведения маркеров. значение true, чтобы включить обнаружение воспроизведения маркеров.</span><span class="sxs-lookup"><span data-stu-id="006db-110">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="006db-111">експиратионпериод</span><span class="sxs-lookup"><span data-stu-id="006db-111">expirationPeriod</span></span>|<span data-ttu-id="006db-112">Значение типа <xref:System.TimeSpan> , указывающее максимальное количество времени, по истечении которого элемент считается просроченным и удаляется из кэша.</span><span class="sxs-lookup"><span data-stu-id="006db-112">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="006db-113">Дополнительные сведения об указании <xref:System.TimeSpan> значений см. в разделе [значения TimeSpan](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="006db-113">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="006db-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="006db-114">Child Elements</span></span>  

 <span data-ttu-id="006db-115">Нет</span><span class="sxs-lookup"><span data-stu-id="006db-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="006db-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="006db-116">Parent Elements</span></span>  
  
|<span data-ttu-id="006db-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="006db-117">Element</span></span>|<span data-ttu-id="006db-118">Описание</span><span class="sxs-lookup"><span data-stu-id="006db-118">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="006db-119">Задает параметры удостоверений уровня службы.</span><span class="sxs-lookup"><span data-stu-id="006db-119">Specifies service-level identity settings.</span></span>|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="006db-120">Предоставляет конфигурацию для коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="006db-120">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="006db-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="006db-121">Remarks</span></span>  

 <span data-ttu-id="006db-122">`<tokenReplayDetection>`Элемент можно указать на уровне службы в `<identityConfiguration>` элементе или на уровне коллекции обработчика маркеров безопасности под `<securityTokenHandlerConfiguration>` элементом.</span><span class="sxs-lookup"><span data-stu-id="006db-122">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="006db-123">Параметры коллекции обработчиков маркеров переопределяют указанные в службе.</span><span class="sxs-lookup"><span data-stu-id="006db-123">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="006db-124">Тип кэша воспроизведения токенов задается [\<tokenReplayCache>](tokenreplaycache.md) элементом.</span><span class="sxs-lookup"><span data-stu-id="006db-124">The type of the token replay cache is specified by the [\<tokenReplayCache>](tokenreplaycache.md) element.</span></span>
