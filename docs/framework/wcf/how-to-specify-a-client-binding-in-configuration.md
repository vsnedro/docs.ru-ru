---
title: Практическое руководство. Указание привязки клиента в конфигурации
description: Узнайте, как декларативно указать привязку для клиента WCF в файле конфигурации. Клиент обращается к службе в этом примере.
ms.date: 03/30/2017
ms.assetid: 4a7c79aa-50ee-4991-891e-adc0599323a7
ms.openlocfilehash: e8a552211b28c1323b2afd595c5b060db6b2824a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236511"
---
# <a name="how-to-specify-a-client-binding-in-configuration"></a><span data-ttu-id="28e31-104">Практическое руководство. Указание привязки клиента в конфигурации</span><span class="sxs-lookup"><span data-stu-id="28e31-104">How to: Specify a Client Binding in Configuration</span></span>

<span data-ttu-id="28e31-105">В этом примере создается клиентское консольное приложение, предназначенное для использования службы калькулятора, и привязка этого клиента задается декларативно в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="28e31-105">In this example, a client console application is created to use a calculator service, and the binding for that client is specified declaratively in configuration.</span></span> <span data-ttu-id="28e31-106">Клиент обращается к службе `CalculatorService`, которая реализует интерфейс `ICalculator`; как служба, так и клиент используют класс <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="28e31-106">The client accesses the `CalculatorService`, which implements the `ICalculator` interface, and both the service and the client use the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span>  
  
 <span data-ttu-id="28e31-107">В приведенной процедуре предполагается, что служба калькулятора работает.</span><span class="sxs-lookup"><span data-stu-id="28e31-107">The procedure outlined assumes that the calculator service is running.</span></span> <span data-ttu-id="28e31-108">Сведения о том, как создать службу, см. в разделе [как указать привязку службы в конфигурации](how-to-specify-a-service-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="28e31-108">For information about how to build the service, see [How to: Specify a Service Binding in Configuration](how-to-specify-a-service-binding-in-configuration.md).</span></span> <span data-ttu-id="28e31-109">Он также использует [средство служебной программы метаданных ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) , которое Windows Communication Foundation (WCF) предоставляет для автоматического создания клиентских компонентов.</span><span class="sxs-lookup"><span data-stu-id="28e31-109">It also uses the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) that Windows Communication Foundation (WCF) provides to automatically generate the client components.</span></span> <span data-ttu-id="28e31-110">Инструмент создает код и конфигурацию клиента для доступа к службе.</span><span class="sxs-lookup"><span data-stu-id="28e31-110">The tool generates the client code and configuration for accessing the service.</span></span>  
  
 <span data-ttu-id="28e31-111">Клиент создается в два этапа.</span><span class="sxs-lookup"><span data-stu-id="28e31-111">The client is built in two parts.</span></span> <span data-ttu-id="28e31-112">Программа Svcutil.exe генерирует класс `ClientCalculator`, реализующий интерфейс `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="28e31-112">Svcutil.exe generates the `ClientCalculator` that implements the `ICalculator` interface.</span></span> <span data-ttu-id="28e31-113">Затем данное клиентское приложение создается путем конструирования экземпляра класса `ClientCalculator`.</span><span class="sxs-lookup"><span data-stu-id="28e31-113">This client application is then constructed by constructing an instance of `ClientCalculator`.</span></span>  
  
 <span data-ttu-id="28e31-114">В большинстве случаев рекомендуется указывать привязку и адрес декларативно в конфигурации, а не принудительно в коде.</span><span class="sxs-lookup"><span data-stu-id="28e31-114">It is usually the best practice to specify the binding and address information declaratively in configuration rather than imperatively in code.</span></span> <span data-ttu-id="28e31-115">Как правило, определять конечные точки в коде непрактично, поскольку привязки и адреса для развернутой службы чаще всего отличаются от привязок и адресов, используемых в процессе разработки службы.</span><span class="sxs-lookup"><span data-stu-id="28e31-115">Defining endpoints in code is usually not practical because the bindings and addresses for a deployed service are typically different from those used while the service is being developed.</span></span> <span data-ttu-id="28e31-116">В общем случае, если не указывать привязку и адрес в коде, их можно изменять без повторной компиляции или повторного развертывания приложения.</span><span class="sxs-lookup"><span data-stu-id="28e31-116">More generally, keeping the binding and addressing information out of the code allows them to change without having to recompile or redeploy the application.</span></span>  
  
 <span data-ttu-id="28e31-117">Вы можете выполнить все описанные ниже действия по настройке с помощью [средства редактора конфигурации (SvcConfigEditor.exe)](configuration-editor-tool-svcconfigeditor-exe.md).</span><span class="sxs-lookup"><span data-stu-id="28e31-117">You can perform all of the following configuration steps by using the [Configuration Editor Tool (SvcConfigEditor.exe)](configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
 <span data-ttu-id="28e31-118">Исходный экземпляр этого примера см. в примере [басикбиндинг](./samples/basicbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="28e31-118">For the source copy of this example, see the [BasicBinding](./samples/basicbinding.md) sample.</span></span>  
  
### <a name="specifying-a-client-binding-in-configuration"></a><span data-ttu-id="28e31-119">Указание привязки клиента в конфигурации</span><span class="sxs-lookup"><span data-stu-id="28e31-119">Specifying a client binding in configuration</span></span>  
  
1. <span data-ttu-id="28e31-120">Из командной строки запустите программу Svcutil.exe, чтобы создать код из метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="28e31-120">Use Svcutil.exe from the command line to generate code from service metadata.</span></span>  
  
    ```console  
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
    ```  
  
2. <span data-ttu-id="28e31-121">Создаваемый клиент содержит интерфейс `ICalculator`, определяющий контракт службы, которому должна удовлетворять реализация клиента.</span><span class="sxs-lookup"><span data-stu-id="28e31-121">The client that is generated contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/generatedclient.cs#1)]
     [!code-csharp[C_HowTo_ConfigureClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/source.cs#1)]  
  
3. <span data-ttu-id="28e31-122">Создаваемый клиент также содержит реализацию класса `ClientCalculator`.</span><span class="sxs-lookup"><span data-stu-id="28e31-122">The generated client also contains the implementation of the `ClientCalculator`.</span></span>  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/generatedclient.cs#2)]
     [!code-csharp[C_HowTo_ConfigureClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/source.cs#2)]  
  
4. <span data-ttu-id="28e31-123">Программа Svcutil.exe также создает конфигурацию для клиента, использующего класс <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="28e31-123">Svcutil.exe also generates the configuration for the client that uses the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span> <span data-ttu-id="28e31-124">При использовании Visual Studio назовите этот файл App.config. Обратите внимание, что адрес и сведения о привязке не указываются в любом месте реализации службы.</span><span class="sxs-lookup"><span data-stu-id="28e31-124">When using Visual Studio, name this file App.config. Note that the address and binding information are not specified anywhere inside the implementation of the service.</span></span> <span data-ttu-id="28e31-125">Кроме того, для извлечения этих сведений из файла конфигурации не требуется писать код.</span><span class="sxs-lookup"><span data-stu-id="28e31-125">Also, code does not have to be written to retrieve that information from the configuration file.</span></span>  
  
     [!code-xml[C_HowTo_ConfigureClientBinding#100](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/common/client.exe.config#100)]

5. <span data-ttu-id="28e31-126">Создайте экземпляр класса `ClientCalculator` в приложении, затем вызовите операции службы.</span><span class="sxs-lookup"><span data-stu-id="28e31-126">Create an instance of the `ClientCalculator` in an application, and then call the service operations.</span></span>  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/client.cs#3)]  
  
6. <span data-ttu-id="28e31-127">Скомпилируйте и запустите клиент.</span><span class="sxs-lookup"><span data-stu-id="28e31-127">Compile and run the client.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28e31-128">См. также</span><span class="sxs-lookup"><span data-stu-id="28e31-128">See also</span></span>

- [<span data-ttu-id="28e31-129">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="28e31-129">Using Bindings to Configure Services and Clients</span></span>](using-bindings-to-configure-services-and-clients.md)
