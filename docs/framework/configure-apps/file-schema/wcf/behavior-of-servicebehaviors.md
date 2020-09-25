---
title: <behavior> из <serviceBehaviors>
ms.date: 03/30/2017
ms.assetid: 78fc0a08-55de-416a-ac12-a5e6ffc9a987
ms.openlocfilehash: 739f95f527fd73062c8cec43efc6777efeb077f3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195159"
---
# <a name="behavior-of-servicebehaviors"></a><span data-ttu-id="82755-102">\<behavior> из \<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="82755-102">\<behavior> of \<serviceBehaviors></span></span>

<span data-ttu-id="82755-103">Элемент `behavior` содержит коллекцию параметров для поведения службы.</span><span class="sxs-lookup"><span data-stu-id="82755-103">The `behavior` element contains a collection of settings for the behavior of a service.</span></span> <span data-ttu-id="82755-104">Каждое поведение индексируется по атрибуту `name`.</span><span class="sxs-lookup"><span data-stu-id="82755-104">Each behavior is indexed by its `name`.</span></span> <span data-ttu-id="82755-105">Службы могут ссылаться на каждое поведение с помощью этого имени, используя `behaviorConfiguration` атрибут [\<endpoint>](endpoint-element.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="82755-105">Services can link to each behavior through this name using the `behaviorConfiguration` attribute of the [\<endpoint>](endpoint-element.md) element.</span></span> <span data-ttu-id="82755-106">Это позволяет конечным точкам иметь общие конфигурации поведений без переопределения параметров.</span><span class="sxs-lookup"><span data-stu-id="82755-106">This allows endpoints to share common behavior configurations without redefining the settings.</span></span> <span data-ttu-id="82755-107">Начиная с .NET Framework 4, привязки и поведения не обязательно должны иметь имя.</span><span class="sxs-lookup"><span data-stu-id="82755-107">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="82755-108">Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="82755-108">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="82755-109">Элементы поведения, относящиеся к действиям рабочего процесса Windows, таким как [\<sendMessageChannelCache>](../windows-workflow-foundation/sendmessagechannelcache.md) элемент, описаны на [ \<behavior> \<serviceBehaviors> ](../windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md) странице.</span><span class="sxs-lookup"><span data-stu-id="82755-109">Behavior elements specific to Windows Workflow activities, such as the [\<sendMessageChannelCache>](../windows-workflow-foundation/sendmessagechannelcache.md) element, are documented in the [\<behavior> of \<serviceBehaviors>](../windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md) page.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<behavior>**  
  
## <a name="syntax"></a><span data-ttu-id="82755-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="82755-110">Syntax</span></span>  
  
```xml  
<system.ServiceModel>
  <behaviors>
    <serviceBehaviors>
       <behavior name="String" />
    </serviceBehaviors>
  </behaviors>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="82755-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="82755-111">Attributes and Elements</span></span>  

 <span data-ttu-id="82755-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="82755-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="82755-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="82755-113">Attributes</span></span>  
  
|<span data-ttu-id="82755-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="82755-114">Attribute</span></span>|<span data-ttu-id="82755-115">Описание</span><span class="sxs-lookup"><span data-stu-id="82755-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="82755-116">name</span><span class="sxs-lookup"><span data-stu-id="82755-116">name</span></span>|<span data-ttu-id="82755-117">Уникальная строка, содержащая имя конфигурации поведения.</span><span class="sxs-lookup"><span data-stu-id="82755-117">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="82755-118">Это значение является заданной пользователем строкой, которая должна быть уникальной, поскольку она действует как строка идентификации для элемента.</span><span class="sxs-lookup"><span data-stu-id="82755-118">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span> <span data-ttu-id="82755-119">Начиная с .NET Framework 4, привязки и поведения не обязательно должны иметь имя.</span><span class="sxs-lookup"><span data-stu-id="82755-119">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="82755-120">Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="82755-120">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="82755-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="82755-121">Child Elements</span></span>  
  
|<span data-ttu-id="82755-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="82755-122">Element</span></span>|<span data-ttu-id="82755-123">Описание</span><span class="sxs-lookup"><span data-stu-id="82755-123">Description</span></span>|  
|-------------|-----------------|  
|[\<dataContractSerializer>](datacontractserializer-element.md)|<span data-ttu-id="82755-124">Содержит данные конфигурации для DataContractSerializer.</span><span class="sxs-lookup"><span data-stu-id="82755-124">Contains configuration data for the DataContractSerializer.</span></span>|  
|[\<persistenceProvider>](persistenceprovider.md)|<span data-ttu-id="82755-125">Задает тип используемой реализации поставщика сохраняемости, а также время ожидания операций сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="82755-125">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>|  
|[\<routing>](routing-of-servicebehavior.md)|<span data-ttu-id="82755-126">Обеспечивает доступ к службе маршрутизации во время выполнения, чтобы вносить динамические изменения в конфигурацию маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="82755-126">Provides run-time access to the routing service to allow dynamic modification of the routing configuration.</span></span>|  
|[\<serviceAuthenticationManager>](serviceauthenticationmanager.md)|<span data-ttu-id="82755-127">Обеспечивает элемент конфигурации рабочего процесса, который устанавливает на уровне службы действительность передачи, сообщения или инициатора.</span><span class="sxs-lookup"><span data-stu-id="82755-127">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator..</span></span>|  
|[\<serviceAuthorization>](serviceauthorization-element.md)|<span data-ttu-id="82755-128">Задает параметры авторизации доступа к операциям службы.</span><span class="sxs-lookup"><span data-stu-id="82755-128">Specifies settings that authorize access to service operations.</span></span>|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="82755-129">Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="82755-129">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>|  
|[\<serviceDebug>](servicedebug.md)|<span data-ttu-id="82755-130">Указывает функции отладки и справочной информации для службы Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="82755-130">Specifies debugging and help information features for a Windows Communication Foundation (WCF) service.</span></span>|  
|[\<serviceDiscovery>](servicediscovery.md)|<span data-ttu-id="82755-131">Указывает возможность обнаружения конечных точек службы.</span><span class="sxs-lookup"><span data-stu-id="82755-131">Specifies the discoverability of service endpoints.</span></span>|  
|[\<serviceMetadata>](servicemetadata.md)|<span data-ttu-id="82755-132">Задает публикацию метаданных службы и связанных сведений.</span><span class="sxs-lookup"><span data-stu-id="82755-132">Specifies the publication of service metadata and associated information.</span></span>|  
|[\<serviceSecurityAudit>](servicesecurityaudit.md)|<span data-ttu-id="82755-133">Задает параметры, позволяющие проводить аудит событий безопасности во время обслуживания.</span><span class="sxs-lookup"><span data-stu-id="82755-133">Specifies settings that enable auditing of security events during service operations.</span></span>|  
|[\<serviceThrottling>](servicethrottling.md)|<span data-ttu-id="82755-134">Указывает механизм регулирования службы WCF.</span><span class="sxs-lookup"><span data-stu-id="82755-134">Specifies the throttling mechanism of a WCF service.</span></span>|  
|[\<serviceTimeouts>](servicetimeouts.md)|<span data-ttu-id="82755-135">Задает время ожидания для службы.</span><span class="sxs-lookup"><span data-stu-id="82755-135">Specifies the timeout for a service.</span></span>|  
|[\<workflowRuntime>](workflowruntime.md)|<span data-ttu-id="82755-136">Задает параметры для экземпляра WorkflowRuntime для размещения служб WCF на основе рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="82755-136">Specifies settings for an instance of WorkflowRuntime for hosting workflow-based WCF services.</span></span>|  
|[\<useRequestHeadersForMetadataAddress>](userequestheadersformetadataaddress.md)|<span data-ttu-id="82755-137">Включает получение сведений об адресе метаданных из заголовков сообщений запросов.</span><span class="sxs-lookup"><span data-stu-id="82755-137">Enables the retrieval of metadata address information from the request message headers.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="82755-138">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="82755-138">Parent Elements</span></span>  
  
|<span data-ttu-id="82755-139">Элемент</span><span class="sxs-lookup"><span data-stu-id="82755-139">Element</span></span>|<span data-ttu-id="82755-140">Описание</span><span class="sxs-lookup"><span data-stu-id="82755-140">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceBehaviors>](servicebehaviors.md)|<span data-ttu-id="82755-141">Коллекция элементов поведений службы.</span><span class="sxs-lookup"><span data-stu-id="82755-141">A collection of service behavior elements.</span></span>|
