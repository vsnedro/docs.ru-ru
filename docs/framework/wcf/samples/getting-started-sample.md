---
title: Пример для начала работы
description: Узнайте, как реализовать типичную службу и обычный клиент с помощью WCF. Этот образец является основой для всех остальных базовых образцов технологий.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- basic samples [WCF], getting started
ms.assetid: 967a3d94-0261-49ff-b85a-20bb07f1af20
ms.openlocfilehash: b23be1b33f227154b916429c063ec4106229bb3c
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246237"
---
# <a name="getting-started-sample"></a><span data-ttu-id="e8966-104">Пример для начала работы</span><span class="sxs-lookup"><span data-stu-id="e8966-104">Getting Started Sample</span></span>

<span data-ttu-id="e8966-105">В начало работы примере демонстрируется реализация типичной службы и стандартного клиента с помощью Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="e8966-105">The Getting Started sample demonstrates how to implement a typical service and a typical client using Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="e8966-106">Этот образец является основой для всех остальных базовых образцов технологий.</span><span class="sxs-lookup"><span data-stu-id="e8966-106">This sample is the basis for all other basic technology samples.</span></span>

> [!NOTE]
> <span data-ttu-id="e8966-107">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="e8966-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e8966-108">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="e8966-108">The samples may already be installed on your computer.</span></span> <span data-ttu-id="e8966-109">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="e8966-109">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="e8966-110">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="e8966-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e8966-111">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="e8966-111">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\GettingStarted\GettingStarted`

<span data-ttu-id="e8966-112">Служба описывает операции, выполняемые ею в контракте службы, который она открыто предоставляет как метаданные.</span><span class="sxs-lookup"><span data-stu-id="e8966-112">The service describes the operations it performs in a service contract that it exposes publicly as metadata.</span></span> <span data-ttu-id="e8966-113">Служба также содержит код для реализации операций.</span><span class="sxs-lookup"><span data-stu-id="e8966-113">The service also contains the code to implement the operations.</span></span>

<span data-ttu-id="e8966-114">Клиент содержит определение контракта службы и прокси-класс для доступа к службе.</span><span class="sxs-lookup"><span data-stu-id="e8966-114">The client contains a definition of the service contract and a proxy class for accessing the service.</span></span> <span data-ttu-id="e8966-115">Код прокси-сервера создается на основе метаданных службы с помощью [средства служебной программы метаданных ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="e8966-115">The proxy code is generated from the service metadata using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>

<span data-ttu-id="e8966-116">В Windows Vista служба размещается в службе активации Windows (WAS).</span><span class="sxs-lookup"><span data-stu-id="e8966-116">On Windows Vista, the service is hosted in the Windows Activation Service (WAS).</span></span> <span data-ttu-id="e8966-117">В Windows XP и Windows Server 2003 она размещена на службы IIS (IIS) и ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="e8966-117">On Windows XP and Windows Server 2003, it is hosted by Internet Information Services (IIS) and ASP.NET.</span></span> <span data-ttu-id="e8966-118">Размещение службы в IIS или WAS позволяет активировать службу автоматически при первом доступе к ней.</span><span class="sxs-lookup"><span data-stu-id="e8966-118">Hosting a service in IIS or WAS allows the service to be activated automatically when it is accessed for the first time.</span></span>

> [!NOTE]
> <span data-ttu-id="e8966-119">Если вы предпочитаете приступить к работе с примером, в котором размещена служба, в консольном приложении, а не IIS, см. пример с помощью [узла для самостоятельного размещения](self-host.md) .</span><span class="sxs-lookup"><span data-stu-id="e8966-119">If you would prefer to get started with a sample that hosts the service in a console application instead of IIS, see the [Self-Host](self-host.md) sample.</span></span>

<span data-ttu-id="e8966-120">Служба и клиент указывают данные для доступа в параметрах файла конфигурации, что обеспечивает гибкость при развертывании.</span><span class="sxs-lookup"><span data-stu-id="e8966-120">The service and client specify access details in configuration file settings, which provide flexibility at the time of deployment.</span></span> <span data-ttu-id="e8966-121">Эти данные включают определение конечной точки, задающей адрес, привязку и контракт.</span><span class="sxs-lookup"><span data-stu-id="e8966-121">This includes an endpoint definition that specifies an address, binding, and contract.</span></span> <span data-ttu-id="e8966-122">Привязка определяет транспорт и детали обеспечения безопасности, касающиеся доступа к службе.</span><span class="sxs-lookup"><span data-stu-id="e8966-122">The binding specifies transport and security details for how the service is to be accessed.</span></span>

<span data-ttu-id="e8966-123">Служба настраивает среду выполнения на публикацию ее метаданных.</span><span class="sxs-lookup"><span data-stu-id="e8966-123">The service configures a run-time behavior to publish its metadata.</span></span>

<span data-ttu-id="e8966-124">Служба реализует контракт, определяющий шаблон взаимодействия "запрос-ответ".</span><span class="sxs-lookup"><span data-stu-id="e8966-124">The service implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="e8966-125">Контракт определяется интерфейсом `ICalculator`, который предоставляет математические операции (сложение, вычитание, умножение и деление).</span><span class="sxs-lookup"><span data-stu-id="e8966-125">The contract is defined by the `ICalculator` interface, which exposes math operations (add, subtract, multiply, and divide).</span></span> <span data-ttu-id="e8966-126">Клиент осуществляет вызовы заданной математической операции, а служба отправляет в ответ результат.</span><span class="sxs-lookup"><span data-stu-id="e8966-126">The client makes requests to a given math operation and the service replies with the result.</span></span> <span data-ttu-id="e8966-127">Служба реализует контракт `ICalculator`, определенный в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="e8966-127">The service implements an `ICalculator` contract that is defined in the following code.</span></span>

```vb
' Define a service contract.
    <ServiceContract(Namespace:="http://Microsoft.Samples.GettingStarted")>
     Public Interface ICalculator
        <OperationContract()>
        Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()>
        Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()>
        Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()>
        Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double
    End Interface
