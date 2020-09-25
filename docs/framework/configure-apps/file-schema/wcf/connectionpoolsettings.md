---
title: <connectionPoolSettings>
ms.date: 03/30/2017
ms.assetid: 6fa7fa65-2c6e-4eab-b8cf-7690112c0be5
ms.openlocfilehash: d8787bc2ef8da4fdc01237ac9b041dfdd66fce03
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175997"
---
# \<connectionPoolSettings>

<span data-ttu-id="38e47-101">Задает дополнительные параметры пула подключений для привязки именованного канала.</span><span class="sxs-lookup"><span data-stu-id="38e47-101">Specifies additional connection pool settings for a Named Pipe binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedPipeTransport>**](namedpipetransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionPoolSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="38e47-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="38e47-102">Syntax</span></span>  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="38e47-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="38e47-103">Attributes and Elements</span></span>  

 <span data-ttu-id="38e47-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="38e47-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="38e47-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="38e47-105">Attributes</span></span>  
  
|<span data-ttu-id="38e47-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="38e47-106">Attribute</span></span>|<span data-ttu-id="38e47-107">Описание</span><span class="sxs-lookup"><span data-stu-id="38e47-107">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="38e47-108">Строка, определяющая имя пула подключений, используемого для исходящих каналов.</span><span class="sxs-lookup"><span data-stu-id="38e47-108">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="38e47-109">В потоковом режиме общий доступ к подключениям не предоставляется, то есть пул подключений отключен.</span><span class="sxs-lookup"><span data-stu-id="38e47-109">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="38e47-110">Значение по умолчанию - строка «default».</span><span class="sxs-lookup"><span data-stu-id="38e47-110">The default is a "default" string.</span></span> <span data-ttu-id="38e47-111">Это значение можно изменить, чтобы изолировать подключения для конкретного клиента в отдельные группы.</span><span class="sxs-lookup"><span data-stu-id="38e47-111">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="38e47-112">Положительное значение <xref:System.TimeSpan>, указывающее максимальное время бездействия для подключения перед его закрытием.</span><span class="sxs-lookup"><span data-stu-id="38e47-112">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="38e47-113">Значение по умолчанию - 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="38e47-113">The default is 00:02:00.</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="38e47-114">Положительное целое число, указывающее максимальное число подключений к удаленной конечной точке, инициированных одной службой.</span><span class="sxs-lookup"><span data-stu-id="38e47-114">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="38e47-115">Соединения сверх лимита помещаются в очередь до высвобождения ресурсов.</span><span class="sxs-lookup"><span data-stu-id="38e47-115">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="38e47-116">Параметр `idleTimeout` ограничивает продолжительность времени, в течение которого подключения остаются в очереди до возникновения исключения.</span><span class="sxs-lookup"><span data-stu-id="38e47-116">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="38e47-117">Значение по умолчанию равно 10.</span><span class="sxs-lookup"><span data-stu-id="38e47-117">The default is 10.</span></span><br /><br /> <span data-ttu-id="38e47-118">Этот атрибут ограничивает число одновременных активных подключений клиента к конкретной конечной точке службы.</span><span class="sxs-lookup"><span data-stu-id="38e47-118">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="38e47-119">В случае превышения этого значения при наличии большего числа активных соединений клиентов служба может прекратить отвечать на запросы клиента.</span><span class="sxs-lookup"><span data-stu-id="38e47-119">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="38e47-120">В таком случае это значение следует скорректировать, чтобы оно было больше предполагаемого максимума одновременных подключений клиента к конкретной конечной точке.</span><span class="sxs-lookup"><span data-stu-id="38e47-120">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="38e47-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="38e47-121">Child Elements</span></span>  

 <span data-ttu-id="38e47-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="38e47-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="38e47-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="38e47-123">Parent Elements</span></span>  
  
|<span data-ttu-id="38e47-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="38e47-124">Element</span></span>|<span data-ttu-id="38e47-125">Описание</span><span class="sxs-lookup"><span data-stu-id="38e47-125">Description</span></span>|  
|-------------|-----------------|  
|[\<namedPipeTransport>](namedpipetransport.md)|<span data-ttu-id="38e47-126">Определяет транспорт, вызывающий передачу сообщений с использованием именованных каналов.</span><span class="sxs-lookup"><span data-stu-id="38e47-126">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="38e47-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="38e47-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.NamedPipeConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="38e47-128">Транспорты</span><span class="sxs-lookup"><span data-stu-id="38e47-128">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="38e47-129">Выбор транспортов</span><span class="sxs-lookup"><span data-stu-id="38e47-129">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="38e47-130">Привязки</span><span class="sxs-lookup"><span data-stu-id="38e47-130">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="38e47-131">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="38e47-131">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="38e47-132">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="38e47-132">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
