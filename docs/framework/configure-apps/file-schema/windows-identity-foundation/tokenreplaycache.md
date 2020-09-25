---
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 5e695bb56b59da40ce9e83f9f4f77d0d22d0b40f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202426"
---
# \<tokenReplayCache>

<span data-ttu-id="94f8f-101">Регистрирует кэш воспроизведения токенов с помощью службы или коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="94f8f-101">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayCache>**  
  
## <a name="syntax"></a><span data-ttu-id="94f8f-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="94f8f-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <tokenReplayCache type=xs:string>  
      </tokenReplayCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="94f8f-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="94f8f-103">Attributes and Elements</span></span>  

 <span data-ttu-id="94f8f-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="94f8f-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="94f8f-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="94f8f-105">Attributes</span></span>  
  
|<span data-ttu-id="94f8f-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="94f8f-106">Attribute</span></span>|<span data-ttu-id="94f8f-107">Описание</span><span class="sxs-lookup"><span data-stu-id="94f8f-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="94f8f-108">type</span><span class="sxs-lookup"><span data-stu-id="94f8f-108">type</span></span>|<span data-ttu-id="94f8f-109">Тип, производный от <xref:System.IdentityModel.Tokens.TokenReplayCache> класса.</span><span class="sxs-lookup"><span data-stu-id="94f8f-109">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="94f8f-110">Дополнительные сведения о том, как указать пользовательский параметр `type` , см. в разделе [ссылки на пользовательские типы].</span><span class="sxs-lookup"><span data-stu-id="94f8f-110">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="94f8f-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="94f8f-111">Child Elements</span></span>  

 <span data-ttu-id="94f8f-112">Нет</span><span class="sxs-lookup"><span data-stu-id="94f8f-112">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="94f8f-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="94f8f-113">Parent Elements</span></span>  
  
|<span data-ttu-id="94f8f-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="94f8f-114">Element</span></span>|<span data-ttu-id="94f8f-115">Описание</span><span class="sxs-lookup"><span data-stu-id="94f8f-115">Description</span></span>|  
|-------------|-----------------|  
|[\<caches>](caches.md)|<span data-ttu-id="94f8f-116">Регистрирует кэши, используемые службой или коллекцией обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="94f8f-116">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94f8f-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="94f8f-117">Remarks</span></span>  

 <span data-ttu-id="94f8f-118">Кэш воспроизведения токенов используется для обнаружения воспроизводимых токенов.</span><span class="sxs-lookup"><span data-stu-id="94f8f-118">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="94f8f-119">Обнаружение воспроизведения токенов включается [\<tokenReplayDetection>](tokenreplaydetection.md) элементом, который также указывает максимальное время окончания срока действия токенов.</span><span class="sxs-lookup"><span data-stu-id="94f8f-119">Token replay detection is enabled by the [\<tokenReplayDetection>](tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94f8f-120">Пример</span><span class="sxs-lookup"><span data-stu-id="94f8f-120">Example</span></span>  

 <span data-ttu-id="94f8f-121">В следующем коде XML показана конфигурация пользовательского кэша для обнаружения воспроизводимых токенов.</span><span class="sxs-lookup"><span data-stu-id="94f8f-121">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="94f8f-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="94f8f-122">See also</span></span>

- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [\<tokenReplayDetection>](tokenreplaydetection.md)
