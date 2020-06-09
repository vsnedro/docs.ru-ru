---
title: Размещение в службах IIS с использованием встроенного кода
ms.date: 03/30/2017
helpviewer_keywords:
- Web hosted service
- IIS Hosting Using Inline Code Sample [Windows Communication Foundation]
ms.assetid: 56fe3687-a34b-4661-8e30-b33770f413fa
ms.openlocfilehash: 47d056e35b92654c8e47647c7273c5d69b37bd97
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594651"
---
# <a name="iis-hosting-using-inline-code"></a><span data-ttu-id="5df79-102">Размещение в службах IIS с использованием встроенного кода</span><span class="sxs-lookup"><span data-stu-id="5df79-102">IIS Hosting Using Inline Code</span></span>

<span data-ttu-id="5df79-103">Этот образец демонстрирует реализацию службы, размещенной в службах IIS, когда код службы находится в строках файла SVC и компилируется по требованию.</span><span class="sxs-lookup"><span data-stu-id="5df79-103">This sample demonstrates how to implement a service hosted by Internet Information Services (IIS), where the service code is contained in-line in a .svc file and is compiled on demand.</span></span> <span data-ttu-id="5df79-104">Код службы может также быть реализован непосредственно в файлах исходного кода, расположенных в каталоге \App_Code приложения, или он может быть скомпилирован в сборку, развернутую в каталоге \bin.</span><span class="sxs-lookup"><span data-stu-id="5df79-104">Service code can also be implemented directly in source code files located in the application's \App_Code directory, or compiled into assembly deployed in \bin.</span></span> <span data-ttu-id="5df79-105">В этом примере такие приемы не демонстрируются.</span><span class="sxs-lookup"><span data-stu-id="5df79-105">This sample does not demonstrate these techniques.</span></span>

> [!NOTE]
> <span data-ttu-id="5df79-106">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="5df79-106">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5df79-107">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="5df79-107">The samples may already be installed on your computer.</span></span> <span data-ttu-id="5df79-108">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="5df79-108">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="5df79-109">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="5df79-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5df79-110">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="5df79-110">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebHost\InlineCode`

<span data-ttu-id="5df79-111">В этом примере показана типичная служба, которая реализует контракт, определяющий шаблон взаимодействия "запрос-ответ".</span><span class="sxs-lookup"><span data-stu-id="5df79-111">The sample demonstrates a typical service that implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="5df79-112">Служба размещается в службах IIS, а весь код службы полностью содержится в файле Service.svc.</span><span class="sxs-lookup"><span data-stu-id="5df79-112">The service is hosted in IIS and the service code is entirely contained in the Service.svc file.</span></span> <span data-ttu-id="5df79-113">Служба активируется ведущим приложением и компилируется по требованию при поступлении первого сообщения, отправленного этой службе.</span><span class="sxs-lookup"><span data-stu-id="5df79-113">The service is host-activated and compiled on-demand by the first message sent to the service.</span></span> <span data-ttu-id="5df79-114">Предварительная компиляция не требуется.</span><span class="sxs-lookup"><span data-stu-id="5df79-114">There is no pre-compilation necessary.</span></span> <span data-ttu-id="5df79-115">Служба реализует контракт `ICalculator`, как показано в следующем примере кода:</span><span class="sxs-lookup"><span data-stu-id="5df79-115">The service implements an `ICalculator` contract as defined in the following code:</span></span>

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

<span data-ttu-id="5df79-116">Реализация службы выполняет вычисления и возвращает соответствующий результат.</span><span class="sxs-lookup"><span data-stu-id="5df79-116">The service implementation calculates and returns the appropriate result.</span></span>

`<%@ServiceHost language=c# Debug="true" Service="Microsoft.ServiceModel.Samples.CalculatorService" %>`

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

<span data-ttu-id="5df79-117">При выполнении примера запросы и ответы операций отображаются в окне консоли клиента.</span><span class="sxs-lookup"><span data-stu-id="5df79-117">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="5df79-118">Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.</span><span class="sxs-lookup"><span data-stu-id="5df79-118">Press ENTER in the client window to shut down the client.</span></span>

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="5df79-119">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="5df79-119">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="5df79-120">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5df79-120">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="5df79-121">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5df79-121">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="5df79-122">После построения решения запустите программу Setup. bat, чтобы настроить приложение ServiceModelSamples в IIS 7,0.</span><span class="sxs-lookup"><span data-stu-id="5df79-122">After the solution has been built, run setup.bat to set up the ServiceModelSamples Application in IIS 7.0.</span></span> <span data-ttu-id="5df79-123">Теперь каталог ServiceModelSamples должен отображаться как приложение IIS 7,0.</span><span class="sxs-lookup"><span data-stu-id="5df79-123">The ServiceModelSamples directory should now appear as an IIS 7.0 Application.</span></span>

4. <span data-ttu-id="5df79-124">Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5df79-124">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span> <span data-ttu-id="5df79-125">Пример создания клиентского приложения, который может вызывать эту службу, см. в разделе [как создать клиент](../how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="5df79-125">For an example on how to create a client application that can call this service, see [How to: Create a Client](../how-to-create-a-wcf-client.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5df79-126">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="5df79-126">See also</span></span>

- <span data-ttu-id="5df79-127">[Образцы размещения и сохраняемости AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="5df79-127">[AppFabric Hosting and Persistence Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))</span></span>
