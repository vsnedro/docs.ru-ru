---
title: <message> из <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9def5a35-475d-40d6-b716-ccdbd93863c7
ms.openlocfilehash: b37d6b1bd8f5372c230acbc2ada299415b2e40b3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204857"
---
# <a name="message-of-nethttpbinding"></a><span data-ttu-id="6757b-102">\<message> из \<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="6757b-102">\<message> of \<netHttpBinding></span></span>

<span data-ttu-id="6757b-103">Определяет параметры безопасности на уровне сообщений для [\<netHttpBinding>](nethttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="6757b-103">Defines the settings for message-level security of the [\<netHttpBinding>](nethttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  
  
## <a name="syntax"></a><span data-ttu-id="6757b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6757b-104">Syntax</span></span>  
  
```xml  
<message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
         clientCredentialType="UserName/Certificate" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6757b-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6757b-105">Attributes and Elements</span></span>  

 <span data-ttu-id="6757b-106">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6757b-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6757b-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6757b-107">Attributes</span></span>  
  
|<span data-ttu-id="6757b-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6757b-108">Attribute</span></span>|<span data-ttu-id="6757b-109">Описание</span><span class="sxs-lookup"><span data-stu-id="6757b-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6757b-110">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="6757b-110">algorithmSuite</span></span>|<span data-ttu-id="6757b-111">Задает алгоритмы шифрования сообщений и ключей.</span><span class="sxs-lookup"><span data-stu-id="6757b-111">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="6757b-112">Этот атрибут имеет тип <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, который задает алгоритмы и размеры ключей.</span><span class="sxs-lookup"><span data-stu-id="6757b-112">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, which specifies the algorithms and the key sizes.</span></span> <span data-ttu-id="6757b-113">Эти алгоритмы соответствуют алгоритмам, заданным в спецификации языка политики безопасности (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="6757b-113">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="6757b-114">Значение по умолчанию — `Basic256`.</span><span class="sxs-lookup"><span data-stu-id="6757b-114">The default value is `Basic256`.</span></span>|  
|<span data-ttu-id="6757b-115">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="6757b-115">clientCredentialType</span></span>|<span data-ttu-id="6757b-116">Задает тип учетных данных, используемых при проверке подлинности клиента с помощью безопасности на уровне сообщений.</span><span class="sxs-lookup"><span data-stu-id="6757b-116">Specifies the type of credential to be used when performing client authentication using message-based security.</span></span> <span data-ttu-id="6757b-117">Значение по умолчанию — `UserName`.</span><span class="sxs-lookup"><span data-stu-id="6757b-117">The default is `UserName`.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="6757b-118">Атрибут clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="6757b-118">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="6757b-119">Значение</span><span class="sxs-lookup"><span data-stu-id="6757b-119">Value</span></span>|<span data-ttu-id="6757b-120">Описание</span><span class="sxs-lookup"><span data-stu-id="6757b-120">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6757b-121">UserName</span><span class="sxs-lookup"><span data-stu-id="6757b-121">UserName</span></span>|<span data-ttu-id="6757b-122">— Требует, чтобы клиент прошел проверку подлинности на сервере с учетными данными пользователя.</span><span class="sxs-lookup"><span data-stu-id="6757b-122">-   Requires the client be authenticated to the server with a UserName credential.</span></span> <span data-ttu-id="6757b-123">Эти учетные данные необходимо указать с помощью `clientCredentials` элемента> <.</span><span class="sxs-lookup"><span data-stu-id="6757b-123">This credential needs to be specified using the <`clientCredentials`> element.</span></span><br /><span data-ttu-id="6757b-124">— WCF не поддерживает отправку дайджеста пароля или получение ключей с помощью паролей и использование таких ключей для обеспечения безопасности сообщений.</span><span class="sxs-lookup"><span data-stu-id="6757b-124">-   WCF does not support sending a password digest or deriving keys using passwords and using such keys for message security.</span></span> <span data-ttu-id="6757b-125">Поэтому WCF обеспечивает защиту транспорта при использовании учетных данных имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="6757b-125">Therefore, WCF enforces that the transport be secured when using UserName credentials.</span></span> <span data-ttu-id="6757b-126">Для `basicHttpBinding` это требует настройки канала SSL.</span><span class="sxs-lookup"><span data-stu-id="6757b-126">For the `basicHttpBinding`, this requires setting up an SSL channel.</span></span>|  
|<span data-ttu-id="6757b-127">Сертификат</span><span class="sxs-lookup"><span data-stu-id="6757b-127">Certificate</span></span>|<span data-ttu-id="6757b-128">Требует, чтобы при подключении к серверу проверка подлинности клиента проводилась с помощью сертификата.</span><span class="sxs-lookup"><span data-stu-id="6757b-128">Requires that the client be authenticated to the server using a certificate.</span></span> <span data-ttu-id="6757b-129">Учетные данные клиента в этом случае необходимо указать с помощью <`clientCredentials`> и <`clientCertificate`>.</span><span class="sxs-lookup"><span data-stu-id="6757b-129">The client credential in this case needs to be specified using <`clientCredentials`> and the <`clientCertificate`>.</span></span> <span data-ttu-id="6757b-130">Кроме того, при использовании режима безопасности сообщений клиенту должен быть предоставлен сертификат службы.</span><span class="sxs-lookup"><span data-stu-id="6757b-130">In addition, when using message security mode, the client needs to be provisioned with the service certificate.</span></span> <span data-ttu-id="6757b-131">Учетные данные службы в этом случае необходимо указать с помощью <xref:System.ServiceModel.Description.ClientCredentials> класса или `ClientCredentials` элемента Behavior, указав сертификат службы с помощью \<serviceCertificate> элемента serviceCredentials.</span><span class="sxs-lookup"><span data-stu-id="6757b-131">The service credential in this case needs to be specified using <xref:System.ServiceModel.Description.ClientCredentials> class or `ClientCredentials` behavior element and specifying the service certificate using the \<serviceCertificate> element of serviceCredentials.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6757b-132">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6757b-132">Child Elements</span></span>  

 <span data-ttu-id="6757b-133">Нет</span><span class="sxs-lookup"><span data-stu-id="6757b-133">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6757b-134">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6757b-134">Parent Elements</span></span>  
  
|<span data-ttu-id="6757b-135">Элемент</span><span class="sxs-lookup"><span data-stu-id="6757b-135">Element</span></span>|<span data-ttu-id="6757b-136">Описание</span><span class="sxs-lookup"><span data-stu-id="6757b-136">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6757b-137"><`security`> элемент <`netHttpBinding`></span><span class="sxs-lookup"><span data-stu-id="6757b-137"><`security`> element of <`netHttpBinding`></span></span>|<span data-ttu-id="6757b-138">Определяет возможности безопасности для `netHttpBinding` элемента> <.</span><span class="sxs-lookup"><span data-stu-id="6757b-138">Defines the security capabilities for the <`netHttpBinding`> Element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6757b-139">Пример</span><span class="sxs-lookup"><span data-stu-id="6757b-139">Example</span></span>  

 <span data-ttu-id="6757b-140">В образце демонстрируется реализация приложения, которое использует basicHttpBinding и безопасность сообщений.</span><span class="sxs-lookup"><span data-stu-id="6757b-140">This sample demonstrates how to implement an application that uses the basicHttpBinding and message security.</span></span> <span data-ttu-id="6757b-141">В следующем примере конфигурации для службы в определении конечной точки задаются привязка basicHttpBinding и ссылки на конфигурацию привязки с именем `Binding1`.</span><span class="sxs-lookup"><span data-stu-id="6757b-141">In the following configuration example for a service, the endpoint definition specifies the basicHttpBinding and references a binding configuration named `Binding1`.</span></span> <span data-ttu-id="6757b-142">Сертификат, используемый службой для своей проверки подлинности при подключении к клиенту, установлен в разделе `behaviors` файла конфигурации в элементе `serviceCredentials`.</span><span class="sxs-lookup"><span data-stu-id="6757b-142">The certificate that the service uses to authenticate itself to the client is set in the `behaviors` section of the configuration file under the `serviceCredentials` element.</span></span> <span data-ttu-id="6757b-143">Режим проверки, применяемый к сертификату, который клиент использует для своей проверки подлинности при подключении к службе, также установлен в разделе `behaviors` в элементе `clientCertificate`.</span><span class="sxs-lookup"><span data-stu-id="6757b-143">The validation mode that applies to the certificate that the client uses to authenticate itself to the service is also set in the `behaviors` section under the `clientCertificate` element.</span></span>  
  
 <span data-ttu-id="6757b-144">Та же привязка и данные безопасности задаются в файле конфигурации клиента.</span><span class="sxs-lookup"><span data-stu-id="6757b-144">The same binding and security details are specified in the client configuration file.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <host>
        <baseAddresses>
          <add baseAddress="http://localhost:8000/ServiceModelSamples/service" />
        </baseAddresses>
      </host>
      <!-- this endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service  -->
      <endpoint address=""
                binding="basicHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
      <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->
      <endpoint address="mex"
                binding="mexHttpBinding"
                contract="IMetadataExchange" />
    </service>
  </services>
  <bindings>
    <basicHttpBinding>
      <!-- This configuration defines the SecurityMode as Message and
           the clientCredentialType as Certificate. -->
      <binding name="Binding1" >
        <security mode = "Message">
          <message clientCredentialType="Certificate" />
        </security>
      </binding>
    </basicHttpBinding>
  </bindings>
  <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
  <behaviors>
    <serviceBehaviors>
      <behavior name="CalculatorServiceBehavior">
        <serviceMetadata httpGetEnabled="True" />
        <serviceDebug includeExceptionDetailInFaults="False" />
        <!-- The serviceCredentials behavior allows one to define a service certificate.
             A service certificate is used by a client to authenticate the service and provide message protection.
             This configuration references the "localhost" certificate installed during the setup instructions. -->
        <serviceCredentials>
          <serviceCertificate findValue="localhost"
                              storeLocation="LocalMachine"
                              storeName="My"
                              x509FindType="FindBySubjectName" />
          <clientCertificate>
            <!-- Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate
                 is in the user's Trusted People store, then it will be trusted without performing a
                 validation of the certificate's issuer chain. This setting is used here for convenience so that the
                 sample can be run without having to have certificates issued by a certification authority (CA).
                 This setting is less secure than the default, ChainTrust. The security implications of this
                 setting should be carefully considered before using PeerOrChainTrust in production code. -->
            <authentication certificateValidationMode="PeerOrChainTrust" />
          </clientCertificate>
        </serviceCredentials>
      </behavior>
    </serviceBehaviors>
  </behaviors>
</system.serviceModel>
```  
  
## <a name="see-also"></a><span data-ttu-id="6757b-145">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6757b-145">See also</span></span>

- [<span data-ttu-id="6757b-146">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="6757b-146">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="6757b-147">Привязки</span><span class="sxs-lookup"><span data-stu-id="6757b-147">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="6757b-148">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="6757b-148">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="6757b-149">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="6757b-149">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
