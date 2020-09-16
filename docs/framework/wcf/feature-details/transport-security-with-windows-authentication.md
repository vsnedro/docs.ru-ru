---
title: Безопасность транспорта с проверкой подлинности Windows
description: Ознакомьтесь с этим сценарием, в котором показан клиент или служба WCF, защищенные системой безопасности Windows. В этом примере служба интрасети отображает сведения о персонале.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 96dd26e2-46e7-4de0-9a29-4fcb05bf187b
ms.openlocfilehash: 9b81f2f2fb6352af254146951ed35ad4fdca8caa
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90545211"
---
# <a name="transport-security-with-windows-authentication"></a><span data-ttu-id="44b13-104">Безопасность транспорта с проверкой подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="44b13-104">Transport Security with Windows Authentication</span></span>
<span data-ttu-id="44b13-105">В следующем сценарии показан клиент Windows Communication Foundation (WCF) и служба, защищенная системой безопасности Windows.</span><span class="sxs-lookup"><span data-stu-id="44b13-105">The following scenario shows a Windows Communication Foundation (WCF) client and service secured by Windows security.</span></span> <span data-ttu-id="44b13-106">Дополнительные сведения о программировании см. [в разделе как защитить службу с помощью учетных данных Windows](../how-to-secure-a-service-with-windows-credentials.md).</span><span class="sxs-lookup"><span data-stu-id="44b13-106">For more information about programming, see [How to: Secure a Service with Windows Credentials](../how-to-secure-a-service-with-windows-credentials.md).</span></span>  
  
 <span data-ttu-id="44b13-107">Веб-служба интрасети отображает информацию о персонале.</span><span class="sxs-lookup"><span data-stu-id="44b13-107">An intranet Web service displays human resources information.</span></span> <span data-ttu-id="44b13-108">Клиентом является приложение Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="44b13-108">The client is a Windows Form application.</span></span> <span data-ttu-id="44b13-109">Приложение развернуто на домене с защищающем его контроллером Kerberos.</span><span class="sxs-lookup"><span data-stu-id="44b13-109">The application is deployed in a domain with a Kerberos controller securing the domain.</span></span>  
  
 ![Безопасность транспорта с аутентификацией Windows](./media/transport-security-with-windows-authentication/secured-windows-authentication.gif)  
  
|<span data-ttu-id="44b13-111">Характеристика</span><span class="sxs-lookup"><span data-stu-id="44b13-111">Characteristic</span></span>|<span data-ttu-id="44b13-112">Описание</span><span class="sxs-lookup"><span data-stu-id="44b13-112">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="44b13-113">Режим безопасности</span><span class="sxs-lookup"><span data-stu-id="44b13-113">Security Mode</span></span>|<span data-ttu-id="44b13-114">Транспорт</span><span class="sxs-lookup"><span data-stu-id="44b13-114">Transport</span></span>|  
|<span data-ttu-id="44b13-115">Совместимость</span><span class="sxs-lookup"><span data-stu-id="44b13-115">Interoperability</span></span>|<span data-ttu-id="44b13-116">Только WCF</span><span class="sxs-lookup"><span data-stu-id="44b13-116">WCF only</span></span>|  
|<span data-ttu-id="44b13-117">Проверка подлинности (сервера)</span><span class="sxs-lookup"><span data-stu-id="44b13-117">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="44b13-118">Проверка подлинности (клиента)</span><span class="sxs-lookup"><span data-stu-id="44b13-118">Authentication (Client)</span></span>|<span data-ttu-id="44b13-119">Да (при помощи встроенной проверки подлинности Windows)</span><span class="sxs-lookup"><span data-stu-id="44b13-119">Yes (using Windows integrated authentication)</span></span><br /><br /> <span data-ttu-id="44b13-120">Да (при помощи встроенной проверки подлинности Windows)</span><span class="sxs-lookup"><span data-stu-id="44b13-120">Yes (using Windows integrated authentication)</span></span>|  
|<span data-ttu-id="44b13-121">Целостность</span><span class="sxs-lookup"><span data-stu-id="44b13-121">Integrity</span></span>|<span data-ttu-id="44b13-122">Да</span><span class="sxs-lookup"><span data-stu-id="44b13-122">Yes</span></span>|  
|<span data-ttu-id="44b13-123">Конфиденциальность</span><span class="sxs-lookup"><span data-stu-id="44b13-123">Confidentiality</span></span>|<span data-ttu-id="44b13-124">Да</span><span class="sxs-lookup"><span data-stu-id="44b13-124">Yes</span></span>|  
|<span data-ttu-id="44b13-125">Транспорт</span><span class="sxs-lookup"><span data-stu-id="44b13-125">Transport</span></span>|<span data-ttu-id="44b13-126">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="44b13-126">NET.TCP</span></span>|  
|<span data-ttu-id="44b13-127">Привязка</span><span class="sxs-lookup"><span data-stu-id="44b13-127">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
  
