---
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 9f3a95fd0a39f199eaf13c7509aff22caa0e3b66
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251786"
---
# \<tokenReplayCache>
<span data-ttu-id="1e544-101">Регистрирует кэш воспроизведения токенов с помощью службы или коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="1e544-101">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayCache>**  
  
## <a name="syntax"></a><span data-ttu-id="1e544-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1e544-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1e544-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1e544-103">Attributes and Elements</span></span>  
 <span data-ttu-id="1e544-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1e544-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1e544-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1e544-105">Attributes</span></span>  
  
|<span data-ttu-id="1e544-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="1e544-106">Attribute</span></span>|<span data-ttu-id="1e544-107">Описание</span><span class="sxs-lookup"><span data-stu-id="1e544-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1e544-108">type</span><span class="sxs-lookup"><span data-stu-id="1e544-108">type</span></span>|<span data-ttu-id="1e544-109">Тип, производный от <xref:System.IdentityModel.Tokens.TokenReplayCache> класса.</span><span class="sxs-lookup"><span data-stu-id="1e544-109">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="1e544-110">Дополнительные сведения о том, как указать пользовательский параметр `type` , см. в разделе [ссылки на пользовательские типы].</span><span class="sxs-lookup"><span data-stu-id="1e544-110">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="1e544-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1e544-111">Child Elements</span></span>  
 <span data-ttu-id="1e544-112">Нет</span><span class="sxs-lookup"><span data-stu-id="1e544-112">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1e544-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1e544-113">Parent Elements</span></span>  
  
|<span data-ttu-id="1e544-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="1e544-114">Element</span></span>|<span data-ttu-id="1e544-115">Описание</span><span class="sxs-lookup"><span data-stu-id="1e544-115">Description</span></span>|  
|-------------|-----------------|  
|[\<caches>](caches.md)|<span data-ttu-id="1e544-116">Регистрирует кэши, используемые службой или коллекцией обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="1e544-116">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e544-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="1e544-117">Remarks</span></span>  
 <span data-ttu-id="1e544-118">Кэш воспроизведения токенов используется для обнаружения воспроизводимых токенов.</span><span class="sxs-lookup"><span data-stu-id="1e544-118">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="1e544-119">Обнаружение воспроизведения токенов включается [\<tokenReplayDetection>](tokenreplaydetection.md) элементом, который также указывает максимальное время окончания срока действия токенов.</span><span class="sxs-lookup"><span data-stu-id="1e544-119">Token replay detection is enabled by the [\<tokenReplayDetection>](tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e544-120">Пример</span><span class="sxs-lookup"><span data-stu-id="1e544-120">Example</span></span>  
 <span data-ttu-id="1e544-121">В следующем коде XML показана конфигурация пользовательского кэша для обнаружения воспроизводимых токенов.</span><span class="sxs-lookup"><span data-stu-id="1e544-121">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1e544-122">См. также</span><span class="sxs-lookup"><span data-stu-id="1e544-122">See also</span></span>

- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [\<tokenReplayDetection>](tokenreplaydetection.md)
