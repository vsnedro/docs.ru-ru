---
title: <add> из <filters>
ms.date: 03/30/2017
ms.assetid: e3bf437c-dd99-49f3-9792-9a8721e6eaad
ms.openlocfilehash: c1de0605bc8afc502a85d9b2917b975ee45a3d26
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201659"
---
# <a name="add-of-filters"></a><span data-ttu-id="8e7e0-102">\<add> из \<filters></span><span class="sxs-lookup"><span data-stu-id="8e7e0-102">\<add> of \<filters></span></span>

<span data-ttu-id="8e7e0-103">Фильтр XPath, задающий тип сообщений для записи в журнал.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-103">A XPath filter that specifies the kind of message to be logged.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<diagnostics>**](diagnostics.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<messageLogging>**](messagelogging.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filters>**](filters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="8e7e0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8e7e0-104">Syntax</span></span>  
  
```xml  
<filters>
  <add filter="String" />
</filters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8e7e0-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8e7e0-105">Attributes and Elements</span></span>  

 <span data-ttu-id="8e7e0-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8e7e0-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8e7e0-107">Attributes</span></span>  
  
|<span data-ttu-id="8e7e0-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8e7e0-108">Attribute</span></span>|<span data-ttu-id="8e7e0-109">Описание</span><span class="sxs-lookup"><span data-stu-id="8e7e0-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8e7e0-110">фильтр</span><span class="sxs-lookup"><span data-stu-id="8e7e0-110">filter</span></span>|<span data-ttu-id="8e7e0-111">Строка, задающая запрос к документу XML, определенный в виде выражения XPath 1.0.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-111">A string that specifies a query on an XML document defined by an XPath 1.0 expression.</span></span> <span data-ttu-id="8e7e0-112">Для получения дополнительной информации см. <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-112">For more information, see <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8e7e0-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8e7e0-113">Child Elements</span></span>  

 <span data-ttu-id="8e7e0-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8e7e0-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8e7e0-115">Parent Elements</span></span>  
  
|<span data-ttu-id="8e7e0-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="8e7e0-116">Element</span></span>|<span data-ttu-id="8e7e0-117">Описание</span><span class="sxs-lookup"><span data-stu-id="8e7e0-117">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters.md)|<span data-ttu-id="8e7e0-118">Содержит коллекцию фильтров XPath, используемых для контроля типов регистрируемых сообщений.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-118">Contains a collection of XPath filters used to control what kind of message is logged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e7e0-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="8e7e0-119">Remarks</span></span>  

 <span data-ttu-id="8e7e0-120">Фильтры применяются только на транспортном уровне, когда параметр `logMessagesAtTransportLevel` имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-120">Filters are applied only at the transport layer, specified by `logMessagesAtTransportLevel` is `true`.</span></span> <span data-ttu-id="8e7e0-121">Фильтры не влияют на ведение журнала сообщений уровня службы и неправильно сформированных сообщений.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-121">Service level and malformed message logging are not affected by filters.</span></span>  
  
 <span data-ttu-id="8e7e0-122">Для добавления нового фильтра в коллекцию используется ключевое слово `add`.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-122">To add a filter to the collection, use the `add` keyword.</span></span> <span data-ttu-id="8e7e0-123">Если в файле конфигурации определены один или несколько фильтров, в журнал записываются только сообщения, соответствующие хотя бы одному из фильтров.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-123">When one or more filters are defined, only messages that match at least one of the filters are logged.</span></span> <span data-ttu-id="8e7e0-124">Если фильтры не заданы, в журнал записываются все сообщения.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-124">If no filter is defined, all messages pass through.</span></span>  
  
 <span data-ttu-id="8e7e0-125">Фильтры поддерживают полный синтаксис XPath и применяются в том порядке, в котором они записаны в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-125">Filters support the full XPath syntax, and are applied in the order they appear in the configuration file.</span></span> <span data-ttu-id="8e7e0-126">Синтаксически неверные фильтры вызывают исключения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-126">A syntactically incorrect filter results in a configuration exception.</span></span>  
  
 <span data-ttu-id="8e7e0-127">В следующем примере показано, как настроить фильтр для записи только сообщений с разделом заголовка SOAP.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-127">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e7e0-128">Пример</span><span class="sxs-lookup"><span data-stu-id="8e7e0-128">Example</span></span>  

 <span data-ttu-id="8e7e0-129">В следующем примере показано, как настроить фильтр для записи только сообщений с разделом заголовка SOAP.</span><span class="sxs-lookup"><span data-stu-id="8e7e0-129">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
```xml  
<messageLogging logEntireMessage="true"
                logMalformedMessages="true"
                logMessagesAtServiceLevel="true"
                logMessagesAtTransportLevel="true"
                maxMessagesToLog="420">
  <filters>
    <add xmlns:soap="http://www.w3.org/2003/05/soap-envelope">
      /soap:Envelope/soap:Headers
    </add>
  </filters>
</messageLogging>
```  
  
## <a name="see-also"></a><span data-ttu-id="8e7e0-130">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8e7e0-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A>
- <xref:System.ServiceModel.Configuration.XPathMessageFilterElement>
- <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>
- [<span data-ttu-id="8e7e0-131">Настройка ведения журналов сообщений</span><span class="sxs-lookup"><span data-stu-id="8e7e0-131">Configuring Message Logging</span></span>](../../../wcf/diagnostics/configuring-message-logging.md)
- [\<messageLogging>](messagelogging.md)
