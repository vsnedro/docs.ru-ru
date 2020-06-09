---
title: Конфигурация клиента
ms.date: 03/30/2017
ms.assetid: 5da5bd3b-65d9-43b7-91b9-cc9e989b1350
ms.openlocfilehash: 2d17438095e65ccf922061c03e406bab35b07c5d
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593663"
---
# <a name="client-configuration"></a><span data-ttu-id="8b6a2-102">Конфигурация клиента</span><span class="sxs-lookup"><span data-stu-id="8b6a2-102">Client Configuration</span></span>
<span data-ttu-id="8b6a2-103">Можно использовать конфигурацию клиента Windows Communication Foundation (WCF) для указания адреса, привязки, поведения и контракта, свойств "ABC" клиентской конечной точки, которые клиенты используют для подключения к конечным точкам службы.</span><span class="sxs-lookup"><span data-stu-id="8b6a2-103">You can use the Windows Communication Foundation (WCF) client configuration to specify the address, binding, behavior, and contract, the "ABC" properties of the client endpoint, which clients use to connect to service endpoints.</span></span> <span data-ttu-id="8b6a2-104">[\<client>](../../configure-apps/file-schema/wcf/client.md)Элемент содержит [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) элемент, атрибуты которого используются для настройки конечной точки ABCs.</span><span class="sxs-lookup"><span data-stu-id="8b6a2-104">The [\<client>](../../configure-apps/file-schema/wcf/client.md) element has an [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) element whose attributes are used to configure the endpoint ABCs.</span></span> <span data-ttu-id="8b6a2-105">Эти атрибуты обсуждаются в разделе [Настройка конечных точек](#configuring-endpoints) .</span><span class="sxs-lookup"><span data-stu-id="8b6a2-105">These attributes are discussed in the [Configuring Endpoints](#configuring-endpoints) section.</span></span>  
  
 <span data-ttu-id="8b6a2-106">[\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-of-client.md)Элемент также содержит [\<metadata>](../../configure-apps/file-schema/wcf/metadata.md) элемент, который используется для задания параметров импорта и экспорта метаданных, [\<headers>](../../configure-apps/file-schema/wcf/headers.md) элемента, содержащего коллекцию настраиваемых заголовков адресов, и [\<identity>](../../configure-apps/file-schema/wcf/identity.md) элемента, который обеспечивает проверку подлинности конечной точки другими конечными точками, которые обмениваются сообщениями.</span><span class="sxs-lookup"><span data-stu-id="8b6a2-106">The [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) element also contains a [\<metadata>](../../configure-apps/file-schema/wcf/metadata.md) element that is used to specify settings for importing and exporting metadata, a [\<headers>](../../configure-apps/file-schema/wcf/headers.md) element that contains a collection of custom address headers, and an [\<identity>](../../configure-apps/file-schema/wcf/identity.md) element that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span> <span data-ttu-id="8b6a2-107">[\<headers>](../../configure-apps/file-schema/wcf/headers.md)Элементы и [\<identity>](../../configure-apps/file-schema/wcf/identity.md) являются частью <xref:System.ServiceModel.EndpointAddress> и обсуждаются в статье [адреса](endpoint-addresses.md) .</span><span class="sxs-lookup"><span data-stu-id="8b6a2-107">The [\<headers>](../../configure-apps/file-schema/wcf/headers.md) and [\<identity>](../../configure-apps/file-schema/wcf/identity.md) elements are part of the <xref:System.ServiceModel.EndpointAddress> and are discussed in the [Addresses](endpoint-addresses.md) article.</span></span> <span data-ttu-id="8b6a2-108">Ссылки на разделы, в которых объясняется использование расширений метаданных, приведены в разделе [Настройка метаданных](#configuring-metadata) .</span><span class="sxs-lookup"><span data-stu-id="8b6a2-108">Links to topics that explain the use of metadata extensions are provided in the [Configuring Metadata](#configuring-metadata) section.</span></span>  
  
## <a name="configuring-endpoints"></a><span data-ttu-id="8b6a2-109">Настройка конечных точек</span><span class="sxs-lookup"><span data-stu-id="8b6a2-109">Configuring Endpoints</span></span>  
 <span data-ttu-id="8b6a2-110">Конфигурация клиента позволяет клиенту указывать одну или несколько конечных точек, каждый из которых имеет собственное имя, адрес и контракт, при этом каждый из них ссылается на [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) элементы и [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) в конфигурации клиента, используемые для настройки этой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="8b6a2-110">The client configuration is designed to allow the client to specify one or more endpoints, each with its own name, address, and contract, with each referencing the [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) and [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) elements in the client configuration to be used to configure that endpoint.</span></span> <span data-ttu-id="8b6a2-111">Файл конфигурации клиента должен называться "App. config", так как это имя, которое требуется среде выполнения WCF.</span><span class="sxs-lookup"><span data-stu-id="8b6a2-111">The client configuration file should be named "App.config" because this is the name that the WCF runtime expects.</span></span> <span data-ttu-id="8b6a2-112">В следующем примере показан файл конфигурации клиента.</span><span class="sxs-lookup"><span data-stu-id="8b6a2-112">The following example shows a client configuration file.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
        <client>  
          <endpoint  
            name="endpoint1"  
            address="http://localhost/ServiceModelSamples/service.svc"  
            binding="wsHttpBinding"  
            bindingConfiguration="WSHttpBinding_IHello"  
            behaviorConfiguration="IHello_Behavior"  
            contract="IHello" >  
  
            <metadata>  
              <wsdlImporters>  
                <extension  
                  type="Microsoft.ServiceModel.Samples.WsdlDocumentationImporter, WsdlDocumentation"/>  
              </wsdlImporters>  
            </metadata>  
  
            <identity>  
              <servicePrincipalName value="host/localhost" />  
            </identity>  
          </endpoint>  
            <!-- Add another endpoint by adding another <endpoint> element. -->
          <endpoint  
            name="endpoint2">  
           //Configure another endpoint here.  
          </endpoint>  
        </client>  
  
//The bindings section references by the bindingConfiguration endpoint attribute.  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_IHello"
                 bypassProxyOnLocal="false"
                 hostNameComparisonMode="StrongWildcard">  
          <readerQuotas maxDepth="32"/>  
          <reliableSession ordered="true"
                           enabled="false" />  
          <security mode="Message">  
           //Security settings go here.  
          </security>  
        </binding>  
        <binding name="Another Binding"  
          <!-- Configure this binding here. -->  
        </binding>  
          </wsHttpBinding>  
     </bindings>  
  
//The behavior section references by the behaviorConfiguration endpoint attribute.  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name=" IHello_Behavior ">  
                    <clientVia />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
  
    </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="8b6a2-113">Необязательный атрибут `name` уникальным образом идентифицирует конечную точку для данного контракта.</span><span class="sxs-lookup"><span data-stu-id="8b6a2-113">The optional `name` attribute uniquely identifies an endpoint for a given contract.</span></span> <span data-ttu-id="8b6a2-114">Он используется методом <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> или <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> для задания целевой конечной точки в конфигурации клиента, которая должна быть загружена при создании канала к службе.</span><span class="sxs-lookup"><span data-stu-id="8b6a2-114">It is used by the <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> or by the <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> to specify which endpoint in the client configuration is being targeted and must be loaded when a channel is created to service.</span></span> <span data-ttu-id="8b6a2-115">Имя конфигурации конечной точки с подстановочным знаком " \* " доступно и указывает <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> методу, что ему следует загрузить любую конфигурацию конечной точки в файле, если имеется только один доступный объект, и в противном случае вызывает исключение.</span><span class="sxs-lookup"><span data-stu-id="8b6a2-115">A wildcard endpoint configuration name "\*" is available and indicates to the <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> method that it should load any endpoint configuration in the file, provided there is precisely one available, and otherwise throws an exception.</span></span> <span data-ttu-id="8b6a2-116">Если этот атрибут опущен, соответствующая конечная точка используется как конечная точка по умолчанию, связанная с заданным типом контракта.</span><span class="sxs-lookup"><span data-stu-id="8b6a2-116">If this attribute is omitted, the corresponding endpoint is used as the default endpoint associated with the specified contract type.</span></span> <span data-ttu-id="8b6a2-117">Значением по умолчанию для атрибута `name` является пустая строка, соответствие для которой проверяется так же, как и для любого другого имени.</span><span class="sxs-lookup"><span data-stu-id="8b6a2-117">The default value for the `name` attribute is an empty string which is matched like any other name.</span></span>  
  
 <span data-ttu-id="8b6a2-118">С каждой конечной точкой связан адрес, который используется для поиска и идентификации этой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="8b6a2-118">Every endpoint must have an address associated with it to locate and identify the endpoint.</span></span> <span data-ttu-id="8b6a2-119">Атрибут `address` может использоваться для указания URL-адреса, задающего расположение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="8b6a2-119">The `address` attribute can be used to specify the URL that provides the location of the endpoint.</span></span> <span data-ttu-id="8b6a2-120">Однако адрес для конечной точки службы может также быть задан в коде путем создания универсального кода ресурса (URI), и он добавляется в <xref:System.ServiceModel.ServiceHost> с помощью одного из методов <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>.</span><span class="sxs-lookup"><span data-stu-id="8b6a2-120">But the address for a service endpoint can also be specified in code by creating a Uniform Resource Identifier (URI) and is added to the <xref:System.ServiceModel.ServiceHost> using one of the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> methods.</span></span> <span data-ttu-id="8b6a2-121">Дополнительные сведения см. в разделе [адреса](endpoint-addresses.md).</span><span class="sxs-lookup"><span data-stu-id="8b6a2-121">For more information, see [Addresses](endpoint-addresses.md).</span></span> <span data-ttu-id="8b6a2-122">Как указано в введении, [\<headers>](../../configure-apps/file-schema/wcf/headers.md) [\<identity>](../../configure-apps/file-schema/wcf/identity.md) элементы и являются частью <xref:System.ServiceModel.EndpointAddress> и также рассматриваются в разделе [адреса](endpoint-addresses.md) .</span><span class="sxs-lookup"><span data-stu-id="8b6a2-122">As the introduction indicates, the [\<headers>](../../configure-apps/file-schema/wcf/headers.md) and [\<identity>](../../configure-apps/file-schema/wcf/identity.md) elements are part of the <xref:System.ServiceModel.EndpointAddress> and are also discussed in the [Addresses](endpoint-addresses.md) topic.</span></span>  
  
 <span data-ttu-id="8b6a2-123">Атрибут `binding` задает тип привязки, использование которого ожидается в конечной точке при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="8b6a2-123">The `binding` attribute indicates the type of binding the endpoint expects to use when connecting to a service.</span></span> <span data-ttu-id="8b6a2-124">Для того чтобы на тип можно было ссылаться, он должен иметь зарегистрированный раздел конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8b6a2-124">The type must have a registered configuration section if it is to be referenced.</span></span> <span data-ttu-id="8b6a2-125">В предыдущем примере это [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) раздел, который указывает, что конечная точка использует <xref:System.ServiceModel.WSHttpBinding> .</span><span class="sxs-lookup"><span data-stu-id="8b6a2-125">In the previous example, this is the [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) section, which indicates that the endpoint uses a <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="8b6a2-126">Однако могут существовать несколько привязок указанного типа, которые могут использоваться конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="8b6a2-126">But there may be more than one binding of a given type that the endpoint can use.</span></span> <span data-ttu-id="8b6a2-127">Каждый из них имеет собственный [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) элемент в элементе типа (Binding).</span><span class="sxs-lookup"><span data-stu-id="8b6a2-127">Each of these has its own [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element within the (binding) type element.</span></span> <span data-ttu-id="8b6a2-128">Для различения привязок одного типа служит атрибут `bindingconfiguration`.</span><span class="sxs-lookup"><span data-stu-id="8b6a2-128">The `bindingconfiguration` attribute is used to distinguish between bindings of the same type.</span></span> <span data-ttu-id="8b6a2-129">Его значение совпадает с `name` атрибутом [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="8b6a2-129">Its value is matched with the `name` attribute of the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element.</span></span> <span data-ttu-id="8b6a2-130">Дополнительные сведения о настройке привязки клиента с помощью конфигурации см. в разделе [инструкции. Указание привязки клиента в конфигурации](../how-to-specify-a-client-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="8b6a2-130">For more information about how to configure a client binding using configuration, see [How to: Specify a Client Binding in Configuration](../how-to-specify-a-client-binding-in-configuration.md).</span></span>  
  
 <span data-ttu-id="8b6a2-131">`behaviorConfiguration`Атрибут используется для указания того, какую [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) из [\<endpointBehaviors>](../../configure-apps/file-schema/wcf/endpointbehaviors.md) конечных точек следует использовать.</span><span class="sxs-lookup"><span data-stu-id="8b6a2-131">The `behaviorConfiguration` attribute is used to specify which [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) of the [\<endpointBehaviors>](../../configure-apps/file-schema/wcf/endpointbehaviors.md) the endpoint should use.</span></span> <span data-ttu-id="8b6a2-132">Его значение совпадает с `name` атрибутом [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="8b6a2-132">Its value is matched with the `name` attribute of the [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element.</span></span> <span data-ttu-id="8b6a2-133">Пример использования конфигурации для указания поведения клиента см. в разделе [Настройка поведения клиента](../configuring-client-behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="8b6a2-133">For an example of using configuration to specify client behaviors, see [Configuring Client Behaviors](../configuring-client-behaviors.md).</span></span>  
  
 <span data-ttu-id="8b6a2-134">Атрибут `contract` задает контракт, который предоставляет данная конечная точка.</span><span class="sxs-lookup"><span data-stu-id="8b6a2-134">The `contract` attribute specifies which contract the endpoint is exposing.</span></span> <span data-ttu-id="8b6a2-135">Это значение соответствует свойству <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> атрибута <xref:System.ServiceModel.ServiceContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="8b6a2-135">This value maps to the <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> of the <xref:System.ServiceModel.ServiceContractAttribute>.</span></span> <span data-ttu-id="8b6a2-136">Значение по умолчанию - это полное имя типа класса, реализующего службу.</span><span class="sxs-lookup"><span data-stu-id="8b6a2-136">The default value is the full type name of the class that implements the service.</span></span>  
  
### <a name="configuring-metadata"></a><span data-ttu-id="8b6a2-137">Настройка метаданных</span><span class="sxs-lookup"><span data-stu-id="8b6a2-137">Configuring Metadata</span></span>  
 <span data-ttu-id="8b6a2-138">[\<metadata>](../../configure-apps/file-schema/wcf/metadata.md)Элемент используется для указания параметров, используемых для регистрации расширений импорта метаданных.</span><span class="sxs-lookup"><span data-stu-id="8b6a2-138">The [\<metadata>](../../configure-apps/file-schema/wcf/metadata.md) element is used to specify settings used to register metadata import extensions.</span></span> <span data-ttu-id="8b6a2-139">Дополнительные сведения о расширении системы метаданных см. в разделе [расширение системы метаданных](../extending/extending-the-metadata-system.md).</span><span class="sxs-lookup"><span data-stu-id="8b6a2-139">For more information about extending the metadata system, see [Extending the Metadata System](../extending/extending-the-metadata-system.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b6a2-140">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="8b6a2-140">See also</span></span>

- [<span data-ttu-id="8b6a2-141">Конечные точки: адреса, привязки и контракты</span><span class="sxs-lookup"><span data-stu-id="8b6a2-141">Endpoints: Addresses, Bindings, and Contracts</span></span>](endpoints-addresses-bindings-and-contracts.md)
- [<span data-ttu-id="8b6a2-142">Настройка поведений клиентов</span><span class="sxs-lookup"><span data-stu-id="8b6a2-142">Configuring Client Behaviors</span></span>](../configuring-client-behaviors.md)
