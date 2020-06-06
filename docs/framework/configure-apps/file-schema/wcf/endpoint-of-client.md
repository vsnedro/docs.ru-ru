---
title: <endpoint> из <client>
ms.date: 03/30/2017
ms.assetid: de6238ae-bbf8-48e9-a1b5-e24c0bea8afa
ms.openlocfilehash: f1ffbc1e8efac70523d7f631c8cf9ba9a1622bfc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855320"
---
# <a name="endpoint-of-client"></a><span data-ttu-id="1e338-102">\<endpoint> из \<client></span><span class="sxs-lookup"><span data-stu-id="1e338-102">\<endpoint> of \<client></span></span>
<span data-ttu-id="1e338-103">Задает свойства контракта, привязки и адреса конечной точки канала, которая используется клиентами для подключения к конечным точкам службы на сервере.</span><span class="sxs-lookup"><span data-stu-id="1e338-103">Specifies contract, binding, and address properties of the channel endpoint, which is used by clients to connect to service endpoints on the server.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="1e338-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1e338-104">Syntax</span></span>  
  
```xml  
<endpoint address="String"
          behaviorConfiguration="String"
          binding="String"
          bindingConfiguration="String"
          contract="String"
          endpointConfiguration="String"
          kind="String"
          name="String">
</endpoint>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1e338-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1e338-105">Attributes and Elements</span></span>  
 <span data-ttu-id="1e338-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1e338-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1e338-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1e338-107">Attributes</span></span>  
  
|<span data-ttu-id="1e338-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="1e338-108">Attribute</span></span>|<span data-ttu-id="1e338-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="1e338-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1e338-110">address</span><span class="sxs-lookup"><span data-stu-id="1e338-110">address</span></span>|<span data-ttu-id="1e338-111">Обязательный строковый атрибут.</span><span class="sxs-lookup"><span data-stu-id="1e338-111">Required string attribute.</span></span><br /><br /> <span data-ttu-id="1e338-112">Задает адрес конечной точки.</span><span class="sxs-lookup"><span data-stu-id="1e338-112">Specifies the address of the endpoint.</span></span> <span data-ttu-id="1e338-113">Значением по умолчанию является пустая строка.</span><span class="sxs-lookup"><span data-stu-id="1e338-113">The default is an empty string.</span></span> <span data-ttu-id="1e338-114">Адрес должен быть абсолютным универсальным кодом ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="1e338-114">The address must be an absolute URI.</span></span>|  
|<span data-ttu-id="1e338-115">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="1e338-115">behaviorConfiguration</span></span>|<span data-ttu-id="1e338-116">Строка, содержащая имя поведения, используемое для создания экземпляра конечной точки.</span><span class="sxs-lookup"><span data-stu-id="1e338-116">A string that contains the behavior name of the behavior to be used to instantiate the endpoint.</span></span> <span data-ttu-id="1e338-117">Имя поведения должно входить в область действия в точке определения службы.</span><span class="sxs-lookup"><span data-stu-id="1e338-117">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="1e338-118">Значением по умолчанию является пустая строка.</span><span class="sxs-lookup"><span data-stu-id="1e338-118">The default is an empty string.</span></span>|  
|<span data-ttu-id="1e338-119">binding</span><span class="sxs-lookup"><span data-stu-id="1e338-119">binding</span></span>|<span data-ttu-id="1e338-120">Обязательный строковый атрибут.</span><span class="sxs-lookup"><span data-stu-id="1e338-120">Required string attribute.</span></span><br /><br /> <span data-ttu-id="1e338-121">Строка, указывающая тип привязки для использования.</span><span class="sxs-lookup"><span data-stu-id="1e338-121">A string that indicates the type of binding to use.</span></span> <span data-ttu-id="1e338-122">Чтобы на тип можно было ссылаться, он должен иметь зарегистрированный раздел конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1e338-122">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="1e338-123">Тип регистрируется по имени раздела, а не по имени типа привязки.</span><span class="sxs-lookup"><span data-stu-id="1e338-123">The type is registered by section name, instead of by the type name of the binding.</span></span>|  
|<span data-ttu-id="1e338-124">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="1e338-124">bindingConfiguration</span></span>|<span data-ttu-id="1e338-125">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="1e338-125">Optional.</span></span> <span data-ttu-id="1e338-126">Строка, содержащая имя конфигурации привязки для использования при создании экземпляра конечной точки.</span><span class="sxs-lookup"><span data-stu-id="1e338-126">A string that contains the name of the binding configuration to be used when the endpoint is instantiated.</span></span> <span data-ttu-id="1e338-127">Конфигурация привязки должна входить в область действия в точке определения конечной точки.</span><span class="sxs-lookup"><span data-stu-id="1e338-127">The binding configuration must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="1e338-128">Значением по умолчанию является пустая строка.</span><span class="sxs-lookup"><span data-stu-id="1e338-128">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="1e338-129">Этот атрибут используется вместе с атрибутом `binding` для ссылки на конкретную конфигурацию привязки в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1e338-129">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="1e338-130">Задайте этот атрибут, если выполняется попытка использовать пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="1e338-130">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="1e338-131">В противном случае может быть создано исключение.</span><span class="sxs-lookup"><span data-stu-id="1e338-131">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="1e338-132">contract</span><span class="sxs-lookup"><span data-stu-id="1e338-132">contract</span></span>|<span data-ttu-id="1e338-133">Обязательный строковый атрибут.</span><span class="sxs-lookup"><span data-stu-id="1e338-133">Required string attribute.</span></span><br /><br /> <span data-ttu-id="1e338-134">Строка, указывающая, к какому контракту предоставляется доступ этой конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="1e338-134">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="1e338-135">В сборке должен быть реализован данный тип контракта.</span><span class="sxs-lookup"><span data-stu-id="1e338-135">The assembly must implement the contract type.</span></span>|  
|<span data-ttu-id="1e338-136">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="1e338-136">endpointConfiguration</span></span>|<span data-ttu-id="1e338-137">Строка, указывающая имя стандартной конечной точки, задаваемой атрибутом `kind`, который ссылается на дополнительные сведения конфигурации этой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="1e338-137">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="1e338-138">Такое же имя должно быть задано в разделе `<standardEndpoints>`.</span><span class="sxs-lookup"><span data-stu-id="1e338-138">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="1e338-139">kind</span><span class="sxs-lookup"><span data-stu-id="1e338-139">kind</span></span>|<span data-ttu-id="1e338-140">Строка, указывающая тип применяемой стандартной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="1e338-140">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="1e338-141">Тип должен быть зарегистрирован в `<extensions>` разделе или файле Machine. config. Если ничего не указано, создается общая конечная точка канала.</span><span class="sxs-lookup"><span data-stu-id="1e338-141">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common channel endpoint is created.</span></span>|  
|<span data-ttu-id="1e338-142">name</span><span class="sxs-lookup"><span data-stu-id="1e338-142">name</span></span>|<span data-ttu-id="1e338-143">Необязательный строковый атрибут.</span><span class="sxs-lookup"><span data-stu-id="1e338-143">Optional string attribute.</span></span> <span data-ttu-id="1e338-144">Этот атрибут уникальным образом идентифицирует конечную точку для данного контракта.</span><span class="sxs-lookup"><span data-stu-id="1e338-144">This attribute uniquely identifies an endpoint for a given contract.</span></span> <span data-ttu-id="1e338-145">Для данного типа контракта можно определить несколько клиентов.</span><span class="sxs-lookup"><span data-stu-id="1e338-145">You can define multiple clients for a given Contract type.</span></span> <span data-ttu-id="1e338-146">Определения должны отличаться друг от друга уникальным именем конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1e338-146">Each definition must be differentiated by a unique configuration name.</span></span> <span data-ttu-id="1e338-147">Если этот атрибут опущен, соответствующая конечная точка используется как конечная точка по умолчанию, связанная с заданным типом контракта.</span><span class="sxs-lookup"><span data-stu-id="1e338-147">If this attribute is omitted, the corresponding endpoint is used as the default endpoint associated with the specified Contract type.</span></span> <span data-ttu-id="1e338-148">Значением по умолчанию является пустая строка.</span><span class="sxs-lookup"><span data-stu-id="1e338-148">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="1e338-149">Атрибут `name` привязки используется для экспорта определения посредством языка WSDL.</span><span class="sxs-lookup"><span data-stu-id="1e338-149">The `name` attribute of a binding is used for definition export through WSDL.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1e338-150">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1e338-150">Child Elements</span></span>  
  
|<span data-ttu-id="1e338-151">Элемент</span><span class="sxs-lookup"><span data-stu-id="1e338-151">Element</span></span>|<span data-ttu-id="1e338-152">Описание</span><span class="sxs-lookup"><span data-stu-id="1e338-152">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers.md)|<span data-ttu-id="1e338-153">Коллекция заголовков адреса.</span><span class="sxs-lookup"><span data-stu-id="1e338-153">A collection of address headers.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="1e338-154">Удостоверение, обеспечивающее проверку подлинности конечной точки другими конечными точками, которые обмениваются с ней сообщениями.</span><span class="sxs-lookup"><span data-stu-id="1e338-154">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1e338-155">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1e338-155">Parent Elements</span></span>  
  
|<span data-ttu-id="1e338-156">Элемент</span><span class="sxs-lookup"><span data-stu-id="1e338-156">Element</span></span>|<span data-ttu-id="1e338-157">Описание</span><span class="sxs-lookup"><span data-stu-id="1e338-157">Description</span></span>|  
|-------------|-----------------|  
|[\<client>](client.md)|<span data-ttu-id="1e338-158">Раздел конфигурации, определяющий список конечных точек, к которым может подключаться клиент.</span><span class="sxs-lookup"><span data-stu-id="1e338-158">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1e338-159">Пример</span><span class="sxs-lookup"><span data-stu-id="1e338-159">Example</span></span>  
 <span data-ttu-id="1e338-160">Далее приведен пример конфигурации конечной точки канала.</span><span class="sxs-lookup"><span data-stu-id="1e338-160">This is an example of a channel endpoint configuration.</span></span>  
  
```xml  
<endpoint address="/HelloWorld/"
          bindingConfiguration="usingDefaults"
          name="MyBinding"
          binding="customBinding"
          contract="HelloWorld">
</endpoint>
```  
  
## <a name="see-also"></a><span data-ttu-id="1e338-161">См. также</span><span class="sxs-lookup"><span data-stu-id="1e338-161">See also</span></span>

- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElementCollection>
- <xref:System.ServiceModel.Configuration.ClientSection.Endpoints%2A>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- [<span data-ttu-id="1e338-162">Конфигурация клиента WCF</span><span class="sxs-lookup"><span data-stu-id="1e338-162">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="1e338-163">Клиенты</span><span class="sxs-lookup"><span data-stu-id="1e338-163">Clients</span></span>](../../../wcf/feature-details/clients.md)
