---
title: <custom>
ms.date: 03/30/2017
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
ms.openlocfilehash: 598b341e8b09acd11ba215e6add3adf9e44b2b81
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400467"
---
# \<custom>
<span data-ttu-id="e7bcb-101">Задает параметры службы пользовательского распознавателя одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-101">Specifies settings for a custom peer resolver service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<resolver>**](resolver.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<custom>**  
  
## <a name="syntax"></a><span data-ttu-id="e7bcb-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e7bcb-102">Syntax</span></span>  
  
```xml  
<custom address="Uri"
        resolverType="String">
  <headers/>
  <identity/>
</custom>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e7bcb-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e7bcb-103">Attributes and Elements</span></span>  
 <span data-ttu-id="e7bcb-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e7bcb-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e7bcb-105">Attributes</span></span>  
  
|<span data-ttu-id="e7bcb-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e7bcb-106">Attribute</span></span>|<span data-ttu-id="e7bcb-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="e7bcb-107">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="e7bcb-108">URI, указывающий адрес конечной точки однорангового узла, на котором размещается пользовательская служба распознавателя одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-108">A URI that specifies the endpoint address of the peer node that hosts the custom peer resolver service.</span></span>|  
|`resolverType`|<span data-ttu-id="e7bcb-109">Строка, задающая тип пользовательской службы распознавателя одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-109">A string that specifies the type of the custom peer resolver service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e7bcb-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e7bcb-110">Child Elements</span></span>  
  
|<span data-ttu-id="e7bcb-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="e7bcb-111">Element</span></span>|<span data-ttu-id="e7bcb-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e7bcb-112">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="e7bcb-113">Задает идентификатор пользовательских распознавателей одноранговых узлов, настроенных для данного элемента.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-113">Specifies the identity for custom peer resolvers configured with this element.</span></span> <span data-ttu-id="e7bcb-114">Это элемент типа <xref:System.ServiceModel.Configuration.IdentityElement>.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-114">This element is of type <xref:System.ServiceModel.Configuration.IdentityElement>.</span></span>|  
|[\<headers>](headers-element.md)|<span data-ttu-id="e7bcb-115">Коллекция заголовков адреса, используемых для сообщений SOAP, обрабатываемых пользовательским распознавателем одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-115">A collection of address header used for SOAP messages handled by the custom peer resolver.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e7bcb-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e7bcb-116">Parent Elements</span></span>  
  
|<span data-ttu-id="e7bcb-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="e7bcb-117">Element</span></span>|<span data-ttu-id="e7bcb-118">Описание</span><span class="sxs-lookup"><span data-stu-id="e7bcb-118">Description</span></span>|  
|-------------|-----------------|  
|[\<resolver>](resolver.md)|<span data-ttu-id="e7bcb-119">Распознаватель одноранговых узлов, используемый для разрешения идентификатора сетки с IP-адресами в набор адресов одноранговых узлов, представляющих несколько узлов, входящих в сетку.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-119">A peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7bcb-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="e7bcb-120">Remarks</span></span>  
 <span data-ttu-id="e7bcb-121">Этот элемент определяет основные параметры пользовательской службы распознавателя одноранговых узлов, включая адрес конечной точки однорангового узла, на котором размещена служба, и любые специальные параметры привязки.</span><span class="sxs-lookup"><span data-stu-id="e7bcb-121">This element defines the basic settings for a custom peer resolver service, including the endpoint address of the peer hosting the service and any specific binding settings.</span></span> <span data-ttu-id="e7bcb-122">Дополнительные сведения о создании пользовательского сопоставителя см. в разделе [Добавление пользовательского сопоставителя в приложение PeerChannel](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="e7bcb-122">For more information on creating a custom resolver, see [Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7bcb-123">См. также</span><span class="sxs-lookup"><span data-stu-id="e7bcb-123">See also</span></span>

- <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>
- <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>
- <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>
- <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>
- [<span data-ttu-id="e7bcb-124">Одноранговые распознаватели</span><span class="sxs-lookup"><span data-stu-id="e7bcb-124">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="e7bcb-125">[Добавление в приложение PeerChannel пользовательского распознавателя](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="e7bcb-125">[Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span></span>
