---
title: Безопасность транспорта с анонимным клиентом
description: Ознакомьтесь с этим сценарием WCF, который использует безопасность транспорта для проверки подлинности сервера с помощью сертификата, которому доверяет клиент. Проверка подлинности клиента не выполнена.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 056653a5-384e-4a02-ae3c-1b0157d2ccb4
ms.openlocfilehash: 08cfb8c1a5581f17a251224430018764bed80b0f
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245015"
---
# <a name="transport-security-with-an-anonymous-client"></a><span data-ttu-id="fa56d-104">Безопасность транспорта с анонимным клиентом</span><span class="sxs-lookup"><span data-stu-id="fa56d-104">Transport security with an anonymous client</span></span>

<span data-ttu-id="fa56d-105">Этот сценарий Windows Communication Foundation (WCF) использует безопасность транспорта (HTTPS) для обеспечения конфиденциальности и целостности.</span><span class="sxs-lookup"><span data-stu-id="fa56d-105">This Windows Communication Foundation (WCF) scenario uses transport security (HTTPS) to ensure confidentiality and integrity.</span></span> <span data-ttu-id="fa56d-106">Сервер должен пройти проверку подлинности с использованием сертификата SSL, и клиенты должны доверять сертификату сервера.</span><span class="sxs-lookup"><span data-stu-id="fa56d-106">The server must be authenticated with a Secure Sockets Layer (SSL) certificate, and the clients must trust the server's certificate.</span></span> <span data-ttu-id="fa56d-107">Проверка подлинности клиента не выполняется никаким механизмом и, следовательно, клиент является анонимным.</span><span class="sxs-lookup"><span data-stu-id="fa56d-107">The client is not authenticated by any mechanism and is, therefore, anonymous.</span></span>

