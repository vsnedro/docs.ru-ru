---
title: <add> из <protocolMapping>
ms.date: 03/30/2017
ms.assetid: 08e62249-1641-41d1-91b1-66d7b46244e4
ms.openlocfilehash: 6197d01665d49a7c97ac9e44251abf15faf80a8f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850379"
---
# <a name="add-of-protocolmapping"></a><span data-ttu-id="8342a-102">\<add> из \<protocolMapping></span><span class="sxs-lookup"><span data-stu-id="8342a-102">\<add> of \<protocolMapping></span></span>
<span data-ttu-id="8342a-103">Представляет сопоставление протокола по умолчанию между схемой транспортного протокола (например, HTTP, net. TCP, net. pipe и т. д.) и привязкой Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="8342a-103">Represents a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a Windows Communication Foundation (WCF) binding.</span></span> <span data-ttu-id="8342a-104">При создании конечных точек по умолчанию во время выполнения WCF проверяет настроенные сопоставления и решает, какая привязка будет использоваться для конкретного адреса на основе.</span><span class="sxs-lookup"><span data-stu-id="8342a-104">When creating default endpoints at runtime, WCF looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<protocolMapping>**](protocolmapping.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="8342a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8342a-105">Syntax</span></span>  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8342a-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8342a-106">Attributes and Elements</span></span>  
 <span data-ttu-id="8342a-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8342a-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8342a-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8342a-108">Attributes</span></span>  
  
|<span data-ttu-id="8342a-109">Элемент</span><span class="sxs-lookup"><span data-stu-id="8342a-109">Element</span></span>|<span data-ttu-id="8342a-110">Описание</span><span class="sxs-lookup"><span data-stu-id="8342a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8342a-111">binding</span><span class="sxs-lookup"><span data-stu-id="8342a-111">binding</span></span>|<span data-ttu-id="8342a-112">Строка, в которой указан тип привязки, используемый для конечной точки во время создания конечной точки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8342a-112">A string that specifies the type of binding to be used for an endpoint during default endpoint creation.</span></span>|  
|<span data-ttu-id="8342a-113">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="8342a-113">bindingConfiguration</span></span>|<span data-ttu-id="8342a-114">Строка, содержащая имя раздела конфигурации привязки, на который будет установлена ссылка.</span><span class="sxs-lookup"><span data-stu-id="8342a-114">A string that specifies the name of the binding configuration section to be referenced.</span></span>|  
|<span data-ttu-id="8342a-115">scheme</span><span class="sxs-lookup"><span data-stu-id="8342a-115">scheme</span></span>|<span data-ttu-id="8342a-116">Схема транспортного протокола, которая будет использоваться для конечной точки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8342a-116">The transport protocol scheme to be used for the default endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8342a-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8342a-117">Child Elements</span></span>  
 <span data-ttu-id="8342a-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8342a-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8342a-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8342a-119">Parent Elements</span></span>  
  
|<span data-ttu-id="8342a-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="8342a-120">Element</span></span>|<span data-ttu-id="8342a-121">Описание</span><span class="sxs-lookup"><span data-stu-id="8342a-121">Description</span></span>|  
|-------------|-----------------|  
|[\<protocolMapping>](protocolmapping.md)|<span data-ttu-id="8342a-122">Представляет раздел конфигурации для определения сопоставлений протоколов по умолчанию между схемами транспортного протокола (например, HTTP, net. TCP, net. pipe и т. д.) и привязками Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="8342a-122">Represents a configuration section for defining default protocol mappings between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and Windows Communication Foundation (WCF) bindings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8342a-123">Пример</span><span class="sxs-lookup"><span data-stu-id="8342a-123">Example</span></span>  
 <span data-ttu-id="8342a-124">В следующем примере конфигурации показано сопоставление протокола по умолчанию в файле machine.config.</span><span class="sxs-lookup"><span data-stu-id="8342a-124">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="8342a-125">Это сопоставление по умолчанию можно переопределить на уровне компьютера путем изменения файла machine.config.</span><span class="sxs-lookup"><span data-stu-id="8342a-125">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="8342a-126">Или же, если необходимо переопределить это сопоставление только в области приложения, можно отменить этот раздел в файле конфигурации приложения и изменить сопоставление для отдельных схем протокола.</span><span class="sxs-lookup"><span data-stu-id="8342a-126">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8342a-127">См. также</span><span class="sxs-lookup"><span data-stu-id="8342a-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>
