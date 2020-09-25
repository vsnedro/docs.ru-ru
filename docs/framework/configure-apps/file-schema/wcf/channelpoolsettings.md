---
title: <channelPoolSettings>
ms.date: 03/30/2017
ms.assetid: 4755f3d3-4213-4c68-ae7f-45b67d744459
ms.openlocfilehash: 8638d56ccb4aaa1c5ac735aa268823af2b1fbc6d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176075"
---
# \<channelPoolSettings>

<span data-ttu-id="cae08-101">Задает параметры пула каналов для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="cae08-101">Specifies the channel pool settings for a custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oneWay>**](oneway.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<channelPoolSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="cae08-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cae08-102">Syntax</span></span>  
  
```xml  
<channelPoolSettings idleTimeout="TimeSpan"
                     leaseTimeout="TimeSpan"
                     maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cae08-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cae08-103">Attributes and Elements</span></span>  

 <span data-ttu-id="cae08-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="cae08-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cae08-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cae08-105">Attributes</span></span>  
  
|<span data-ttu-id="cae08-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="cae08-106">Attribute</span></span>|<span data-ttu-id="cae08-107">Описание</span><span class="sxs-lookup"><span data-stu-id="cae08-107">Description</span></span>|  
|---------------|-----------------|  
|`idleTimeout`|<span data-ttu-id="cae08-108">Положительное значение <xref:System.TimeSpan>, указывающее максимальное время бездействия канала в пуле перед отключением.</span><span class="sxs-lookup"><span data-stu-id="cae08-108">A positive <xref:System.TimeSpan> that specifies the maximum time the channels in the pool can be idle before being disconnected.</span></span> <span data-ttu-id="cae08-109">Значение по умолчанию - 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="cae08-109">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="cae08-110">Значение <xref:System.TimeSpan>, которое задает интервал времени, после которого канал закрывается при возвращении в пул.</span><span class="sxs-lookup"><span data-stu-id="cae08-110">A <xref:System.TimeSpan> that specifies the interval of time after which a channel, when returned to the pool, is closed.</span></span> <span data-ttu-id="cae08-111">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="cae08-111">The default is 00:10:00.</span></span>|  
|`maxOutboundChannelsPerEndpoint`|<span data-ttu-id="cae08-112">Положительное целое число, задающее максимальное количество каналов, которое можно хранить в пуле для каждой удаленной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="cae08-112">A positive integer that specifies the maximum number of channels that can be stored in the pool for each remote endpoint.</span></span> <span data-ttu-id="cae08-113">Значение по умолчанию равно 10.</span><span class="sxs-lookup"><span data-stu-id="cae08-113">The default is 10.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cae08-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cae08-114">Child Elements</span></span>  

 <span data-ttu-id="cae08-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="cae08-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cae08-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cae08-116">Parent Elements</span></span>  
  
|<span data-ttu-id="cae08-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="cae08-117">Element</span></span>|<span data-ttu-id="cae08-118">Описание</span><span class="sxs-lookup"><span data-stu-id="cae08-118">Description</span></span>|  
|-------------|-----------------|  
|[\<oneWay>](oneway.md)|<span data-ttu-id="cae08-119">Включает маршрутизацию пакетов для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="cae08-119">Enables packet routing for a custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cae08-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="cae08-120">Remarks</span></span>  

 <span data-ttu-id="cae08-121">Квоты используются как механизм политики, служащий для предотвращения чрезмерного потребления ресурсов.</span><span class="sxs-lookup"><span data-stu-id="cae08-121">Quotas are used as a policy mechanism to prevent the consumption of excessive resources.</span></span> <span data-ttu-id="cae08-122">Они препятствуют злонамеренным или неумышленным атакам типа «отказ в обслуживании» (DoS).</span><span class="sxs-lookup"><span data-stu-id="cae08-122">They prevent Denial of Service (DOS) attacks that are either malicious or unintentional.</span></span> <span data-ttu-id="cae08-123">Этот элемент используется при установке квот на пользовательском канале.</span><span class="sxs-lookup"><span data-stu-id="cae08-123">Use this element when setting channel quotas on a custom channel.</span></span>  
  
 <span data-ttu-id="cae08-124">`ChannelPoolSettings` задает три квоты.</span><span class="sxs-lookup"><span data-stu-id="cae08-124">`ChannelPoolSettings` specifies three quotas:</span></span>  
  
- <span data-ttu-id="cae08-125">Квота `idleTimeout` используется для ослабления эффекта атак типа «отказ в обслуживании» (DoS) на сервере, при котором ресурсы блокируются на продолжительный период времени.</span><span class="sxs-lookup"><span data-stu-id="cae08-125">The `idleTimeout` quota is used to mitigate Denial of Service (DOS) attacks on the server that rely on tying up resources for an extended period of time.</span></span> <span data-ttu-id="cae08-126">На клиенте установка правильного значения может повысить надежность соединения со службой.</span><span class="sxs-lookup"><span data-stu-id="cae08-126">On the client, setting the correct value can increase the reliability of connecting with the service.</span></span> <span data-ttu-id="cae08-127">Значение по умолчанию основано на консервативно умеренном выделении ресурсов.</span><span class="sxs-lookup"><span data-stu-id="cae08-127">The default value is based on a conservatively modest allocation of resources.</span></span> <span data-ttu-id="cae08-128">Это подходит для среды разработки и небольших сценариев установок.</span><span class="sxs-lookup"><span data-stu-id="cae08-128">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="cae08-129">Администраторы должны обновлять значение, если данной установке начинает не хватать ресурсов или если число подключений ограничено, несмотря на доступность дополнительных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="cae08-129">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
- <span data-ttu-id="cae08-130">Квота `leaseTimeout` используется для интеграции с механизмами балансировки нагрузки и для повышения надежности.</span><span class="sxs-lookup"><span data-stu-id="cae08-130">The `leaseTimeout` quota is used to for integration with load balancers and for improving reliability.</span></span> <span data-ttu-id="cae08-131">Значение по умолчанию основано на консервативном выделении ресурсов.</span><span class="sxs-lookup"><span data-stu-id="cae08-131">The default value is based on a conservative allocation of resources.</span></span> <span data-ttu-id="cae08-132">Это подходит для среды разработки и небольших сценариев установок.</span><span class="sxs-lookup"><span data-stu-id="cae08-132">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="cae08-133">Администраторы должны обновлять значение, если данной установке начинает не хватать ресурсов или если число подключений ограничено, несмотря на доступность дополнительных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="cae08-133">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
- <span data-ttu-id="cae08-134">Квота `maxOutboundChannelsPerEndpoint` устанавливает предельные значения кэша на сервере и на клиенте и используется для повышения надежности.</span><span class="sxs-lookup"><span data-stu-id="cae08-134">The `maxOutboundChannelsPerEndpoint` quota sets cache limits on both the server and the client and is used to improve reliability.</span></span> <span data-ttu-id="cae08-135">Значение по умолчанию основано на консервативно умеренном выделении ресурсов, которое подходит для среды разработки и небольших установок.</span><span class="sxs-lookup"><span data-stu-id="cae08-135">The default value is based on a conservatively modest allocation of resources that is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="cae08-136">Администраторы должны обновлять значение, если данной установке начинает не хватать ресурсов или если число подключений ограничено, несмотря на доступность дополнительных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="cae08-136">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cae08-137">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cae08-137">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
- <xref:System.ServiceModel.Configuration.OneWayElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [\<oneWay>](oneway.md)
- [<span data-ttu-id="cae08-138">Привязки</span><span class="sxs-lookup"><span data-stu-id="cae08-138">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="cae08-139">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="cae08-139">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="cae08-140">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="cae08-140">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