```

```csharp
// Define a service contract.
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface ICalculator
{
    [OperationContract]
    double Add(double n1, double n2);
    [OperationContract]
    double Subtract(double n1, double n2);
    [OperationContract]
    double Multiply(double n1, double n2);
    [OperationContract]
    double Divide(double n1, double n2);
}
```

<span data-ttu-id="e8966-128">Реализация службы вычисляет и возвращает соответствующий результат, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="e8966-128">The service implementation calculates and returns the appropriate result, as shown in the following example code.</span></span>

```vb
' Service class which implements the service contract.
Public Class CalculatorService
Implements ICalculator
Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Add
Return n1 + n2
End Function

Public Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Subtract
Return n1 - n2
End Function

Public Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Multiply
Return n1 * n2
End Function

Public Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Divide
Return n1 / n2
End Function
End Class
```

```csharp
// Service class that implements the service contract.
public class CalculatorService : ICalculator
{
    public double Add(double n1, double n2)
    {
        return n1 + n2;
    }
    public double Subtract(double n1, double n2)
    {
        return n1 - n2;
    }
    public double Multiply(double n1, double n2)
    {
        return n1 * n2;
    }
    public double Divide(double n1, double n2)
    {
        return n1 / n2;
    }
}
```

<span data-ttu-id="e8966-129">Служба предоставляет конечную точку для взаимодействия с ней; конечная точка определяется в файле конфигурации (Web.config). См. следующий образец конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e8966-129">The service exposes an endpoint for communicating with the service, defined using a configuration file (Web.config), as shown in the following sample configuration.</span></span>

```xaml
<services>
    <service
        name="Microsoft.ServiceModel.Samples.CalculatorService"
        behaviorConfiguration="CalculatorServiceBehavior">
        <!-- ICalculator is exposed at the base address provided by
         host: http://localhost/servicemodelsamples/service.svc.  -->
       <endpoint address=""
              binding="wsHttpBinding"
              contract="Microsoft.ServiceModel.Samples.ICalculator" />
       ...
    </service>
