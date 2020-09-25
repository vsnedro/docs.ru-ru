---
title: <pnrpPeerResolver>
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: 0a8cc60226b13552d47faec3a156ed1f59acacb9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181405"
---
# \<pnrpPeerResolver>

<span data-ttu-id="10c76-101">Задает использование распознавателя протокола PNRP (протокола однорангового разрешения имен) в качестве распознавателя.</span><span class="sxs-lookup"><span data-stu-id="10c76-101">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="10c76-102">Этот элемент является необязательным, поскольку протокол PNRP является распознавателем по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="10c76-102">This element is optional because PNRP is the default resolver.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<pnrpResolver>**  
  
## <a name="syntax"></a><span data-ttu-id="10c76-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="10c76-103">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="10c76-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="10c76-104">Attributes and Elements</span></span>  

 <span data-ttu-id="10c76-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="10c76-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="10c76-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="10c76-106">Attributes</span></span>  
  
|<span data-ttu-id="10c76-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="10c76-107">Attribute</span></span>|<span data-ttu-id="10c76-108">Описание</span><span class="sxs-lookup"><span data-stu-id="10c76-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="10c76-109">resolverType</span><span class="sxs-lookup"><span data-stu-id="10c76-109">resolverType</span></span>|<span data-ttu-id="10c76-110">Строка, указывающая распознаватель для использования.</span><span class="sxs-lookup"><span data-stu-id="10c76-110">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="10c76-111">Этот атрибут является необязательным.</span><span class="sxs-lookup"><span data-stu-id="10c76-111">This attribute is optional.</span></span> <span data-ttu-id="10c76-112">Если значение не задано или равно пустой строке, используется протокол PNRP.</span><span class="sxs-lookup"><span data-stu-id="10c76-112">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="10c76-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="10c76-113">Child Elements</span></span>  

 <span data-ttu-id="10c76-114">Нет</span><span class="sxs-lookup"><span data-stu-id="10c76-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="10c76-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="10c76-115">Parent Elements</span></span>  
  
|<span data-ttu-id="10c76-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="10c76-116">Element</span></span>|<span data-ttu-id="10c76-117">Описание</span><span class="sxs-lookup"><span data-stu-id="10c76-117">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="10c76-118">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="10c76-118">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="10c76-119">Пример</span><span class="sxs-lookup"><span data-stu-id="10c76-119">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="see-also"></a><span data-ttu-id="10c76-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="10c76-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>
- <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="10c76-121">Привязки</span><span class="sxs-lookup"><span data-stu-id="10c76-121">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="10c76-122">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="10c76-122">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="10c76-123">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="10c76-123">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="10c76-124">Одноранговые распознаватели</span><span class="sxs-lookup"><span data-stu-id="10c76-124">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
