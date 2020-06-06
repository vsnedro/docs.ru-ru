---
title: <protocolMapping>
ms.date: 03/30/2017
ms.assetid: 5076644b-1f33-4f26-9488-87de9fcda04c
ms.openlocfilehash: be4224ef1a8b17653df8123aaf89e105a496355a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400025"
---
# \<protocolMapping>
<span data-ttu-id="f8527-101">Представляет раздел конфигурации, в котором определяется набор сопоставления протоколов по умолчанию между схемами транспортных протоколов (например, http, net.tcp, net.pipe и т. д.) и привязками WCF.</span><span class="sxs-lookup"><span data-stu-id="f8527-101">Represents a configuration section for defining a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span> <span data-ttu-id="f8527-102">При создании конечных точек по умолчанию во время выполнения Windows Communication Foundation (WCF) рассматривает настроенные сопоставления и решает, какую привязку использовать для конкретного адреса на основе.</span><span class="sxs-lookup"><span data-stu-id="f8527-102">When creating default endpoints at runtime, Windows Communication Foundation (WCF) looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<protocolMapping>**  
  
## <a name="syntax"></a><span data-ttu-id="f8527-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f8527-103">Syntax</span></span>  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f8527-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f8527-104">Attributes and Elements</span></span>  
 <span data-ttu-id="f8527-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f8527-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f8527-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f8527-106">Attributes</span></span>  
 <span data-ttu-id="f8527-107">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f8527-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f8527-108">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f8527-108">Child Elements</span></span>  
  
|<span data-ttu-id="f8527-109">Элемент</span><span class="sxs-lookup"><span data-stu-id="f8527-109">Element</span></span>|<span data-ttu-id="f8527-110">Описание</span><span class="sxs-lookup"><span data-stu-id="f8527-110">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|<span data-ttu-id="f8527-111">Содержит сопоставление протокола по умолчанию между схемой транспортного протокола (например http, net.tcp, net.pipe и т. д.) и привязкой WCF.</span><span class="sxs-lookup"><span data-stu-id="f8527-111">Contains a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a WCF binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f8527-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f8527-112">Parent Elements</span></span>  
  
|<span data-ttu-id="f8527-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="f8527-113">Element</span></span>|<span data-ttu-id="f8527-114">Описание</span><span class="sxs-lookup"><span data-stu-id="f8527-114">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel>](system-servicemodel.md)|<span data-ttu-id="f8527-115">Корневой элемент всех элементов конфигурации WCF.</span><span class="sxs-lookup"><span data-stu-id="f8527-115">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f8527-116">Пример</span><span class="sxs-lookup"><span data-stu-id="f8527-116">Example</span></span>  
 <span data-ttu-id="f8527-117">В следующем примере конфигурации показано сопоставление протокола по умолчанию в файле machine.config.</span><span class="sxs-lookup"><span data-stu-id="f8527-117">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="f8527-118">Это сопоставление по умолчанию можно переопределить на уровне компьютера путем изменения файла machine.config.</span><span class="sxs-lookup"><span data-stu-id="f8527-118">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="f8527-119">Или же, если необходимо переопределить это сопоставление только в области приложения, можно отменить этот раздел в файле конфигурации приложения и изменить сопоставление для отдельных схем протокола.</span><span class="sxs-lookup"><span data-stu-id="f8527-119">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
```xml  
<protocolMapping>
  <add scheme="http"
       binding="basicHttpBinding" />
  <add scheme="net.tcp"
       binding="netTcpBinding" />
  <add scheme="net.pipe"
       binding="netNamedPipeBinding" />
  <add scheme="net.msmq"
       binding="netMsmqBinding" />
</protocolMapping>
```  
  
## <a name="see-also"></a><span data-ttu-id="f8527-120">См. также</span><span class="sxs-lookup"><span data-stu-id="f8527-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>
