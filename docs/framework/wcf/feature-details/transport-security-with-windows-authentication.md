---
title: Безопасность транспорта с проверкой подлинности Windows
description: Ознакомьтесь с этим сценарием, в котором показан клиент или служба WCF, защищенные системой безопасности Windows. В этом примере служба интрасети отображает сведения о персонале.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 96dd26e2-46e7-4de0-9a29-4fcb05bf187b
ms.openlocfilehash: 47f5a2a3b2c8815e2ccb0cc4d4bf3c408f4992e2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251741"
---
# <a name="transport-security-with-windows-authentication"></a><span data-ttu-id="12058-104">Безопасность транспорта с проверкой подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="12058-104">Transport Security with Windows Authentication</span></span>

<span data-ttu-id="12058-105">В следующем сценарии показан клиент Windows Communication Foundation (WCF) и служба, защищенная системой безопасности Windows.</span><span class="sxs-lookup"><span data-stu-id="12058-105">The following scenario shows a Windows Communication Foundation (WCF) client and service secured by Windows security.</span></span> <span data-ttu-id="12058-106">Дополнительные сведения о программировании см. [в разделе как защитить службу с помощью учетных данных Windows](../how-to-secure-a-service-with-windows-credentials.md).</span><span class="sxs-lookup"><span data-stu-id="12058-106">For more information about programming, see [How to: Secure a Service with Windows Credentials](../how-to-secure-a-service-with-windows-credentials.md).</span></span>  
  
 <span data-ttu-id="12058-107">Веб-служба интрасети отображает информацию о персонале.</span><span class="sxs-lookup"><span data-stu-id="12058-107">An intranet Web service displays human resources information.</span></span> <span data-ttu-id="12058-108">Клиентом является приложение Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="12058-108">The client is a Windows Form application.</span></span> <span data-ttu-id="12058-109">Приложение развернуто на домене с защищающем его контроллером Kerberos.</span><span class="sxs-lookup"><span data-stu-id="12058-109">The application is deployed in a domain with a Kerberos controller securing the domain.</span></span>  
  
 ![Безопасность транспорта с аутентификацией Windows](./media/transport-security-with-windows-authentication/secured-windows-authentication.gif)  
  
|<span data-ttu-id="12058-111">Характеристика</span><span class="sxs-lookup"><span data-stu-id="12058-111">Characteristic</span></span>|<span data-ttu-id="12058-112">Описание</span><span class="sxs-lookup"><span data-stu-id="12058-112">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="12058-113">Режим безопасности</span><span class="sxs-lookup"><span data-stu-id="12058-113">Security Mode</span></span>|<span data-ttu-id="12058-114">Транспорт</span><span class="sxs-lookup"><span data-stu-id="12058-114">Transport</span></span>|  
|<span data-ttu-id="12058-115">Совместимость</span><span class="sxs-lookup"><span data-stu-id="12058-115">Interoperability</span></span>|<span data-ttu-id="12058-116">Только WCF</span><span class="sxs-lookup"><span data-stu-id="12058-116">WCF only</span></span>|  
|<span data-ttu-id="12058-117">Проверка подлинности (сервера)</span><span class="sxs-lookup"><span data-stu-id="12058-117">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="12058-118">Проверка подлинности (клиента)</span><span class="sxs-lookup"><span data-stu-id="12058-118">Authentication (Client)</span></span>|<span data-ttu-id="12058-119">Да (при помощи встроенной проверки подлинности Windows)</span><span class="sxs-lookup"><span data-stu-id="12058-119">Yes (using Windows integrated authentication)</span></span><br /><br /> <span data-ttu-id="12058-120">Да (при помощи встроенной проверки подлинности Windows)</span><span class="sxs-lookup"><span data-stu-id="12058-120">Yes (using Windows integrated authentication)</span></span>|  
|<span data-ttu-id="12058-121">Целостность</span><span class="sxs-lookup"><span data-stu-id="12058-121">Integrity</span></span>|<span data-ttu-id="12058-122">Да</span><span class="sxs-lookup"><span data-stu-id="12058-122">Yes</span></span>|  
|<span data-ttu-id="12058-123">Конфиденциальность</span><span class="sxs-lookup"><span data-stu-id="12058-123">Confidentiality</span></span>|<span data-ttu-id="12058-124">Да</span><span class="sxs-lookup"><span data-stu-id="12058-124">Yes</span></span>|  
|<span data-ttu-id="12058-125">Транспорт</span><span class="sxs-lookup"><span data-stu-id="12058-125">Transport</span></span>|<span data-ttu-id="12058-126">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="12058-126">NET.TCP</span></span>|  
|<span data-ttu-id="12058-127">Привязка</span><span class="sxs-lookup"><span data-stu-id="12058-127">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
  