</services>
```

<span data-ttu-id="e8966-130">Служба предоставляет конечную точку по базовому адресу, который предоставляется узлом IIS или WAS.</span><span class="sxs-lookup"><span data-stu-id="e8966-130">The service exposes the endpoint at the base address provided by the IIS or WAS host.</span></span> <span data-ttu-id="e8966-131">Привязка настраивается с использованием стандартного объекта <xref:System.ServiceModel.WSHttpBinding>, обеспечивающего взаимодействие по протоколу HTTP и стандартному протоколу веб-служб для адресации и безопасности.</span><span class="sxs-lookup"><span data-stu-id="e8966-131">The binding is configured with a standard <xref:System.ServiceModel.WSHttpBinding>, which provides HTTP communication and standard Web service protocols for addressing and security.</span></span> <span data-ttu-id="e8966-132">Контрактом является интерфейс `ICalculator`, реализуемый службой.</span><span class="sxs-lookup"><span data-stu-id="e8966-132">The contract is the `ICalculator` implemented by the service.</span></span>

<span data-ttu-id="e8966-133">Как настроено, доступ к службе может осуществляться `http://localhost/servicemodelsamples/service.svc` клиентом на том же компьютере.</span><span class="sxs-lookup"><span data-stu-id="e8966-133">As configured, the service can be accessed at `http://localhost/servicemodelsamples/service.svc` by a client on the same computer.</span></span> <span data-ttu-id="e8966-134">Чтобы к службе могли получить доступ клиенты на удаленных компьютерах, вместо имени localhost необходимо указать полное имя домена.</span><span class="sxs-lookup"><span data-stu-id="e8966-134">For clients on remote computers to access the service, a fully-qualified domain name must be specified instead of localhost.</span></span>

<span data-ttu-id="e8966-135">По умолчанию платформа не предоставляет никаких метаданных.</span><span class="sxs-lookup"><span data-stu-id="e8966-135">The framework does not expose metadata by default.</span></span> <span data-ttu-id="e8966-136">Таким образом, служба включает <xref:System.ServiceModel.Description.ServiceMetadataBehavior> и предоставляет конечную точку обмена метаданными (MEX) в `http://localhost/servicemodelsamples/service.svc/mex` .</span><span class="sxs-lookup"><span data-stu-id="e8966-136">As such, the service turns on the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> and exposes a metadata exchange (MEX) endpoint at `http://localhost/servicemodelsamples/service.svc/mex`.</span></span> <span data-ttu-id="e8966-137">Это демонстрируется в следующей конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e8966-137">The following configuration demonstrates this.</span></span>

```xaml
<system.serviceModel>
  <services>
    <service
        name="Microsoft.ServiceModel.Samples.CalculatorService"
        behaviorConfiguration="CalculatorServiceBehavior">
      ...
      <!-- the mex endpoint is exposed at
       http://localhost/servicemodelsamples/service.svc/mex -->
      <endpoint address="mex"
                binding="mexHttpBinding"
                contract="IMetadataExchange" />
    </service>
  </services>

  <!--For debugging purposes set the includeExceptionDetailInFaults
   attribute to true-->
  <behaviors>
    <serviceBehaviors>
      <behavior name="CalculatorServiceBehavior">
        <serviceMetadata httpGetEnabled="True"/>
        <serviceDebug includeExceptionDetailInFaults="False" />
      </behavior>
    </serviceBehaviors>
  </behaviors>
</system.serviceModel>
```

