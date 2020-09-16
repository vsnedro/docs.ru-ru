---
title: Безопасность сообщений с использованием взаимных сертификатов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 99d7a528-7ae4-4d39-a0f9-3066ea237de0
ms.openlocfilehash: bbe99b133e7edda191d17e9fe8a1dea89d3f0eb7
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556529"
---
# <a name="message-security-with-mutual-certificates"></a><span data-ttu-id="d8c1c-102">Безопасность сообщений с использованием взаимных сертификатов</span><span class="sxs-lookup"><span data-stu-id="d8c1c-102">Message Security with Mutual Certificates</span></span>
<span data-ttu-id="d8c1c-103">В следующем сценарии показана служба Windows Communication Foundation (WCF) и клиент защищены с помощью режима безопасности сообщений.</span><span class="sxs-lookup"><span data-stu-id="d8c1c-103">The following scenario shows a Windows Communication Foundation (WCF) service and client secured using message security mode.</span></span> <span data-ttu-id="d8c1c-104">Проверка подлинности клиента и службы выполняется с помощью сертификатов.</span><span class="sxs-lookup"><span data-stu-id="d8c1c-104">The client and the service are authenticated with certificates.</span></span>  
  
 <span data-ttu-id="d8c1c-105">Данный сценарий поддерживает возможность взаимодействия, поскольку в нем используется WS-Security с профилем маркера сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="d8c1c-105">This scenario is interoperable because it uses WS-Security with the X.509 certificate token profile.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d8c1c-106">Данный сценарий не выполняет согласование сертификата службы.</span><span class="sxs-lookup"><span data-stu-id="d8c1c-106">This scenario does not perform negotiation of the service certificate.</span></span> <span data-ttu-id="d8c1c-107">Сертификат службы должен быть предоставлен клиенту перед началом любой связи.</span><span class="sxs-lookup"><span data-stu-id="d8c1c-107">The service certificate must be provided to the client in advance of any communication.</span></span> <span data-ttu-id="d8c1c-108">Сертификат сервера может быть распределен приложением или предоставлен во внеполосной связи.</span><span class="sxs-lookup"><span data-stu-id="d8c1c-108">The server certificate can be distributed with the application or provided in an out-of-band communication.</span></span>  
  
 <span data-ttu-id="d8c1c-109">![Безопасность сообщений с помощью взаимных сертификатов](media/f4157312-b17c-416c-a5ee-fa7b54db211b.gif "f4157312-b17c-416c-a5ee-fa7b54db211b")</span><span class="sxs-lookup"><span data-stu-id="d8c1c-109">![Message security with mutual certificates](media/f4157312-b17c-416c-a5ee-fa7b54db211b.gif "f4157312-b17c-416c-a5ee-fa7b54db211b")</span></span>  
  
