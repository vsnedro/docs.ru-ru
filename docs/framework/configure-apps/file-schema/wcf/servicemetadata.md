---
title: <serviceMetadata>
ms.date: 03/30/2017
ms.assetid: 2b4c3b4c-31d4-4908-a9b7-5bb411c221f2
ms.openlocfilehash: 2236361316254d065abd1fb62fd2e509be289a4c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153863"
---
# \<serviceMetadata>

<span data-ttu-id="2b215-101">Задает публикацию метаданных службы и связанных сведений.</span><span class="sxs-lookup"><span data-stu-id="2b215-101">Specifies the publication of service metadata and associated information.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceMetadata>**  
  
## <a name="syntax"></a><span data-ttu-id="2b215-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2b215-102">Syntax</span></span>  
  
```xml  
<serviceMetadata externalMetadataLocation="String"
                 httpGetBinding="String"
                 httpGetBindingConfiguration="String"
                 httpGetEnabled="Boolean"
                 httpGetUrl="String"
                 httpsGetBinding="String"
                 httpsGetBindingConfiguration="String"
                 httpsGetEnabled="Boolean"
                 httpsGetUrl="String"
                 policyVersion="Policy12/Policy15" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2b215-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2b215-103">Attributes and Elements</span></span>  

 <span data-ttu-id="2b215-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2b215-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2b215-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2b215-105">Attributes</span></span>  
  
|<span data-ttu-id="2b215-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2b215-106">Attribute</span></span>|<span data-ttu-id="2b215-107">Описание</span><span class="sxs-lookup"><span data-stu-id="2b215-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2b215-108">externalMetadataLocation</span><span class="sxs-lookup"><span data-stu-id="2b215-108">externalMetadataLocation</span></span>|<span data-ttu-id="2b215-109">Универсальный код ресурса (URI), содержащий местоположение WSDL-файла, возвращаемый пользователю в ответ на запросы WSDL и MEX, вместо автоматически создаваемых WSDL.</span><span class="sxs-lookup"><span data-stu-id="2b215-109">A Uri that contains the location of a WSDL file, which is returned to the user in response to WSDL and MEX requests instead of the auto-generated WSDL.</span></span> <span data-ttu-id="2b215-110">Если атрибут не задан, по умолчанию возвращается WSDL.</span><span class="sxs-lookup"><span data-stu-id="2b215-110">When this attribute is not set, the default WSDL is returned.</span></span> <span data-ttu-id="2b215-111">Значением по умолчанию является пустая строка.</span><span class="sxs-lookup"><span data-stu-id="2b215-111">The default is an empty string.</span></span>|  
|<span data-ttu-id="2b215-112">httpGetBinding</span><span class="sxs-lookup"><span data-stu-id="2b215-112">httpGetBinding</span></span>|<span data-ttu-id="2b215-113">Строковое значение, в котором указывается тип привязки, используемой для загрузки метаданных посредством HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="2b215-113">A string that specifies the type of the binding that will be used for metadata retrieval via HTTP GET.</span></span> <span data-ttu-id="2b215-114">Это необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="2b215-114">This setting is optional.</span></span> <span data-ttu-id="2b215-115">Если он не указан, то будут использоваться привязки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2b215-115">If it is not specified, the default bindings will be used.</span></span><br /><br /> <span data-ttu-id="2b215-116">Поддерживаются только привязки с внутренними элементами привязки, поддерживающими <xref:System.ServiceModel.Channels.IReplyChannel>.</span><span class="sxs-lookup"><span data-stu-id="2b215-116">Only bindings with inner binding elements that support <xref:System.ServiceModel.Channels.IReplyChannel> will be supported.</span></span> <span data-ttu-id="2b215-117">Кроме этого, свойство <xref:System.ServiceModel.Channels.MessageVersion> привязки должно иметь значение <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="2b215-117">Additionally, the <xref:System.ServiceModel.Channels.MessageVersion> property of the binding must be <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span>|  
|<span data-ttu-id="2b215-118">httpGetBindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="2b215-118">httpGetBindingConfiguration</span></span>|<span data-ttu-id="2b215-119">Строка, задающая имя привязки, указанной атрибутом `httpGetBinding`, который ссылается на дополнительные сведения конфигурации этой привязки.</span><span class="sxs-lookup"><span data-stu-id="2b215-119">A string that sets the name of the binding that is specified in the `httpGetBinding` attribute, which references to the additional configuration information of this binding.</span></span> <span data-ttu-id="2b215-120">Такое же имя должно быть задано в разделе `<bindings>`.</span><span class="sxs-lookup"><span data-stu-id="2b215-120">The same name must be defined in the `<bindings>` section.</span></span>|  
|<span data-ttu-id="2b215-121">httpGetEnabled</span><span class="sxs-lookup"><span data-stu-id="2b215-121">httpGetEnabled</span></span>|<span data-ttu-id="2b215-122">Логическое значение, указывающее, следует ли опубликовывать метаданные службы для извлечения с помощью запроса HTTP-GET.</span><span class="sxs-lookup"><span data-stu-id="2b215-122">A Boolean value that specifies whether to publish service metadata for retrieval using an HTTP/Get request.</span></span> <span data-ttu-id="2b215-123">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="2b215-123">The default is `false`.</span></span><br /><br /> <span data-ttu-id="2b215-124">Если атрибут httpGetUrl не указан, адрес, по которому публикуются метаданные, - это адрес службы плюс «?wsdl».</span><span class="sxs-lookup"><span data-stu-id="2b215-124">If the httpGetUrl attribute is not specified, the address at which the metadata is published is the service address plus a "?wsdl".</span></span> <span data-ttu-id="2b215-125">Например, если адрес службы — `http://localhost:8080/CalculatorService` , адрес МЕТАДАННЫХ HTTP/Get — `http://localhost:8080/CalculatorService?wsdl` .</span><span class="sxs-lookup"><span data-stu-id="2b215-125">For example, if the service address is `http://localhost:8080/CalculatorService`, the HTTP/Get metadata address is `http://localhost:8080/CalculatorService?wsdl`.</span></span><br /><br /> <span data-ttu-id="2b215-126">Если это свойство имеет значение `false` или адрес службы не основан на HTTP или HTTPS, "? WSDL" игнорируется.</span><span class="sxs-lookup"><span data-stu-id="2b215-126">If this property is `false`, or the address of the service is not based on HTTP or HTTPS, "?wsdl" is ignored.</span></span>|  
|<span data-ttu-id="2b215-127">httpGetUrl</span><span class="sxs-lookup"><span data-stu-id="2b215-127">httpGetUrl</span></span>|<span data-ttu-id="2b215-128">URI, указывающий адрес, по которому метаданные публикуются для извлечения с использованием запроса HTTP-GET.</span><span class="sxs-lookup"><span data-stu-id="2b215-128">A Uri that specifies the address at which the metadata is published for retrieval using an HTTP/Get request.</span></span> <span data-ttu-id="2b215-129">Если указан относительный URI, то он будет обрабатываться относительно базового адреса службы.</span><span class="sxs-lookup"><span data-stu-id="2b215-129">If a relative Uri is specified it will be treated as relative to the service’s base address.</span></span>|  
|<span data-ttu-id="2b215-130">httpsGetBinding</span><span class="sxs-lookup"><span data-stu-id="2b215-130">httpsGetBinding</span></span>|<span data-ttu-id="2b215-131">Строковое значение, в котором указывается тип привязки, используемой для загрузки метаданных посредством HTTPS GET.</span><span class="sxs-lookup"><span data-stu-id="2b215-131">A string that specifies the type of the binding that will be used for metadata retrieval via HTTPS GET.</span></span> <span data-ttu-id="2b215-132">Это необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="2b215-132">This setting is optional.</span></span> <span data-ttu-id="2b215-133">Если он не указан, то будут использоваться привязки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2b215-133">If it is not specified, the default bindings will be used.</span></span><br /><br /> <span data-ttu-id="2b215-134">Поддерживаются только привязки с внутренними элементами привязки, поддерживающими <xref:System.ServiceModel.Channels.IReplyChannel>.</span><span class="sxs-lookup"><span data-stu-id="2b215-134">Only bindings with inner binding elements that support <xref:System.ServiceModel.Channels.IReplyChannel> will be supported.</span></span> <span data-ttu-id="2b215-135">Кроме этого, свойство <xref:System.ServiceModel.Channels.MessageVersion> привязки должно иметь значение <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="2b215-135">Additionally, the <xref:System.ServiceModel.Channels.MessageVersion> property of the binding must be <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span>|  
|<span data-ttu-id="2b215-136">httpsGetBindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="2b215-136">httpsGetBindingConfiguration</span></span>|<span data-ttu-id="2b215-137">Строка, задающая имя привязки, указанной атрибутом `httpsGetBinding`, который ссылается на дополнительные сведения конфигурации этой привязки.</span><span class="sxs-lookup"><span data-stu-id="2b215-137">A string that sets the name of the binding that is specified in the `httpsGetBinding` attribute, which references to the additional configuration information of this binding.</span></span> <span data-ttu-id="2b215-138">Такое же имя должно быть задано в разделе `<bindings>`.</span><span class="sxs-lookup"><span data-stu-id="2b215-138">The same name must be defined in the `<bindings>` section.</span></span>|  
|<span data-ttu-id="2b215-139">httpsGetEnabled</span><span class="sxs-lookup"><span data-stu-id="2b215-139">httpsGetEnabled</span></span>|<span data-ttu-id="2b215-140">Логическое значение, указывающее, следует ли опубликовывать метаданные службы для извлечения с помощью запроса HTTPS-GET.</span><span class="sxs-lookup"><span data-stu-id="2b215-140">A Boolean value that specifies whether to publish service metadata for retrieval using an HTTPS/Get request.</span></span> <span data-ttu-id="2b215-141">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="2b215-141">The default is `false`.</span></span><br /><br /> <span data-ttu-id="2b215-142">Если атрибут httpsGetUrl не указан, адрес, по которому публикуются метаданные, - это адрес службы плюс «?wsdl».</span><span class="sxs-lookup"><span data-stu-id="2b215-142">If the httpsGetUrl attribute is not specified, the address at which the metadata is published is the service address plus a "?wsdl".</span></span> <span data-ttu-id="2b215-143">Например, если адрес службы — " https://localhost:8080/CalculatorService ", адрес МЕТАДАННЫХ HTTP/GET — " https://localhost:8080/CalculatorService?wsdl ".</span><span class="sxs-lookup"><span data-stu-id="2b215-143">For example, if the service address is "https://localhost:8080/CalculatorService", the HTTP/Get metadata address is "https://localhost:8080/CalculatorService?wsdl".</span></span><br /><br /> <span data-ttu-id="2b215-144">Если это свойство имеет значение `false` или адрес службы не основан на HTTP или HTTPS, "? WSDL" игнорируется.</span><span class="sxs-lookup"><span data-stu-id="2b215-144">If this property is `false`, or the address of the service is not based on HTTP or HTTPS, "?wsdl" is ignored.</span></span>|  
|<span data-ttu-id="2b215-145">httpsGetUrl</span><span class="sxs-lookup"><span data-stu-id="2b215-145">httpsGetUrl</span></span>|<span data-ttu-id="2b215-146">URI, указывающий адрес, по которому метаданные публикуются для извлечения с использованием запроса HTTPS-GET.</span><span class="sxs-lookup"><span data-stu-id="2b215-146">A Uri that specifies the address at which the metadata is published for retrieval using an HTTPS/Get request.</span></span>|  
|<span data-ttu-id="2b215-147">policyVersion</span><span class="sxs-lookup"><span data-stu-id="2b215-147">policyVersion</span></span>|<span data-ttu-id="2b215-148">Строка, указывающая версию используемой спецификации Web Services Policy.</span><span class="sxs-lookup"><span data-stu-id="2b215-148">A string that specifies the version of the WS-Policy specification being used.</span></span> <span data-ttu-id="2b215-149">Это атрибут типа <xref:System.ServiceModel.Description.PolicyVersion>.</span><span class="sxs-lookup"><span data-stu-id="2b215-149">This attribute is of type <xref:System.ServiceModel.Description.PolicyVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2b215-150">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2b215-150">Child Elements</span></span>  

 <span data-ttu-id="2b215-151">Нет</span><span class="sxs-lookup"><span data-stu-id="2b215-151">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2b215-152">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2b215-152">Parent Elements</span></span>  
  
