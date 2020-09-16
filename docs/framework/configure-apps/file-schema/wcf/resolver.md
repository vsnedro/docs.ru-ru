---
title: <resolver>
ms.date: 03/30/2017
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
ms.openlocfilehash: c6f5db96ded422493b819d4d75dda6abc9a1676e
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558866"
---
# \<resolver>
<span data-ttu-id="c67ed-101">Указывает распознаватель одноранговых узлов, используемый для распознавания идентификатора сетки с IP-адресами в набор адресов одноранговых узлов, которые представляют несколько узлов, входящих в сетку.</span><span class="sxs-lookup"><span data-stu-id="c67ed-101">Specifies a peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<resolver>**  
  
## <a name="syntax"></a><span data-ttu-id="c67ed-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c67ed-102">Syntax</span></span>  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"
          referralPolicy="DoNotShare/Service/Share">
</resolver>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c67ed-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c67ed-103">Attributes and Elements</span></span>  
 <span data-ttu-id="c67ed-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c67ed-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c67ed-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c67ed-105">Attributes</span></span>  
  
|<span data-ttu-id="c67ed-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c67ed-106">Attribute</span></span>|<span data-ttu-id="c67ed-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c67ed-107">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="c67ed-108">Строка, которая указывает, зависит ли экземпляр распознавателя одноранговых узлов, связанный с данной службой, от PNRP, является ли он пользовательским распознавателем или определяется автоматически.</span><span class="sxs-lookup"><span data-stu-id="c67ed-108">A string that specifies whether the peer resolver instance associated with this service is either PNRP-specific, a custom resolver, or automatically determined.</span></span> <span data-ttu-id="c67ed-109">Это атрибут типа <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span><span class="sxs-lookup"><span data-stu-id="c67ed-109">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span></span>|  
|`referralPolicy`|<span data-ttu-id="c67ed-110">Строка, указывающая, каким образом отсылки распределяются между одноранговыми узлами.</span><span class="sxs-lookup"><span data-stu-id="c67ed-110">A string that specifies the way referrals are shared among peers.</span></span> <span data-ttu-id="c67ed-111">Это атрибут типа <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span><span class="sxs-lookup"><span data-stu-id="c67ed-111">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c67ed-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c67ed-112">Child Elements</span></span>  
  
|<span data-ttu-id="c67ed-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="c67ed-113">Element</span></span>|<span data-ttu-id="c67ed-114">Описание</span><span class="sxs-lookup"><span data-stu-id="c67ed-114">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers.md)|<span data-ttu-id="c67ed-115">Задает параметры службы пользовательского распознавателя одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="c67ed-115">Specifies settings for a custom peer resolver service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c67ed-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c67ed-116">Parent Elements</span></span>  
  
|<span data-ttu-id="c67ed-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="c67ed-117">Element</span></span>|<span data-ttu-id="c67ed-118">Описание</span><span class="sxs-lookup"><span data-stu-id="c67ed-118">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="c67ed-119">Определяет все возможности привязки [\<netPeerTcpBinding>](netpeertcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="c67ed-119">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c67ed-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="c67ed-120">Remarks</span></span>  
 <span data-ttu-id="c67ed-121">Распознаватель одноранговых узлов представляет собой службу обнаружения, используемую одноранговыми каналами для поиска одноранговых узлов, участвующих в сетке с IP-адресами.</span><span class="sxs-lookup"><span data-stu-id="c67ed-121">A peer name resolver is a discovery service used by peer channels to find peer nodes that participate in a peer mesh.</span></span> <span data-ttu-id="c67ed-122">Он также используется для «регистрации» узла в сетке с IP-адресами; с помощью такого механизма одноранговый узел становится известным и доступным из сетки с IP-адресами.</span><span class="sxs-lookup"><span data-stu-id="c67ed-122">It is also used to "register" a node with a peer mesh, the mechanism by which the peer node becomes known and available from the peer mesh.</span></span> <span data-ttu-id="c67ed-123">Дополнительные сведения об одноранговых решениях см. в разделе [одноранговые арбитры конфликтов](../../../wcf/feature-details/peer-resolvers.md).</span><span class="sxs-lookup"><span data-stu-id="c67ed-123">For more information on peer resolvers, see [Peer Resolvers](../../../wcf/feature-details/peer-resolvers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c67ed-124">См. также</span><span class="sxs-lookup"><span data-stu-id="c67ed-124">See also</span></span>

- <xref:System.ServiceModel.PeerResolver>
- <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>
- <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>
- <xref:System.ServiceModel.Configuration.PeerResolverElement>
- [<span data-ttu-id="c67ed-125">Одноранговые распознаватели</span><span class="sxs-lookup"><span data-stu-id="c67ed-125">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="c67ed-126">[Добавление в приложение PeerChannel пользовательского распознавателя](/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="c67ed-126">[Adding a Custom Resolver to a PeerChannel Application](/previous-versions/ms730105(v=vs.90))</span></span>
