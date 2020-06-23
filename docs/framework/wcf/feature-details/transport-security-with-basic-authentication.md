---
title: Безопасность транспорта с обычной проверкой подлинности
description: Ознакомьтесь с этим сценарием WCF, который показывает обычную проверку подлинности для службы WCF и клиента. Службе требуется действительный сертификат, которому доверяет клиент.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b54f491d-196b-4279-876c-76b83ec0442c
ms.openlocfilehash: f15a19feaed631a76948efd24ee225acf789cb2d
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244859"
---
# <a name="transport-security-with-basic-authentication"></a><span data-ttu-id="8d7e9-104">Безопасность транспорта с обычной проверкой подлинности</span><span class="sxs-lookup"><span data-stu-id="8d7e9-104">Transport Security with Basic Authentication</span></span>
<span data-ttu-id="8d7e9-105">На следующем рисунке показана служба Windows Communication Foundation (WCF) и клиент.</span><span class="sxs-lookup"><span data-stu-id="8d7e9-105">The following illustration shows a Windows Communication Foundation (WCF) service and client.</span></span> <span data-ttu-id="8d7e9-106">Серверу требуется действительный сертификат X.509, который можно использовать для протокола SSL, а клиенты должны доверять сертификату сервера.</span><span class="sxs-lookup"><span data-stu-id="8d7e9-106">The server needs a valid X.509 certificate that can be used for Secure Sockets Layer (SSL), and the clients must trust the server’s certificate.</span></span> <span data-ttu-id="8d7e9-107">Кроме того, у веб-службы уже имеется сертификат SSL, который можно использовать.</span><span class="sxs-lookup"><span data-stu-id="8d7e9-107">Further, the Web service already has an SSL implementation that can be used.</span></span> <span data-ttu-id="8d7e9-108">Дополнительные сведения о включении обычной проверки подлинности для службы IIS (IIS) см. в разделе <https://docs.microsoft.com/iis/configuration/system.webserver/security/authentication/basicauthentication> .</span><span class="sxs-lookup"><span data-stu-id="8d7e9-108">For more information about enabling basic authentication on Internet Information Services (IIS), see <https://docs.microsoft.com/iis/configuration/system.webserver/security/authentication/basicauthentication>.</span></span>  
  
 ![Снимок экрана, показывающий безопасность транспорта с обычной проверкой подлинности.](./media/transport-security-with-basic-authentication/transport-security-basic-authentication.gif)  
  