|<span data-ttu-id="2b215-153">Элемент</span><span class="sxs-lookup"><span data-stu-id="2b215-153">Element</span></span>|<span data-ttu-id="2b215-154">Описание</span><span class="sxs-lookup"><span data-stu-id="2b215-154">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="2b215-155">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="2b215-155">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b215-156">Remarks</span><span class="sxs-lookup"><span data-stu-id="2b215-156">Remarks</span></span>  

 <span data-ttu-id="2b215-157">Элемент конфигурации позволяет управлять возможностями публикации метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="2b215-157">This configuration element allows you to control the metadata publishing features of a service.</span></span> <span data-ttu-id="2b215-158">Чтобы предотвратить непреднамеренное раскрытие потенциально конфиденциальных метаданных службы, конфигурация по умолчанию для служб Windows Communication Foundation (WCF) отключает публикацию метаданных.</span><span class="sxs-lookup"><span data-stu-id="2b215-158">To prevent unintentional disclosure of potentially sensitive service metadata, the default configuration for Windows Communication Foundation (WCF) services disables metadata publishing.</span></span> <span data-ttu-id="2b215-159">Такое расширение функциональности по умолчанию защищено, но это также означает, что при этом невозможно использовать средство импорта метаданных (например, Svcutil.exe) для создания клиентского кода, необходимого для вызова службы, если поведение публикации не включено явно в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2b215-159">This behavior is secure by default, but also means that you cannot use a metadata import tool (such as Svcutil.exe) to generate the client code required to call the service unless the service’s metadata publishing behavior is explicitly enabled in configuration.</span></span> <span data-ttu-id="2b215-160">Включить такое поведение публикации для службы можно с помощью элемента конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2b215-160">Using this configuration element, you can enable this publishing behavior for your service.</span></span>  
  
 <span data-ttu-id="2b215-161">Подробный пример настройки этого поведения см. в разделе [поведение публикации метаданных](../../../wcf/samples/metadata-publishing-behavior.md).</span><span class="sxs-lookup"><span data-stu-id="2b215-161">For a detailed example of configuring this behavior, see [Metadata Publishing Behavior](../../../wcf/samples/metadata-publishing-behavior.md).</span></span>  
  
 <span data-ttu-id="2b215-162">Дополнительные атрибуты `httpGetBinding` и `httpsGetBinding` позволяют настроить привязки, используемые для извлечения метаданных посредством HTTP-GET (или HTTPS-GET).</span><span class="sxs-lookup"><span data-stu-id="2b215-162">The optional `httpGetBinding` and `httpsGetBinding` attributes allow you to configure the bindings used for metadata retrieval via HTTP GET (or HTTPS GET).</span></span> <span data-ttu-id="2b215-163">Если они не заданы, для извлечения метаданных применяются привязки по умолчанию (`HttpTransportBindingElement` для HTTP и `HttpsTransportBindingElement` для HTTPS).</span><span class="sxs-lookup"><span data-stu-id="2b215-163">If they are not specified, the default bindings (`HttpTransportBindingElement`, in the case of HTTP and `HttpsTransportBindingElement`, in the case of HTTPS) are used for metadata retrieval as appropriate.</span></span> <span data-ttu-id="2b215-164">Обратите внимание, что эти атрибуты нельзя использовать вместе со встроенными привязками WCF.</span><span class="sxs-lookup"><span data-stu-id="2b215-164">Notice that you cannot use these attributes with the built-in WCF bindings.</span></span> <span data-ttu-id="2b215-165">Поддерживаются только привязки с внутренними элементами привязки, поддерживающими <xref:System.ServiceModel.Channels.IReplyChannel>.</span><span class="sxs-lookup"><span data-stu-id="2b215-165">Only bindings with inner binding elements that support <xref:System.ServiceModel.Channels.IReplyChannel> will be supported.</span></span> <span data-ttu-id="2b215-166">Кроме этого, свойство <xref:System.ServiceModel.Channels.MessageVersion> привязки должно иметь значение <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="2b215-166">Additionally, the <xref:System.ServiceModel.Channels.MessageVersion> property of the binding must be <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span>  
  
 <span data-ttu-id="2b215-167">Для снижения подверженности службы действиям недобросовестных пользователей перенос можно защитить с помощью механизма SSL по протоколу HTTP (HTTPS).</span><span class="sxs-lookup"><span data-stu-id="2b215-167">To reduce the exposure of a service to malicious users, it is possible to secure the transfer using the SSL over HTTP (HTTPS) mechanism.</span></span> <span data-ttu-id="2b215-168">Для этого необходимо вначале выполнить привязку подходящего сертификата X.509 к конкретному порту компьютера, на котором размещена служба.</span><span class="sxs-lookup"><span data-stu-id="2b215-168">To do so, you must first bind a suitable X.509 certificate to a specific port on the computer that is hosting the service.</span></span> <span data-ttu-id="2b215-169">(Дополнительные сведения см. в разделе [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md).) Во вторых, добавьте этот элемент в конфигурацию службы и присвойте `httpsGetEnabled` атрибуту значение `true` .</span><span class="sxs-lookup"><span data-stu-id="2b215-169">(For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).) Second, add this element to the service configuration and set the `httpsGetEnabled` attribute to `true`.</span></span> <span data-ttu-id="2b215-170">После этого следует присвоить атрибуту `httpsGetUrl` URL-адрес конечной точки метаданных службы, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="2b215-170">Finally, set the `httpsGetUrl` attribute to the URL of the service metadata endpoint, as shown in the following example.</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="NewBehavior">
      <serviceMetadata httpsGetEnabled="true"
                       httpsGetUrl="https://myComputerName/myEndpoint" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="example"></a><span data-ttu-id="2b215-171">Пример</span><span class="sxs-lookup"><span data-stu-id="2b215-171">Example</span></span>  

 <span data-ttu-id="2b215-172">В следующем примере служба настраивается для предоставления метаданных с помощью \<serviceMetadata> элемента.</span><span class="sxs-lookup"><span data-stu-id="2b215-172">The following example configure a service to expose metadata by using the \<serviceMetadata> element.</span></span> <span data-ttu-id="2b215-173">Здесь также настраивается конечная точка предоставления доступа к контракту `IMetadataExchange` как реализации протокола WS-MetadataExchange (MEX).</span><span class="sxs-lookup"><span data-stu-id="2b215-173">It also configures an endpoint to expose the `IMetadataExchange` contract as an implementation of a WS-MetadataExchange (MEX) protocol.</span></span> <span data-ttu-id="2b215-174">В примере используется привязка `mexHttpBinding`, являющаяся удобной стандартной привязкой, эквивалентной привязке `wsHttpBinding` с режимом безопасности `None`.</span><span class="sxs-lookup"><span data-stu-id="2b215-174">The example uses the `mexHttpBinding`, which is a convenience standard binding that is equivalent to the `wsHttpBinding` with the security mode set to `None`.</span></span> <span data-ttu-id="2b215-175">В конечной точке используется относительный адрес MEX, который при разрешении по базовому адресу служб приводит к адресу конечной точки `http://localhost/servicemodelsamples/service.svc/mex` .</span><span class="sxs-lookup"><span data-stu-id="2b215-175">A relative address of "mex" is used in the endpoint, which when resolved against the services base address results in an endpoint address of `http://localhost/servicemodelsamples/service.svc/mex`.</span></span>  
  
