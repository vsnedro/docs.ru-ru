---
title: <net.tcp>
ms.date: 03/30/2017
ms.assetid: 8bc2f2be-11c1-4bab-9018-1d21ae568d94
ms.openlocfilehash: 12709d58d9192825598b15a50baa10a54450226e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178077"
---
# \<net.tcp>

<span data-ttu-id="09f84-102">Задает параметры конфигурации для службы общего доступа к портам Net.Tcp, которая позволяет нескольким процессам совместно использовать один и тот же порт протокола TCP.</span><span class="sxs-lookup"><span data-stu-id="09f84-102">Specifies configuration settings for the NET.TCP Port Sharing Service, which allows multiple processes to share the same TCP port.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<net.tcp>**  
  
## <a name="syntax"></a><span data-ttu-id="09f84-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="09f84-103">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <net.tcp listenBacklog="Integer"
             maxPendingAccepts="Integer"
             maxPendingConnections="Integer"
             receiveTimeout="TimeSpan"
             teredoEnabled="Boolean">
      <allowAccounts>
        <!-- LocalSystem account -->
        <add securityIdentifier="S-1-5-18"/>
        <!-- LocalService account -->
        <add securityIdentifier="S-1-5-19"/>
        <!-- Administrators account -->
        <add securityIdentifier="S-1-5-20"/>
        <!-- Network Service account -->
        <add securityIdentifier="S-1-5-32-544" />
        <!-- IIS_IUSRS account (Vista only)-->
        <add securityIdentifier="S-1-5-32-568"/>
      </allowAccounts>
    </net.tcp>
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="09f84-104">Type</span><span class="sxs-lookup"><span data-stu-id="09f84-104">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="09f84-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="09f84-105">Attributes and Elements</span></span>  

 <span data-ttu-id="09f84-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="09f84-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="09f84-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="09f84-107">Attributes</span></span>  
  
|<span data-ttu-id="09f84-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="09f84-108">Attribute</span></span>|<span data-ttu-id="09f84-109">Описание</span><span class="sxs-lookup"><span data-stu-id="09f84-109">Description</span></span>|  
|---------------|-----------------|  
|`listenBacklog`|<span data-ttu-id="09f84-110">Целое число, указывающее максимальное количество необработанных соединений, принимаемых из общего соединения, но еще не отправленных в службы Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="09f84-110">An integer that specifies the maximum outstanding connections that are accepted from the shared connection, but are not yet dispatched to Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="09f84-111">Значение по умолчанию равно 10.</span><span class="sxs-lookup"><span data-stu-id="09f84-111">The default is 10.</span></span>|  
|`maxPendingAccepts`|<span data-ttu-id="09f84-112">Целое число, которое определяет максимальное количество одновременных необработанных принимающих потоков в конечной точке для общей службы.</span><span class="sxs-lookup"><span data-stu-id="09f84-112">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="09f84-113">Значение по умолчанию — 2</span><span class="sxs-lookup"><span data-stu-id="09f84-113">The default is 2.</span></span>|  
|`MaxPendingConnections`|<span data-ttu-id="09f84-114">Максимальное число подключений, принятия которых приложением может ожидать прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="09f84-114">The maximum number of connections that the listener can have waiting to be accepted by the application.</span></span> <span data-ttu-id="09f84-115">После превышения значения этой квоты новые входящие подключения сбрасываются, а не ожидают принятия.</span><span class="sxs-lookup"><span data-stu-id="09f84-115">When this quota value is exceeded, new incoming connections are dropped rather than waiting to be accepted.</span></span> <span data-ttu-id="09f84-116">Возможности подключения (такие как безопасность сообщения) могут вынудить клиента открыть несколько подключений.</span><span class="sxs-lookup"><span data-stu-id="09f84-116">Connection features such as message security can cause a client to open more than one connection.</span></span> <span data-ttu-id="09f84-117">При установке значения квоты администраторы службы должны учитывать возможность установления дополнительных подключений.</span><span class="sxs-lookup"><span data-stu-id="09f84-117">Service administrators should account for these additional connections when setting this quota value.</span></span> <span data-ttu-id="09f84-118">Значение по умолчанию равно 10.</span><span class="sxs-lookup"><span data-stu-id="09f84-118">The default is 10.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="09f84-119">Значение <xref:System.TimeSpan>, определяющее время ожидания для чтения данных кадрирования и проведения распределения подключений из базовых подключений.</span><span class="sxs-lookup"><span data-stu-id="09f84-119">A <xref:System.TimeSpan> that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="09f84-120">Значение по умолчанию - 00:00:10.</span><span class="sxs-lookup"><span data-stu-id="09f84-120">The default is "00:00:10".</span></span>|  
|`teredoEnabled`|<span data-ttu-id="09f84-121">Логическое значение, указывающее, использует ли служба совместного использования портов службу Microsoft Teredo для прослушивания TCP-портов от имени служб WCF.</span><span class="sxs-lookup"><span data-stu-id="09f84-121">A Boolean value that indicates whether the port sharing service uses Microsoft Teredo service to listen on TCP ports on behalf of WCF services.</span></span> <span data-ttu-id="09f84-122">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="09f84-122">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="09f84-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="09f84-123">Child Elements</span></span>  
  
|<span data-ttu-id="09f84-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="09f84-124">Element</span></span>|<span data-ttu-id="09f84-125">Описание</span><span class="sxs-lookup"><span data-stu-id="09f84-125">Description</span></span>|  
|-------------|-----------------|  
|[\<allowAccounts>](allowaccounts.md)|<span data-ttu-id="09f84-126">Коллекция элементов конфигурации, которая содержит `securityIdentifier` атрибут для указания учетных записей пользователей для процессов, размещающий службы WCF, и которым предоставляется доступ к службе общего доступа.</span><span class="sxs-lookup"><span data-stu-id="09f84-126">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="09f84-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="09f84-127">Parent Elements</span></span>  
  
|<span data-ttu-id="09f84-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="09f84-128">Element</span></span>|<span data-ttu-id="09f84-129">Описание</span><span class="sxs-lookup"><span data-stu-id="09f84-129">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel.activation>](system-servicemodel-activation.md)|<span data-ttu-id="09f84-130">Содержит параметры конфигурации для процесса прослушивателя SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="09f84-130">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09f84-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="09f84-131">Remarks</span></span>  

 <span data-ttu-id="09f84-132">Дополнительные сведения о совместном использовании портов см. в разделе [общий доступ к портам Net. TCP](../../../wcf/feature-details/net-tcp-port-sharing.md).</span><span class="sxs-lookup"><span data-stu-id="09f84-132">For more information on port sharing, see [Net.TCP Port Sharing](../../../wcf/feature-details/net-tcp-port-sharing.md).</span></span> <span data-ttu-id="09f84-133">Сведения о настройке службы общего доступа к портам см. в разделе [Настройка службы совместного использования портов net. TCP](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md).</span><span class="sxs-lookup"><span data-stu-id="09f84-133">To understand how to configure the port sharing service, see [Configuring the Net.TCP Port Sharing Service](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09f84-134">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="09f84-134">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection>
- [<span data-ttu-id="09f84-135">Совместное использование портов Net.TCP</span><span class="sxs-lookup"><span data-stu-id="09f84-135">Net.TCP Port Sharing</span></span>](../../../wcf/feature-details/net-tcp-port-sharing.md)
- [<span data-ttu-id="09f84-136">Настройка службы совместного использования портов Net.TCP</span><span class="sxs-lookup"><span data-stu-id="09f84-136">Configuring the Net.TCP Port Sharing Service</span></span>](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)
