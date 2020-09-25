---
title: <webSocketSettings>
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: 6cfddfb9ebfc7c3447af977e14738baabebc8fe9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177855"
---
# \<webSocketSettings>

<span data-ttu-id="599b4-101">Элемент конфигурации, который служит для задания параметров веб-сокета.</span><span class="sxs-lookup"><span data-stu-id="599b4-101">A configuration element used to specify Web Socket settings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webSocketSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="599b4-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="599b4-102">Syntax</span></span>  
  
```xml  
<netHttpBinding>
  <binding>
    <webSocketSettings createNotificationOnConnection="Boolean"
                       disablePayloadMasking="Boolean"
                       keepAliveInterval="TimeSpan"
                       maxPendingConnections="Integer"
                       receiveBufferSize="Integer"
                       sendBufferSize="Integer"
                       subProtocol="String"
                       transportUsage="WhenDuplex/Always/Never" />
  </binding>
</netHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="599b4-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="599b4-103">Attributes and Elements</span></span>  

 <span data-ttu-id="599b4-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="599b4-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="599b4-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="599b4-105">Attributes</span></span>  
  
|<span data-ttu-id="599b4-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="599b4-106">Attribute</span></span>|<span data-ttu-id="599b4-107">Описание</span><span class="sxs-lookup"><span data-stu-id="599b4-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="599b4-108">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="599b4-108">createNotificationOnConnection</span></span>|<span data-ttu-id="599b4-109">Определяет, следует ли отправлять уведомления при соединении.</span><span class="sxs-lookup"><span data-stu-id="599b4-109">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="599b4-110">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="599b4-110">disablePayloadMasking</span></span>|<span data-ttu-id="599b4-111">Определяет, отключено ли маскирование веб-сокета.</span><span class="sxs-lookup"><span data-stu-id="599b4-111">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="599b4-112">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="599b4-112">keepAliveInterval</span></span>|<span data-ttu-id="599b4-113">Определяет интервал поддержки активности канала.</span><span class="sxs-lookup"><span data-stu-id="599b4-113">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="599b4-114">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="599b4-114">maxPendingConnections</span></span>|<span data-ttu-id="599b4-115">Определяет максимальное число подключений, ожидающих распределения в службе.</span><span class="sxs-lookup"><span data-stu-id="599b4-115">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="599b4-116">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="599b4-116">receiveBufferSize</span></span>|<span data-ttu-id="599b4-117">Определяет размер буфера приема.</span><span class="sxs-lookup"><span data-stu-id="599b4-117">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="599b4-118">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="599b4-118">sendBufferSize</span></span>|<span data-ttu-id="599b4-119">Определяет размер буфера отправки.</span><span class="sxs-lookup"><span data-stu-id="599b4-119">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="599b4-120">subProtocol</span><span class="sxs-lookup"><span data-stu-id="599b4-120">subProtocol</span></span>|<span data-ttu-id="599b4-121">Определяет подпротокол веб-сокета.</span><span class="sxs-lookup"><span data-stu-id="599b4-121">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="599b4-122">transportUsage</span><span class="sxs-lookup"><span data-stu-id="599b4-122">transportUsage</span></span>|<span data-ttu-id="599b4-123">Указывает, когда использовать веб-сокеты.</span><span class="sxs-lookup"><span data-stu-id="599b4-123">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="599b4-124">Атрибут transportUsage</span><span class="sxs-lookup"><span data-stu-id="599b4-124">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="599b4-125">Значение</span><span class="sxs-lookup"><span data-stu-id="599b4-125">Value</span></span>|<span data-ttu-id="599b4-126">Описание</span><span class="sxs-lookup"><span data-stu-id="599b4-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="599b4-127">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="599b4-127">WhenDuplex</span></span>|<span data-ttu-id="599b4-128">Использовать протокол веб-сокета, если контракт является дуплексным.</span><span class="sxs-lookup"><span data-stu-id="599b4-128">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="599b4-129">Всегда</span><span class="sxs-lookup"><span data-stu-id="599b4-129">Always</span></span>|<span data-ttu-id="599b4-130">Всегда использовать протокол веб-сокетов независимо от контракта.</span><span class="sxs-lookup"><span data-stu-id="599b4-130">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="599b4-131">Никогда</span><span class="sxs-lookup"><span data-stu-id="599b4-131">Never</span></span>|<span data-ttu-id="599b4-132">Никогда не использовать протокол веб-сокетов.</span><span class="sxs-lookup"><span data-stu-id="599b4-132">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="599b4-133">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="599b4-133">Child Elements</span></span>  

 <span data-ttu-id="599b4-134">Нет</span><span class="sxs-lookup"><span data-stu-id="599b4-134">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="599b4-135">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="599b4-135">Parent Elements</span></span>  
  
|<span data-ttu-id="599b4-136">Элемент</span><span class="sxs-lookup"><span data-stu-id="599b4-136">Element</span></span>|<span data-ttu-id="599b4-137">Описание</span><span class="sxs-lookup"><span data-stu-id="599b4-137">Description</span></span>|  
|-------------|-----------------|  
|\<netHttpBinding>|<span data-ttu-id="599b4-138">Определяет привязку NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="599b4-138">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="599b4-139">Пример</span><span class="sxs-lookup"><span data-stu-id="599b4-139">Example</span></span>  

 <span data-ttu-id="599b4-140">В следующем примере показано использование элемента \<webSocketSettings>.</span><span class="sxs-lookup"><span data-stu-id="599b4-140">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
```xml  
<netHttpBinding>
  <binding>
    <webSocketSettings createNotificationOnConnection="true"
                       disablePayloadMasking="false"
                       keepAliveInterval="00:10:00"
                       maxPendingConnections="100"
                       receiveBufferSize="1000"
                       sendBufferSize="1000"
                       subProtocol="Soap"
                       transportUsage="WhenDuplex/Always/Never" />
  </binding>
</netHttpBinding>
```  
  
## <a name="see-also"></a><span data-ttu-id="599b4-141">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="599b4-141">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="599b4-142">Привязки</span><span class="sxs-lookup"><span data-stu-id="599b4-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="599b4-143">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="599b4-143">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="599b4-144">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="599b4-144">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
