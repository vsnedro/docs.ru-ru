---
title: <namedPipeTransport>
ms.date: 03/30/2017
ms.assetid: 9fc3f42f-43e2-4ab1-8bc7-3c95a9220df1
ms.openlocfilehash: 4582066098feaf50b33b083de56bcb8c3e04df0f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204623"
---
# \<namedPipeTransport>

<span data-ttu-id="ae421-101">Задает транспорт, принуждающий канал передавать сообщения с использованием именованных каналов, когда он включается в пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="ae421-101">Defines a transport that causes a channel to transfer messages using named pipes when it is included in a custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namedPipeTransport>**  
  
## <a name="syntax"></a><span data-ttu-id="ae421-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ae421-102">Syntax</span></span>  
  
```xml  
<namedPipeTransport channelInitializationTimeout="TimeSpan"
                    connectionBufferSize="Integer"
                    hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"
                    manualAddressing="Boolean"
                    maxBufferPoolSize="Integer"
                    maxBufferSize="Integer"
                    maxOutputDelay="TimeSpan"
                    maxPendingAccepts="Integer"
                    maxPendingConnections="Integer"
                    maxReceivedMessageSize="Integer"
                    transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse">
  <connectionPoolSettings groupName="String"
                          idleTimeout="TimeSpan"
                          maxOutboundConnectionsPerEndpoint="Integer" />
</namedPipeTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ae421-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ae421-103">Attributes and Elements</span></span>  

<span data-ttu-id="ae421-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ae421-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ae421-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ae421-105">Attributes</span></span>  

<span data-ttu-id="ae421-106">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ae421-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ae421-107">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ae421-107">Child Elements</span></span>  
  
|<span data-ttu-id="ae421-108">Элемент</span><span class="sxs-lookup"><span data-stu-id="ae421-108">Element</span></span>|<span data-ttu-id="ae421-109">Описание</span><span class="sxs-lookup"><span data-stu-id="ae421-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ae421-110">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="ae421-110">ChannelInitializationTimeout</span></span>|<span data-ttu-id="ae421-111">Получает или задает <xref:System.TimeSpan>, определяющий максимальное время, в течение которого канал может находиться в состоянии инициализации перед отключением.</span><span class="sxs-lookup"><span data-stu-id="ae421-111">Gets or sets a <xref:System.TimeSpan> that determines the maximum time a channel can be in the initialization status before being disconnected.</span></span>|  
|<span data-ttu-id="ae421-112">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="ae421-112">ConnectionBufferSize</span></span>|<span data-ttu-id="ae421-113">Возвращает или задает размер буфера, используемого для передачи фрагмента сериализованного сообщения от клиента серверу по сети.</span><span class="sxs-lookup"><span data-stu-id="ae421-113">Gets or sets the size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>|  
|<span data-ttu-id="ae421-114">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="ae421-114">hostNameComparisonMode</span></span>|<span data-ttu-id="ae421-115">Возвращает или задает значение, указывающее, используется ли имя узла для доступа к службе при сопоставлении по универсальному коду ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="ae421-115">Gets or sets a value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>|  
|<span data-ttu-id="ae421-116">manualAddressing</span><span class="sxs-lookup"><span data-stu-id="ae421-116">manualAddressing</span></span>|<span data-ttu-id="ae421-117">Возвращает или задает значение, показывающее, требуется ли создание адреса сообщения вручную.</span><span class="sxs-lookup"><span data-stu-id="ae421-117">Gets or sets a value that indicates whether manual addressing of the message is required.</span></span>|  
|<span data-ttu-id="ae421-118">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="ae421-118">maxBufferPoolSize</span></span>|<span data-ttu-id="ae421-119">Получает или задает максимальный размер (в байтах) буферных пулов, используемых транспортом.</span><span class="sxs-lookup"><span data-stu-id="ae421-119">Gets or sets the maximum size, in bytes, of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="ae421-120">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="ae421-120">maxBufferSize</span></span>|<span data-ttu-id="ae421-121">Возвращает или задает максимальный размер используемого буфера.</span><span class="sxs-lookup"><span data-stu-id="ae421-121">Gets or sets the maximum size of the buffer to use.</span></span> <span data-ttu-id="ae421-122">Для потоковых сообщений это значение не должно быть меньше максимального возможного размера заголовков сообщения, считываемых в режиме буферизации.</span><span class="sxs-lookup"><span data-stu-id="ae421-122">For streamed messages, this value should be at least the maximum possible size of the message headers, which are read in buffered mode.</span></span>|  
|<span data-ttu-id="ae421-123">максаутпутделай</span><span class="sxs-lookup"><span data-stu-id="ae421-123">maxOutputDelay</span></span>|<span data-ttu-id="ae421-124">Возвращает или задает максимальный промежуток времени, в течение которого фрагмент сообщения или все сообщение может оставаться в буфере перед отправкой.</span><span class="sxs-lookup"><span data-stu-id="ae421-124">Gets or sets the maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>|  
|<span data-ttu-id="ae421-125">maxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="ae421-125">maxPendingAccepts</span></span>|<span data-ttu-id="ae421-126">Получает или задает максимальное количество у службы каналов, ожидающих на прослушивателе для обработки входящих подключений к службе.</span><span class="sxs-lookup"><span data-stu-id="ae421-126">Gets or sets the maximum number of channels a service can have waiting on a listener for processing incoming connections to the service.</span></span>|  
|<span data-ttu-id="ae421-127">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="ae421-127">maxPendingConnections</span></span>|<span data-ttu-id="ae421-128">Возвращает или задает максимальное число подключений, ожидающих распределения в службе.</span><span class="sxs-lookup"><span data-stu-id="ae421-128">Gets or sets the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="ae421-129">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="ae421-129">maxReceivedMessageSize</span></span>|<span data-ttu-id="ae421-130">Возвращает и задает максимально допустимый размер сообщения (в байтах), который может быть получен.</span><span class="sxs-lookup"><span data-stu-id="ae421-130">Gets and sets the maximum allowable message size, in bytes, that can be received.</span></span>|  
|<span data-ttu-id="ae421-131">transferMode</span><span class="sxs-lookup"><span data-stu-id="ae421-131">transferMode</span></span>|<span data-ttu-id="ae421-132">Возвращает или задает значение, указывающее, следует ли помещать сообщения в буфер или передавать их потоком с использованием транспорта, ориентированного на подключение.</span><span class="sxs-lookup"><span data-stu-id="ae421-132">Gets or sets a value that indicates whether the messages are buffered or streamed with the connection-oriented transport.</span></span>|  
|[<span data-ttu-id="ae421-133">\<connectionPoolSettings> из \<namedPipeTransport></span><span class="sxs-lookup"><span data-stu-id="ae421-133">\<connectionPoolSettings> of \<namedPipeTransport></span></span>](connectionpoolsettings.md)|<span data-ttu-id="ae421-134">Задает дополнительные параметры пула подключений для привязки именованного канала.</span><span class="sxs-lookup"><span data-stu-id="ae421-134">Specifies additional connection pool settings for a Named Pipe binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ae421-135">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ae421-135">Parent Elements</span></span>  
  
|<span data-ttu-id="ae421-136">Элемент</span><span class="sxs-lookup"><span data-stu-id="ae421-136">Element</span></span>|<span data-ttu-id="ae421-137">Описание</span><span class="sxs-lookup"><span data-stu-id="ae421-137">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="ae421-138">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="ae421-138">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae421-139">Remarks</span><span class="sxs-lookup"><span data-stu-id="ae421-139">Remarks</span></span>  

<span data-ttu-id="ae421-140">Этот транспорт использует универсальные коды ресурсов (URI) вида net.pipe://hostname/path.</span><span class="sxs-lookup"><span data-stu-id="ae421-140">This transport uses URIs of the form "net.pipe://hostname/path".</span></span> <span data-ttu-id="ae421-141">Другие элементы универсального кода ресурса (URI) не обязательны.</span><span class="sxs-lookup"><span data-stu-id="ae421-141">Other URI components are optional.</span></span>  
  
<span data-ttu-id="ae421-142">Элемент `namedPipeTransport` является отправной точкой для создания пользовательской привязки, реализующей именованные каналы транспорта HTTPS.</span><span class="sxs-lookup"><span data-stu-id="ae421-142">The `namedPipeTransport` element is the starting point for creating a custom binding that implements the named pipes transport protocol.</span></span> <span data-ttu-id="ae421-143">Этот транспорт используется для взаимодействия служб WCF на компьютере.</span><span class="sxs-lookup"><span data-stu-id="ae421-143">This transport is used for on-machine Windows Communication Foundation (WCF)-to-WCF communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae421-144">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ae421-144">See also</span></span>

- <xref:System.ServiceModel.Configuration.NamedPipeTransportElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="ae421-145">Транспорты</span><span class="sxs-lookup"><span data-stu-id="ae421-145">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="ae421-146">Выбор транспортов</span><span class="sxs-lookup"><span data-stu-id="ae421-146">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="ae421-147">Привязки</span><span class="sxs-lookup"><span data-stu-id="ae421-147">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ae421-148">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="ae421-148">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="ae421-149">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="ae421-149">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