```xml  
<configuration>
  <system.serviceModel>
    <services>
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"
               behaviorConfiguration="CalculatorServiceBehavior">
        <!-- This endpoint is exposed at the base address provided by the host: http://localhost/servicemodelsamples/service.svc -->
        <endpoint address=""
                  binding="wsHttpBinding"
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />
        <!-- The mex endpoint is exposed at http://localhost/servicemodelsamples/service.svc/mex
             To expose the IMetadataExchange contract, you must enable the serviceMetadata behavior as demonstrated below. -->
        <endpoint address="mex"
                  binding="mexHttpBinding"
                  contract="IMetadataExchange" />
      </service>
    </services>
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
    <behaviors>
      <serviceBehaviors>
        <behavior name="CalculatorServiceBehavior">
          <!-- The serviceMetadata behavior publishes metadata through the IMetadataExchange contract. When this behavior is
               present, you can expose this contract through an endpoint as shown above. Setting httpGetEnabled to true publishes
               the service's WSDL at the <baseaddress>?wsdl eg. http://localhost/servicemodelsamples/service.svc?wsdl -->
          <serviceMetadata httpGetEnabled="True" />
          <serviceDebug includeExceptionDetailInFaults="False" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="2b215-176">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2b215-176">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceMetadataPublishingElement>
- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
- [<span data-ttu-id="2b215-177">Поведение безопасности</span><span class="sxs-lookup"><span data-stu-id="2b215-177">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="2b215-178">Поведение публикации метаданных</span><span class="sxs-lookup"><span data-stu-id="2b215-178">Metadata Publishing Behavior</span></span>](../../../wcf/samples/metadata-publishing-behavior.md)