|<span data-ttu-id="8d7e9-110">Характеристика</span><span class="sxs-lookup"><span data-stu-id="8d7e9-110">Characteristic</span></span>|<span data-ttu-id="8d7e9-111">Описание</span><span class="sxs-lookup"><span data-stu-id="8d7e9-111">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="8d7e9-112">Режим безопасности</span><span class="sxs-lookup"><span data-stu-id="8d7e9-112">Security Mode</span></span>|<span data-ttu-id="8d7e9-113">Транспортировка</span><span class="sxs-lookup"><span data-stu-id="8d7e9-113">Transport</span></span>|  
|<span data-ttu-id="8d7e9-114">Совместимость</span><span class="sxs-lookup"><span data-stu-id="8d7e9-114">Interoperability</span></span>|<span data-ttu-id="8d7e9-115">С существующими службами и клиентами веб-служб</span><span class="sxs-lookup"><span data-stu-id="8d7e9-115">With existing Web service clients and services</span></span>|  
|<span data-ttu-id="8d7e9-116">Проверка подлинности (сервера)</span><span class="sxs-lookup"><span data-stu-id="8d7e9-116">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="8d7e9-117">Проверка подлинности (клиента)</span><span class="sxs-lookup"><span data-stu-id="8d7e9-117">Authentication (Client)</span></span>|<span data-ttu-id="8d7e9-118">Да (по протоколу HTTPS)</span><span class="sxs-lookup"><span data-stu-id="8d7e9-118">Yes (using HTTPS)</span></span><br /><br /> <span data-ttu-id="8d7e9-119">Да (по имени/паролю пользователя)</span><span class="sxs-lookup"><span data-stu-id="8d7e9-119">Yes (through User name/Password)</span></span>|  
|<span data-ttu-id="8d7e9-120">Целостность</span><span class="sxs-lookup"><span data-stu-id="8d7e9-120">Integrity</span></span>|<span data-ttu-id="8d7e9-121">Да</span><span class="sxs-lookup"><span data-stu-id="8d7e9-121">Yes</span></span>|  
|<span data-ttu-id="8d7e9-122">Конфиденциальность</span><span class="sxs-lookup"><span data-stu-id="8d7e9-122">Confidentiality</span></span>|<span data-ttu-id="8d7e9-123">Да</span><span class="sxs-lookup"><span data-stu-id="8d7e9-123">Yes</span></span>|  
|<span data-ttu-id="8d7e9-124">Транспортировка</span><span class="sxs-lookup"><span data-stu-id="8d7e9-124">Transport</span></span>|<span data-ttu-id="8d7e9-125">HTTPS</span><span class="sxs-lookup"><span data-stu-id="8d7e9-125">HTTPS</span></span>|  
|<span data-ttu-id="8d7e9-126">Привязка</span><span class="sxs-lookup"><span data-stu-id="8d7e9-126">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="8d7e9-127">Служба</span><span class="sxs-lookup"><span data-stu-id="8d7e9-127">Service</span></span>  
 <span data-ttu-id="8d7e9-128">Предполагается, что представленные ниже код и конфигурация выполняются независимо.</span><span class="sxs-lookup"><span data-stu-id="8d7e9-128">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="8d7e9-129">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="8d7e9-129">Do one of the following:</span></span>  
  