## <a name="service"></a><span data-ttu-id="12058-128">Служба</span><span class="sxs-lookup"><span data-stu-id="12058-128">Service</span></span>  

 <span data-ttu-id="12058-129">Предполагается, что представленные ниже код и конфигурация выполняются независимо.</span><span class="sxs-lookup"><span data-stu-id="12058-129">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="12058-130">Используйте один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="12058-130">Do one of the following:</span></span>  
  
- <span data-ttu-id="12058-131">Создайте автономную службу, используя код без конфигурации.</span><span class="sxs-lookup"><span data-stu-id="12058-131">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="12058-132">Создайте службу, используя предоставленную конфигурацию, но не определяйте конечные точки.</span><span class="sxs-lookup"><span data-stu-id="12058-132">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="12058-133">Код</span><span class="sxs-lookup"><span data-stu-id="12058-133">Code</span></span>  

 <span data-ttu-id="12058-134">В следующем коде показано, как создать конечную точку службы, которая использует безопасность Windows.</span><span class="sxs-lookup"><span data-stu-id="12058-134">The following code shows how to create a service endpoint that uses a Windows security.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#3)]
 [!code-vb[C_SecurityScenarios#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#3)]  
  
### <a name="configuration"></a><span data-ttu-id="12058-135">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="12058-135">Configuration</span></span>  

 <span data-ttu-id="12058-136">Вместо кода для настройки конечной точки службы можно использовать следующую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="12058-136">The following configuration can be used instead of the code to set up the service endpoint:</span></span>  
  
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
  
## <a name="client"></a><span data-ttu-id="12058-137">Клиент</span><span class="sxs-lookup"><span data-stu-id="12058-137">Client</span></span>  

 <span data-ttu-id="12058-138">Предполагается, что представленные ниже код и конфигурация выполняются независимо.</span><span class="sxs-lookup"><span data-stu-id="12058-138">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="12058-139">Используйте один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="12058-139">Do one of the following:</span></span>  
  
- <span data-ttu-id="12058-140">Создайте автономный клиент, используя код (и код клиента).</span><span class="sxs-lookup"><span data-stu-id="12058-140">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="12058-141">Создайте клиент, который не определяет никаких адресов конечных точек.</span><span class="sxs-lookup"><span data-stu-id="12058-141">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="12058-142">Вместо этого используйте конструктор клиента, который принимает в качестве аргумента имя конфигурации.</span><span class="sxs-lookup"><span data-stu-id="12058-142">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="12058-143">Пример:</span><span class="sxs-lookup"><span data-stu-id="12058-143">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="12058-144">Код</span><span class="sxs-lookup"><span data-stu-id="12058-144">Code</span></span>  

 <span data-ttu-id="12058-145">Следующий код служит для создания клиента.</span><span class="sxs-lookup"><span data-stu-id="12058-145">The following code creates the client.</span></span> <span data-ttu-id="12058-146">Привязка настроена на использование безопасности транспортного режима с транспортом TCP, с типом учетных данных клиента, установленных на Windows.</span><span class="sxs-lookup"><span data-stu-id="12058-146">The binding is configured to use the Transport mode security, with the TCP transport, with the client credential type set to Windows.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#4)]
 [!code-vb[C_SecurityScenarios#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#4)]  
  
### <a name="configuration"></a><span data-ttu-id="12058-147">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="12058-147">Configuration</span></span>  

 <span data-ttu-id="12058-148">Вместо кода для создания клиента можно использовать следующую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="12058-148">The following configuration can be used instead of the code to create the client.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="12058-149">См. также</span><span class="sxs-lookup"><span data-stu-id="12058-149">See also</span></span>

- [<span data-ttu-id="12058-150">Обзор безопасности</span><span class="sxs-lookup"><span data-stu-id="12058-150">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="12058-151">Практическое руководство. Защита службы с использованием учетных данных Windows</span><span class="sxs-lookup"><span data-stu-id="12058-151">How to: Secure a Service with Windows Credentials</span></span>](../how-to-secure-a-service-with-windows-credentials.md)
- <span data-ttu-id="12058-152">[Модель безопасности для Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="12058-152">[Security Model for Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
