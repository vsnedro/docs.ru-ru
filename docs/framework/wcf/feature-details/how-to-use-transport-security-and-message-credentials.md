---
title: Практическое руководство. Использование средств обеспечения безопасности транспорта и учетных данных сообщения
description: Узнайте, как реализовать защиту транспорта с помощью учетных данных сообщений, что обеспечивает лучшее из режимов транспорта и безопасности сообщений в WCF.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TransportWithMessageCredentials
ms.assetid: 6cc35346-c37a-4859-b82b-946c0ba6e68f
ms.openlocfilehash: f632a4389eafc155cedcae94707c9418b6696f2c
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246653"
---
# <a name="how-to-use-transport-security-and-message-credentials"></a><span data-ttu-id="1c50a-103">Практическое руководство. Использование средств обеспечения безопасности транспорта и учетных данных сообщения</span><span class="sxs-lookup"><span data-stu-id="1c50a-103">How to: Use Transport Security and Message Credentials</span></span>
<span data-ttu-id="1c50a-104">Защита службы с помощью транспорта и учетных данных сообщений использует оптимальные режимы безопасности транспорта и сообщений в Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="1c50a-104">Securing a service with both transport and message credentials uses the best of both Transport and Message security modes in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="1c50a-105">В общих словах, TLS обеспечивает целостность и конфиденциальность, а MLS предоставляет различные учетные данные, которые невозможно использовать в строгих механизмах обеспечения безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="1c50a-105">In sum, transport-layer security provides integrity and confidentiality, while message-layer security provides a variety of credentials that are not possible with strict transport security mechanisms.</span></span> <span data-ttu-id="1c50a-106">В этом разделе приведены основные этапы реализации транспорта с учетными данными сообщения с помощью привязок <xref:System.ServiceModel.WSHttpBinding> и <xref:System.ServiceModel.NetTcpBinding>.</span><span class="sxs-lookup"><span data-stu-id="1c50a-106">This topic shows the basic steps for implementing transport with message credentials using the <xref:System.ServiceModel.WSHttpBinding> and <xref:System.ServiceModel.NetTcpBinding> bindings.</span></span> <span data-ttu-id="1c50a-107">Дополнительные сведения о настройке режима безопасности см. в разделе [инструкции. Установка режима безопасности](../how-to-set-the-security-mode.md).</span><span class="sxs-lookup"><span data-stu-id="1c50a-107">For more information about setting the security mode, see [How to: Set the Security Mode](../how-to-set-the-security-mode.md).</span></span>  
  
 <span data-ttu-id="1c50a-108">При задании режима безопасности`TransportWithMessageCredential` транспорт определяет фактический механизм, обеспечивающий безопасность на транспортном уровне.</span><span class="sxs-lookup"><span data-stu-id="1c50a-108">When setting the security mode to `TransportWithMessageCredential`, the transport determines the actual mechanism that provides the transport-level security.</span></span> <span data-ttu-id="1c50a-109">В случае HTTP таким механизмом является SSL по HTTP (HTTPS); в случае TCP таким механизмом является SSL по TCP или Windows.</span><span class="sxs-lookup"><span data-stu-id="1c50a-109">For HTTP, the mechanism is Secure Sockets Layer (SSL) over HTTP (HTTPS); for TCP, it is SSL over TCP or Windows.</span></span>  
  
 <span data-ttu-id="1c50a-110">Если транспортом является HTTP (используется <xref:System.ServiceModel.WSHttpBinding>), SSL по HTTP обеспечивает безопасность на транспортном уровне.</span><span class="sxs-lookup"><span data-stu-id="1c50a-110">If the transport is HTTP (using the <xref:System.ServiceModel.WSHttpBinding>), SSL over HTTP provides the transport-level security.</span></span> <span data-ttu-id="1c50a-111">В этом случае необходимо задать для компьютера, на котором размещена служба, SSL-сертификат, привязанный к порту, как показано далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="1c50a-111">In that case, you must configure the computer hosting the service with an SSL certificate bound to a port, as shown later in this topic.</span></span>  
  
 <span data-ttu-id="1c50a-112">Если транспортом является TCP (используется <xref:System.ServiceModel.NetTcpBinding>), по умолчанию безопасность на транспортном уровне обеспечивается механизмом безопасности Windows или SSL по TCP.</span><span class="sxs-lookup"><span data-stu-id="1c50a-112">If the transport is TCP (using the <xref:System.ServiceModel.NetTcpBinding>), by default the transport-level security provided is Windows security, or SSL over TCP.</span></span> <span data-ttu-id="1c50a-113">При использовании SSL по TCP необходимо указать сертификат с помощью метода <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>, как показано далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="1c50a-113">When using SSL over TCP, you must specify the certificate using the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> method, as shown later in this topic.</span></span>  
  