- <span data-ttu-id="8d7e9-130">Создайте автономную службу, используя код без конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8d7e9-130">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="8d7e9-131">Создайте службу, используя предоставленную конфигурацию, но не определяйте конечные точки.</span><span class="sxs-lookup"><span data-stu-id="8d7e9-131">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="8d7e9-132">Код</span><span class="sxs-lookup"><span data-stu-id="8d7e9-132">Code</span></span>  
 <span data-ttu-id="8d7e9-133">В следующем примере кода показано, как создавать конечную точку службы, использующую имя и пароль пользователя в домене Windows для безопасности передачи.</span><span class="sxs-lookup"><span data-stu-id="8d7e9-133">The following code shows how to create a service endpoint that uses a Windows domain user name and password for transfer security.</span></span> <span data-ttu-id="8d7e9-134">Обратите внимание, что для проверки подлинности клиента службе требуется сертификат X.509.</span><span class="sxs-lookup"><span data-stu-id="8d7e9-134">Note that the service requires an X.509 certificate to authenticate to the client.</span></span> <span data-ttu-id="8d7e9-135">Дополнительные сведения см. в статьях [Работа с сертификатами](working-with-certificates.md) и [инструкции. Настройка порта с помощью SSL-сертификата](how-to-configure-a-port-with-an-ssl-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="8d7e9-135">For more information, see [Working with Certificates](working-with-certificates.md) and [How to: Configure a Port with an SSL Certificate](how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>  
  
 [!code-csharp[C_SecurityScenarios#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#1)]
 [!code-vb[C_SecurityScenarios#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#1)]  
  
## <a name="configuration"></a><span data-ttu-id="8d7e9-136">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="8d7e9-136">Configuration</span></span>  
 <span data-ttu-id="8d7e9-137">Следующий код служит для настройки службы на использование обычной проверки подлинности с безопасностью на уровне транспорта.</span><span class="sxs-lookup"><span data-stu-id="8d7e9-137">The following configures a service to use basic authentication with transport-level security:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
    <system.serviceModel>  
        <bindings>  
            <wsHttpBinding>  
                <binding name="UsernameWithTransport">  
                    <security mode="Transport">  
                        <transport clientCredentialType="Basic" />  
                    </security>  
                </binding>  
            </wsHttpBinding>  
        </bindings>  
        <services>  
            <service name="BasicAuthentication.Calculator">  
                <endpoint address="https://localhost/Calculator"  
                          binding="wsHttpBinding"
                          bindingConfiguration="UsernameWithTransport"  
                          name="BasicEndpoint"
                          contract="BasicAuthentication.ICalculator" />  
            </service>  
        </services>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="8d7e9-138">клиент</span><span class="sxs-lookup"><span data-stu-id="8d7e9-138">Client</span></span>  
  
### <a name="code"></a><span data-ttu-id="8d7e9-139">Код</span><span class="sxs-lookup"><span data-stu-id="8d7e9-139">Code</span></span>  
 <span data-ttu-id="8d7e9-140">В следующем примере кода демонстрируется код клиента, который содержит имя и пароль пользователя.</span><span class="sxs-lookup"><span data-stu-id="8d7e9-140">The following code shows the client code that includes the user name and password.</span></span> <span data-ttu-id="8d7e9-141">Обратите внимание, что пользователь должен предоставить действительные имя и пароль пользователя в Windows.</span><span class="sxs-lookup"><span data-stu-id="8d7e9-141">Note that the user must provide a valid Windows user name and password.</span></span> <span data-ttu-id="8d7e9-142">В данном разделе не представлен код, возвращающий имя и пароль пользователя.</span><span class="sxs-lookup"><span data-stu-id="8d7e9-142">The code to return the user name and password is not shown here.</span></span> <span data-ttu-id="8d7e9-143">Используйте диалоговое окно или другой интерфейс, чтобы запросить пользователя об этой информации.</span><span class="sxs-lookup"><span data-stu-id="8d7e9-143">Use a dialog box or other interface to query the user for the information.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8d7e9-144">Имя и пароль пользователя задаются только с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="8d7e9-144">User name and password can only be set using code.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#2)]
 [!code-vb[C_SecurityScenarios#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#2)]  
  
### <a name="configuration"></a><span data-ttu-id="8d7e9-145">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="8d7e9-145">Configuration</span></span>  
 <span data-ttu-id="8d7e9-146">В следующем примере кода показана конфигурация клиента.</span><span class="sxs-lookup"><span data-stu-id="8d7e9-146">The following code shows the client configuration.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8d7e9-147">Конфигурацию невозможно использовать для задания имени и пароля пользователя.</span><span class="sxs-lookup"><span data-stu-id="8d7e9-147">You cannot use configuration to set the user name and password.</span></span> <span data-ttu-id="8d7e9-148">Представленную в этом примере конфигурацию необходимо дополнить с помощью кода, чтобы разрешить задание имени и пароля пользователя.</span><span class="sxs-lookup"><span data-stu-id="8d7e9-148">The configuration shown here must be augmented using code to set the user name and password.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Transport">  
            <transport clientCredentialType="Basic" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="https://machineName/Calculator"
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8d7e9-149">См. также</span><span class="sxs-lookup"><span data-stu-id="8d7e9-149">See also</span></span>

- <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential>
- [<span data-ttu-id="8d7e9-150">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="8d7e9-150">Working with Certificates</span></span>](working-with-certificates.md)
- [<span data-ttu-id="8d7e9-151">Практическое руководство. Настройка порта с использованием SSL-сертификата</span><span class="sxs-lookup"><span data-stu-id="8d7e9-151">How to: Configure a Port with an SSL Certificate</span></span>](how-to-configure-a-port-with-an-ssl-certificate.md)
- [<span data-ttu-id="8d7e9-152">Обзор безопасности</span><span class="sxs-lookup"><span data-stu-id="8d7e9-152">Security Overview</span></span>](security-overview.md)
- [\<clientCredentials>](../../configure-apps/file-schema/wcf/clientcredentials.md)
- <span data-ttu-id="8d7e9-153">[Модель безопасности для Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="8d7e9-153">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
