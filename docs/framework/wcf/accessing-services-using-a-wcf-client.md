---
title: Обращение к службам с использованием клиента WCF
description: Узнайте, как создать прокси клиента WCF для службы WCF. Клиентское приложение использует клиентский прокси для взаимодействия со службой.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clients [WCF], consuming services
ms.assetid: d780af9f-73c5-42db-9e52-077a5e4de7fe
ms.openlocfilehash: 25446a89a0b5657d32d77e2d0d57f58f36bed71b
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245548"
---
# <a name="accessing-services-using-a-wcf-client"></a><span data-ttu-id="cca88-104">Обращение к службам с использованием клиента WCF</span><span class="sxs-lookup"><span data-stu-id="cca88-104">Accessing Services Using a WCF Client</span></span>

<span data-ttu-id="cca88-105">После создания службы следующим шагом является создание прокси клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="cca88-105">After you create a service, the next step is to create a WCF client proxy.</span></span> <span data-ttu-id="cca88-106">Клиентское приложение использует клиентский прокси-сервер WCF для взаимодействия со службой.</span><span class="sxs-lookup"><span data-stu-id="cca88-106">A client application uses the WCF client proxy to communicate with the service.</span></span> <span data-ttu-id="cca88-107">Клиентские приложения обычно импортируют метаданные службы для создания клиентского кода WCF, который можно использовать для вызова службы.</span><span class="sxs-lookup"><span data-stu-id="cca88-107">Client applications usually import a service's metadata to generate WCF client code that can be used to invoke the service.</span></span>

 <span data-ttu-id="cca88-108">Ниже приведены основные шаги для создания клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="cca88-108">The basic steps for creating a WCF client include the following:</span></span>

1. <span data-ttu-id="cca88-109">Скомпилируйте код службы.</span><span class="sxs-lookup"><span data-stu-id="cca88-109">Compile the service code.</span></span>

2. <span data-ttu-id="cca88-110">Создайте прокси клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="cca88-110">Generate the WCF client proxy.</span></span>

3. <span data-ttu-id="cca88-111">Создайте экземпляр клиентского прокси-класса WCF.</span><span class="sxs-lookup"><span data-stu-id="cca88-111">Instantiate the WCF client proxy.</span></span>

