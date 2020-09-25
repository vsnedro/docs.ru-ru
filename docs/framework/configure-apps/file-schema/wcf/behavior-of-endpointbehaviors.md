---
title: <behavior> из <endpointBehaviors>
ms.date: 03/30/2017
ms.assetid: b90ca3bc-3c22-4174-b903-e3a39898bd27
ms.openlocfilehash: d191b968e1c3fd1db0837ba7e03f210a1b00062d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201503"
---
# <a name="behavior-of-endpointbehaviors"></a><span data-ttu-id="8d244-102">\<behavior> из \<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="8d244-102">\<behavior> of \<endpointBehaviors></span></span>

<span data-ttu-id="8d244-103">Элемент `behavior` содержит коллекцию параметров поведения конечной точки.</span><span class="sxs-lookup"><span data-stu-id="8d244-103">The `behavior` element contains a collection of settings for the behavior of an endpoint.</span></span> <span data-ttu-id="8d244-104">Каждое поведение индексируется по атрибуту `name`.</span><span class="sxs-lookup"><span data-stu-id="8d244-104">Each behavior is indexed by its `name`.</span></span> <span data-ttu-id="8d244-105">Конечные точки могут ссылаться на каждое поведение по этому имени.</span><span class="sxs-lookup"><span data-stu-id="8d244-105">Endpoints can link to each behavior through this name.</span></span> <span data-ttu-id="8d244-106">Начиная с .NET Framework 4, привязки и поведения не обязательно должны иметь имя.</span><span class="sxs-lookup"><span data-stu-id="8d244-106">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="8d244-107">Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="8d244-107">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<behavior>**  
  
## <a name="syntax"></a><span data-ttu-id="8d244-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8d244-108">Syntax</span></span>  
  
