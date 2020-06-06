---
title: <net.pipe>
ms.date: 03/30/2017
ms.assetid: 6a0f0318-f8f6-466c-9fae-199d7274a82e
ms.openlocfilehash: dd984b2ab89060451b1b2d02c324e803766908ce
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397718"
---
# \<net.pipe>
<span data-ttu-id="3ba08-102">Задает параметры конфигурации для службы активации именованных каналов, которая управляет временем существования соединения для именованного канала, а также обрабатывает запросы на активацию, которые поступают по именованным каналам.</span><span class="sxs-lookup"><span data-stu-id="3ba08-102">Specifies configuration settings for the Named Pipe Activation Service, which manages the lifetime of the named pipe connection, and handles activation requests that arrive over named pipes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<net.pipe>**  
  
## <a name="syntax"></a><span data-ttu-id="3ba08-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3ba08-103">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="3ba08-104">Type</span><span class="sxs-lookup"><span data-stu-id="3ba08-104">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3ba08-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3ba08-105">Attributes and Elements</span></span>  
 <span data-ttu-id="3ba08-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3ba08-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3ba08-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3ba08-107">Attributes</span></span>  
  
|<span data-ttu-id="3ba08-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3ba08-108">Attribute</span></span>|<span data-ttu-id="3ba08-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="3ba08-109">Description</span></span>|  
|---------------|-----------------|  
|`maxPendingAccepts`|<span data-ttu-id="3ba08-110">Целое число, которое определяет максимальное количество одновременных необработанных принимающих потоков в конечной точке для общей службы.</span><span class="sxs-lookup"><span data-stu-id="3ba08-110">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="3ba08-111">Значение по умолчанию — 2</span><span class="sxs-lookup"><span data-stu-id="3ba08-111">The default is 2.</span></span>|  
|`maxPendingConnections`|<span data-ttu-id="3ba08-112">Целое число, задающее максимальное количество соединений, которые могут ожидать распределения.</span><span class="sxs-lookup"><span data-stu-id="3ba08-112">An integer that specifies the maximum number of connections that can wait for dispatch.</span></span> <span data-ttu-id="3ba08-113">Значение по умолчанию — 100.</span><span class="sxs-lookup"><span data-stu-id="3ba08-113">The default is 100.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="3ba08-114">Значение <xref:System.TimeSpan>, определяющее время ожидания для чтения данных кадрирования и проведения распределения подключений из базовых подключений.</span><span class="sxs-lookup"><span data-stu-id="3ba08-114">A <xref:System.TimeSpan> that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="3ba08-115">Значение по умолчанию - 00:00:10.</span><span class="sxs-lookup"><span data-stu-id="3ba08-115">The default is "00:00:10"</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3ba08-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3ba08-116">Child Elements</span></span>  
  
|<span data-ttu-id="3ba08-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="3ba08-117">Element</span></span>|<span data-ttu-id="3ba08-118">Описание</span><span class="sxs-lookup"><span data-stu-id="3ba08-118">Description</span></span>|  
|-------------|-----------------|  
|[\<allowAccounts>](allowaccounts.md)|<span data-ttu-id="3ba08-119">Коллекция элементов конфигурации, которая содержит `securityIdentifier` атрибут для указания учетных записей пользователей для процессов, размещающий службы WCF, и которым предоставляется доступ к службе общего доступа.</span><span class="sxs-lookup"><span data-stu-id="3ba08-119">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3ba08-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3ba08-120">Parent Elements</span></span>  
  
|<span data-ttu-id="3ba08-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="3ba08-121">Element</span></span>|<span data-ttu-id="3ba08-122">Описание</span><span class="sxs-lookup"><span data-stu-id="3ba08-122">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel.activation>](system-servicemodel-activation.md)|<span data-ttu-id="3ba08-123">Содержит параметры конфигурации для процесса прослушивателя SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="3ba08-123">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3ba08-124">См. также</span><span class="sxs-lookup"><span data-stu-id="3ba08-124">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection>