|<span data-ttu-id="d8c1c-110">Характеристика</span><span class="sxs-lookup"><span data-stu-id="d8c1c-110">Characteristic</span></span>|<span data-ttu-id="d8c1c-111">Описание</span><span class="sxs-lookup"><span data-stu-id="d8c1c-111">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="d8c1c-112">Режим безопасности</span><span class="sxs-lookup"><span data-stu-id="d8c1c-112">Security Mode</span></span>|<span data-ttu-id="d8c1c-113">Сообщение</span><span class="sxs-lookup"><span data-stu-id="d8c1c-113">Message</span></span>|  
|<span data-ttu-id="d8c1c-114">Совместимость</span><span class="sxs-lookup"><span data-stu-id="d8c1c-114">Interoperability</span></span>|<span data-ttu-id="d8c1c-115">Да, с клиентами и службами, совместимыми с профилем маркера WS-Security и сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="d8c1c-115">Yes, with WS-Security and X.509 certificate token profile compatible clients and services.</span></span>|  
|<span data-ttu-id="d8c1c-116">Аутентификация</span><span class="sxs-lookup"><span data-stu-id="d8c1c-116">Authentication</span></span>|<span data-ttu-id="d8c1c-117">Взаимная проверка подлинности сервера и клиента.</span><span class="sxs-lookup"><span data-stu-id="d8c1c-117">Mutual authentication of the server and client.</span></span>|  
|<span data-ttu-id="d8c1c-118">Целостность</span><span class="sxs-lookup"><span data-stu-id="d8c1c-118">Integrity</span></span>|<span data-ttu-id="d8c1c-119">Да</span><span class="sxs-lookup"><span data-stu-id="d8c1c-119">Yes</span></span>|  
|<span data-ttu-id="d8c1c-120">Конфиденциальность</span><span class="sxs-lookup"><span data-stu-id="d8c1c-120">Confidentiality</span></span>|<span data-ttu-id="d8c1c-121">Да</span><span class="sxs-lookup"><span data-stu-id="d8c1c-121">Yes</span></span>|  
|<span data-ttu-id="d8c1c-122">Транспорт</span><span class="sxs-lookup"><span data-stu-id="d8c1c-122">Transport</span></span>|<span data-ttu-id="d8c1c-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="d8c1c-123">HTTP</span></span>|  
|<span data-ttu-id="d8c1c-124">Привязка</span><span class="sxs-lookup"><span data-stu-id="d8c1c-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="d8c1c-125">Служба</span><span class="sxs-lookup"><span data-stu-id="d8c1c-125">Service</span></span>  
 <span data-ttu-id="d8c1c-126">Предполагается, что представленные ниже код и конфигурация выполняются независимо.</span><span class="sxs-lookup"><span data-stu-id="d8c1c-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="d8c1c-127">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="d8c1c-127">Do one of the following:</span></span>  
  