<span data-ttu-id="fa56d-108">Пример приложения см. в разделе [WS Transport Security](../samples/ws-transport-security.md).</span><span class="sxs-lookup"><span data-stu-id="fa56d-108">For a sample application, see [WS Transport Security](../samples/ws-transport-security.md).</span></span> <span data-ttu-id="fa56d-109">Дополнительные сведения о безопасности транспорта см. в статье [Общие сведения о безопасности транспорта](transport-security-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fa56d-109">For more information about transport security, see [Transport Security Overview](transport-security-overview.md).</span></span>

<span data-ttu-id="fa56d-110">Дополнительные сведения об использовании сертификата со службой см. в разделе [Работа с](working-with-certificates.md) сертификатами и [инструкции. Настройка порта с помощью SSL-сертификата](how-to-configure-a-port-with-an-ssl-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="fa56d-110">For more information about using a certificate with a service, see [Working with Certificates](working-with-certificates.md) and [How to: Configure a Port with an SSL Certificate](how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>

![Использование безопасности транспорта с анонимным клиентом](./media/8fa2e931-0cfb-4aaa-9272-91d652b85d8d.gif)

|<span data-ttu-id="fa56d-112">Характеристика</span><span class="sxs-lookup"><span data-stu-id="fa56d-112">Characteristic</span></span>|<span data-ttu-id="fa56d-113">Описание</span><span class="sxs-lookup"><span data-stu-id="fa56d-113">Description</span></span>|
|--------------------|-----------------|
|<span data-ttu-id="fa56d-114">Режим безопасности</span><span class="sxs-lookup"><span data-stu-id="fa56d-114">Security Mode</span></span>|<span data-ttu-id="fa56d-115">Транспортировка</span><span class="sxs-lookup"><span data-stu-id="fa56d-115">Transport</span></span>|
|<span data-ttu-id="fa56d-116">Совместимость</span><span class="sxs-lookup"><span data-stu-id="fa56d-116">Interoperability</span></span>|<span data-ttu-id="fa56d-117">С существующими веб-службами и клиентами</span><span class="sxs-lookup"><span data-stu-id="fa56d-117">With existing Web services and clients</span></span>|
|<span data-ttu-id="fa56d-118">Проверка подлинности (сервера)</span><span class="sxs-lookup"><span data-stu-id="fa56d-118">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="fa56d-119">Проверка подлинности (клиента)</span><span class="sxs-lookup"><span data-stu-id="fa56d-119">Authentication (Client)</span></span>|<span data-ttu-id="fa56d-120">Да</span><span class="sxs-lookup"><span data-stu-id="fa56d-120">Yes</span></span><br /><br /> <span data-ttu-id="fa56d-121">Уровень приложения (без поддержки WCF)</span><span class="sxs-lookup"><span data-stu-id="fa56d-121">Application level (no WCF support)</span></span>|
|<span data-ttu-id="fa56d-122">Целостность</span><span class="sxs-lookup"><span data-stu-id="fa56d-122">Integrity</span></span>|<span data-ttu-id="fa56d-123">Да</span><span class="sxs-lookup"><span data-stu-id="fa56d-123">Yes</span></span>|
|<span data-ttu-id="fa56d-124">Конфиденциальность</span><span class="sxs-lookup"><span data-stu-id="fa56d-124">Confidentiality</span></span>|<span data-ttu-id="fa56d-125">Да</span><span class="sxs-lookup"><span data-stu-id="fa56d-125">Yes</span></span>|
|<span data-ttu-id="fa56d-126">Транспортировка</span><span class="sxs-lookup"><span data-stu-id="fa56d-126">Transport</span></span>|<span data-ttu-id="fa56d-127">HTTPS</span><span class="sxs-lookup"><span data-stu-id="fa56d-127">HTTPS</span></span>|
|<span data-ttu-id="fa56d-128">Привязка</span><span class="sxs-lookup"><span data-stu-id="fa56d-128">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|

## <a name="service"></a><span data-ttu-id="fa56d-129">Служба</span><span class="sxs-lookup"><span data-stu-id="fa56d-129">Service</span></span>

<span data-ttu-id="fa56d-130">Предполагается, что представленные ниже код и конфигурация выполняются независимо.</span><span class="sxs-lookup"><span data-stu-id="fa56d-130">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="fa56d-131">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="fa56d-131">Do one of the following:</span></span>

- <span data-ttu-id="fa56d-132">Создайте автономную службу, используя код без конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fa56d-132">Create a stand-alone service using the code with no configuration.</span></span>

- <span data-ttu-id="fa56d-133">Создайте службу, используя предоставленную конфигурацию, но не определяйте конечные точки.</span><span class="sxs-lookup"><span data-stu-id="fa56d-133">Create a service using the supplied configuration, but do not define any endpoints.</span></span>

### <a name="code"></a><span data-ttu-id="fa56d-134">Код</span><span class="sxs-lookup"><span data-stu-id="fa56d-134">Code</span></span>

<span data-ttu-id="fa56d-135">В следующем коде показано создание конечной точки с использованием безопасности транспорта:</span><span class="sxs-lookup"><span data-stu-id="fa56d-135">The following code shows how to create an endpoint using transport security:</span></span>

[!code-csharp[c_SecurityScenarios#5](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#5)]
[!code-vb[c_SecurityScenarios#5](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#5)]

### <a name="configuration"></a><span data-ttu-id="fa56d-136">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="fa56d-136">Configuration</span></span>

<span data-ttu-id="fa56d-137">В следующем коде настраивается та же конечная точка с использованием конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fa56d-137">The following code sets up the same endpoint using configuration.</span></span> <span data-ttu-id="fa56d-138">Проверка подлинности клиента не выполняется никаким механизмом и, следовательно, клиент является анонимным.</span><span class="sxs-lookup"><span data-stu-id="fa56d-138">The client is not authenticated by any mechanism, and is therefore anonymous.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.serviceModel>
    <services>
      <service name="ServiceModel.Calculator">
        <endpoint address="https://localhost/Calculator"
                  binding="wsHttpBinding"
                  bindingConfiguration="WSHttpBinding_ICalculator"
                  name="SecuredByTransportEndpoint"
                  contract="ServiceModel.ICalculator" />
      </service>
    </services>
    <bindings>
      <wsHttpBinding>
        <binding name="WSHttpBinding_ICalculator">
          <security mode="Transport">
            <transport clientCredentialType="None" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    <client />
  </system.serviceModel>
</configuration>
```

## <a name="client"></a><span data-ttu-id="fa56d-139">клиент</span><span class="sxs-lookup"><span data-stu-id="fa56d-139">Client</span></span>

<span data-ttu-id="fa56d-140">Предполагается, что представленные ниже код и конфигурация выполняются независимо.</span><span class="sxs-lookup"><span data-stu-id="fa56d-140">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="fa56d-141">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="fa56d-141">Do one of the following:</span></span>

- <span data-ttu-id="fa56d-142">Создайте автономный клиент, используя код (и код клиента).</span><span class="sxs-lookup"><span data-stu-id="fa56d-142">Create a stand-alone client using the code (and client code).</span></span>

- <span data-ttu-id="fa56d-143">Создайте клиент, который не определяет никаких адресов конечных точек.</span><span class="sxs-lookup"><span data-stu-id="fa56d-143">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="fa56d-144">Вместо этого используйте конструктор клиента, который принимает в качестве аргумента имя конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fa56d-144">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="fa56d-145">Пример:</span><span class="sxs-lookup"><span data-stu-id="fa56d-145">For example:</span></span>

     [!code-csharp[C_SecurityScenarios#0](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]

### <a name="code"></a><span data-ttu-id="fa56d-146">Код</span><span class="sxs-lookup"><span data-stu-id="fa56d-146">Code</span></span>

[!code-csharp[c_SecurityScenarios#6](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#6)]
[!code-vb[c_SecurityScenarios#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#6)]

### <a name="configuration"></a><span data-ttu-id="fa56d-147">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="fa56d-147">Configuration</span></span>

<span data-ttu-id="fa56d-148">Вместо кода для настройки службы можно использовать следующую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="fa56d-148">The following configuration can be used instead of the code to set up the service.</span></span>

```xml
<configuration>
  <system.serviceModel>
    <bindings>
      <wsHttpBinding>
        <binding name="WSHttpBinding_ICalculator" >
          <security mode="Transport">
            <transport clientCredentialType="None" />
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

## <a name="see-also"></a><span data-ttu-id="fa56d-149">См. также</span><span class="sxs-lookup"><span data-stu-id="fa56d-149">See also</span></span>

- [<span data-ttu-id="fa56d-150">Обзор безопасности</span><span class="sxs-lookup"><span data-stu-id="fa56d-150">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="fa56d-151">Безопасность транспорта WS</span><span class="sxs-lookup"><span data-stu-id="fa56d-151">WS Transport Security</span></span>](../samples/ws-transport-security.md)
- [<span data-ttu-id="fa56d-152">Общие сведения о безопасности транспорта</span><span class="sxs-lookup"><span data-stu-id="fa56d-152">Transport Security Overview</span></span>](transport-security-overview.md)
- <span data-ttu-id="fa56d-153">[Модель безопасности для Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="fa56d-153">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
