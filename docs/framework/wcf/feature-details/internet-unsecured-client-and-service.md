---
title: Незащищенные интернет-клиент и служба
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 97a10d79-3e7d-4bd1-9a99-fd9807fd70bc
ms.openlocfilehash: 017744d692d6fd4183fde3c21e71fcee2f35844e
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90535362"
---
# <a name="internet-unsecured-client-and-service"></a><span data-ttu-id="db683-102">Незащищенные интернет-клиент и служба</span><span class="sxs-lookup"><span data-stu-id="db683-102">Internet Unsecured Client and Service</span></span>
<span data-ttu-id="db683-103">На следующем рисунке показан пример общедоступного, незащищенного Windows Communication Foundation (WCF) клиента и службы.</span><span class="sxs-lookup"><span data-stu-id="db683-103">The following illustration shows an example of a public, unsecured Windows Communication Foundation (WCF) client and service:</span></span>  
  
 ![Снимок экрана, на котором показан незащищенный Интернет](./media/internet-unsecured-client-and-service/public-unsecured-internet.gif)  
  
|<span data-ttu-id="db683-105">Характеристика</span><span class="sxs-lookup"><span data-stu-id="db683-105">Characteristic</span></span>|<span data-ttu-id="db683-106">Описание</span><span class="sxs-lookup"><span data-stu-id="db683-106">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="db683-107">Режим безопасности</span><span class="sxs-lookup"><span data-stu-id="db683-107">Security Mode</span></span>|<span data-ttu-id="db683-108">None</span><span class="sxs-lookup"><span data-stu-id="db683-108">None</span></span>|  
|<span data-ttu-id="db683-109">Транспорт</span><span class="sxs-lookup"><span data-stu-id="db683-109">Transport</span></span>|<span data-ttu-id="db683-110">HTTP</span><span class="sxs-lookup"><span data-stu-id="db683-110">HTTP</span></span>|  
|<span data-ttu-id="db683-111">Привязка</span><span class="sxs-lookup"><span data-stu-id="db683-111">Binding</span></span>|<span data-ttu-id="db683-112"><xref:System.ServiceModel.BasicHttpBinding> в коде или в [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) элементе конфигурации.</span><span class="sxs-lookup"><span data-stu-id="db683-112"><xref:System.ServiceModel.BasicHttpBinding> in code, or the [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) element in configuration.</span></span>|  
|<span data-ttu-id="db683-113">Совместимость</span><span class="sxs-lookup"><span data-stu-id="db683-113">Interoperability</span></span>|<span data-ttu-id="db683-114">С существующими службами и клиентами веб-служб</span><span class="sxs-lookup"><span data-stu-id="db683-114">With existing Web service clients and services</span></span>|  
|<span data-ttu-id="db683-115">Аутентификация</span><span class="sxs-lookup"><span data-stu-id="db683-115">Authentication</span></span>|<span data-ttu-id="db683-116">None</span><span class="sxs-lookup"><span data-stu-id="db683-116">None</span></span>|  
|<span data-ttu-id="db683-117">Целостность</span><span class="sxs-lookup"><span data-stu-id="db683-117">Integrity</span></span>|<span data-ttu-id="db683-118">None</span><span class="sxs-lookup"><span data-stu-id="db683-118">None</span></span>|  
|<span data-ttu-id="db683-119">Конфиденциальность</span><span class="sxs-lookup"><span data-stu-id="db683-119">Confidentiality</span></span>|<span data-ttu-id="db683-120">None</span><span class="sxs-lookup"><span data-stu-id="db683-120">None</span></span>|  
  
## <a name="service"></a><span data-ttu-id="db683-121">Служба</span><span class="sxs-lookup"><span data-stu-id="db683-121">Service</span></span>  
 <span data-ttu-id="db683-122">Предполагается, что представленные ниже код и конфигурация выполняются независимо.</span><span class="sxs-lookup"><span data-stu-id="db683-122">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="db683-123">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="db683-123">Do one of the following:</span></span>  
  
