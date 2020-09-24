---
title: <tcpTransport>
ms.date: 03/30/2017
ms.assetid: 8fcd18c1-9958-42e7-b442-7903f7bdb563
ms.openlocfilehash: 6d4302e1840f58e2daad855942493cc96b7d5e34
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158673"
---
# \<tcpTransport>

<span data-ttu-id="92e01-101">Определяет транспорт TCP, который может использоваться каналом для передачи сообщений для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="92e01-101">Defines a TCP transport that can be used by a channel to transfers messages for a custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tcpTransport>**  
  
## <a name="syntax"></a><span data-ttu-id="92e01-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="92e01-102">Syntax</span></span>  
  
```xml  
<tcpTransport channelInitializationTimeout="TimeSpan"
              connectionBufferSize="Integer"
              hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"
              listenBacklog="Integer"
              manualAddressing="Boolean"
              maxBufferPoolSize="Integer"
              maxBufferSize="Integer"
              maxOutputDelay="TimeSpan"
              maxPendingAccepts="Integer"
              maxPendingConnections="Integer"
              maxReceivedMessageSize="Integer"
              portSharingEnabled="Boolean"
              teredoEnabled="Boolean"
              transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse" >
  <connectionPoolSettings groupName="String"
                          idleTimeout="TimeSpan"
                          leaseTimeout="TimeSpan"
                          maxOutboundConnectionsPerEndpoint="Integer" />
</tcpTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="92e01-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="92e01-103">Attributes and Elements</span></span>  

 <span data-ttu-id="92e01-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="92e01-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="92e01-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="92e01-105">Attributes</span></span>  
  
|<span data-ttu-id="92e01-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="92e01-106">Attribute</span></span>|<span data-ttu-id="92e01-107">Описание</span><span class="sxs-lookup"><span data-stu-id="92e01-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="92e01-108">channelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="92e01-108">channelInitializationTimeout</span></span>|<span data-ttu-id="92e01-109">Возвращает или задает ограничение по времени для приема инициализации канала.</span><span class="sxs-lookup"><span data-stu-id="92e01-109">Gets or sets the time limit for initializing a channel to be accepted.</span></span>  <span data-ttu-id="92e01-110">Максимальное время в секундах, в течение которого канал может находиться в состоянии инициализации, прежде чем будет отключен.</span><span class="sxs-lookup"><span data-stu-id="92e01-110">The maximum time a channel can be in the initialization state before being disconnected in seconds.</span></span> <span data-ttu-id="92e01-111">Эта квота включает в себя время, которое TCP-подключение может пройти для проверки подлинности с помощью протокола кадрирования сообщений .NET.</span><span class="sxs-lookup"><span data-stu-id="92e01-111">This quota includes the time a TCP connection can take to authenticate itself using the .NET Message Framing protocol.</span></span> <span data-ttu-id="92e01-112">Клиенту необходимо отправить некоторые исходные данные, прежде чем сервер получит достаточно сведений для аутентификации.</span><span class="sxs-lookup"><span data-stu-id="92e01-112">A client needs to send some initial data before the server has enough information to perform authentication.</span></span> <span data-ttu-id="92e01-113">По умолчанию это 30 секунд.</span><span class="sxs-lookup"><span data-stu-id="92e01-113">The default is 30 seconds.</span></span>|  
|<span data-ttu-id="92e01-114">коннектионбуфферсизе</span><span class="sxs-lookup"><span data-stu-id="92e01-114">connectionBufferSize</span></span>|<span data-ttu-id="92e01-115">Возвращает или задает размер буфера, используемого для передачи фрагмента сериализованного сообщения от клиента серверу по сети.</span><span class="sxs-lookup"><span data-stu-id="92e01-115">Gets or sets the size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>|  
|<span data-ttu-id="92e01-116">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="92e01-116">hostNameComparisonMode</span></span>|<span data-ttu-id="92e01-117">Возвращает или задает значение, указывающее, используется ли имя узла для доступа к службе при сопоставлении по универсальному коду ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="92e01-117">Gets or sets a value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>|  
|<span data-ttu-id="92e01-118">listenBacklog</span><span class="sxs-lookup"><span data-stu-id="92e01-118">listenBacklog</span></span>|<span data-ttu-id="92e01-119">Максимальное количество запросов на соединение в очереди, которые могут ожидать обработки веб-службой.</span><span class="sxs-lookup"><span data-stu-id="92e01-119">The maximum number of queued connection requests that can be pending for a Web service.</span></span> <span data-ttu-id="92e01-120">Атрибут `connectionLeaseTimeout` ограничивает время ожидания подключения клиентом до создания исключения подключения.</span><span class="sxs-lookup"><span data-stu-id="92e01-120">The `connectionLeaseTimeout` attribute limits the duration the client will wait to be connected before throwing a connection exception.</span></span> <span data-ttu-id="92e01-121">Это свойство уровня сокетов, которое определяет максимальное количество запросов на подключение в очереди, которые могут ожидать обработки веб-службой.</span><span class="sxs-lookup"><span data-stu-id="92e01-121">This is a socket level property which controls the maximum number of queued connection requests that can be pending for a Web service.</span></span> <span data-ttu-id="92e01-122">Если Листенбакклог имеет слишком малое значение, WCF перестанет принимать запросы и, следовательно, удалит новые подключения, пока сервер не подтвердит некоторые существующие соединения в очереди.</span><span class="sxs-lookup"><span data-stu-id="92e01-122">When ListenBacklog is too low, WCF will stop accepting requests and therefore drop new connections until the server acknowledges some of the existing queued connections.</span></span> <span data-ttu-id="92e01-123">Значение по умолчанию — 16 \* число процессоров.</span><span class="sxs-lookup"><span data-stu-id="92e01-123">The default is 16 \* number of processors.</span></span>|  
|<span data-ttu-id="92e01-124">manualAddressing</span><span class="sxs-lookup"><span data-stu-id="92e01-124">manualAddressing</span></span>|<span data-ttu-id="92e01-125">Возвращает или задает значение, показывающее, требуется ли создание адреса сообщения вручную.</span><span class="sxs-lookup"><span data-stu-id="92e01-125">Gets or sets a value that indicates whether manual addressing of the message is required.</span></span>|  
|<span data-ttu-id="92e01-126">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="92e01-126">maxBufferPoolSize</span></span>|<span data-ttu-id="92e01-127">Возвращает или задает максимальное значение буферных пулов, используемых транспортом.</span><span class="sxs-lookup"><span data-stu-id="92e01-127">Gets or sets the maximum size of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="92e01-128">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="92e01-128">maxBufferSize</span></span>|<span data-ttu-id="92e01-129">Возвращает или задает максимальный размер используемого буфера.</span><span class="sxs-lookup"><span data-stu-id="92e01-129">Gets or sets the maximum size of the buffer to use.</span></span> <span data-ttu-id="92e01-130">Для потоковых сообщений это значение не должно быть меньше максимального возможного размера заголовков сообщения, считываемых в режиме буферизации.</span><span class="sxs-lookup"><span data-stu-id="92e01-130">For streamed messages, this value should be at least the maximum possible size of the message headers, which are read in buffered mode.</span></span>|  
|<span data-ttu-id="92e01-131">максаутпутделай</span><span class="sxs-lookup"><span data-stu-id="92e01-131">maxOutputDelay</span></span>|<span data-ttu-id="92e01-132">Возвращает или задает максимальный промежуток времени, в течение которого фрагмент сообщения или все сообщение может оставаться в буфере перед отправкой.</span><span class="sxs-lookup"><span data-stu-id="92e01-132">Gets or sets the maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>|  
|<span data-ttu-id="92e01-133">maxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="92e01-133">maxPendingAccepts</span></span>|<span data-ttu-id="92e01-134">Возвращает или задает максимальное число ожидающих асинхронных операций приема, доступных для обработки входящих подключений к службе.</span><span class="sxs-lookup"><span data-stu-id="92e01-134">Gets or sets the maximum number of pending asynchronous accept operations that are available for processing incoming connections to the service.</span></span>|  
|<span data-ttu-id="92e01-135">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="92e01-135">maxPendingConnections</span></span>|<span data-ttu-id="92e01-136">Возвращает или задает максимальное число подключений, ожидающих распределения в службе.</span><span class="sxs-lookup"><span data-stu-id="92e01-136">Gets or sets the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="92e01-137">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="92e01-137">maxReceivedMessageSize</span></span>|<span data-ttu-id="92e01-138">Возвращает и задает максимально допустимый размер принимаемого сообщения.</span><span class="sxs-lookup"><span data-stu-id="92e01-138">Gets and sets the maximum allowable message size that can be received.</span></span>|  
|<span data-ttu-id="92e01-139">portSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="92e01-139">portSharingEnabled</span></span>|<span data-ttu-id="92e01-140">Логическое значение, определяющее, включено ли совместное использование порта TCP для этого подключения.</span><span class="sxs-lookup"><span data-stu-id="92e01-140">A Boolean value that specifies if TCP port sharing is enabled for this connection.</span></span> <span data-ttu-id="92e01-141">Если атрибут имеет значение `false`, каждая привязка будет использовать уникальный порт.</span><span class="sxs-lookup"><span data-stu-id="92e01-141">If this is `false`, each binding will use its own exclusive port.</span></span> <span data-ttu-id="92e01-142">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="92e01-142">The default is `false`.</span></span><br /><br /> <span data-ttu-id="92e01-143">Этот параметр действителен только для служб.</span><span class="sxs-lookup"><span data-stu-id="92e01-143">This setting is relevant only to services.</span></span> <span data-ttu-id="92e01-144">Клиенты не затрагиваются.</span><span class="sxs-lookup"><span data-stu-id="92e01-144">Clients are not affected.</span></span><br /><br /> <span data-ttu-id="92e01-145">Использование этого параметра требует включения службы общего доступа к портам TCP Windows Communication Foundation (WCF) путем изменения типа запуска на «Вручную» или «Авто».</span><span class="sxs-lookup"><span data-stu-id="92e01-145">Using this setting requires enabling the Windows Communication Foundation (WCF) TCP Port Sharing Service by changing its Startup Type to Manual or Automatic</span></span>|  
|<span data-ttu-id="92e01-146">teredoEnabled</span><span class="sxs-lookup"><span data-stu-id="92e01-146">teredoEnabled</span></span>|<span data-ttu-id="92e01-147">Логическое значение, указывающее, используется ли Teredo (технология адресации клиентов, защищенных брандмауэром).</span><span class="sxs-lookup"><span data-stu-id="92e01-147">A Boolean value that specifies whether Teredo (a technology for addressing clients that are behind firewalls) is enabled.</span></span> <span data-ttu-id="92e01-148">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="92e01-148">The default is `false`.</span></span><br /><br /> <span data-ttu-id="92e01-149">Это свойство включает использование Teredo для базового сокета TCP.</span><span class="sxs-lookup"><span data-stu-id="92e01-149">This property enables Teredo for the underlying TCP socket.</span></span> <span data-ttu-id="92e01-150">Дополнительные сведения см. в разделе [Общие сведения о Teredo](/previous-versions/windows/it-pro/windows-xp/bb457011(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="92e01-150">For more information, see [Teredo Overview](/previous-versions/windows/it-pro/windows-xp/bb457011(v=technet.10)).</span></span><br /><br /> <span data-ttu-id="92e01-151">Это свойство применимо только в Windows XP с пакетом обновления 2 (SP2) и Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="92e01-151">This property is applicable only on Windows XP SP2 and Windows Server 2003.</span></span> <span data-ttu-id="92e01-152">В Windows Vista используется параметр конфигурации на уровне компьютера для Teredo, поэтому при запуске Vista это свойство игнорируется.</span><span class="sxs-lookup"><span data-stu-id="92e01-152">Windows Vista has a machine-wide configuration option for Teredo, so when running Vista, this property is ignored.</span></span> <span data-ttu-id="92e01-153">Для Teredo необходимо, чтобы на компьютере, где работает служба, и на компьютере-клиенте был установлен и настроен правильно для использования Teredo стек протокола Microsoft IPv6.</span><span class="sxs-lookup"><span data-stu-id="92e01-153">Teredo requires that the client and service machines both have the Microsoft IPv6 stack installed and correctly configured for Teredo usage.</span></span>|  
|<span data-ttu-id="92e01-154">transferMode</span><span class="sxs-lookup"><span data-stu-id="92e01-154">transferMode</span></span>|<span data-ttu-id="92e01-155">Возвращает или задает значение, указывающее, следует ли помещать сообщения в буфер или передавать их потоком с использованием транспорта, ориентированного на подключение.</span><span class="sxs-lookup"><span data-stu-id="92e01-155">Gets or sets a value that indicates whether the messages are buffered or streamed with the connection-oriented transport.</span></span>|  
|<span data-ttu-id="92e01-156">connectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="92e01-156">connectionPoolSettings</span></span>|<span data-ttu-id="92e01-157">Задает дополнительные параметры пула подключений для привязки именованного канала.</span><span class="sxs-lookup"><span data-stu-id="92e01-157">Specifies additional connection pool settings for a Named Pipe binding.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="92e01-158">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="92e01-158">Child Elements</span></span>  

 <span data-ttu-id="92e01-159">Нет</span><span class="sxs-lookup"><span data-stu-id="92e01-159">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="92e01-160">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="92e01-160">Parent Elements</span></span>  
  
|<span data-ttu-id="92e01-161">Элемент</span><span class="sxs-lookup"><span data-stu-id="92e01-161">Element</span></span>|<span data-ttu-id="92e01-162">Описание</span><span class="sxs-lookup"><span data-stu-id="92e01-162">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="92e01-163">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="92e01-163">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="92e01-164">Remarks</span><span class="sxs-lookup"><span data-stu-id="92e01-164">Remarks</span></span>  

 <span data-ttu-id="92e01-165">Этот транспорт использует универсальные коды ресурсов (URI) вида net.tcp://hostname:port/path.</span><span class="sxs-lookup"><span data-stu-id="92e01-165">This transport uses URIs of the form "net.tcp://hostname:port/path".</span></span> <span data-ttu-id="92e01-166">Другие элементы универсального кода ресурса (URI) не обязательны.</span><span class="sxs-lookup"><span data-stu-id="92e01-166">Other URI components are optional.</span></span>  
  
 <span data-ttu-id="92e01-167">Элемент `tcpTransport` является начальной точкой для создания пользовательской привязки, реализующей транспортный протокол TCP.</span><span class="sxs-lookup"><span data-stu-id="92e01-167">The `tcpTransport` element is the starting point for creating a custom binding that implements the TCP transport protocol.</span></span> <span data-ttu-id="92e01-168">Этот транспорт оптимизирован для взаимодействия между службами WCF.</span><span class="sxs-lookup"><span data-stu-id="92e01-168">This transport is optimized for WCF-to-WCF communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92e01-169">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="92e01-169">See also</span></span>

- <xref:System.ServiceModel.Configuration.TcpTransportElement>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="92e01-170">Транспорты</span><span class="sxs-lookup"><span data-stu-id="92e01-170">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="92e01-171">Выбор транспортов</span><span class="sxs-lookup"><span data-stu-id="92e01-171">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="92e01-172">Привязки</span><span class="sxs-lookup"><span data-stu-id="92e01-172">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="92e01-173">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="92e01-173">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="92e01-174">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="92e01-174">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
