---
title: <peerTransport>
ms.date: 03/30/2017
ms.assetid: c1a5013a-9dd4-4a27-b114-795b8b323177
ms.openlocfilehash: 99fb013e052329ae4b99c4db89565ace8935c456
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736505"
---
# \<peerTransport>
<span data-ttu-id="eedeb-101">Определяет одноранговый транспорт для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="eedeb-101">Defines a peer transport for a custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peerTransport>**  
  
## <a name="syntax"></a><span data-ttu-id="eedeb-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eedeb-102">Syntax</span></span>  
  
```xml  
<peerTransport listenIpAddress="String"
               maxBufferPoolSize="Integer"
               maxReceivedMessageSize="Integer"
               port="Integer">
  <security>
  </security>
</peerTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eedeb-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="eedeb-103">Attributes and Elements</span></span>  
 <span data-ttu-id="eedeb-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="eedeb-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eedeb-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="eedeb-105">Attributes</span></span>  
  
|<span data-ttu-id="eedeb-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="eedeb-106">Attribute</span></span>|<span data-ttu-id="eedeb-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="eedeb-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="eedeb-108">listenIpAddress</span><span class="sxs-lookup"><span data-stu-id="eedeb-108">listenIpAddress</span></span>|<span data-ttu-id="eedeb-109">Строка, указывающая IP-адрес, на котором одноранговый узел будет ожидать TCP-сообщения.</span><span class="sxs-lookup"><span data-stu-id="eedeb-109">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="eedeb-110">Значение по умолчанию — `null`.</span><span class="sxs-lookup"><span data-stu-id="eedeb-110">The default is `null`.</span></span>|  
|<span data-ttu-id="eedeb-111">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="eedeb-111">maxBufferPoolSize</span></span>|<span data-ttu-id="eedeb-112">Положительное целое число, указывающее максимальный размер буферного пула.</span><span class="sxs-lookup"><span data-stu-id="eedeb-112">A positive integer that specifies the maximum size of the buffer pool.</span></span> <span data-ttu-id="eedeb-113">Значение по умолчанию — 524288.</span><span class="sxs-lookup"><span data-stu-id="eedeb-113">The default is 524288.</span></span><br /><br /> <span data-ttu-id="eedeb-114">Многие элементы WCF используют буферы.</span><span class="sxs-lookup"><span data-stu-id="eedeb-114">Many parts of WCF use buffers.</span></span> <span data-ttu-id="eedeb-115">При создании буферов и их уничтожении после каждого использования расходуется слишком много ресурсов; при сборке мусора для буферов также расходуется слишком много ресурсов.</span><span class="sxs-lookup"><span data-stu-id="eedeb-115">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="eedeb-116">Буферные пулы позволяют брать буфер из пула, использовать его, а затем возвращать обратно, когда он больше не требуется.</span><span class="sxs-lookup"><span data-stu-id="eedeb-116">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="eedeb-117">Это позволяет избежать излишней нагрузки, связанной с созданием и уничтожением буферов.</span><span class="sxs-lookup"><span data-stu-id="eedeb-117">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="eedeb-118">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="eedeb-118">maxReceivedMessageSize</span></span>|<span data-ttu-id="eedeb-119">Положительное целое число, определяющее максимальный размер сообщения (в байтах), включая заголовки.</span><span class="sxs-lookup"><span data-stu-id="eedeb-119">A positive integer that defines the maximum message size in bytes including headers.</span></span> <span data-ttu-id="eedeb-120">Отправитель сообщения получает ошибку протокола SOAP, когда размер сообщения оказывается слишком большим для получателя.</span><span class="sxs-lookup"><span data-stu-id="eedeb-120">The sender of a message receives a SOAP fault when the message is too large for the receiver.</span></span> <span data-ttu-id="eedeb-121">Получатель отклоняет сообщение и создает запись о событии в журнале трассировки.</span><span class="sxs-lookup"><span data-stu-id="eedeb-121">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="eedeb-122">Значение по умолчанию — 65536.</span><span class="sxs-lookup"><span data-stu-id="eedeb-122">The default is 65536.</span></span>|  
|<span data-ttu-id="eedeb-123">порт</span><span class="sxs-lookup"><span data-stu-id="eedeb-123">port</span></span>|<span data-ttu-id="eedeb-124">Целое число, задающее порт сетевого интерфейса, на котором эта привязка будет обрабатывать TCP-сообщения однорангового канала.</span><span class="sxs-lookup"><span data-stu-id="eedeb-124">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="eedeb-125">Это значение должно принадлежать диапазону от <xref:System.Net.IPEndPoint.MinPort> до <xref:System.Net.IPEndPoint.MaxPort>.</span><span class="sxs-lookup"><span data-stu-id="eedeb-125">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="eedeb-126">Значение по умолчанию равно 0.</span><span class="sxs-lookup"><span data-stu-id="eedeb-126">The default is 0.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eedeb-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="eedeb-127">Child Elements</span></span>  
  
|<span data-ttu-id="eedeb-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="eedeb-128">Element</span></span>|<span data-ttu-id="eedeb-129">Описание</span><span class="sxs-lookup"><span data-stu-id="eedeb-129">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-peertransport.md)|<span data-ttu-id="eedeb-130">Определяет параметры безопасности для данного транспорта.</span><span class="sxs-lookup"><span data-stu-id="eedeb-130">Defines the security settings for this transport.</span></span> <span data-ttu-id="eedeb-131">Это элемент типа <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="eedeb-131">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="eedeb-132">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="eedeb-132">Parent Elements</span></span>  
  
|<span data-ttu-id="eedeb-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="eedeb-133">Element</span></span>|<span data-ttu-id="eedeb-134">Описание</span><span class="sxs-lookup"><span data-stu-id="eedeb-134">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="eedeb-135">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="eedeb-135">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eedeb-136">Примечания</span><span class="sxs-lookup"><span data-stu-id="eedeb-136">Remarks</span></span>  
 <span data-ttu-id="eedeb-137">Данный транспорт нельзя использовать с контрактами, имеющими операции запроса-ответа.</span><span class="sxs-lookup"><span data-stu-id="eedeb-137">This transport cannot be used with contracts that have request/reply operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eedeb-138">См. также</span><span class="sxs-lookup"><span data-stu-id="eedeb-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportElement>
- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="eedeb-139">Транспорты</span><span class="sxs-lookup"><span data-stu-id="eedeb-139">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="eedeb-140">Выбор транспортов</span><span class="sxs-lookup"><span data-stu-id="eedeb-140">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="eedeb-141">Привязки</span><span class="sxs-lookup"><span data-stu-id="eedeb-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="eedeb-142">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="eedeb-142">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="eedeb-143">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="eedeb-143">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
