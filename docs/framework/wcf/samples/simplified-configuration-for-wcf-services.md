---
title: Упрощенная конфигурация служб WCF
description: Узнайте, как реализовать и настроить типичную службу и клиент с помощью WCF. Служба взаимодействует с помощью конечной точки, указанной в файле конфигурации.
ms.date: 03/30/2017
ms.assetid: 1e39ec25-18a3-4fdc-b6a3-9dfafbd60112
ms.openlocfilehash: 46a0c878b29de34219413a508799ddaddf507dd8
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246224"
---
# <a name="simplified-configuration-for-wcf-services"></a><span data-ttu-id="ecf3d-104">Упрощенная конфигурация служб WCF</span><span class="sxs-lookup"><span data-stu-id="ecf3d-104">Simplified Configuration for WCF Services</span></span>
<span data-ttu-id="ecf3d-105">В этом примере показано, как реализовать и настроить типичную службу и клиент с помощью Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="ecf3d-105">This sample demonstrates how to implement and configure a typical service and client using Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="ecf3d-106">Этот образец является основой для всех остальных базовых образцов технологий.</span><span class="sxs-lookup"><span data-stu-id="ecf3d-106">This sample is the basis for all other basic technology samples.</span></span>  
  
 <span data-ttu-id="ecf3d-107">Эта служба, которая предоставляет конечную точку для взаимодействия со службой, использует упрощенную конфигурацию в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="ecf3d-107">This service, which exposes an endpoint for communicating with the service, uses the simplified configuration in .NET Framework 4.</span></span> <span data-ttu-id="ecf3d-108">До .NET Framework 4 конечная точка обычно определяется в файле конфигурации (Web.config), как показано в следующем примере кода конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ecf3d-108">Prior to .NET Framework 4, the endpoint is typically defined in a configuration file (Web.config), as shown in the following example configuration code.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright ©) Microsoft Corporation.  All Rights Reserved. -->  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service name="Microsoft.Samples.GettingStarted.CalculatorService"  
               behaviorConfiguration="CalculatorServiceBehavior">  
        <endpoint address="" binding="basicHttpBinding" contract="ICalculator"/>  
        <endpoint address="mex" binding="mexHttpBinding" contract="IMetadataExchange"/>  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="ecf3d-109">В .NET Framework 4 `<service>` элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="ecf3d-109">In .NET Framework 4, the `<service>` element is optional.</span></span> <span data-ttu-id="ecf3d-110">Если конечные точки не заданы в службе, то к службе добавляется конечная точка для каждого базового адреса и реализованного контракта.</span><span class="sxs-lookup"><span data-stu-id="ecf3d-110">When a service does not define any endpoints, an endpoint for each base address and contract implemented are added to the service.</span></span> <span data-ttu-id="ecf3d-111">Базовый адрес добавляется к имени контракта для определения конечной точки, и привязка определяется с помощью схемы адреса.</span><span class="sxs-lookup"><span data-stu-id="ecf3d-111">The base address is appended to the contract name to determine the endpoint and the binding is determined by the address scheme.</span></span> <span data-ttu-id="ecf3d-112">В следующем примере кода показан файл упрощенной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ecf3d-112">The following code example demonstrates a simplified configuration file.</span></span> <span data-ttu-id="ecf3d-113">Как настроено, доступ к службе может осуществляться `http://localhost/servicemodelsamples/service.svc` клиентом на том же компьютере.</span><span class="sxs-lookup"><span data-stu-id="ecf3d-113">As configured, the service can be accessed at `http://localhost/servicemodelsamples/service.svc` by a client on the same computer.</span></span> <span data-ttu-id="ecf3d-114">Чтобы к службе могли получить доступ клиенты на удаленных компьютерах, вместо имени localhost необходимо указать полное имя домена.</span><span class="sxs-lookup"><span data-stu-id="ecf3d-114">For clients on remote computers to access the service, a fully-qualified domain name must be specified instead of localhost.</span></span> <span data-ttu-id="ecf3d-115">По умолчанию служба не предоставляет метаданных.</span><span class="sxs-lookup"><span data-stu-id="ecf3d-115">The service does not expose metadata by default.</span></span> <span data-ttu-id="ecf3d-116">При этом служба включает поведение <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.</span><span class="sxs-lookup"><span data-stu-id="ecf3d-116">As such, the service turns on the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> behavior.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright © Microsoft Corporation.  All Rights Reserved. -->  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
### <a name="to-use-this-sample"></a><span data-ttu-id="ecf3d-117">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="ecf3d-117">To use this sample</span></span>  
  
1. <span data-ttu-id="ecf3d-118">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ecf3d-118">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="ecf3d-119">Чтобы выполнить сборку решения, следуйте инструкциям в разделе [Создание примеров Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ecf3d-119">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="ecf3d-120">Запустите образец, выполнив следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="ecf3d-120">Run the sample by following these steps:</span></span>  
  
    1. <span data-ttu-id="ecf3d-121">Щелкните правой кнопкой мыши проект **службы** и выберите **Назначить запускаемым проектом**, а затем нажмите клавиши **CTRL + F5**.</span><span class="sxs-lookup"><span data-stu-id="ecf3d-121">Right click the **Service** project and select **Set as StartUp project**, then press **Ctrl+F5**.</span></span>  
  
    2. <span data-ttu-id="ecf3d-122">Дождитесь вывода данных на консоли, подтверждающих запуск и выполнение службы.</span><span class="sxs-lookup"><span data-stu-id="ecf3d-122">Wait for the console output confirming that the service is up and running.</span></span>  
  
    3. <span data-ttu-id="ecf3d-123">Щелкните правой кнопкой мыши проект **клиента** и выберите **Назначить запускаемым проектом**, а затем нажмите клавиши **CTRL + F5**.</span><span class="sxs-lookup"><span data-stu-id="ecf3d-123">Right click the **Client** project and select **Set as StartUp project**, then press **Ctrl+F5**.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ecf3d-124">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="ecf3d-124">The samples may already be installed on your computer.</span></span> <span data-ttu-id="ecf3d-125">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="ecf3d-125">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="ecf3d-126">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="ecf3d-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ecf3d-127">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="ecf3d-127">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigSimplificationIn40`  
  
## <a name="see-also"></a><span data-ttu-id="ecf3d-128">См. также</span><span class="sxs-lookup"><span data-stu-id="ecf3d-128">See also</span></span>

- <span data-ttu-id="ecf3d-129">[Образцы управления AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383405(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="ecf3d-129">[AppFabric Management Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383405(v=azure.10))</span></span>
- [<span data-ttu-id="ecf3d-130">Упрощенная конфигурация</span><span class="sxs-lookup"><span data-stu-id="ecf3d-130">Simplified Configuration</span></span>](../simplified-configuration.md)
