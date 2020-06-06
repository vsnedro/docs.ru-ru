---
title: Раздел <extensions>
ms.date: 03/30/2017
ms.assetid: 53a59fb6-dede-47ec-9384-b3c2e8f0c1fa
ms.openlocfilehash: 35621acaf96a80ffa3ffe4a3c6605143c48995a5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855352"
---
# <a name="extensions-section"></a><span data-ttu-id="b6e4b-102">Раздел \<extensions></span><span class="sxs-lookup"><span data-stu-id="b6e4b-102">\<extensions> section</span></span>
<span data-ttu-id="b6e4b-103">Данный раздел конфигурации содержит коллекцию расширений, которые позволяют пользователю создавать пользовательские привязки, поведения и другие возможности расширений.</span><span class="sxs-lookup"><span data-stu-id="b6e4b-103">This configuration section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<extensions>**  
  
## <a name="syntax"></a><span data-ttu-id="b6e4b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b6e4b-104">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <extensions>
    <bindingExtensions>
    </bindingExtensions>
    <behaviorExtensions>
    </behaviorExtensions>
    <bindingElementExtensions>
    </bindingElementExtensions>
    <endpointExtensions>
    </endpointExtensions>
  </extensions>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b6e4b-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b6e4b-105">Attributes and Elements</span></span>  
 <span data-ttu-id="b6e4b-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b6e4b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b6e4b-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b6e4b-107">Attributes</span></span>  
 <span data-ttu-id="b6e4b-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b6e4b-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b6e4b-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b6e4b-109">Child Elements</span></span>  
  
|<span data-ttu-id="b6e4b-110">Элемент</span><span class="sxs-lookup"><span data-stu-id="b6e4b-110">Element</span></span>|<span data-ttu-id="b6e4b-111">Описание</span><span class="sxs-lookup"><span data-stu-id="b6e4b-111">Description</span></span>|  
|-------------|-----------------|  
|[\<behaviorExtensions>](behaviorextensions.md)|<span data-ttu-id="b6e4b-112">Этот раздел содержит дочерние элементы, которые задают расширения поведений, которые позволяют пользователю настроить поведения службы или конечной точки.</span><span class="sxs-lookup"><span data-stu-id="b6e4b-112">This section contains child elements that specify behavior extensions, which enable the user to customize service or endpoint behaviors.</span></span>|  
|[\<bindingElementExtensions>](bindingelementextensions.md)|<span data-ttu-id="b6e4b-113">В этом разделе описывается, как обеспечивается использование пользовательского элемента привязки в файле конфигурации компьютера или приложения.</span><span class="sxs-lookup"><span data-stu-id="b6e4b-113">This section enables the use of a custom binding element from a machine or application configuration file.</span></span>|  
|[\<bindingExtensions>](bindingextensions.md)|<span data-ttu-id="b6e4b-114">Этот раздел содержит дочерние элементы, которые задают расширения привязки, которые позволяют пользователю настроить привязки.</span><span class="sxs-lookup"><span data-stu-id="b6e4b-114">This section contains child elements that specify binding extensions, which enable the user to customize bindings.</span></span>|  
|[\<endpointExtensions>](endpointextensions.md)|<span data-ttu-id="b6e4b-115">Этот раздел содержит дочерние элементы, которые регистрируют стандартные конечные точки.</span><span class="sxs-lookup"><span data-stu-id="b6e4b-115">This section contains child elements that registers standard endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b6e4b-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b6e4b-116">Parent Elements</span></span>  
  
|<span data-ttu-id="b6e4b-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="b6e4b-117">Element</span></span>|<span data-ttu-id="b6e4b-118">Описание</span><span class="sxs-lookup"><span data-stu-id="b6e4b-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b6e4b-119">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b6e4b-119">system.ServiceModel</span></span>|<span data-ttu-id="b6e4b-120">Корневой элемент всех элементов конфигурации WCF.</span><span class="sxs-lookup"><span data-stu-id="b6e4b-120">The root element of all WCF configuration elements.</span></span>|