- <span data-ttu-id="db683-124">Создайте автономную службу, используя код без конфигурации.</span><span class="sxs-lookup"><span data-stu-id="db683-124">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="db683-125">Создайте службу, используя предоставленную конфигурацию, но не определяйте конечные точки.</span><span class="sxs-lookup"><span data-stu-id="db683-125">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="db683-126">Код</span><span class="sxs-lookup"><span data-stu-id="db683-126">Code</span></span>  
 <span data-ttu-id="db683-127">В следующем коде показано создание конечной точки без безопасности.</span><span class="sxs-lookup"><span data-stu-id="db683-127">The following code shows how to create an endpoint with no security.</span></span> <span data-ttu-id="db683-128">По умолчанию режим безопасности <xref:System.ServiceModel.BasicHttpBinding> задан режим <xref:System.ServiceModel.BasicHttpSecurityMode.None>.</span><span class="sxs-lookup"><span data-stu-id="db683-128">By default, the <xref:System.ServiceModel.BasicHttpBinding> has the security mode set to <xref:System.ServiceModel.BasicHttpSecurityMode.None>.</span></span>  
  
 [!code-csharp[C_UnsecuredService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredservice/cs/source.cs#1)]
 [!code-vb[C_UnsecuredService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredservice/vb/source.vb#1)]  
  
### <a name="service-configuration"></a><span data-ttu-id="db683-129">Конфигурация службы</span><span class="sxs-lookup"><span data-stu-id="db683-129">Service Configuration</span></span>  
 <span data-ttu-id="db683-130">В следующем коде настраивается та же конечная точка с использованием конфигурации.</span><span class="sxs-lookup"><span data-stu-id="db683-130">The following code sets up the same endpoint using configuration.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration="" name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"
                  binding="basicHttpBinding"  
                  bindingConfiguration="Basic_Unsecured"
                  name="BasicHttp_ICalculator"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <basicHttpBinding>  
        <binding name="Basic_Unsecured" />  
      </basicHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="db683-131">Клиент</span><span class="sxs-lookup"><span data-stu-id="db683-131">Client</span></span>  
 <span data-ttu-id="db683-132">Предполагается, что представленные ниже код и конфигурация выполняются независимо.</span><span class="sxs-lookup"><span data-stu-id="db683-132">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="db683-133">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="db683-133">Do one of the following:</span></span>  
  
- <span data-ttu-id="db683-134">Создайте автономный клиент, используя код (и код клиента).</span><span class="sxs-lookup"><span data-stu-id="db683-134">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="db683-135">Создайте клиент, который не определяет никаких адресов конечных точек.</span><span class="sxs-lookup"><span data-stu-id="db683-135">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="db683-136">Вместо этого используйте конструктор клиента, который принимает в качестве аргумента имя конфигурации.</span><span class="sxs-lookup"><span data-stu-id="db683-136">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="db683-137">Пример:</span><span class="sxs-lookup"><span data-stu-id="db683-137">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="db683-138">Код</span><span class="sxs-lookup"><span data-stu-id="db683-138">Code</span></span>  
 <span data-ttu-id="db683-139">В следующем коде показан базовый клиент WCF, обращающийся к незащищенной конечной точке.</span><span class="sxs-lookup"><span data-stu-id="db683-139">The following code shows a basic WCF client that accesses an unsecured endpoint.</span></span>  
  
 [!code-csharp[C_UnsecuredClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredclient/cs/source.cs#1)]
 [!code-vb[C_UnsecuredClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredclient/vb/source.vb#1)]  
  
### <a name="client-configuration"></a><span data-ttu-id="db683-140">Конфигурация клиента</span><span class="sxs-lookup"><span data-stu-id="db683-140">Client Configuration</span></span>  
 <span data-ttu-id="db683-141">Следующий код служит для настройки клиента.</span><span class="sxs-lookup"><span data-stu-id="db683-141">The following code configures the client.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <basicHttpBinding>  
        <binding name="BasicHttpBinding_ICalculator" >  
          <security mode="None">  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://localhost/Calculator/Unsecured"  
          binding="basicHttpBinding"
          bindingConfiguration="BasicHttpBinding_ICalculator"  
          contract="ICalculator"
          name="BasicHttpBinding_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="db683-142">См. также</span><span class="sxs-lookup"><span data-stu-id="db683-142">See also</span></span>

- [<span data-ttu-id="db683-143">Типовые сценарии безопасности</span><span class="sxs-lookup"><span data-stu-id="db683-143">Common Security Scenarios</span></span>](common-security-scenarios.md)
- [<span data-ttu-id="db683-144">Обзор безопасности</span><span class="sxs-lookup"><span data-stu-id="db683-144">Security Overview</span></span>](security-overview.md)
- <span data-ttu-id="db683-145">[Модель безопасности для Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="db683-145">[Security Model for Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