<span data-ttu-id="e8966-138">Клиент обменивается данными с использованием заданного типа контракта с помощью клиентского класса, созданного [служебной программой метаданных ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="e8966-138">The client communicates using a given contract type by using a client class that is generated by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="e8966-139">Этот созданный клиент содержится в файлах generatedClient.cs или generatedClient.vb.</span><span class="sxs-lookup"><span data-stu-id="e8966-139">This generated client is contained in the file generatedClient.cs or generatedClient.vb.</span></span> <span data-ttu-id="e8966-140">Это средство извлекает метаданные для заданной службы и создает клиент, который будет использоваться клиентским приложением для взаимодействия по заданному контракту.</span><span class="sxs-lookup"><span data-stu-id="e8966-140">This utility retrieves metadata for a given service and generates a client for use by the client application to communicate using a given contract type.</span></span> <span data-ttu-id="e8966-141">Размещенная служба должна быть доступна для создания кода клиента, поскольку служба используется для извлечения обновленных метаданных.</span><span class="sxs-lookup"><span data-stu-id="e8966-141">The hosted service must be available to generate the client code, because the service is used to retrieve the updated metadata.</span></span>

 <span data-ttu-id="e8966-142">Чтобы создать типизированный прокси, выполните следующую команду из командной строки SDK в каталоге клиента.</span><span class="sxs-lookup"><span data-stu-id="e8966-142">Run the following command from the SDK command prompt in the client directory to generate the typed proxy:</span></span>

```console
svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /out:generatedClient.cs
```

<span data-ttu-id="e8966-143">Чтобы создать клиент на языке Visual Basic, введите следующую команду в командной строке SDK.</span><span class="sxs-lookup"><span data-stu-id="e8966-143">To generate client in Visual Basic type the following from the SDK command prompt:</span></span>

`Svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /l:vb /out:generatedClient.vb`

<span data-ttu-id="e8966-144">С помощью созданного клиента можно получить доступ к заданной конечной точке службы, настроив соответствующий адрес и привязку.</span><span class="sxs-lookup"><span data-stu-id="e8966-144">By using the generated client, the client can access a given service endpoint by configuring the appropriate address and binding.</span></span> <span data-ttu-id="e8966-145">Как и служба, клиент использует файл конфигурации (App.config), чтобы задать конечную точку для взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="e8966-145">Like the service, the client uses a configuration file (App.config) to specify the endpoint with which it wants to communicate.</span></span> <span data-ttu-id="e8966-146">Конфигурация конечной точки клиента состоит из абсолютного адреса конечной точки службы, привязки и контракта, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="e8966-146">The client endpoint configuration consists of an absolute address for the service endpoint, the binding, and the contract, as shown in the following example.</span></span>

```xaml
<client>
     <endpoint
         address="http://localhost/servicemodelsamples/service.svc"
         binding="wsHttpBinding"
         contract=" Microsoft.ServiceModel.Samples.ICalculator" />
</client>
```

<span data-ttu-id="e8966-147">Реализация клиента создает клиент и использует интерфейс, чтобы начать взаимодействие со службой, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="e8966-147">The client implementation instantiates the client and uses the typed interface to begin communicating with the service, as shown in the following example code.</span></span>

```vb
' Create a client
Dim client As New CalculatorClient()

' Call the Add service operation.
            Dim value1 = 100.0R
            Dim value2 = 15.99R
            Dim result = client.Add(value1, value2)
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)

' Call the Subtract service operation.
value1 = 145.00R
value2 = 76.54R
result = client.Subtract(value1, value2)
Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result)

' Call the Multiply service operation.
value1 = 9.00R
value2 = 81.25R
result = client.Multiply(value1, value2)
Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result)

' Call the Divide service operation.
value1 = 22.00R
value2 = 7.00R
result = client.Divide(value1, value2)
Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result)

'Closing the client gracefully closes the connection and cleans up resources
```

```csharp
// Create a client.
CalculatorClient client = new CalculatorClient();

// Call the Add service operation.
double value1 = 100.00D;
double value2 = 15.99D;
double result = client.Add(value1, value2);
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);

// Call the Subtract service operation.
value1 = 145.00D;
value2 = 76.54D;
result = client.Subtract(value1, value2);
Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);

// Call the Multiply service operation.
value1 = 9.00D;
value2 = 81.25D;
result = client.Multiply(value1, value2);
Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);

// Call the Divide service operation.
value1 = 22.00D;
value2 = 7.00D;
result = client.Divide(value1, value2);
Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);

//Closing the client releases all communication resources.
client.Close();
```

<span data-ttu-id="e8966-148">При выполнении примера запросы и ответы операций отображаются в окне консоли клиента.</span><span class="sxs-lookup"><span data-stu-id="e8966-148">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="e8966-149">Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.</span><span class="sxs-lookup"><span data-stu-id="e8966-149">Press ENTER in the client window to shut down the client.</span></span>

```output
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

<span data-ttu-id="e8966-150">В образце "Начало работы" показан стандартный способ создания службы и клиента.</span><span class="sxs-lookup"><span data-stu-id="e8966-150">The Getting Started sample shows the standard way to create a service and client.</span></span> <span data-ttu-id="e8966-151">Другой [базовый](basic-sample.md) пример сборки этого образца для демонстрации конкретных функций продукта.</span><span class="sxs-lookup"><span data-stu-id="e8966-151">The other [Basic](basic-sample.md) build on this sample to demonstrate specific product features.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="e8966-152">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="e8966-152">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="e8966-153">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e8966-153">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="e8966-154">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e8966-154">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="e8966-155">Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e8966-155">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e8966-156">См. также</span><span class="sxs-lookup"><span data-stu-id="e8966-156">See also</span></span>

- [<span data-ttu-id="e8966-157">Практическое руководство. Размещение службы WCF в управляемом приложении</span><span class="sxs-lookup"><span data-stu-id="e8966-157">How to: Host a WCF Service in a Managed Application</span></span>](../how-to-host-a-wcf-service-in-a-managed-application.md)
- [<span data-ttu-id="e8966-158">Практическое руководство. Размещение службы WCF в IIS</span><span class="sxs-lookup"><span data-stu-id="e8966-158">How to: Host a WCF Service in IIS</span></span>](../feature-details/how-to-host-a-wcf-service-in-iis.md)
