---
title: <oneWay>
ms.date: 03/30/2017
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
ms.openlocfilehash: 92cd6b280305c223ee125a45724691c5205ce3c1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195016"
---
# \<oneWay>

<span data-ttu-id="c0b38-101">Включает поддержку маршрутизации пакетов и использования односторонних методов для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="c0b38-101">Enables packet routing and the use of one-way methods for a custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oneWay>**  
  
## <a name="syntax"></a><span data-ttu-id="c0b38-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c0b38-102">Syntax</span></span>  
  
```xml  
<oneWay packetRoutable="Boolean">
  <channelPoolSettings idleTimeout="TimeSpan"
                       leaseTimeout="TimeSpan"
                       maxOutboundConnectionsPerEndpoint="Integer" />
</oneWay>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c0b38-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c0b38-103">Attributes and Elements</span></span>  

 <span data-ttu-id="c0b38-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c0b38-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c0b38-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c0b38-105">Attributes</span></span>  
  
|<span data-ttu-id="c0b38-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c0b38-106">Attribute</span></span>|<span data-ttu-id="c0b38-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c0b38-107">Description</span></span>|  
|---------------|-----------------|  
|`packetRoutable`|<span data-ttu-id="c0b38-108">Логическое значение, указывающее, включена ли поддержка маршрутизации пакетов.</span><span class="sxs-lookup"><span data-stu-id="c0b38-108">A Boolean value that specifies whether packet routing is enabled.</span></span> <span data-ttu-id="c0b38-109">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="c0b38-109">The default is `false`.</span></span>|  
|`MaxAcceptedChannels`|<span data-ttu-id="c0b38-110">Целое число, указывающее максимальное количество принимаемых каналов.</span><span class="sxs-lookup"><span data-stu-id="c0b38-110">An integer that specifies the maximum number of channels that can be accepted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c0b38-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c0b38-111">Child Elements</span></span>  
  
|<span data-ttu-id="c0b38-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="c0b38-112">Element</span></span>|<span data-ttu-id="c0b38-113">Описание</span><span class="sxs-lookup"><span data-stu-id="c0b38-113">Description</span></span>|  
|-------------|-----------------|  
|[\<channelPoolSettings>](channelpoolsettings.md)|<span data-ttu-id="c0b38-114">Объект <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>, содержащий свойства пула каналов для текущего канала.</span><span class="sxs-lookup"><span data-stu-id="c0b38-114">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> object that contains properties of the channel pool for the current channel.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c0b38-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c0b38-115">Parent Elements</span></span>  
  
|<span data-ttu-id="c0b38-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="c0b38-116">Element</span></span>|<span data-ttu-id="c0b38-117">Описание</span><span class="sxs-lookup"><span data-stu-id="c0b38-117">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="c0b38-118">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="c0b38-118">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0b38-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="c0b38-119">Remarks</span></span>  

 <span data-ttu-id="c0b38-120">Чтобы включить поддержку маршрутизации пакетов, необходим уровень одностороннего преобразования, предоставляемый данным элементом.</span><span class="sxs-lookup"><span data-stu-id="c0b38-120">To enable packet routing, a one-way conversion layer is required, which this element provides.</span></span> <span data-ttu-id="c0b38-121">Пользователь может создавать пользовательские привязки, которые выполняют наложение данной привязки на транспорт с поддержкой сеансов или типа «запрос-отклик», чтобы включить для него поддержку маршрутизации пакетов.</span><span class="sxs-lookup"><span data-stu-id="c0b38-121">A user can create a custom binding that layers this binding over a session-aware or request-reply transport to make it packet routable.</span></span> <span data-ttu-id="c0b38-122">Этот элемент также полезен, если необходимо предоставить односторонние методы более естественным образом.</span><span class="sxs-lookup"><span data-stu-id="c0b38-122">This element is also useful when you want to expose one-way methods in a more native fashion.</span></span> <span data-ttu-id="c0b38-123">К данному уровню могут применяться дополнительные преобразования, например Composite Duplex и Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="c0b38-123">More transformations can be applied over this layer, such as Composite Duplex and Reliable Messaging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0b38-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c0b38-124">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
- <xref:System.ServiceModel.Configuration.OneWayElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="c0b38-125">Привязки</span><span class="sxs-lookup"><span data-stu-id="c0b38-125">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c0b38-126">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="c0b38-126">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="c0b38-127">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="c0b38-127">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
