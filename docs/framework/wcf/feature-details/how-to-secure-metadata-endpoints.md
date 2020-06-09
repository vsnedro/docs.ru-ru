---
title: Практическое руководство. Защита конечных точек метаданных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9f71b6ae-737c-4382-8d89-0a7b1c7e182b
ms.openlocfilehash: c5efd921d3826ef814bf45d6895255981101d992
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84592961"
---
# <a name="how-to-secure-metadata-endpoints"></a><span data-ttu-id="37e23-102">Практическое руководство. Защита конечных точек метаданных</span><span class="sxs-lookup"><span data-stu-id="37e23-102">How to: Secure Metadata Endpoints</span></span>

<span data-ttu-id="37e23-103">Метаданные для службы могут содержать конфиденциальные сведения о приложении, которые могут быть использованы злоумышленником.</span><span class="sxs-lookup"><span data-stu-id="37e23-103">Metadata for a service can contain sensitive information about your application that a malicious user can leverage.</span></span> <span data-ttu-id="37e23-104">Потребителям службы может также потребоваться безопасный механизм получения метаданных о службе.</span><span class="sxs-lookup"><span data-stu-id="37e23-104">Consumers of your service may also require a secure mechanism for obtaining metadata about your service.</span></span> <span data-ttu-id="37e23-105">Поэтому необходимо время от времени публиковать метаданные с помощью защищенной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="37e23-105">Therefore, it is sometimes necessary to publish your metadata using a secure endpoint.</span></span>

<span data-ttu-id="37e23-106">Конечные точки метаданных обычно защищаются с помощью стандартных механизмов безопасности, определенных в Windows Communication Foundation (WCF) для защиты конечных точек приложений.</span><span class="sxs-lookup"><span data-stu-id="37e23-106">Metadata endpoints are generally secured using the standard security mechanisms defined in Windows Communication Foundation (WCF) for securing application endpoints.</span></span> <span data-ttu-id="37e23-107">Дополнительные сведения см. в [обзоре безопасности](security-overview.md).</span><span class="sxs-lookup"><span data-stu-id="37e23-107">For more information, see [Security Overview](security-overview.md).</span></span>

<span data-ttu-id="37e23-108">В этом разделе содержится пошаговое руководство по созданию конечной точки, безопасность которой обеспечивается SSL-сертификатом, то есть конечной точкой HTTPS.</span><span class="sxs-lookup"><span data-stu-id="37e23-108">This topic walks through the steps to create an endpoint secured by a Secure Sockets Layer (SSL) certificate or, in other words, an HTTPS endpoint.</span></span>

### <a name="to-create-a-secure-https-get-metadata-endpoint-in-code"></a><span data-ttu-id="37e23-109">Добавление защищенной конечной точки метаданных HTTPS GET в код</span><span class="sxs-lookup"><span data-stu-id="37e23-109">To create a secure HTTPS GET metadata endpoint in code</span></span>