<span data-ttu-id="cca88-112">Клиентский прокси-сервер WCF может быть создан вручную с помощью служебной программы метаданных модели службы (SvcUtil.exe) Дополнительные сведения см. в разделе [средство служебной программы метаданных ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="cca88-112">The WCF client proxy can be generated manually by using the Service Model Metadata Utility Tool (SvcUtil.exe) for more information see, [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="cca88-113">Клиентский прокси-сервер WCF также может быть создан в Visual Studio с помощью функции **Добавление ссылки на службу** .</span><span class="sxs-lookup"><span data-stu-id="cca88-113">The WCF client proxy can also be generated within Visual Studio using the **Add Service Reference**  feature.</span></span> <span data-ttu-id="cca88-114">Для создания клиентского прокси-класса WCF любым методом выбранная служба должна быть запущена.</span><span class="sxs-lookup"><span data-stu-id="cca88-114">To generate the WCF client proxy using either method the service must be running.</span></span> <span data-ttu-id="cca88-115">Если служба размещается резидентно, то необходимо запустить узел.</span><span class="sxs-lookup"><span data-stu-id="cca88-115">If the service is self-hosted you must run the host.</span></span> <span data-ttu-id="cca88-116">Если служба размещена на веб-сервере IIS/WAS, то больше ничего делать не нужно.</span><span class="sxs-lookup"><span data-stu-id="cca88-116">If the service is hosted in IIS/WAS you do not need to do anything else.</span></span>

## <a name="servicemodel-metadata-utility-tool"></a><span data-ttu-id="cca88-117">Средство ServiceModel Metadata Utility Tool</span><span class="sxs-lookup"><span data-stu-id="cca88-117">ServiceModel Metadata Utility Tool</span></span>
 <span data-ttu-id="cca88-118">[Средство служебной программы метаданных ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) — это программа командной строки для создания кода из метаданных.</span><span class="sxs-lookup"><span data-stu-id="cca88-118">The [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) is a command-line tool for generating code from metadata.</span></span> <span data-ttu-id="cca88-119">Ниже приведен пример базовой команды Svcutil.exe.</span><span class="sxs-lookup"><span data-stu-id="cca88-119">The following use is an example of a basic Svcutil.exe command.</span></span>

```console
Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
```

 <span data-ttu-id="cca88-120">Средство Svcutil.exe можно также использовать с файлами языков WSDL (язык описания веб-служб) и XSD (язык определения схемы XML) в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="cca88-120">Alternatively, you can use Svcutil.exe with Web Services Description Language (WSDL) and XML Schema definition language (XSD) files on the file system.</span></span>

```console
Svcutil.exe <list of WSDL and XSD files on file system>
```

 <span data-ttu-id="cca88-121">Результатом является файл кода, содержащий клиентский код WCF, который клиентское приложение может использовать для вызова службы.</span><span class="sxs-lookup"><span data-stu-id="cca88-121">The result is a code file that contains WCF client code that the client application can use to invoke the service.</span></span>

 <span data-ttu-id="cca88-122">Кроме того, с помощью этого средства можно создавать файлы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="cca88-122">You can also use the tool to generate configuration files.</span></span>

```console
Svcutil.exe <file1 [,file2]>
```

 <span data-ttu-id="cca88-123">Если задано только одно имя файла, это имя выходного файла.</span><span class="sxs-lookup"><span data-stu-id="cca88-123">If only one file name is given, that is the name of the output file.</span></span> <span data-ttu-id="cca88-124">Если задано два имени файла, то первый файл является исходным файлом конфигурации, содержимое которого объединяется с создаваемой конфигурацией и записывается во второй файл.</span><span class="sxs-lookup"><span data-stu-id="cca88-124">If two file names are given, then the first file is an input configuration file whose contents are merged with the generated configuration and written out into the second file.</span></span> <span data-ttu-id="cca88-125">Дополнительные сведения о конфигурации см. в разделе [Настройка привязок для служб](configuring-bindings-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="cca88-125">For more information about configuration, see [Configuring Bindings for Services](configuring-bindings-for-wcf-services.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cca88-126">Незащищенные запросы метаданных представляют определенную угрозу, подобно незащищенным сетевым запросам. Если нет уверенности, что конечная точка, с которой осуществляется взаимодействие, является той точкой, за которую она себя выдает, получаемая информация может представлять собой метаданные вредоносной службы.</span><span class="sxs-lookup"><span data-stu-id="cca88-126">Unsecured metadata requests pose certain risks in the same way that any unsecured network request does: If you are not certain that the endpoint you are communicating with is who it says it is, the information you retrieve might be metadata from a malicious service.</span></span>

## <a name="add-service-reference-in-visual-studio"></a><span data-ttu-id="cca88-127">Функция «Добавить ссылку на службу» в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cca88-127">Add Service Reference in Visual Studio</span></span>

 <span data-ttu-id="cca88-128">После запуска службы щелкните правой кнопкой мыши проект, который будет содержать прокси клиента WCF, и выберите пункт **Добавить**  >  **ссылку на службу**.</span><span class="sxs-lookup"><span data-stu-id="cca88-128">With the service running, right click the project that will contain the WCF client proxy and select **Add** > **Service Reference**.</span></span> <span data-ttu-id="cca88-129">В **диалоговом окне Добавление ссылки на службу**введите URL-адрес службы, которую необходимо вызвать, и нажмите кнопку **Go (переход** ).</span><span class="sxs-lookup"><span data-stu-id="cca88-129">In the **Add Service Reference Dialog**, type in the URL to the service you want to call and click the **Go** button.</span></span> <span data-ttu-id="cca88-130">В диалоговом окне отобразится список доступных служб по указанному адресу.</span><span class="sxs-lookup"><span data-stu-id="cca88-130">The dialog will display a list of services available at the address you specify.</span></span> <span data-ttu-id="cca88-131">Дважды щелкните службу, чтобы просмотреть доступные контракты и операции, укажите пространство имен для созданного кода и нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="cca88-131">Double click the service to see the contracts and operations available, specify a namespace for the generated code, and click the **OK** button.</span></span>

## <a name="example"></a><span data-ttu-id="cca88-132">Пример</span><span class="sxs-lookup"><span data-stu-id="cca88-132">Example</span></span>
 <span data-ttu-id="cca88-133">В следующем примере кода показан созданный контракт службы.</span><span class="sxs-lookup"><span data-stu-id="cca88-133">The following code example shows a service contract created for a service.</span></span>

```csharp
// Define a service contract.
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface ICalculator
{
    [OperationContract]
    double Add(double n1, double n2);
    // Other methods are not shown here.
}
```

```vb
' Define a service contract.
<ServiceContract(Namespace:="http://Microsoft.ServiceModel.Samples")> _
Public Interface ICalculator
    <OperationContract()>  _
    Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
    ' Other methods are not shown here.
End Interface
```

 <span data-ttu-id="cca88-134">Средство служебной программы для метаданных ServiceModel и **Добавление ссылки на службу** в Visual Studio создает следующий класс клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="cca88-134">The ServiceModel Metadata utility tool and **Add Service Reference** in Visual Studio generates the following WCF client class.</span></span> <span data-ttu-id="cca88-135">Класс наследует универсальному классу <xref:System.ServiceModel.ClientBase%601> и реализует интерфейс `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="cca88-135">The class inherits from the generic <xref:System.ServiceModel.ClientBase%601> class and implements the `ICalculator` interface.</span></span> <span data-ttu-id="cca88-136">Кроме того, это средство создает интерфейс `ICalculator` (не показан в этом примере).</span><span class="sxs-lookup"><span data-stu-id="cca88-136">The tool also generates the `ICalculator` interface (not shown here).</span></span>

```csharp
public partial class CalculatorClient : System.ServiceModel.ClientBase<ICalculator>, ICalculator
{
    public CalculatorClient()
    {}

    public CalculatorClient(string endpointConfigurationName) :
            base(endpointConfigurationName)
    {}

    public CalculatorClient(string endpointConfigurationName, string remoteAddress) :
            base(endpointConfigurationName, remoteAddress)
    {}

    public CalculatorClient(string endpointConfigurationName,
        System.ServiceModel.EndpointAddress remoteAddress) :
            base(endpointConfigurationName, remoteAddress)
    {}

    public CalculatorClient(System.ServiceModel.Channels.Binding binding,
        System.ServiceModel.EndpointAddress remoteAddress) :
            base(binding, remoteAddress)
    {}

    public double Add(double n1, double n2)
    {
        return base.Channel.Add(n1, n2);
    }
}
```

```vb
Partial Public Class CalculatorClient
    Inherits System.ServiceModel.ClientBase(Of ICalculator)
    Implements ICalculator

    Public Sub New()
        MyBase.New
    End Sub

    Public Sub New(ByVal endpointConfigurationName As String)
        MyBase.New(endpointConfigurationName)
    End Sub

    Public Sub New(ByVal endpointConfigurationName As String, ByVal remoteAddress As String)
        MyBase.New(endpointConfigurationName, remoteAddress)
    End Sub

    Public Sub New(ByVal endpointConfigurationName As String,
        ByVal remoteAddress As System.ServiceModel.EndpointAddress)
        MyBase.New(endpointConfigurationName, remoteAddress)
    End Sub

    Public Sub New(ByVal binding As System.ServiceModel.Channels.Binding,
        ByVal remoteAddress As System.ServiceModel.EndpointAddress)
        MyBase.New(binding, remoteAddress)
    End Sub

    Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
        Implements ICalculator.Add
        Return MyBase.Channel.Add(n1, n2)
    End Function
End Class
```

## <a name="using-the-wcf-client"></a><span data-ttu-id="cca88-137">Использование клиента WCF</span><span class="sxs-lookup"><span data-stu-id="cca88-137">Using the WCF Client</span></span>
 <span data-ttu-id="cca88-138">Чтобы использовать клиент WCF, создайте экземпляр клиента WCF, а затем вызовите его методы, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="cca88-138">To use the WCF client, create an instance of the WCF client, and then call its methods, as shown in the following code.</span></span>

```csharp
// Create a client object with the given client endpoint configuration.
CalculatorClient calcClient = new CalculatorClient("CalculatorEndpoint"));
// Call the Add service operation.
double value1 = 100.00D;
double value2 = 15.99D;
double result = calcClient.Add(value1, value2);
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);
```

```vb
' Create a client object with the given client endpoint configuration.
Dim calcClient As CalculatorClient = _
New CalculatorClient("CalculatorEndpoint")

' Call the Add service operation.
Dim value1 As Double = 100.00D
Dim value2 As Double = 15.99D
Dim result As Double = calcClient.Add(value1, value2)
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)
```

## <a name="debugging-exceptions-thrown-by-a-client"></a><span data-ttu-id="cca88-139">Отладка создаваемых клиентом исключений</span><span class="sxs-lookup"><span data-stu-id="cca88-139">Debugging Exceptions Thrown by a Client</span></span>

<span data-ttu-id="cca88-140">Многие исключения, вызванные клиентом WCF, вызваны исключением в службе.</span><span class="sxs-lookup"><span data-stu-id="cca88-140">Many exceptions thrown by a WCF client are caused by an exception on the service.</span></span> <span data-ttu-id="cca88-141">Ниже приведены некоторые примеры.</span><span class="sxs-lookup"><span data-stu-id="cca88-141">Some examples of this are:</span></span>

- <span data-ttu-id="cca88-142"><xref:System.Net.Sockets.SocketException>: существующее подключение было принудительно закрыто удаленным узлом.</span><span class="sxs-lookup"><span data-stu-id="cca88-142"><xref:System.Net.Sockets.SocketException>: An existing connection was forcibly closed by the remote host.</span></span>

- <span data-ttu-id="cca88-143"><xref:System.ServiceModel.CommunicationException>: базовое подключение было неожиданно закрыто.</span><span class="sxs-lookup"><span data-stu-id="cca88-143"><xref:System.ServiceModel.CommunicationException>: The underlying connection was closed unexpectedly.</span></span>

- <span data-ttu-id="cca88-144"><xref:System.ServiceModel.CommunicationObjectAbortedException>: подключение к сокету было прервано.</span><span class="sxs-lookup"><span data-stu-id="cca88-144"><xref:System.ServiceModel.CommunicationObjectAbortedException>: The socket connection was aborted.</span></span> <span data-ttu-id="cca88-145">Это может быть вызвано ошибкой при обработке сообщения, истечением времени ожидания на удаленном узле или проблемой с соответствующим сетевым ресурсом.</span><span class="sxs-lookup"><span data-stu-id="cca88-145">This could be caused by an error processing your message, a receive time-out being exceeded by the remote host, or an underlying network resource issue.</span></span>

<span data-ttu-id="cca88-146">Если происходят исключения этих типов, лучшим решением проблемы является включение трассировки на стороне службы и определение исключения, которое там произошло.</span><span class="sxs-lookup"><span data-stu-id="cca88-146">When these types of exceptions occur, the best way to solve the problem is to turn on tracing on the service side and determine what exception occurred there.</span></span> <span data-ttu-id="cca88-147">Дополнительные сведения о трассировке см. в разделе [Трассировка](./diagnostics/tracing/index.md) и [Использование трассировки для устранения неполадок в приложении](./diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).</span><span class="sxs-lookup"><span data-stu-id="cca88-147">For more information about tracing, see [Tracing](./diagnostics/tracing/index.md) and [Using Tracing to Troubleshoot Your Application](./diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cca88-148">См. также</span><span class="sxs-lookup"><span data-stu-id="cca88-148">See also</span></span>

- [<span data-ttu-id="cca88-149">Практическое руководство. Создание клиента</span><span class="sxs-lookup"><span data-stu-id="cca88-149">How to: Create a Client</span></span>](how-to-create-a-wcf-client.md)
- [<span data-ttu-id="cca88-150">Практическое руководство. Доступ к службам с дуплексным контрактом</span><span class="sxs-lookup"><span data-stu-id="cca88-150">How to: Access Services with a Duplex Contract</span></span>](./feature-details/how-to-access-services-with-a-duplex-contract.md)
- [<span data-ttu-id="cca88-151">Практическое руководство. Асинхронный вызов операций службы</span><span class="sxs-lookup"><span data-stu-id="cca88-151">How to: Call Service Operations Asynchronously</span></span>](./feature-details/how-to-call-wcf-service-operations-asynchronously.md)
- [<span data-ttu-id="cca88-152">Практическое руководство. Доступ к службам с односторонним контрактом и контрактом типа "запрос — ответ"</span><span class="sxs-lookup"><span data-stu-id="cca88-152">How to: Access Services with One-Way and Request-Reply Contracts</span></span>](./feature-details/how-to-access-wcf-services-with-one-way-and-request-reply-contracts.md)
- [<span data-ttu-id="cca88-153">Практическое руководство. Доступ к службе WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="cca88-153">How to: Access a WSE 3.0 Service</span></span>](./feature-details/how-to-access-a-wse-3-0-service-with-a-wcf-client.md)
- [<span data-ttu-id="cca88-154">Основные сведения о созданном коде клиента</span><span class="sxs-lookup"><span data-stu-id="cca88-154">Understanding Generated Client Code</span></span>](./feature-details/understanding-generated-client-code.md)
- [<span data-ttu-id="cca88-155">Практическое руководство. Сокращение времени запуска клиентских приложений WCF с использованием XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="cca88-155">How to: Improve the Startup Time of WCF Client Applications using the XmlSerializer</span></span>](./feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md)
- [<span data-ttu-id="cca88-156">Задание поведения клиента во время выполнения</span><span class="sxs-lookup"><span data-stu-id="cca88-156">Specifying Client Run-Time Behavior</span></span>](specifying-client-run-time-behavior.md)
- [<span data-ttu-id="cca88-157">Настройка поведений клиентов</span><span class="sxs-lookup"><span data-stu-id="cca88-157">Configuring Client Behaviors</span></span>](configuring-client-behaviors.md)