- <span data-ttu-id="d8c1c-128">Создайте автономную службу, используя код без конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d8c1c-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="d8c1c-129">Создайте службу, используя предоставленную конфигурацию, но не определяйте конечные точки.</span><span class="sxs-lookup"><span data-stu-id="d8c1c-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="d8c1c-130">Код</span><span class="sxs-lookup"><span data-stu-id="d8c1c-130">Code</span></span>  
 <span data-ttu-id="d8c1c-131">В следующем коде показано, как создать конечную точку службы, которая использует безопасность сообщений.</span><span class="sxs-lookup"><span data-stu-id="d8c1c-131">The following code shows creates a service endpoint that uses message security.</span></span> <span data-ttu-id="d8c1c-132">Служба требует прохождения проверки подлинности сертификата.</span><span class="sxs-lookup"><span data-stu-id="d8c1c-132">The service requires a certificate to authenticate itself.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#13)]
 [!code-vb[C_SecurityScenarios#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#13)]  
  
### <a name="configuration"></a><span data-ttu-id="d8c1c-133">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="d8c1c-133">Configuration</span></span>  
 <span data-ttu-id="d8c1c-134">Вместо кода для создания той же службы можно использовать следующую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="d8c1c-134">The following configuration can be used instead of the code to create the same service.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="serviceCredentialBehavior">  
          <serviceCredentials>  
            <serviceCertificate findValue="Contoso.com"
                                storeLocation="LocalMachine"  
                                storeName="My"
                                x509FindType="FindBySubjectName" />  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service behaviorConfiguration="serviceCredentialBehavior"
               name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"
                  binding="wsHttpBinding"  
                  bindingConfiguration="InteropCertificateBinding"  
                  name="WSHttpBinding_ICalculator"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="InteropCertificateBinding">  
          <security mode="Message">  
            <message clientCredentialType="Certificate"  
                     negotiateServiceCredential="false"  
                     establishSecurityContext="false" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="d8c1c-135">Клиент</span><span class="sxs-lookup"><span data-stu-id="d8c1c-135">Client</span></span>  
 <span data-ttu-id="d8c1c-136">Предполагается, что представленные ниже код и конфигурация выполняются независимо.</span><span class="sxs-lookup"><span data-stu-id="d8c1c-136">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="d8c1c-137">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="d8c1c-137">Do one of the following:</span></span>  
  
- <span data-ttu-id="d8c1c-138">Создайте автономный клиент, используя код (и код клиента).</span><span class="sxs-lookup"><span data-stu-id="d8c1c-138">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="d8c1c-139">Создайте клиент, который не определяет никаких адресов конечных точек.</span><span class="sxs-lookup"><span data-stu-id="d8c1c-139">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="d8c1c-140">Вместо этого используйте конструктор клиента, который принимает в качестве аргумента имя конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d8c1c-140">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="d8c1c-141">Пример:</span><span class="sxs-lookup"><span data-stu-id="d8c1c-141">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="d8c1c-142">Код</span><span class="sxs-lookup"><span data-stu-id="d8c1c-142">Code</span></span>  
 <span data-ttu-id="d8c1c-143">Следующий код служит для создания клиента.</span><span class="sxs-lookup"><span data-stu-id="d8c1c-143">The following code creates the client.</span></span> <span data-ttu-id="d8c1c-144">Режим безопасности установлен в Message, и типу учетных данных клиента присвоено значение Certificate.</span><span class="sxs-lookup"><span data-stu-id="d8c1c-144">The security mode is set to Message, and the client credential type is set to Certificate.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#20](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#20)]
 [!code-vb[C_SecurityScenarios#20](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#20)]  
  
### <a name="configuration"></a><span data-ttu-id="d8c1c-145">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="d8c1c-145">Configuration</span></span>  
 <span data-ttu-id="d8c1c-146">Следующий код служит для настройки клиента.</span><span class="sxs-lookup"><span data-stu-id="d8c1c-146">The following configures the client.</span></span> <span data-ttu-id="d8c1c-147">Сертификат клиента должен быть указан с помощью [\<clientCertificate>](../../configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md) .</span><span class="sxs-lookup"><span data-stu-id="d8c1c-147">A client certificate must be specified using the [\<clientCertificate>](../../configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md).</span></span> <span data-ttu-id="d8c1c-148">Кроме того, сертификат службы указывается с помощью [\<defaultCertificate>](../../configure-apps/file-schema/wcf/defaultcertificate-element.md) .</span><span class="sxs-lookup"><span data-stu-id="d8c1c-148">Also, the service certificate is specified using the [\<defaultCertificate>](../../configure-apps/file-schema/wcf/defaultcertificate-element.md).</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="ClientCredentialsBehavior">  
          <clientCredentials>  
            <clientCertificate findValue="Cohowinery.com"
                 storeLocation="CurrentUser"  
                 storeName="My"  
                 x509FindType="FindBySubjectName" />  
            <serviceCertificate>  
              <defaultCertificate findValue="Contoso.com"
                                  storeLocation="CurrentUser"  
                                  storeName="TrustedPeople"  
                                  x509FindType="FindBySubjectName" />  
            </serviceCertificate>  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="Certificate"
                     negotiateServiceCredential="false"  
                     establishSecurityContext="false" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://machineName/Calculator"
                behaviorConfiguration="ClientCredentialsBehavior"  
                binding="wsHttpBinding"
                bindingConfiguration="WSHttpBinding_ICalculator"  
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator">  
        <identity>  
          <certificate encodedValue="Encoded_Value_Not_Shown" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d8c1c-149">См. также</span><span class="sxs-lookup"><span data-stu-id="d8c1c-149">See also</span></span>

- [<span data-ttu-id="d8c1c-150">Обзор безопасности</span><span class="sxs-lookup"><span data-stu-id="d8c1c-150">Security Overview</span></span>](security-overview.md)
- <span data-ttu-id="d8c1c-151">[Модель безопасности для Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="d8c1c-151">[Security Model for Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
- <span data-ttu-id="d8c1c-152">[Как создавать и устанавливать временные сертификаты в WCF для обеспечения безопасности транспорта во время разработки](/previous-versions/msp-n-p/ff648498(v=pandp.10))</span><span class="sxs-lookup"><span data-stu-id="d8c1c-152">[How to: Create and Install Temporary Certificates in WCF for Transport Security During Development](/previous-versions/msp-n-p/ff648498(v=pandp.10))</span></span>