```xml  
<system.ServiceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior name="String" />
    </endpointBehaviors>
  </behaviors>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8d244-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8d244-109">Attributes and Elements</span></span>  

 <span data-ttu-id="8d244-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8d244-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8d244-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8d244-111">Attributes</span></span>  
  
|<span data-ttu-id="8d244-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8d244-112">Attribute</span></span>|<span data-ttu-id="8d244-113">Описание</span><span class="sxs-lookup"><span data-stu-id="8d244-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8d244-114">name</span><span class="sxs-lookup"><span data-stu-id="8d244-114">name</span></span>|<span data-ttu-id="8d244-115">Уникальная строка, содержащая имя конфигурации поведения.</span><span class="sxs-lookup"><span data-stu-id="8d244-115">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="8d244-116">Это значение является заданной пользователем строкой, которая должна быть уникальной, поскольку она действует как строка идентификации для элемента.</span><span class="sxs-lookup"><span data-stu-id="8d244-116">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span> <span data-ttu-id="8d244-117">Начиная с .NET Framework 4, привязки и поведения не обязательно должны иметь имя.</span><span class="sxs-lookup"><span data-stu-id="8d244-117">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="8d244-118">Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="8d244-118">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8d244-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8d244-119">Child Elements</span></span>  
  
|<span data-ttu-id="8d244-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="8d244-120">Element</span></span>|<span data-ttu-id="8d244-121">Описание</span><span class="sxs-lookup"><span data-stu-id="8d244-121">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="8d244-122">Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="8d244-122">Specifies the credentials used to authenticate the client to a service.</span></span>|  
|[\<callbackDebug>](callbackdebug.md)|<span data-ttu-id="8d244-123">Указывает отладку службы для объекта обратного вызова Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="8d244-123">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>|  
|[\<callbackTimeouts>](callbacktimeouts.md)|<span data-ttu-id="8d244-124">Задает время ожидания для обратного вызова клиента.</span><span class="sxs-lookup"><span data-stu-id="8d244-124">Specifies the timeout for the client callback.</span></span>|  
|[\<clientVia>](clientvia.md)|<span data-ttu-id="8d244-125">Задает маршрут, по которому должно быть передано сообщение.</span><span class="sxs-lookup"><span data-stu-id="8d244-125">Specifies the route a message should take.</span></span>|  
|[\<dataContractSerializer>](datacontractserializer.md)|<span data-ttu-id="8d244-126">Содержит данные конфигурации для DataContractSerializer.</span><span class="sxs-lookup"><span data-stu-id="8d244-126">Contains configuration data for the DataContractSerializer.</span></span>|  
|[\<dispatcherSynchronization>](dispatchersynchronization.md)|<span data-ttu-id="8d244-127">Указывает поведение конечной точки, которое позволяет службе отправлять ответы в асинхронном режиме.</span><span class="sxs-lookup"><span data-stu-id="8d244-127">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>|  
|[\<enableWebScript>](enablewebscript.md)|<span data-ttu-id="8d244-128">Включает поведение конечной точки, позволяющее использовать службу с веб-страниц ASP.NET с поддержкой технологии AJAX.</span><span class="sxs-lookup"><span data-stu-id="8d244-128">Enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span> <span data-ttu-id="8d244-129">Поведение следует использовать только в сочетании со \<webHttpBinding> стандартной привязкой или с \<webMessageEncoding> элементом Binding.</span><span class="sxs-lookup"><span data-stu-id="8d244-129">The behavior should only be used in conjunction with either the \<webHttpBinding> standard binding, or the \<webMessageEncoding> binding element.</span></span>|  
|[\<endpointDiscovery>](endpointdiscovery.md)|<span data-ttu-id="8d244-130">Указывает различные параметры обнаружения для конечной точки, такие как возможность обнаружения, области и любые пользовательские модули для ее метаданных.</span><span class="sxs-lookup"><span data-stu-id="8d244-130">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
|[\<soapProcessing>](soapprocessing.md)|<span data-ttu-id="8d244-131">Определяет поведение конечной точки клиента, используемое для маршалинга сообщений между различными типами привязок и версиями сообщения.</span><span class="sxs-lookup"><span data-stu-id="8d244-131">Defines the client endpoint behavior used to marshal messages between different binding types and message versions.</span></span>|  
|[\<synchronousReceive>](synchronousreceive-element.md)|<span data-ttu-id="8d244-132">Задает поведение времени выполнения для получения сообщений в службе или клиентском приложении.</span><span class="sxs-lookup"><span data-stu-id="8d244-132">Specifies run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="8d244-133">Он не имеет атрибутов или дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="8d244-133">It does not have any attributes or child elements.</span></span>|  
|[\<transactedBatching>](transactedbatching.md)|<span data-ttu-id="8d244-134">Указывает, поддерживается ли объединение транзакций для операций получения.</span><span class="sxs-lookup"><span data-stu-id="8d244-134">Specifies whether transaction batching is supported for receive operations.</span></span>|  
|[\<webHttp>](webhttp.md)|<span data-ttu-id="8d244-135">Задает WebHttpBehavior в конечной точке посредством настройки конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8d244-135">Specifies the WebHttpBehavior on an endpoint through configuration.</span></span> <span data-ttu-id="8d244-136">Такое поведение при использовании в сочетании со \<webHttpBinding> стандартной привязкой включает в себя модель веб-программирования для службы WCF.</span><span class="sxs-lookup"><span data-stu-id="8d244-136">This behavior, when used in conjunction with the \<webHttpBinding> standard binding, enables the Web programming model for a WCF service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8d244-137">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8d244-137">Parent Elements</span></span>  
  
|<span data-ttu-id="8d244-138">Элемент</span><span class="sxs-lookup"><span data-stu-id="8d244-138">Element</span></span>|<span data-ttu-id="8d244-139">Описание</span><span class="sxs-lookup"><span data-stu-id="8d244-139">Description</span></span>|  
|-------------|-----------------|  
|[\<endpointBehaviors>](endpointbehaviors.md)|<span data-ttu-id="8d244-140">Коллекция элементов поведения конечной точки.</span><span class="sxs-lookup"><span data-stu-id="8d244-140">A collection of endpoint behavior elements.</span></span>|