1. <span data-ttu-id="37e23-110">Настройте порт с соответствующим сертификатом X.509.</span><span class="sxs-lookup"><span data-stu-id="37e23-110">Configure a port with an appropriate X.509 certificate.</span></span> <span data-ttu-id="37e23-111">Сертификат должен быть получен из надежного центра сертификации и должен предназначаться для авторизации службы.</span><span class="sxs-lookup"><span data-stu-id="37e23-111">The certificate must come from a trusted authority, and it must have an intended use of "Service Authorization."</span></span> <span data-ttu-id="37e23-112">Для привязки сертификата к конкретному порту используйте средство HttpCfg.exe.</span><span class="sxs-lookup"><span data-stu-id="37e23-112">You must use the HttpCfg.exe tool to attach the certificate to the port.</span></span> <span data-ttu-id="37e23-113">См. раздел [как настроить порт с помощью SSL-сертификата](how-to-configure-a-port-with-an-ssl-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="37e23-113">See [How to: Configure a Port with an SSL Certificate](how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="37e23-114">Субъект сертификата или его служба доменных имен (DNS) должны соответствовать имени компьютера.</span><span class="sxs-lookup"><span data-stu-id="37e23-114">The subject of the certificate or its Domain Name System (DNS) must match the name of the computer.</span></span> <span data-ttu-id="37e23-115">Это важно, так как одним из первых шагов механизма HTTPS является проверка соответствия сертификата универсальному коду ресурса (URI) и адресу, для которого он вызван.</span><span class="sxs-lookup"><span data-stu-id="37e23-115">This is essential because one of the first steps the HTTPS mechanism performs is to check that the certificate is issued to the same Uniform Resource Identifier (URI) as the address upon which it is invoked.</span></span>

2. <span data-ttu-id="37e23-116">Создайте новый экземпляр класса <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.</span><span class="sxs-lookup"><span data-stu-id="37e23-116">Create a new instance of the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> class.</span></span>

3. <span data-ttu-id="37e23-117">Задайте свойству <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> класса <xref:System.ServiceModel.Description.ServiceMetadataBehavior> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="37e23-117">Set the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> property of the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> class to `true`.</span></span>

4. <span data-ttu-id="37e23-118">Присвойте свойству <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A> соответствующее значение URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="37e23-118">Set the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A> property to an appropriate URL.</span></span> <span data-ttu-id="37e23-119">Обратите внимание, что при указании абсолютного адреса URL-адрес должен начинаться с схемы `https://` .</span><span class="sxs-lookup"><span data-stu-id="37e23-119">Note that if you specify an absolute address, the URL must begin with the scheme `https://`.</span></span> <span data-ttu-id="37e23-120">При указании относительного адреса необходимо определить базовый адрес HTTPS узла службы.</span><span class="sxs-lookup"><span data-stu-id="37e23-120">If you specify a relative address, you must supply an HTTPS base address for your service host.</span></span> <span data-ttu-id="37e23-121">Если это свойство службы не задано, за адрес по умолчанию принимается "" или непосредственно базовый адрес HTTPS службы.</span><span class="sxs-lookup"><span data-stu-id="37e23-121">If this property is not set, the default address is "", or directly at the HTTPS base address for the service.</span></span>

5. <span data-ttu-id="37e23-122">Создайте экземпляр коллекции поведений, который возвращает свойство <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> класса <xref:System.ServiceModel.Description.ServiceDescription> в соответствии со следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="37e23-122">Add the instance to the behaviors collection that the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> property of the <xref:System.ServiceModel.Description.ServiceDescription> class returns, as shown in the following code.</span></span>

    [!code-csharp[c_HowToSecureEndpoint#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosecureendpoint/cs/source.cs#1)]
    [!code-vb[c_HowToSecureEndpoint#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosecureendpoint/vb/source.vb#1)]

### <a name="to-create-a-secure-https-get-metadata-endpoint-in-configuration"></a><span data-ttu-id="37e23-123">Добавление защищенной конечной точки метаданных HTTPS GET в конфигурацию</span><span class="sxs-lookup"><span data-stu-id="37e23-123">To create a secure HTTPS GET metadata endpoint in configuration</span></span>

1. <span data-ttu-id="37e23-124">Добавьте [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) элемент в [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) элемент файла конфигурации для службы.</span><span class="sxs-lookup"><span data-stu-id="37e23-124">Add a [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element to the [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element of the configuration file for your service.</span></span>

2. <span data-ttu-id="37e23-125">Добавьте [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) элемент в [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="37e23-125">Add a [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) element to the [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element.</span></span>

3. <span data-ttu-id="37e23-126">Добавьте [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) элемент в `<serviceBehaviors>` элемент.</span><span class="sxs-lookup"><span data-stu-id="37e23-126">Add a [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element to the `<serviceBehaviors>` element.</span></span>

4. <span data-ttu-id="37e23-127">Задайте атрибуту `name` элемента `<behavior>` соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="37e23-127">Set the `name` attribute of the `<behavior>` element to an appropriate value.</span></span> <span data-ttu-id="37e23-128">Атрибут `name` является обязательным.</span><span class="sxs-lookup"><span data-stu-id="37e23-128">The `name` attribute is required.</span></span> <span data-ttu-id="37e23-129">В приведенном ниже примере используется значение `mySvcBehavior`.</span><span class="sxs-lookup"><span data-stu-id="37e23-129">The example below uses the value `mySvcBehavior`.</span></span>

5. <span data-ttu-id="37e23-130">Добавьте в [\<serviceMetadata>](../../configure-apps/file-schema/wcf/servicemetadata.md) `<behavior>` элемент.</span><span class="sxs-lookup"><span data-stu-id="37e23-130">Add a [\<serviceMetadata>](../../configure-apps/file-schema/wcf/servicemetadata.md) to the `<behavior>` element.</span></span>

6. <span data-ttu-id="37e23-131">Задайте атрибуту `httpsGetEnabled` элемента `<serviceMetadata>` значение `true`.</span><span class="sxs-lookup"><span data-stu-id="37e23-131">Set the `httpsGetEnabled` attribute of the `<serviceMetadata>` element to `true`.</span></span>

7. <span data-ttu-id="37e23-132">Задайте атрибуту `httpsGetUrl` элемента `<serviceMetadata>` соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="37e23-132">Set the `httpsGetUrl` attribute of the `<serviceMetadata>` element to an appropriate value.</span></span> <span data-ttu-id="37e23-133">Обратите внимание, что при указании абсолютного адреса URL-адрес должен начинаться с схемы `https://` .</span><span class="sxs-lookup"><span data-stu-id="37e23-133">Note that if you specify an absolute address, the URL must begin with the scheme `https://`.</span></span> <span data-ttu-id="37e23-134">При указании относительного адреса необходимо определить базовый адрес HTTPS узла службы.</span><span class="sxs-lookup"><span data-stu-id="37e23-134">If you specify a relative address, you must supply an HTTPS base address for your service host.</span></span> <span data-ttu-id="37e23-135">Если это свойство службы не задано, за адрес по умолчанию принимается "" или непосредственно базовый адрес HTTPS службы.</span><span class="sxs-lookup"><span data-stu-id="37e23-135">If this property is not set, the default address is "", or directly at the HTTPS base address for the service.</span></span>

8. <span data-ttu-id="37e23-136">Чтобы использовать поведение службы, присвойте `behaviorConfiguration` атрибуту [\<service>](../../configure-apps/file-schema/wcf/service.md) элемента значение атрибута Name элемента Behavior.</span><span class="sxs-lookup"><span data-stu-id="37e23-136">To use the behavior with a service, set the `behaviorConfiguration` attribute of the [\<service>](../../configure-apps/file-schema/wcf/service.md) element to the value of the name attribute of the behavior element.</span></span> <span data-ttu-id="37e23-137">В следующем примере приводится полный код конфигурации.</span><span class="sxs-lookup"><span data-stu-id="37e23-137">The following configuration code shows a complete example.</span></span>

    ```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
     <system.serviceModel>
      <behaviors>
       <serviceBehaviors>
        <behavior name="mySvcBehavior">
         <serviceMetadata httpsGetEnabled="true"
              httpsGetUrl="https://localhost:8036/calcMetadata" />
        </behavior>
       </serviceBehaviors>
      </behaviors>
     <services>
      <service behaviorConfiguration="mySvcBehavior"
            name="Microsoft.Security.Samples.Calculator">
       <endpoint address="http://localhost:8037/ServiceModelSamples/calculator"
       binding="wsHttpBinding" bindingConfiguration=""
       contract="Microsoft.Security.Samples.ICalculator" />
      </service>
     </services>
    </system.serviceModel>
    </configuration>
    ```

## <a name="example"></a><span data-ttu-id="37e23-138">Пример</span><span class="sxs-lookup"><span data-stu-id="37e23-138">Example</span></span>

<span data-ttu-id="37e23-139">В следующем примере создается экземпляр класса <xref:System.ServiceModel.ServiceHost> и добавляется конечная точка.</span><span class="sxs-lookup"><span data-stu-id="37e23-139">The following example creates an instance of a <xref:System.ServiceModel.ServiceHost> class and adds an endpoint.</span></span> <span data-ttu-id="37e23-140">Затем создается экземпляр класса <xref:System.ServiceModel.Description.ServiceMetadataBehavior> и задаются свойства для создания защищенной точки обмена метаданными.</span><span class="sxs-lookup"><span data-stu-id="37e23-140">The code then creates an instance of the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> class and sets the properties to create a secure metadata exchange point.</span></span>

[!code-csharp[c_HowToSecureEndpoint#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosecureendpoint/cs/source.cs#0)]
[!code-vb[c_HowToSecureEndpoint#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosecureendpoint/vb/source.vb#0)]

## <a name="compiling-the-code"></a><span data-ttu-id="37e23-141">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="37e23-141">Compiling the Code</span></span>

<span data-ttu-id="37e23-142">В примере кода используются следующие пространства имен:</span><span class="sxs-lookup"><span data-stu-id="37e23-142">The code example uses the following namespaces:</span></span>

- <xref:System.ServiceModel?displayProperty=nameWithType>

- <xref:System.ServiceModel.Description?displayProperty=nameWithType>

## <a name="see-also"></a><span data-ttu-id="37e23-143">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="37e23-143">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A>
- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
- <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A>
- [<span data-ttu-id="37e23-144">Практическое руководство. Настройка порта с использованием SSL-сертификата</span><span class="sxs-lookup"><span data-stu-id="37e23-144">How to: Configure a Port with an SSL Certificate</span></span>](how-to-configure-a-port-with-an-ssl-certificate.md)
- [<span data-ttu-id="37e23-145">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="37e23-145">Working with Certificates</span></span>](working-with-certificates.md)
- [<span data-ttu-id="37e23-146">Вопросы безопасности при использовании метаданных</span><span class="sxs-lookup"><span data-stu-id="37e23-146">Security Considerations with Metadata</span></span>](security-considerations-with-metadata.md)
- [<span data-ttu-id="37e23-147">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="37e23-147">Securing Services and Clients</span></span>](securing-services-and-clients.md)