## <a name="service"></a><span data-ttu-id="44b13-128">Служба</span><span class="sxs-lookup"><span data-stu-id="44b13-128">Service</span></span>  
 <span data-ttu-id="44b13-129">Предполагается, что представленные ниже код и конфигурация выполняются независимо.</span><span class="sxs-lookup"><span data-stu-id="44b13-129">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="44b13-130">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="44b13-130">Do one of the following:</span></span>  
  
- <span data-ttu-id="44b13-131">Создайте автономную службу, используя код без конфигурации.</span><span class="sxs-lookup"><span data-stu-id="44b13-131">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="44b13-132">Создайте службу, используя предоставленную конфигурацию, но не определяйте конечные точки.</span><span class="sxs-lookup"><span data-stu-id="44b13-132">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="44b13-133">Код</span><span class="sxs-lookup"><span data-stu-id="44b13-133">Code</span></span>  
 <span data-ttu-id="44b13-134">В следующем коде показано, как создать конечную точку службы, которая использует безопасность Windows.</span><span class="sxs-lookup"><span data-stu-id="44b13-134">The following code shows how to create a service endpoint that uses a Windows security.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#3)]
 [!code-vb[C_SecurityScenarios#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#3)]  
  
### <a name="configuration"></a><span data-ttu-id="44b13-135">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="44b13-135">Configuration</span></span>  
 <span data-ttu-id="44b13-136">Вместо кода для настройки конечной точки службы можно использовать следующую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="44b13-136">The following configuration can be used instead of the code to set up the service endpoint:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration="" name="ServiceModel.Calculator">  
        <endpoint address="net.tcp://localhost:8008/Calculator"
                  binding="netTcpBinding"  
          bindingConfiguration="WindowsClientOverTcp"
                  name="WindowsClientOverTcp"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <netTcpBinding>  
        <binding name="WindowsClientOverTcp">  
          <security mode="Transport">  
            <transport clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="44b13-137">Клиент</span><span class="sxs-lookup"><span data-stu-id="44b13-137">Client</span></span>  
 <span data-ttu-id="44b13-138">Предполагается, что представленные ниже код и конфигурация выполняются независимо.</span><span class="sxs-lookup"><span data-stu-id="44b13-138">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="44b13-139">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="44b13-139">Do one of the following:</span></span>  
  
- <span data-ttu-id="44b13-140">Создайте автономный клиент, используя код (и код клиента).</span><span class="sxs-lookup"><span data-stu-id="44b13-140">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="44b13-141">Создайте клиент, который не определяет никаких адресов конечных точек.</span><span class="sxs-lookup"><span data-stu-id="44b13-141">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="44b13-142">Вместо этого используйте конструктор клиента, который принимает в качестве аргумента имя конфигурации.</span><span class="sxs-lookup"><span data-stu-id="44b13-142">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="44b13-143">Пример:</span><span class="sxs-lookup"><span data-stu-id="44b13-143">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="44b13-144">Код</span><span class="sxs-lookup"><span data-stu-id="44b13-144">Code</span></span>  
 <span data-ttu-id="44b13-145">Следующий код служит для создания клиента.</span><span class="sxs-lookup"><span data-stu-id="44b13-145">The following code creates the client.</span></span> <span data-ttu-id="44b13-146">Привязка настроена на использование безопасности транспортного режима с транспортом TCP, с типом учетных данных клиента, установленных на Windows.</span><span class="sxs-lookup"><span data-stu-id="44b13-146">The binding is configured to use the Transport mode security, with the TCP transport, with the client credential type set to Windows.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#4)]
 [!code-vb[C_SecurityScenarios#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#4)]  
  
### <a name="configuration"></a><span data-ttu-id="44b13-147">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="44b13-147">Configuration</span></span>  
 <span data-ttu-id="44b13-148">Вместо кода для создания клиента можно использовать следующую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="44b13-148">The following configuration can be used instead of the code to create the client.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <netTcpBinding>  
        <binding name="NetTcpBinding_ICalculator" >  
          <security mode="Transport">  
            <transport clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client>  
      <endpoint address="net.tcp://localhost:8008/Calculator"
                binding="netTcpBinding"
                bindingConfiguration="NetTcpBinding_ICalculator"
                contract="ICalculator"  
                name="NetTcpBinding_ICalculator">  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="44b13-149">См. также</span><span class="sxs-lookup"><span data-stu-id="44b13-149">See also</span></span>

- [<span data-ttu-id="44b13-150">Обзор безопасности</span><span class="sxs-lookup"><span data-stu-id="44b13-150">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="44b13-151">Практическое руководство. Защита службы с использованием учетных данных Windows</span><span class="sxs-lookup"><span data-stu-id="44b13-151">How to: Secure a Service with Windows Credentials</span></span>](../how-to-secure-a-service-with-windows-credentials.md)
- <span data-ttu-id="44b13-152">[Модель безопасности для Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="44b13-152">[Security Model for Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
