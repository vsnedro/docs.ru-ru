---
title: Раздел <extensions>
ms.date: 03/30/2017
ms.assetid: 53a59fb6-dede-47ec-9384-b3c2e8f0c1fa
ms.openlocfilehash: f3eb5d446291dfa6b7c8e0f1ee2b6a5cf53c2162
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185786"
---
# <a name="extensions-section"></a><span data-ttu-id="a94ae-102">Раздел \<extensions></span><span class="sxs-lookup"><span data-stu-id="a94ae-102">\<extensions> section</span></span>

<span data-ttu-id="a94ae-103">Данный раздел конфигурации содержит коллекцию расширений, которые позволяют пользователю создавать пользовательские привязки, поведения и другие возможности расширений.</span><span class="sxs-lookup"><span data-stu-id="a94ae-103">This configuration section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<extensions>**  
  
## <a name="syntax"></a><span data-ttu-id="a94ae-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a94ae-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a94ae-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a94ae-105">Attributes and Elements</span></span>  

 <span data-ttu-id="a94ae-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a94ae-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a94ae-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a94ae-107">Attributes</span></span>  

 <span data-ttu-id="a94ae-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a94ae-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a94ae-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a94ae-109">Child Elements</span></span>  
  
|<span data-ttu-id="a94ae-110">Элемент</span><span class="sxs-lookup"><span data-stu-id="a94ae-110">Element</span></span>|<span data-ttu-id="a94ae-111">Описание</span><span class="sxs-lookup"><span data-stu-id="a94ae-111">Description</span></span>|  
|-------------|-----------------|  
|[\<behaviorExtensions>](behaviorextensions.md)|<span data-ttu-id="a94ae-112">Этот раздел содержит дочерние элементы, которые задают расширения поведений, которые позволяют пользователю настроить поведения службы или конечной точки.</span><span class="sxs-lookup"><span data-stu-id="a94ae-112">This section contains child elements that specify behavior extensions, which enable the user to customize service or endpoint behaviors.</span></span>|  
|[\<bindingElementExtensions>](bindingelementextensions.md)|<span data-ttu-id="a94ae-113">В этом разделе описывается, как обеспечивается использование пользовательского элемента привязки в файле конфигурации компьютера или приложения.</span><span class="sxs-lookup"><span data-stu-id="a94ae-113">This section enables the use of a custom binding element from a machine or application configuration file.</span></span>|  
|[\<bindingExtensions>](bindingextensions.md)|<span data-ttu-id="a94ae-114">Этот раздел содержит дочерние элементы, которые задают расширения привязки, которые позволяют пользователю настроить привязки.</span><span class="sxs-lookup"><span data-stu-id="a94ae-114">This section contains child elements that specify binding extensions, which enable the user to customize bindings.</span></span>|  
|[\<endpointExtensions>](endpointextensions.md)|<span data-ttu-id="a94ae-115">Этот раздел содержит дочерние элементы, которые регистрируют стандартные конечные точки.</span><span class="sxs-lookup"><span data-stu-id="a94ae-115">This section contains child elements that registers standard endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a94ae-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a94ae-116">Parent Elements</span></span>  
  
|<span data-ttu-id="a94ae-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="a94ae-117">Element</span></span>|<span data-ttu-id="a94ae-118">Описание</span><span class="sxs-lookup"><span data-stu-id="a94ae-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a94ae-119">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a94ae-119">system.ServiceModel</span></span>|<span data-ttu-id="a94ae-120">Корневой элемент всех элементов конфигурации WCF.</span><span class="sxs-lookup"><span data-stu-id="a94ae-120">The root element of all WCF configuration elements.</span></span>|