### <a name="to-use-the-wshttpbinding-with-a-certificate-for-transport-security-in-code"></a><span data-ttu-id="1c50a-114">Использование привязки WSHttpBinding с сертификатом для обеспечения безопасности транспорта (в коде)</span><span class="sxs-lookup"><span data-stu-id="1c50a-114">To use the WSHttpBinding with a certificate for transport security (in code)</span></span>  
  
1. <span data-ttu-id="1c50a-115">Воспользуйтесь средством HttpCfg.exe для привязки SSL-сертификата к порту на компьютере.</span><span class="sxs-lookup"><span data-stu-id="1c50a-115">Use the HttpCfg.exe tool to bind an SSL certificate to a port on the machine.</span></span> <span data-ttu-id="1c50a-116">Дополнительные сведения см. [в разделе как настроить порт с помощью SSL-сертификата](how-to-configure-a-port-with-an-ssl-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="1c50a-116">For more information, see [How to: Configure a Port with an SSL Certificate](how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>  
  
2. <span data-ttu-id="1c50a-117">Создайте экземпляр класса <xref:System.ServiceModel.WSHttpBinding> и задайте для свойства <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> значение <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span><span class="sxs-lookup"><span data-stu-id="1c50a-117">Create an instance of the <xref:System.ServiceModel.WSHttpBinding> class and set the <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> property to <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>  
  
3. <span data-ttu-id="1c50a-118">Присвойте свойству <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="1c50a-118">Set the <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> property to an appropriate value.</span></span> <span data-ttu-id="1c50a-119">(Дополнительные сведения см. [в разделе Выбор типа учетных данных](selecting-a-credential-type.md).) В следующем коде используется <xref:System.ServiceModel.MessageCredentialType.Certificate> значение.</span><span class="sxs-lookup"><span data-stu-id="1c50a-119">(For more information, see [Selecting a Credential Type](selecting-a-credential-type.md).) The following code uses the <xref:System.ServiceModel.MessageCredentialType.Certificate> value.</span></span>  
  
4. <span data-ttu-id="1c50a-120">Создайте экземпляр класса <xref:System.Uri> с соответствующим базовым адресом.</span><span class="sxs-lookup"><span data-stu-id="1c50a-120">Create an instance of the <xref:System.Uri> class with an appropriate base address.</span></span> <span data-ttu-id="1c50a-121">Обратите внимание, что адрес должен использовать схему "HTTPS" и содержать фактическое имя компьютера и номер порта, к которому привязан SSL-сертификат.</span><span class="sxs-lookup"><span data-stu-id="1c50a-121">Note that the address must use the "HTTPS" scheme and must contain the actual name of the machine and the port number that the SSL certificate is bound to.</span></span> <span data-ttu-id="1c50a-122">(Кроме того, базовый адрес можно задать в конфигурации.)</span><span class="sxs-lookup"><span data-stu-id="1c50a-122">(Alternatively, you can set the base address in configuration.)</span></span>  
  
5. <span data-ttu-id="1c50a-123">Добавьте конечную точку службы с помощью метода <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>.</span><span class="sxs-lookup"><span data-stu-id="1c50a-123">Add a service endpoint using the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method.</span></span>  
  
6. <span data-ttu-id="1c50a-124">Создайте экземпляр класса <xref:System.ServiceModel.ServiceHost> и вызовите метод <xref:System.ServiceModel.ICommunicationObject.Open%2A>, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="1c50a-124">Create the instance of the <xref:System.ServiceModel.ServiceHost> and call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#7)]
     [!code-vb[c_SettingSecurityMode#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#7)]  
  
### <a name="to-use-the-nettcpbinding-with-a-certificate-for-transport-security-in-code"></a><span data-ttu-id="1c50a-125">Использование привязки NetTcpBinding с сертификатом для обеспечения безопасности транспорта (в коде)</span><span class="sxs-lookup"><span data-stu-id="1c50a-125">To use the NetTcpBinding with a certificate for transport security (in code)</span></span>  
  
1. <span data-ttu-id="1c50a-126">Создайте экземпляр класса <xref:System.ServiceModel.NetTcpBinding> и задайте для свойства <xref:System.ServiceModel.NetTcpSecurity.Mode%2A> значение <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span><span class="sxs-lookup"><span data-stu-id="1c50a-126">Create an instance of the <xref:System.ServiceModel.NetTcpBinding> class and set the <xref:System.ServiceModel.NetTcpSecurity.Mode%2A> property to <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>  
  
2. <span data-ttu-id="1c50a-127">Присвойте свойству <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A> соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="1c50a-127">Set the <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A> to an appropriate value.</span></span> <span data-ttu-id="1c50a-128">В следующем коде используется значение <xref:System.ServiceModel.MessageCredentialType.Certificate>.</span><span class="sxs-lookup"><span data-stu-id="1c50a-128">The following code uses the <xref:System.ServiceModel.MessageCredentialType.Certificate> value.</span></span>  
  
3. <span data-ttu-id="1c50a-129">Создайте экземпляр класса <xref:System.Uri> с соответствующим базовым адресом.</span><span class="sxs-lookup"><span data-stu-id="1c50a-129">Create an instance of the <xref:System.Uri> class with an appropriate base address.</span></span> <span data-ttu-id="1c50a-130">Обратите внимание, что адрес должен использовать схему "net.tcp".</span><span class="sxs-lookup"><span data-stu-id="1c50a-130">Note that the address must use the "net.tcp" scheme.</span></span> <span data-ttu-id="1c50a-131">(Кроме того, базовый адрес можно задать в конфигурации.)</span><span class="sxs-lookup"><span data-stu-id="1c50a-131">(Alternatively, you can set the base address in configuration.)</span></span>  
  
4. <span data-ttu-id="1c50a-132">Создайте экземпляр класса <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="1c50a-132">Create the instance of the <xref:System.ServiceModel.ServiceHost> class.</span></span>  
  
5. <span data-ttu-id="1c50a-133">Воспользуйтесь методом <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> класса <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>, чтобы явно задать сертификат X.509 для службы.</span><span class="sxs-lookup"><span data-stu-id="1c50a-133">Use the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> method of the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> class to explicitly set the X.509 certificate for the service.</span></span>  
  
6. <span data-ttu-id="1c50a-134">Добавьте конечную точку службы с помощью метода <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>.</span><span class="sxs-lookup"><span data-stu-id="1c50a-134">Add a service endpoint using the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method.</span></span>  
  
7. <span data-ttu-id="1c50a-135">Вызовите метод <xref:System.ServiceModel.ICommunicationObject.Open%2A>, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="1c50a-135">Call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#8)]
     [!code-vb[c_SettingSecurityMode#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#8)]  
  
### <a name="to-use-the-nettcpbinding-with-windows-for-transport-security-in-code"></a><span data-ttu-id="1c50a-136">Использование привязки NetTcpBinding с Windows для обеспечения безопасности транспорта (в коде)</span><span class="sxs-lookup"><span data-stu-id="1c50a-136">To use the NetTcpBinding with Windows for transport security (in code)</span></span>  
  
1. <span data-ttu-id="1c50a-137">Создайте экземпляр класса <xref:System.ServiceModel.NetTcpBinding> и задайте для свойства <xref:System.ServiceModel.NetTcpSecurity.Mode%2A> значение <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span><span class="sxs-lookup"><span data-stu-id="1c50a-137">Create an instance of the <xref:System.ServiceModel.NetTcpBinding> class and set the <xref:System.ServiceModel.NetTcpSecurity.Mode%2A> property to <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>  
  
2. <span data-ttu-id="1c50a-138">Настройте безопасность транспорта на использование Windows, задав для свойства <xref:System.ServiceModel.TcpTransportSecurity.ClientCredentialType%2A> значение <xref:System.ServiceModel.TcpClientCredentialType.Windows>.</span><span class="sxs-lookup"><span data-stu-id="1c50a-138">Set the transport security to use Windows by setting the <xref:System.ServiceModel.TcpTransportSecurity.ClientCredentialType%2A> to <xref:System.ServiceModel.TcpClientCredentialType.Windows>.</span></span> <span data-ttu-id="1c50a-139">(Обратите внимание, что это значение используется по умолчанию.)</span><span class="sxs-lookup"><span data-stu-id="1c50a-139">(Note that this is the default.)</span></span>  
  
3. <span data-ttu-id="1c50a-140">Присвойте свойству <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A> соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="1c50a-140">Set the <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A> to an appropriate value.</span></span> <span data-ttu-id="1c50a-141">В следующем коде используется значение <xref:System.ServiceModel.MessageCredentialType.Certificate>.</span><span class="sxs-lookup"><span data-stu-id="1c50a-141">The following code uses the <xref:System.ServiceModel.MessageCredentialType.Certificate> value.</span></span>  
  
4. <span data-ttu-id="1c50a-142">Создайте экземпляр класса <xref:System.Uri> с соответствующим базовым адресом.</span><span class="sxs-lookup"><span data-stu-id="1c50a-142">Create an instance of the <xref:System.Uri> class with an appropriate base address.</span></span> <span data-ttu-id="1c50a-143">Обратите внимание, что адрес должен использовать схему "net.tcp".</span><span class="sxs-lookup"><span data-stu-id="1c50a-143">Note that the address must use the "net.tcp" scheme.</span></span> <span data-ttu-id="1c50a-144">(Кроме того, базовый адрес можно задать в конфигурации.)</span><span class="sxs-lookup"><span data-stu-id="1c50a-144">(Alternatively, you can set the base address in configuration.)</span></span>  
  
5. <span data-ttu-id="1c50a-145">Создайте экземпляр класса <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="1c50a-145">Create the instance of the <xref:System.ServiceModel.ServiceHost> class.</span></span>  
  
6. <span data-ttu-id="1c50a-146">Воспользуйтесь методом <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> класса <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>, чтобы явно задать сертификат X.509 для службы.</span><span class="sxs-lookup"><span data-stu-id="1c50a-146">Use the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> method of the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> class to explicitly set the X.509 certificate for the service.</span></span>  
  
7. <span data-ttu-id="1c50a-147">Добавьте конечную точку службы с помощью метода <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>.</span><span class="sxs-lookup"><span data-stu-id="1c50a-147">Add a service endpoint using the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method.</span></span>  
  
8. <span data-ttu-id="1c50a-148">Вызовите метод <xref:System.ServiceModel.ICommunicationObject.Open%2A>, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="1c50a-148">Call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#9)]
     [!code-vb[c_SettingSecurityMode#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#9)]  
  
## <a name="using-configuration"></a><span data-ttu-id="1c50a-149">Использование конфигурации</span><span class="sxs-lookup"><span data-stu-id="1c50a-149">Using Configuration</span></span>  
  
#### <a name="to-use-the-wshttpbinding"></a><span data-ttu-id="1c50a-150">Использование привязки WSHttpBinding</span><span class="sxs-lookup"><span data-stu-id="1c50a-150">To use the WSHttpBinding</span></span>  
  
1. <span data-ttu-id="1c50a-151">Задайте для компьютера SSL-сертификат, привязанный к порту.</span><span class="sxs-lookup"><span data-stu-id="1c50a-151">Configure the computer with an SSL certificate bound to a port.</span></span> <span data-ttu-id="1c50a-152">(Дополнительные сведения см. [в разделе как настроить порт с помощью SSL-сертификата](how-to-configure-a-port-with-an-ssl-certificate.md)).</span><span class="sxs-lookup"><span data-stu-id="1c50a-152">(For more information, see [How to: Configure a Port with an SSL Certificate](how-to-configure-a-port-with-an-ssl-certificate.md)).</span></span> <span data-ttu-id="1c50a-153">В этой конфигурации не нужно задавать `transport` значение элемента> <.</span><span class="sxs-lookup"><span data-stu-id="1c50a-153">You do not need to set a <`transport`> element value with this configuration.</span></span>  
  
2. <span data-ttu-id="1c50a-154">Задайте тип учетных данных клиента для MLS.</span><span class="sxs-lookup"><span data-stu-id="1c50a-154">Specify the client credential type for the message-level security.</span></span> <span data-ttu-id="1c50a-155">В следующем примере `clientCredentialType` атрибуту элемента <> присваивается `message` значение `UserName` .</span><span class="sxs-lookup"><span data-stu-id="1c50a-155">The following example sets the `clientCredentialType` attribute of the <`message`> element to `UserName`.</span></span>  
  
    ```xml  
    <wsHttpBinding>  
    <binding name="WsHttpBinding_ICalculator">  
            <security mode="TransportWithMessageCredential" >  
               <message clientCredentialType="UserName" />  
            </security>  
    </binding>  
    </wsHttpBinding>  
    ```  
  
#### <a name="to-use-the-nettcpbinding-with-a-certificate-for-transport-security"></a><span data-ttu-id="1c50a-156">Использование привязки NetTcpBinding с сертификатом для обеспечения безопасности транспорта</span><span class="sxs-lookup"><span data-stu-id="1c50a-156">To use the NetTcpBinding with a certificate for transport security</span></span>  
  
1. <span data-ttu-id="1c50a-157">В случае SSL по TCP необходимо явно задать сертификат в элементе `<behaviors>`.</span><span class="sxs-lookup"><span data-stu-id="1c50a-157">For SSL over TCP, you must explicitly specify the certificate in the `<behaviors>` element.</span></span> <span data-ttu-id="1c50a-158">В следующем примере сертификат задается своим издателем в хранилище по умолчанию (в хранилище локального компьютера и личном хранилище).</span><span class="sxs-lookup"><span data-stu-id="1c50a-158">The following example specifies a certificate by its issuer in the default store location (local machine and personal stores).</span></span>  
  
    ```xml  
    <behaviors>  
     <serviceBehaviors>  
       <behavior name="mySvcBehavior">  
           <serviceCredentials>  
             <serviceCertificate findValue="contoso.com"  
                                 x509FindType="FindByIssuerName" />  
           </serviceCredentials>  
       </behavior>  
     </serviceBehaviors>  
    </behaviors>  
    ```  
  
2. <span data-ttu-id="1c50a-159">Добавление в [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md) раздел привязок</span><span class="sxs-lookup"><span data-stu-id="1c50a-159">Add a [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md) to the bindings section</span></span>  
  
3. <span data-ttu-id="1c50a-160">Добавьте элемент привязки и присвойте атрибуту `name` соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="1c50a-160">Add a binding element, and set the `name` attribute to an appropriate value.</span></span>  
  
4. <span data-ttu-id="1c50a-161">Добавьте `security` элемент> <и присвойте `mode` атрибуту значение `TransportWithMessageCredential` .</span><span class="sxs-lookup"><span data-stu-id="1c50a-161">Add a <`security`> element, and set the `mode` attribute to `TransportWithMessageCredential`.</span></span>  
  
5. <span data-ttu-id="1c50a-162">Добавьте элемент <`message>` и задайте `clientCredentialType` для атрибута соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="1c50a-162">Add a <`message>` element, and set the `clientCredentialType` attribute to an appropriate value.</span></span>  
  
    ```xml  
    <bindings>  
    <netTcpBinding>  
      <binding name="myTcpBinding">  
        <security mode="TransportWithMessageCredential" >  
           <message clientCredentialType="Windows" />  
        </security>  
      </binding>  
    </netTcpBinding>  
    </bindings>  
    ```  
  
#### <a name="to-use-the-nettcpbinding-with-windows-for-transport-security"></a><span data-ttu-id="1c50a-163">Использование привязки NetTcpBinding с Windows для обеспечения безопасности транспорта</span><span class="sxs-lookup"><span data-stu-id="1c50a-163">To use the NetTcpBinding with Windows for transport security</span></span>  
  
1. <span data-ttu-id="1c50a-164">Добавьте в [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md) раздел привязок.</span><span class="sxs-lookup"><span data-stu-id="1c50a-164">Add a [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md) to the bindings section,</span></span>  
  
2. <span data-ttu-id="1c50a-165">Добавьте `binding` элемент> <и присвойте `name` атрибуту соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="1c50a-165">Add a <`binding`> element and set the `name` attribute to an appropriate value.</span></span>  
  
3. <span data-ttu-id="1c50a-166">Добавьте `security` элемент> <и присвойте `mode` атрибуту значение `TransportWithMessageCredential` .</span><span class="sxs-lookup"><span data-stu-id="1c50a-166">Add a <`security`> element, and set the `mode` attribute to `TransportWithMessageCredential`.</span></span>  
  
4. <span data-ttu-id="1c50a-167">Добавьте `transport` элемент> <и присвойте `clientCredentialType` атрибуту значение `Windows` .</span><span class="sxs-lookup"><span data-stu-id="1c50a-167">Add a <`transport`> element and set the `clientCredentialType` attribute to `Windows`.</span></span>  
  
5. <span data-ttu-id="1c50a-168">Добавьте `message` элемент> <и присвойте `clientCredentialType` атрибуту соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="1c50a-168">Add a <`message`> element and set the `clientCredentialType` attribute to an appropriate value.</span></span> <span data-ttu-id="1c50a-169">В следующем коде задается значение для сертификата.</span><span class="sxs-lookup"><span data-stu-id="1c50a-169">The following code sets the value to a certificate.</span></span>  
  
    ```xml  
    <bindings>  
    <netTcpBinding>  
      <binding name="myTcpBinding">  
        <security mode="TransportWithMessageCredential" >  
           <transport clientCredentialType="Windows" />  
           <message clientCredentialType="Certificate" />  
        </security>  
      </binding>  
    </netTcpBinding>  
    </bindings>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1c50a-170">См. также</span><span class="sxs-lookup"><span data-stu-id="1c50a-170">See also</span></span>

- [<span data-ttu-id="1c50a-171">Практическое руководство. Задание режима безопасности</span><span class="sxs-lookup"><span data-stu-id="1c50a-171">How to: Set the Security Mode</span></span>](../how-to-set-the-security-mode.md)
- [<span data-ttu-id="1c50a-172">Защита служб</span><span class="sxs-lookup"><span data-stu-id="1c50a-172">Securing Services</span></span>](../securing-services.md)
- [<span data-ttu-id="1c50a-173">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="1c50a-173">Securing Services and Clients</span></span>](securing-services-and-clients.md)
