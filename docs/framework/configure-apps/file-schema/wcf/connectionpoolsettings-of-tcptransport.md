---
title: <connectionPoolSettings> из <tcpTransport>
ms.date: 03/30/2017
ms.assetid: 2fbc3aa7-fcc9-4193-99a3-85d31d60d3f7
ms.openlocfilehash: 53523fd550ecad931bfb2af5eb9beb71c60d44f8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176010"
---
# <a name="connectionpoolsettings-of-tcptransport"></a><span data-ttu-id="e2502-102">\<connectionPoolSettings> из \<tcpTransport></span><span class="sxs-lookup"><span data-stu-id="e2502-102">\<connectionPoolSettings> of \<tcpTransport></span></span>

<span data-ttu-id="e2502-103">Задает дополнительные параметры пула подключений для транспорта TCP.</span><span class="sxs-lookup"><span data-stu-id="e2502-103">Specifies additional connection pool settings for a TCP transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<tcpTransport>**](tcptransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionPoolSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="e2502-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e2502-104">Syntax</span></span>  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        leaseTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e2502-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e2502-105">Attributes and Elements</span></span>  

 <span data-ttu-id="e2502-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e2502-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e2502-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e2502-107">Attributes</span></span>  
  
|<span data-ttu-id="e2502-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e2502-108">Attribute</span></span>|<span data-ttu-id="e2502-109">Описание</span><span class="sxs-lookup"><span data-stu-id="e2502-109">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="e2502-110">Строка, определяющая имя пула подключений, используемого для исходящих каналов.</span><span class="sxs-lookup"><span data-stu-id="e2502-110">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="e2502-111">В потоковом режиме общий доступ к подключениям не предоставляется, то есть пул подключений отключен.</span><span class="sxs-lookup"><span data-stu-id="e2502-111">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="e2502-112">Значение по умолчанию - строка «default».</span><span class="sxs-lookup"><span data-stu-id="e2502-112">The default is a "default" string.</span></span> <span data-ttu-id="e2502-113">Это значение можно изменить, чтобы изолировать подключения для конкретного клиента в отдельные группы.</span><span class="sxs-lookup"><span data-stu-id="e2502-113">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="e2502-114">Положительное значение <xref:System.TimeSpan>, указывающее максимальное время бездействия для подключения перед его закрытием.</span><span class="sxs-lookup"><span data-stu-id="e2502-114">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="e2502-115">Значение по умолчанию - 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="e2502-115">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="e2502-116">Параметр <xref:System.TimeSpan>, задающий время ожидания перед закрытием активного подключения.</span><span class="sxs-lookup"><span data-stu-id="e2502-116">A <xref:System.TimeSpan> that specifies the time after which an active connection is closed.</span></span> <span data-ttu-id="e2502-117">Значение по умолчанию - 00:05:00.</span><span class="sxs-lookup"><span data-stu-id="e2502-117">The default is 00:05:00.</span></span><br /><br /> <span data-ttu-id="e2502-118">Подключение закрывается после возврата в кэш подключений, а не во время активной передачи.</span><span class="sxs-lookup"><span data-stu-id="e2502-118">A connection is closed after it has been returned to the connection cache and not during active transmission.</span></span> <span data-ttu-id="e2502-119">Кэш подключений, используемый транспортом TCP, по мере необходимости создает новые подключения для каждой конечной точки, до достижения лимита кэша, который задается параметром `maxOutboundConnectionsPerEndpoint.`</span><span class="sxs-lookup"><span data-stu-id="e2502-119">The connection cache used by the TCP transport creates new connections as required for each endpoint, up to the cache limit that is set by `maxOutboundConnectionsPerEndpoint.`</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="e2502-120">Положительное целое число, указывающее максимальное число подключений к удаленной конечной точке, инициированных одной службой.</span><span class="sxs-lookup"><span data-stu-id="e2502-120">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="e2502-121">Соединения сверх лимита помещаются в очередь до высвобождения ресурсов.</span><span class="sxs-lookup"><span data-stu-id="e2502-121">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="e2502-122">Параметр `idleTimeout` ограничивает продолжительность времени, в течение которого подключения остаются в очереди до возникновения исключения.</span><span class="sxs-lookup"><span data-stu-id="e2502-122">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="e2502-123">Значение по умолчанию равно 10.</span><span class="sxs-lookup"><span data-stu-id="e2502-123">The default is 10.</span></span><br /><br /> <span data-ttu-id="e2502-124">Этот атрибут ограничивает число одновременных активных подключений клиента к конкретной конечной точке службы.</span><span class="sxs-lookup"><span data-stu-id="e2502-124">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="e2502-125">В случае превышения этого значения при наличии большего числа активных соединений клиентов служба может прекратить отвечать на запросы клиента.</span><span class="sxs-lookup"><span data-stu-id="e2502-125">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="e2502-126">В таком случае это значение следует скорректировать, чтобы оно было больше предполагаемого максимума одновременных подключений клиента к конкретной конечной точке.</span><span class="sxs-lookup"><span data-stu-id="e2502-126">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e2502-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e2502-127">Child Elements</span></span>  

 <span data-ttu-id="e2502-128">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e2502-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e2502-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e2502-129">Parent Elements</span></span>  
  
|<span data-ttu-id="e2502-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="e2502-130">Element</span></span>|<span data-ttu-id="e2502-131">Описание</span><span class="sxs-lookup"><span data-stu-id="e2502-131">Description</span></span>|  
|-------------|-----------------|  
|[\<namedPipeTransport>](namedpipetransport.md)|<span data-ttu-id="e2502-132">Определяет транспорт, вызывающий передачу сообщений с использованием именованных каналов.</span><span class="sxs-lookup"><span data-stu-id="e2502-132">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e2502-133">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e2502-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.TcpConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="e2502-134">Транспорты</span><span class="sxs-lookup"><span data-stu-id="e2502-134">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="e2502-135">Выбор транспортов</span><span class="sxs-lookup"><span data-stu-id="e2502-135">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="e2502-136">Привязки</span><span class="sxs-lookup"><span data-stu-id="e2502-136">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e2502-137">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="e2502-137">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="e2502-138">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="e2502-138">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
