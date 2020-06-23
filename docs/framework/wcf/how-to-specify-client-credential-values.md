---
title: Практическое руководство. Задание значений учетных данных клиента
description: Узнайте, как служба WCF может указать, как клиент проходит проверку подлинности в этой службе. В этом примере указывается сертификат X. 509 и транспортный режим.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 82293d7f-471a-4549-8f19-0be890e7b074
ms.openlocfilehash: 75a21a7dc083282f6b2fe839167ff1b2eddfb373
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244456"
---
# <a name="how-to-specify-client-credential-values"></a><span data-ttu-id="0c2d4-104">Практическое руководство. Задание значений учетных данных клиента</span><span class="sxs-lookup"><span data-stu-id="0c2d4-104">How to: Specify Client Credential Values</span></span>

<span data-ttu-id="0c2d4-105">С помощью Windows Communication Foundation (WCF) служба может указать, как клиент проходит проверку подлинности в службе.</span><span class="sxs-lookup"><span data-stu-id="0c2d4-105">Using Windows Communication Foundation (WCF), the service can specify how a client is authenticated to the service.</span></span> <span data-ttu-id="0c2d4-106">Например, в службе можно указать, что клиент проходит проверку подлинности с помощью сертификата.</span><span class="sxs-lookup"><span data-stu-id="0c2d4-106">For example, a service can stipulate that the client be authenticated with a certificate.</span></span>

## <a name="to-determine-the-client-credential-type"></a><span data-ttu-id="0c2d4-107">Определение типа учетных данных клиента</span><span class="sxs-lookup"><span data-stu-id="0c2d4-107">To determine the client credential type</span></span>

1. <span data-ttu-id="0c2d4-108">Получите метаданные из конечной точки метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="0c2d4-108">Retrieve metadata from the service's metadata endpoint.</span></span> <span data-ttu-id="0c2d4-109">Метаданные обычно состоят из двух файлов: код клиента на выбранном языке программирования (по умолчанию - Visual C#) и XML-файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0c2d4-109">The metadata typically consists of two files: the client code in the programming language of your choice (the default is Visual C#), and an XML configuration file.</span></span> <span data-ttu-id="0c2d4-110">Одним из способов получения метаданных является использование программы Svcutil.exe для возвращения кода клиента и конфигурации клиента.</span><span class="sxs-lookup"><span data-stu-id="0c2d4-110">One way to retrieve metadata is to use the Svcutil.exe tool to return the client code and client configuration.</span></span> <span data-ttu-id="0c2d4-111">Дополнительные сведения см. в разделе [Получение метаданных](./feature-details/retrieving-metadata.md) и [служебная программа метаданных ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="0c2d4-111">For more information, see [Retrieving Metadata](./feature-details/retrieving-metadata.md) and [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>

2. <span data-ttu-id="0c2d4-112">Откройте XML-файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0c2d4-112">Open the XML configuration file.</span></span> <span data-ttu-id="0c2d4-113">Если используется программа Svcutil.exe, то по умолчанию файл имеет имя Output.config.</span><span class="sxs-lookup"><span data-stu-id="0c2d4-113">If you use the Svcutil.exe tool, the default name of the file is Output.config.</span></span>

