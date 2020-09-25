---
title: <net.pipe>
ms.date: 03/30/2017
ms.assetid: 6a0f0318-f8f6-466c-9fae-199d7274a82e
ms.openlocfilehash: d070b822cefeef3c281d5b0e47411f4c624dd83f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204610"
---
# \<net.pipe>

<span data-ttu-id="6ba29-102">Задает параметры конфигурации для службы активации именованных каналов, которая управляет временем существования соединения для именованного канала, а также обрабатывает запросы на активацию, которые поступают по именованным каналам.</span><span class="sxs-lookup"><span data-stu-id="6ba29-102">Specifies configuration settings for the Named Pipe Activation Service, which manages the lifetime of the named pipe connection, and handles activation requests that arrive over named pipes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<net.pipe>**  
  
## <a name="syntax"></a><span data-ttu-id="6ba29-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6ba29-103">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <net.pipe maxPendingAccepts="Integer"
              maxPendingConnections="Integer"
              receiveTimeout="TimeSpan">
      <allowAccounts>
        <!-- LocalSystem account -->
        <add securityIdentifier="S-1-5-18" />
        <!-- LocalService account -->
        <add securityIdentifier="S-1-5-19" />
        <!-- Administrators account -->
        <add securityIdentifier="S-1-5-20" />
        <!-- Network Service account -->
        <add securityIdentifier="S-1-5-32-544" />
        <!-- IIS_IUSRS account (Vista only) -->
        <add securityIdentifier="S-1-5-32-568" />
      </allowAccounts>
    </net.pipe>
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="6ba29-104">Type</span><span class="sxs-lookup"><span data-stu-id="6ba29-104">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6ba29-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6ba29-105">Attributes and Elements</span></span>  

 <span data-ttu-id="6ba29-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6ba29-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6ba29-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6ba29-107">Attributes</span></span>  
  
|<span data-ttu-id="6ba29-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6ba29-108">Attribute</span></span>|<span data-ttu-id="6ba29-109">Описание</span><span class="sxs-lookup"><span data-stu-id="6ba29-109">Description</span></span>|  
|---------------|-----------------|  
|`maxPendingAccepts`|<span data-ttu-id="6ba29-110">Целое число, которое определяет максимальное количество одновременных необработанных принимающих потоков в конечной точке для общей службы.</span><span class="sxs-lookup"><span data-stu-id="6ba29-110">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="6ba29-111">Значение по умолчанию — 2</span><span class="sxs-lookup"><span data-stu-id="6ba29-111">The default is 2.</span></span>|  
|`maxPendingConnections`|<span data-ttu-id="6ba29-112">Целое число, задающее максимальное количество соединений, которые могут ожидать распределения.</span><span class="sxs-lookup"><span data-stu-id="6ba29-112">An integer that specifies the maximum number of connections that can wait for dispatch.</span></span> <span data-ttu-id="6ba29-113">Значение по умолчанию — 100.</span><span class="sxs-lookup"><span data-stu-id="6ba29-113">The default is 100.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="6ba29-114">Значение <xref:System.TimeSpan>, определяющее время ожидания для чтения данных кадрирования и проведения распределения подключений из базовых подключений.</span><span class="sxs-lookup"><span data-stu-id="6ba29-114">A <xref:System.TimeSpan> that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="6ba29-115">Значение по умолчанию - 00:00:10.</span><span class="sxs-lookup"><span data-stu-id="6ba29-115">The default is "00:00:10"</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6ba29-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6ba29-116">Child Elements</span></span>  
  
|<span data-ttu-id="6ba29-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="6ba29-117">Element</span></span>|<span data-ttu-id="6ba29-118">Описание</span><span class="sxs-lookup"><span data-stu-id="6ba29-118">Description</span></span>|  
|-------------|-----------------|  
|[\<allowAccounts>](allowaccounts.md)|<span data-ttu-id="6ba29-119">Коллекция элементов конфигурации, которая содержит `securityIdentifier` атрибут для указания учетных записей пользователей для процессов, размещающий службы WCF, и которым предоставляется доступ к службе общего доступа.</span><span class="sxs-lookup"><span data-stu-id="6ba29-119">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6ba29-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6ba29-120">Parent Elements</span></span>  
  
|<span data-ttu-id="6ba29-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="6ba29-121">Element</span></span>|<span data-ttu-id="6ba29-122">Описание</span><span class="sxs-lookup"><span data-stu-id="6ba29-122">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel.activation>](system-servicemodel-activation.md)|<span data-ttu-id="6ba29-123">Содержит параметры конфигурации для процесса прослушивателя SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="6ba29-123">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6ba29-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6ba29-124">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection>
