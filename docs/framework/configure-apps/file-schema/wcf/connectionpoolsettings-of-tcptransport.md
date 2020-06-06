---
title: <connectionPoolSettings> из <tcpTransport>
ms.date: 03/30/2017
ms.assetid: 2fbc3aa7-fcc9-4193-99a3-85d31d60d3f7
ms.openlocfilehash: f9b0fff741c32c1a3d6f9461f478e89acc18114e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398094"
---
# <a name="connectionpoolsettings-of-tcptransport"></a><span data-ttu-id="4c620-102">\<connectionPoolSettings> из \<tcpTransport></span><span class="sxs-lookup"><span data-stu-id="4c620-102">\<connectionPoolSettings> of \<tcpTransport></span></span>
<span data-ttu-id="4c620-103">Задает дополнительные параметры пула подключений для транспорта TCP.</span><span class="sxs-lookup"><span data-stu-id="4c620-103">Specifies additional connection pool settings for a TCP transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<tcpTransport>**](tcptransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionPoolSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="4c620-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4c620-104">Syntax</span></span>  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        leaseTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4c620-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4c620-105">Attributes and Elements</span></span>  
 <span data-ttu-id="4c620-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4c620-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4c620-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4c620-107">Attributes</span></span>  
  
|<span data-ttu-id="4c620-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4c620-108">Attribute</span></span>|<span data-ttu-id="4c620-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="4c620-109">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="4c620-110">Строка, определяющая имя пула подключений, используемого для исходящих каналов.</span><span class="sxs-lookup"><span data-stu-id="4c620-110">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="4c620-111">В потоковом режиме общий доступ к подключениям не предоставляется, то есть пул подключений отключен.</span><span class="sxs-lookup"><span data-stu-id="4c620-111">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="4c620-112">Значение по умолчанию - строка «default».</span><span class="sxs-lookup"><span data-stu-id="4c620-112">The default is a "default" string.</span></span> <span data-ttu-id="4c620-113">Это значение можно изменить, чтобы изолировать подключения для конкретного клиента в отдельные группы.</span><span class="sxs-lookup"><span data-stu-id="4c620-113">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="4c620-114">Положительное значение <xref:System.TimeSpan>, указывающее максимальное время бездействия для подключения перед его закрытием.</span><span class="sxs-lookup"><span data-stu-id="4c620-114">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="4c620-115">Значение по умолчанию - 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="4c620-115">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="4c620-116">Параметр <xref:System.TimeSpan>, задающий время ожидания перед закрытием активного подключения.</span><span class="sxs-lookup"><span data-stu-id="4c620-116">A <xref:System.TimeSpan> that specifies the time after which an active connection is closed.</span></span> <span data-ttu-id="4c620-117">Значение по умолчанию - 00:05:00.</span><span class="sxs-lookup"><span data-stu-id="4c620-117">The default is 00:05:00.</span></span><br /><br /> <span data-ttu-id="4c620-118">Подключение закрывается после возврата в кэш подключений, а не во время активной передачи.</span><span class="sxs-lookup"><span data-stu-id="4c620-118">A connection is closed after it has been returned to the connection cache and not during active transmission.</span></span> <span data-ttu-id="4c620-119">Кэш подключений, используемый транспортом TCP, по мере необходимости создает новые подключения для каждой конечной точки, до достижения лимита кэша, который задается параметром `maxOutboundConnectionsPerEndpoint.`</span><span class="sxs-lookup"><span data-stu-id="4c620-119">The connection cache used by the TCP transport creates new connections as required for each endpoint, up to the cache limit that is set by `maxOutboundConnectionsPerEndpoint.`</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="4c620-120">Положительное целое число, указывающее максимальное число подключений к удаленной конечной точке, инициированных одной службой.</span><span class="sxs-lookup"><span data-stu-id="4c620-120">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="4c620-121">Соединения сверх лимита помещаются в очередь до высвобождения ресурсов.</span><span class="sxs-lookup"><span data-stu-id="4c620-121">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="4c620-122">Параметр `idleTimeout` ограничивает продолжительность времени, в течение которого подключения остаются в очереди до возникновения исключения.</span><span class="sxs-lookup"><span data-stu-id="4c620-122">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="4c620-123">Значение по умолчанию равно 10.</span><span class="sxs-lookup"><span data-stu-id="4c620-123">The default is 10.</span></span><br /><br /> <span data-ttu-id="4c620-124">Этот атрибут ограничивает число одновременных активных подключений клиента к конкретной конечной точке службы.</span><span class="sxs-lookup"><span data-stu-id="4c620-124">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="4c620-125">В случае превышения этого значения при наличии большего числа активных соединений клиентов служба может прекратить отвечать на запросы клиента.</span><span class="sxs-lookup"><span data-stu-id="4c620-125">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="4c620-126">В таком случае это значение следует скорректировать, чтобы оно было больше предполагаемого максимума одновременных подключений клиента к конкретной конечной точке.</span><span class="sxs-lookup"><span data-stu-id="4c620-126">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4c620-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4c620-127">Child Elements</span></span>  
 <span data-ttu-id="4c620-128">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="4c620-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4c620-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4c620-129">Parent Elements</span></span>  
  
|<span data-ttu-id="4c620-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="4c620-130">Element</span></span>|<span data-ttu-id="4c620-131">Описание</span><span class="sxs-lookup"><span data-stu-id="4c620-131">Description</span></span>|  
|-------------|-----------------|  
|[\<namedPipeTransport>](namedpipetransport.md)|<span data-ttu-id="4c620-132">Определяет транспорт, вызывающий передачу сообщений с использованием именованных каналов.</span><span class="sxs-lookup"><span data-stu-id="4c620-132">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4c620-133">См. также</span><span class="sxs-lookup"><span data-stu-id="4c620-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.TcpConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="4c620-134">Транспорты</span><span class="sxs-lookup"><span data-stu-id="4c620-134">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="4c620-135">Выбор транспортов</span><span class="sxs-lookup"><span data-stu-id="4c620-135">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="4c620-136">Привязки</span><span class="sxs-lookup"><span data-stu-id="4c620-136">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="4c620-137">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="4c620-137">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="4c620-138">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="4c620-138">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