3. <span data-ttu-id="0c2d4-114">Найдите **\<security>** элемент с помощью атрибута **mode** ( **\<security mode =**`MessageOrTransport`**>** где `MessageOrTransport` задается один из режимов безопасности.</span><span class="sxs-lookup"><span data-stu-id="0c2d4-114">Find the **\<security>** element with the **mode** attribute (**\<security mode =**`MessageOrTransport`**>** where `MessageOrTransport` is set to one of the security modes.</span></span>

4. <span data-ttu-id="0c2d4-115">Найдите дочерний элемент, соответствующий значению режима.</span><span class="sxs-lookup"><span data-stu-id="0c2d4-115">Find the child element that matches the mode value.</span></span> <span data-ttu-id="0c2d4-116">Например, если для режима задано значение **Message**, найдите элемент, **\<message>** содержащийся в **\<security>** элементе.</span><span class="sxs-lookup"><span data-stu-id="0c2d4-116">For example, if the mode is set to **Message**, find the **\<message>** element contained in the **\<security>** element.</span></span>

5. <span data-ttu-id="0c2d4-117">Запишите значение, присвоенное атрибуту **ClientCredentialType** .</span><span class="sxs-lookup"><span data-stu-id="0c2d4-117">Note the value assigned to the **clientCredentialType** attribute.</span></span> <span data-ttu-id="0c2d4-118">Фактическое значение зависит от используемого режима - транспорт или сообщение.</span><span class="sxs-lookup"><span data-stu-id="0c2d4-118">The actual value depends on which mode is used, transport or message.</span></span>

<span data-ttu-id="0c2d4-119">Следующий XML-код представляет конфигурацию для клиента, использующего безопасность сообщений. Для проверки подлинности клиента требуется сертификат.</span><span class="sxs-lookup"><span data-stu-id="0c2d4-119">The following XML code shows configuration for a client using message security and requiring a certificate to authenticate the client.</span></span>

```xml
<security mode="Message">
    <transport clientCredentialType="Windows" proxyCredentialType="None"
        realm="" />
     <message clientCredentialType="Certificate" negotiateServiceCredential="true"
    algorithmSuite="Default" establishSecurityContext="true" />
</security>
```

## <a name="example-tcp-transport-mode-with-certificate-as-client-credential"></a><span data-ttu-id="0c2d4-120">Пример: транспортный режим TCP с сертификатом в качестве учетных данных клиента</span><span class="sxs-lookup"><span data-stu-id="0c2d4-120">Example: TCP Transport Mode with Certificate as Client Credential</span></span>

<span data-ttu-id="0c2d4-121">В этом примере в качестве режима безопасности задается Transport, а в качестве значения учетных данных клиента - сертификат X.509.</span><span class="sxs-lookup"><span data-stu-id="0c2d4-121">This example sets the security mode to Transport mode and sets the client credential value to an X.509 certificate.</span></span> <span data-ttu-id="0c2d4-122">В следующих процедурах показано, как задать значение учетных данных клиента в коде клиента и в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0c2d4-122">The following procedures demonstrate how to set the client credential value on the client in code and configuration.</span></span> <span data-ttu-id="0c2d4-123">Предполагается, что вы использовали [средство служебной программы метаданных ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) для возврата метаданных (кода и конфигурации) из службы.</span><span class="sxs-lookup"><span data-stu-id="0c2d4-123">This assumes that you have used the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) to return the metadata (code and configuration) from the service.</span></span> <span data-ttu-id="0c2d4-124">Дополнительные сведения см. [в разделе инструкции. Создание клиента](how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="0c2d4-124">For more information, see [How to: Create a Client](how-to-create-a-wcf-client.md).</span></span>

### <a name="to-specify-the-client-credential-value-on-the-client-in-code"></a><span data-ttu-id="0c2d4-125">Указание значения учетных данных клиента в коде клиента</span><span class="sxs-lookup"><span data-stu-id="0c2d4-125">To specify the client credential value on the client in code</span></span>

1. <span data-ttu-id="0c2d4-126">Используйте [средство служебной программы метаданных ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) для создания кода и конфигурации из службы.</span><span class="sxs-lookup"><span data-stu-id="0c2d4-126">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) to generate code and configuration from the service.</span></span>

2. <span data-ttu-id="0c2d4-127">Создайте экземпляр клиента WCF с помощью созданного кода.</span><span class="sxs-lookup"><span data-stu-id="0c2d4-127">Create an instance of the WCF client using the generated code.</span></span>

3. <span data-ttu-id="0c2d4-128">В классе клиента задайте соответствующее значение для свойства <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> класса <xref:System.ServiceModel.ClientBase%601>.</span><span class="sxs-lookup"><span data-stu-id="0c2d4-128">On the client class, set the <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> property of the <xref:System.ServiceModel.ClientBase%601> class to an appropriate value.</span></span> <span data-ttu-id="0c2d4-129">В этом примере в качестве значения свойства задается сертификат X.509 с помощью метода <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> класса <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>.</span><span class="sxs-lookup"><span data-stu-id="0c2d4-129">This example sets the property to an X.509 certificate using the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> method of the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential> class.</span></span>

     [!code-csharp[c_TcpService#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpservice/cs/source.cs#4)]
     [!code-vb[c_TcpService#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpservice/vb/source.vb#4)]

     <span data-ttu-id="0c2d4-130">Можно использовать любое перечисление класса <xref:System.Security.Cryptography.X509Certificates.X509FindType>.</span><span class="sxs-lookup"><span data-stu-id="0c2d4-130">You can use any of the enumerations of the <xref:System.Security.Cryptography.X509Certificates.X509FindType> class.</span></span> <span data-ttu-id="0c2d4-131">В случае, если сертификат изменен (в связи с истечением срока действия) используется имя субъекта.</span><span class="sxs-lookup"><span data-stu-id="0c2d4-131">The subject name is used here in case the certificate is changed (due to an expiration date).</span></span> <span data-ttu-id="0c2d4-132">Использование имени субъекта позволяет инфраструктуре снова найти сертификат.</span><span class="sxs-lookup"><span data-stu-id="0c2d4-132">Using the subject name enables the infrastructure to find the certificate again.</span></span>

### <a name="to-specify-the-client-credential-value-on-the-client-in-configuration"></a><span data-ttu-id="0c2d4-133">Указание значения учетных данных клиента в конфигурации клиента</span><span class="sxs-lookup"><span data-stu-id="0c2d4-133">To specify the client credential value on the client in configuration</span></span>

1. <span data-ttu-id="0c2d4-134">Добавьте [\<behavior>](../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) элемент в [\<behaviors>](../configure-apps/file-schema/wcf/behaviors.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="0c2d4-134">Add a [\<behavior>](../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element to the [\<behaviors>](../configure-apps/file-schema/wcf/behaviors.md) element.</span></span>

2. <span data-ttu-id="0c2d4-135">Добавьте [\<clientCredentials>](../configure-apps/file-schema/wcf/clientcredentials.md) элемент в [\<behaviors>](../configure-apps/file-schema/wcf/behaviors.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="0c2d4-135">Add a [\<clientCredentials>](../configure-apps/file-schema/wcf/clientcredentials.md) element to the [\<behaviors>](../configure-apps/file-schema/wcf/behaviors.md) element.</span></span> <span data-ttu-id="0c2d4-136">Необходимо присвоить обязательному атрибуту `name` соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="0c2d4-136">Be sure to set the required `name` attribute to an appropriate value.</span></span>

3. <span data-ttu-id="0c2d4-137">Добавьте [\<clientCertificate>](../configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md) элемент в [\<clientCredentials>](../configure-apps/file-schema/wcf/clientcredentials.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="0c2d4-137">Add a [\<clientCertificate>](../configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md) element to the [\<clientCredentials>](../configure-apps/file-schema/wcf/clientcredentials.md) element.</span></span>

4. <span data-ttu-id="0c2d4-138">Присвойте соответствующие значения следующим атрибутам: `storeLocation`, `storeName`, `x509FindType` и `findValue`, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="0c2d4-138">Set the following attributes to appropriate values: `storeLocation`, `storeName`, `x509FindType`, and `findValue`, as shown in the following code.</span></span> <span data-ttu-id="0c2d4-139">Дополнительные сведения см. в разделе [Работа с сертификатами](./feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="0c2d4-139">For more information about certificates, see [Working with Certificates](./feature-details/working-with-certificates.md).</span></span>

    ```xml
    <behaviors>
       <endpointBehaviors>
          <behavior name="endpointCredentialBehavior">
            <clientCredentials>
              <clientCertificate findValue="Contoso.com"
                                 storeLocation="LocalMachine"
                                 storeName="TrustedPeople"
                                 x509FindType="FindBySubjectName" />
            </clientCredentials>
          </behavior>
       </endpointBehaviors>
    </behaviors>
    ```

5. <span data-ttu-id="0c2d4-140">При настройке клиента укажите поведение, задав атрибут `behaviorConfiguration` элемента `<endpoint>`, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="0c2d4-140">When configuring the client, specify the behavior by setting the `behaviorConfiguration` attribute of the `<endpoint>` element, as shown in the following code.</span></span> <span data-ttu-id="0c2d4-141">Элемент конечной точки является дочерним по отношению к [\<client>](../configure-apps/file-schema/wcf/client.md) элементу.</span><span class="sxs-lookup"><span data-stu-id="0c2d4-141">The endpoint element is a child of the [\<client>](../configure-apps/file-schema/wcf/client.md) element.</span></span> <span data-ttu-id="0c2d4-142">Также укажите имя конфигурации привязки, установив привязку для клиента в атрибуте `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="0c2d4-142">Also, specify the name of the binding configuration by setting the `bindingConfiguration` attribute to the binding for the client.</span></span> <span data-ttu-id="0c2d4-143">Если используется созданный файл конфигурации, имя привязки создается автоматически.</span><span class="sxs-lookup"><span data-stu-id="0c2d4-143">If you are using a generated configuration file, the binding's name is automatically generated.</span></span> <span data-ttu-id="0c2d4-144">В этом примере используется имя `"tcpBindingWithCredential"`.</span><span class="sxs-lookup"><span data-stu-id="0c2d4-144">In this example, the name is `"tcpBindingWithCredential"`.</span></span>

    ```xml
    <client>
      <endpoint name =""
                address="net.tcp://contoso.com:8036/aloha"
                binding="netTcpBinding"
                bindingConfiguration="tcpBindingWithCredential"
                behaviorConfiguration="endpointCredentialBehavior" />
    </client>
    ```

## <a name="see-also"></a><span data-ttu-id="0c2d4-145">См. также</span><span class="sxs-lookup"><span data-stu-id="0c2d4-145">See also</span></span>

- <xref:System.ServiceModel.NetTcpBinding>
- <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>
- <xref:System.ServiceModel.ClientBase%601>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>
- [<span data-ttu-id="0c2d4-146">Программирование безопасности WCF</span><span class="sxs-lookup"><span data-stu-id="0c2d4-146">Programming WCF Security</span></span>](./feature-details/programming-wcf-security.md)
- [<span data-ttu-id="0c2d4-147">Выбор типа учетных данных</span><span class="sxs-lookup"><span data-stu-id="0c2d4-147">Selecting a Credential Type</span></span>](./feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="0c2d4-148">Служебное средство ServiceModel Metadata Utility Tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="0c2d4-148">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="0c2d4-149">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="0c2d4-149">Working with Certificates</span></span>](./feature-details/working-with-certificates.md)
- [<span data-ttu-id="0c2d4-150">Практическое руководство. Создание клиента</span><span class="sxs-lookup"><span data-stu-id="0c2d4-150">How to: Create a Client</span></span>](how-to-create-a-wcf-client.md)
- [\<netTcpBinding>](../configure-apps/file-schema/wcf/nettcpbinding.md)
- [\<security>](../configure-apps/file-schema/wcf/security-of-nettcpbinding.md)
- [\<message>](../configure-apps/file-schema/wcf/message-element-of-nettcpbinding.md)
- [\<behavior>](../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)
- [\<behaviors>](../configure-apps/file-schema/wcf/behaviors.md)
- [\<clientCertificate>](../configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)
- [\<clientCredentials>](../configure-apps/file-schema/wcf/clientcredentials.md)
