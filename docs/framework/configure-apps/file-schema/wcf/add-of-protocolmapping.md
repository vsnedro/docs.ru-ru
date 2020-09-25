---
title: <add> из <protocolMapping>
ms.date: 03/30/2017
ms.assetid: 08e62249-1641-41d1-91b1-66d7b46244e4
ms.openlocfilehash: 46ba21b65f524f88bfce81739f0cd73040a2ad45
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91205013"
---
# <a name="add-of-protocolmapping"></a><span data-ttu-id="f89d0-102">\<add> из \<protocolMapping></span><span class="sxs-lookup"><span data-stu-id="f89d0-102">\<add> of \<protocolMapping></span></span>

<span data-ttu-id="f89d0-103">Представляет сопоставление протокола по умолчанию между схемой транспортного протокола (например, HTTP, net. TCP, net. pipe и т. д.) и привязкой Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="f89d0-103">Represents a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a Windows Communication Foundation (WCF) binding.</span></span> <span data-ttu-id="f89d0-104">При создании конечных точек по умолчанию во время выполнения WCF проверяет настроенные сопоставления и решает, какая привязка будет использоваться для конкретного адреса на основе.</span><span class="sxs-lookup"><span data-stu-id="f89d0-104">When creating default endpoints at runtime, WCF looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<protocolMapping>**](protocolmapping.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="f89d0-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f89d0-105">Syntax</span></span>  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f89d0-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f89d0-106">Attributes and Elements</span></span>  

 <span data-ttu-id="f89d0-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f89d0-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f89d0-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f89d0-108">Attributes</span></span>  
  
|<span data-ttu-id="f89d0-109">Элемент</span><span class="sxs-lookup"><span data-stu-id="f89d0-109">Element</span></span>|<span data-ttu-id="f89d0-110">Описание</span><span class="sxs-lookup"><span data-stu-id="f89d0-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f89d0-111">binding</span><span class="sxs-lookup"><span data-stu-id="f89d0-111">binding</span></span>|<span data-ttu-id="f89d0-112">Строка, в которой указан тип привязки, используемый для конечной точки во время создания конечной точки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f89d0-112">A string that specifies the type of binding to be used for an endpoint during default endpoint creation.</span></span>|  
|<span data-ttu-id="f89d0-113">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="f89d0-113">bindingConfiguration</span></span>|<span data-ttu-id="f89d0-114">Строка, содержащая имя раздела конфигурации привязки, на который будет установлена ссылка.</span><span class="sxs-lookup"><span data-stu-id="f89d0-114">A string that specifies the name of the binding configuration section to be referenced.</span></span>|  
|<span data-ttu-id="f89d0-115">scheme</span><span class="sxs-lookup"><span data-stu-id="f89d0-115">scheme</span></span>|<span data-ttu-id="f89d0-116">Схема транспортного протокола, которая будет использоваться для конечной точки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f89d0-116">The transport protocol scheme to be used for the default endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f89d0-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f89d0-117">Child Elements</span></span>  

 <span data-ttu-id="f89d0-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f89d0-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f89d0-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f89d0-119">Parent Elements</span></span>  
  
|<span data-ttu-id="f89d0-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="f89d0-120">Element</span></span>|<span data-ttu-id="f89d0-121">Описание</span><span class="sxs-lookup"><span data-stu-id="f89d0-121">Description</span></span>|  
|-------------|-----------------|  
|[\<protocolMapping>](protocolmapping.md)|<span data-ttu-id="f89d0-122">Представляет раздел конфигурации для определения сопоставлений протоколов по умолчанию между схемами транспортного протокола (например, HTTP, net. TCP, net. pipe и т. д.) и привязками Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="f89d0-122">Represents a configuration section for defining default protocol mappings between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and Windows Communication Foundation (WCF) bindings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f89d0-123">Пример</span><span class="sxs-lookup"><span data-stu-id="f89d0-123">Example</span></span>  

 <span data-ttu-id="f89d0-124">В следующем примере конфигурации показано сопоставление протокола по умолчанию в файле machine.config.</span><span class="sxs-lookup"><span data-stu-id="f89d0-124">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="f89d0-125">Это сопоставление по умолчанию можно переопределить на уровне компьютера путем изменения файла machine.config.</span><span class="sxs-lookup"><span data-stu-id="f89d0-125">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="f89d0-126">Или же, если необходимо переопределить это сопоставление только в области приложения, можно отменить этот раздел в файле конфигурации приложения и изменить сопоставление для отдельных схем протокола.</span><span class="sxs-lookup"><span data-stu-id="f89d0-126">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f89d0-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f89d0-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>
