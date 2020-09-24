---
title: <endpoint> - элемент
ms.date: 03/30/2017
ms.assetid: 2fc8fedc-78d0-4e87-8142-fbfd26c15a4e
ms.openlocfilehash: befebc090900576b1e0f7ca679e1f5f5cd15af9a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183810"
---
# <a name="endpoint-element"></a><span data-ttu-id="1f2d5-102">Элемент \<endpoint></span><span class="sxs-lookup"><span data-stu-id="1f2d5-102">\<endpoint> element</span></span>

<span data-ttu-id="1f2d5-103">Задает свойства привязки, контракта и адреса для конечной точки службы, которая используется для предоставления доступа к службам.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-103">Specifies binding, contract, and address properties for a service endpoint, which is used to expose services.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="1f2d5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1f2d5-104">Syntax</span></span>  
  
```xml  
<endpoint address="String"
          behaviorConfiguration="String"
          binding="String"
          bindingConfiguration="String"
          bindingName="String"
          bindingNamespace="String"
          contract="String"
          endpointConfiguration="String"
          isSystemEndpoint="Boolean"
          kind="String"
          listenUriMode="Explicit/Unique"
          listenUri="Uri">
</endpoint>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1f2d5-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1f2d5-105">Attributes and Elements</span></span>  

 <span data-ttu-id="1f2d5-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1f2d5-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1f2d5-107">Attributes</span></span>  
  
|<span data-ttu-id="1f2d5-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="1f2d5-108">Attribute</span></span>|<span data-ttu-id="1f2d5-109">Описание</span><span class="sxs-lookup"><span data-stu-id="1f2d5-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1f2d5-110">address</span><span class="sxs-lookup"><span data-stu-id="1f2d5-110">address</span></span>|<span data-ttu-id="1f2d5-111">Строка, содержащая адрес конечной точки.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-111">A string that contains the address of the endpoint.</span></span> <span data-ttu-id="1f2d5-112">Адрес может быть указан как абсолютный или относительный адрес.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-112">The address can be specified as an absolute or relative address.</span></span> <span data-ttu-id="1f2d5-113">Если указан относительный адрес, от соответствующего узла ожидается предоставление базового адреса, подходящего для схемы транспорта, используемой в привязке.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-113">If a relative address is provided, the host is expected to provide a base address appropriate for the transport scheme used in the binding.</span></span> <span data-ttu-id="1f2d5-114">Если адрес не настроен, в качестве базового адреса используется адрес соответствующей конечной точки.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-114">If an address is not configured, the base address is assumed to be the address for that endpoint.</span></span><br /><br /> <span data-ttu-id="1f2d5-115">Значением по умолчанию является пустая строка.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-115">The default is an empty string.</span></span>|  
|<span data-ttu-id="1f2d5-116">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="1f2d5-116">behaviorConfiguration</span></span>|<span data-ttu-id="1f2d5-117">Строка, содержащая имя поведения для использования в конечной точке.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-117">A string that contains the name of the behavior to be used in the endpoint.</span></span>|  
|<span data-ttu-id="1f2d5-118">binding</span><span class="sxs-lookup"><span data-stu-id="1f2d5-118">binding</span></span>|<span data-ttu-id="1f2d5-119">Требуемый строковый атрибут, указывающий тип используемой привязки.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-119">Required string attribute that specifies the type of binding to use.</span></span> <span data-ttu-id="1f2d5-120">Чтобы на тип можно было ссылаться, он должен иметь зарегистрированный раздел конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-120">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="1f2d5-121">Тип регистрируется по имени раздела, а не по имени типа привязки.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-121">The type is the registered by section name, rather than by the type name of the binding.</span></span>|  
|<span data-ttu-id="1f2d5-122">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="1f2d5-122">bindingConfiguration</span></span>|<span data-ttu-id="1f2d5-123">Строка, указывающая имя привязки для использования при создании экземпляра конечной точки.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-123">A string that specifies the binding name of the binding to use when the endpoint is instantiated.</span></span> <span data-ttu-id="1f2d5-124">Имя привязки должно входить в область в точке определения конечной точки.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-124">The binding name must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="1f2d5-125">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-125">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="1f2d5-126">Этот атрибут используется вместе с атрибутом `binding` для ссылки на конкретную конфигурацию привязки в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-126">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="1f2d5-127">Задайте этот атрибут, если выполняется попытка использовать пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-127">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="1f2d5-128">В противном случае может быть создано исключение.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-128">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="1f2d5-129">bindingName</span><span class="sxs-lookup"><span data-stu-id="1f2d5-129">bindingName</span></span>|<span data-ttu-id="1f2d5-130">Строка, указывающая уникальное полное имя привязки для экспорта определения посредством WSDL.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-130">A string that specifies the unique qualified name of the binding for definition export through WSDL.</span></span> <span data-ttu-id="1f2d5-131">Значением по умолчанию является пустая строка.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-131">The default is an empty string.</span></span>|  
|<span data-ttu-id="1f2d5-132">bindingNamespace</span><span class="sxs-lookup"><span data-stu-id="1f2d5-132">bindingNamespace</span></span>|<span data-ttu-id="1f2d5-133">Строка, указывающая уникальное полное имя пространства имен привязки для экспорта определения посредством WSDL.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-133">A string that specifies the qualified name of the namespace of the binding for definition export through WSDL.</span></span> <span data-ttu-id="1f2d5-134">Значением по умолчанию является пустая строка.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-134">The default is an empty string.</span></span>|  
|<span data-ttu-id="1f2d5-135">contract</span><span class="sxs-lookup"><span data-stu-id="1f2d5-135">contract</span></span>|<span data-ttu-id="1f2d5-136">Строка, указывающая, к какому контракту предоставляется доступ этой конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-136">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="1f2d5-137">В сборке должен быть реализован данный тип контракта.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-137">The assembly must implement the contract type.</span></span> <span data-ttu-id="1f2d5-138">Если реализация службы реализует один тип контракта, это свойство может быть опущено.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-138">If a service implementation implements a single contract type, then this property can be omitted.</span></span> <span data-ttu-id="1f2d5-139">Значением по умолчанию является пустая строка.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-139">The default is an empty string.</span></span>|  
|<span data-ttu-id="1f2d5-140">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="1f2d5-140">endpointConfiguration</span></span>|<span data-ttu-id="1f2d5-141">Строка, указывающая имя стандартной конечной точки, задаваемой атрибутом `kind`, который ссылается на дополнительные сведения конфигурации этой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-141">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="1f2d5-142">Такое же имя должно быть задано в разделе `<standardEndpoints>`.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-142">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="1f2d5-143">isSystemEndpoint</span><span class="sxs-lookup"><span data-stu-id="1f2d5-143">isSystemEndpoint</span></span>|<span data-ttu-id="1f2d5-144">Логическое значение, указывающее, является ли конечная точка конечной точкой инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-144">A Boolean value that specifies whether an endpoint is an infrastructure endpoint.</span></span>|  
|<span data-ttu-id="1f2d5-145">kind</span><span class="sxs-lookup"><span data-stu-id="1f2d5-145">kind</span></span>|<span data-ttu-id="1f2d5-146">Строка, указывающая тип применяемой стандартной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-146">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="1f2d5-147">Тип должен быть зарегистрирован в разделе `<extensions>` или файле machine.config. Если ничего не указано, создается общая конечная точка службы.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-147">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common service endpoint is created.</span></span>|  
|<span data-ttu-id="1f2d5-148">listenUriMode</span><span class="sxs-lookup"><span data-stu-id="1f2d5-148">listenUriMode</span></span>|<span data-ttu-id="1f2d5-149">Указывает способ обработки транспортом значения `ListenUri`, предоставленного для ожидания передачи данных службой.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-149">Specifies how the transport treats the `ListenUri` provided for the service to listen on.</span></span> <span data-ttu-id="1f2d5-150">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="1f2d5-150">Valid values are</span></span><br /><br /> <span data-ttu-id="1f2d5-151">-Explicit</span><span class="sxs-lookup"><span data-stu-id="1f2d5-151">-   Explicit</span></span><br /><span data-ttu-id="1f2d5-152">— Уникальный</span><span class="sxs-lookup"><span data-stu-id="1f2d5-152">-   Unique</span></span><br /><br /> <span data-ttu-id="1f2d5-153">Значение по умолчанию - Explicit.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-153">The default value is Explicit.</span></span>|  
|<span data-ttu-id="1f2d5-154">listenUri</span><span class="sxs-lookup"><span data-stu-id="1f2d5-154">listenUri</span></span>|<span data-ttu-id="1f2d5-155">Строка, указывающая URI, по которому конечная точка службы ожидает передачи данных.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-155">A string that specifies the URI at which the service endpoint listens.</span></span> <span data-ttu-id="1f2d5-156">Значением по умолчанию является пустая строка.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-156">The default is an empty string.</span></span>|  
|<span data-ttu-id="1f2d5-157">name</span><span class="sxs-lookup"><span data-stu-id="1f2d5-157">name</span></span>|<span data-ttu-id="1f2d5-158">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-158">Optional attribute.</span></span> <span data-ttu-id="1f2d5-159">Строка, указывающая имя конечной точки службы.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-159">A string that specifies the name the service endpoint.</span></span> <span data-ttu-id="1f2d5-160">По умолчанию используется объединение имени привязки и имя описания контракта.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-160">The default value is the concatenation of the binding name and the contract description name.</span></span> <span data-ttu-id="1f2d5-161">Службы могут иметь несколько конечных точек, поэтому атрибут конечной точки `name` отличается от имени службы.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-161">Services may have multiple endpoints, so the endpoint’s `name` attribute is distinct from the name of the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1f2d5-162">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1f2d5-162">Child Elements</span></span>  
  
|<span data-ttu-id="1f2d5-163">Элемент</span><span class="sxs-lookup"><span data-stu-id="1f2d5-163">Element</span></span>|<span data-ttu-id="1f2d5-164">Описание</span><span class="sxs-lookup"><span data-stu-id="1f2d5-164">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers.md)|<span data-ttu-id="1f2d5-165">Коллекция заголовков адреса.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-165">A collection of address headers.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="1f2d5-166">Удостоверение, обеспечивающее проверку подлинности конечной точки другими конечными точками, которые обмениваются с ней сообщениями.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-166">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1f2d5-167">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1f2d5-167">Parent Elements</span></span>  
  
|<span data-ttu-id="1f2d5-168">Элемент</span><span class="sxs-lookup"><span data-stu-id="1f2d5-168">Element</span></span>|<span data-ttu-id="1f2d5-169">Описание</span><span class="sxs-lookup"><span data-stu-id="1f2d5-169">Description</span></span>|  
|-------------|-----------------|  
|[\<service>](service.md)|<span data-ttu-id="1f2d5-170">Раздел конфигурации, определяющий список конечных точек, к которым может подключаться клиент.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-170">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1f2d5-171">Пример</span><span class="sxs-lookup"><span data-stu-id="1f2d5-171">Example</span></span>  

 <span data-ttu-id="1f2d5-172">Ниже приведен пример конфигурации конечной точки службы.</span><span class="sxs-lookup"><span data-stu-id="1f2d5-172">This is an example of a service endpoint configuration.</span></span>  
  
```xml  
<endpoint address="/HelloWorld/"
          bindingConfiguration="usingDefaults"
          bindingName="MyBinding"
          binding="customBinding"
          contract="HelloWorld">
  <headers>
    <region xmlns="http://tempuri.org/">EastCoast</region>
    <member xmlns="http://tempuri.org/">Gold</member>
  </headers>
</endpoint>
```  
  
## <a name="see-also"></a><span data-ttu-id="1f2d5-173">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1f2d5-173">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceEndpointElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.Description.ServiceEndpoint>
- [<span data-ttu-id="1f2d5-174">Конечные точки: адреса, привязки и контракты</span><span class="sxs-lookup"><span data-stu-id="1f2d5-174">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
- [<span data-ttu-id="1f2d5-175">Практическое руководство. Создание конечной точки службы в конфигурации</span><span class="sxs-lookup"><span data-stu-id="1f2d5-175">How to: Create a Service Endpoint in Configuration</span></span>](../../../wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)
