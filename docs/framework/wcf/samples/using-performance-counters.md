---
title: Использование счетчиков производительности
ms.date: 03/30/2017
ms.assetid: 00a787af-1876-473c-a48d-f52b51e28a3f
ms.openlocfilehash: f2b0f39303d000e2e9aab8fc5280f75ab9309c4d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553048"
---
# <a name="using-performance-counters"></a><span data-ttu-id="f9d72-102">Использование счетчиков производительности</span><span class="sxs-lookup"><span data-stu-id="f9d72-102">Using Performance Counters</span></span>
<span data-ttu-id="f9d72-103">В этом образце показано, как получить доступ к счетчикам производительности Windows Communication Foundation (WCF) и как создавать определяемые пользователем счетчики производительности.</span><span class="sxs-lookup"><span data-stu-id="f9d72-103">This sample demonstrates how to access Windows Communication Foundation (WCF) performance counters and how to create user-defined performance counters.</span></span> <span data-ttu-id="f9d72-104">Этот образец основан на [Начало работы](getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="f9d72-104">This sample is based on the [Getting Started](getting-started-sample.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f9d72-105">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="f9d72-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="f9d72-106">В этом образце клиент вызывает четыре метода службы `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="f9d72-106">In this sample, the client calls the four methods of the `ICalculator` service.</span></span> <span data-ttu-id="f9d72-107">Вызов данных методов осуществляется клиентом до тех пор, пока не будет прерван пользователем.</span><span class="sxs-lookup"><span data-stu-id="f9d72-107">The client continues to do this until it is interrupted by the user.</span></span> <span data-ttu-id="f9d72-108">Служба остается неизменной.</span><span class="sxs-lookup"><span data-stu-id="f9d72-108">The service remains unchanged.</span></span>  
  
 <span data-ttu-id="f9d72-109">Счетчики производительности включаются в разделе diagnostics файла Web.config службы, как показано в следующем образце конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f9d72-109">Performance counters are enabled in the diagnostics section of the Web.config file for the service, as shown in the following sample configuration.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <diagnostics performanceCounters="All" />
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="f9d72-110">Эту задачу можно также выполнить с помощью [средства редактора конфигурации (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md).</span><span class="sxs-lookup"><span data-stu-id="f9d72-110">This task can also be done using the [Configuration Editor Tool (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
 <span data-ttu-id="f9d72-111">Если счетчики производительности включены, для службы включается весь набор счетчиков производительности WCF.</span><span class="sxs-lookup"><span data-stu-id="f9d72-111">When performance counters are enabled, the entire suite of WCF performance counters is enabled for the service.</span></span> <span data-ttu-id="f9d72-112">Платформа .NET Framework автоматически поддерживает данные о производительности на трех уровнях: `ServiceModelService`, `ServiceModelEndpoint` и `ServiceModelOperation`.</span><span class="sxs-lookup"><span data-stu-id="f9d72-112">The .NET Framework automatically maintains performance data at three levels: `ServiceModelService`, `ServiceModelEndpoint` and `ServiceModelOperation`.</span></span> <span data-ttu-id="f9d72-113">На каждом из этих уровней имеются счетчики производительности, например "Calls", "Calls per Second" и "Security Calls Not Authorized".</span><span class="sxs-lookup"><span data-stu-id="f9d72-113">Each of these levels has performance counters such as "Calls", "Calls per Second", and "Security Calls Not Authorized".</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="f9d72-114">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="f9d72-114">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="f9d72-115">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f9d72-115">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="f9d72-116">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f9d72-116">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="f9d72-117">Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f9d72-117">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
### <a name="to-view-performance-data"></a><span data-ttu-id="f9d72-118">Просмотр данных о производительности</span><span class="sxs-lookup"><span data-stu-id="f9d72-118">To view performance data</span></span>  
  
1. <span data-ttu-id="f9d72-119">Запустите средство "монитор производительности", нажав кнопку **Пуск**, **выполните...**, введите `perfmon` и нажмите кнопку **ОК** или в панели управления выберите **Администрирование** и дважды щелкните **производительность**.</span><span class="sxs-lookup"><span data-stu-id="f9d72-119">Start the Performance Monitor Tool by clicking **Start**, **Run…**, enter `perfmon` and click **OK,** or from Control Panel, select **Administrative Tools** and double-click **Performance**.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="f9d72-120">Пока не начнется выполнение кода образца, добавить счетчики невозможно.</span><span class="sxs-lookup"><span data-stu-id="f9d72-120">You cannot add counters until the sample code is running.</span></span>  
  
2. <span data-ttu-id="f9d72-121">Удалите доступные счетчики производительности, выбирая их и нажимая клавишу DELETE.</span><span class="sxs-lookup"><span data-stu-id="f9d72-121">Remove the performance counters that are listed by selecting them and pressing the Delete key.</span></span>  
  
3. <span data-ttu-id="f9d72-122">Добавьте счетчики WCF, щелкнув правой кнопкой мыши панель графа и выбрав пункт **Добавить счетчики**.</span><span class="sxs-lookup"><span data-stu-id="f9d72-122">Add WCF counters by right-clicking the graph pane and selecting **Add Counters**.</span></span> <span data-ttu-id="f9d72-123">В диалоговом окне **Добавление счетчиков** выберите **Сервицемоделоператион 3.0.0.0, Сервицемоделендпоинт 3.0.0.0 или сервицемоделсервице 3.0.0.0** в раскрывающемся списке Объект производительности.</span><span class="sxs-lookup"><span data-stu-id="f9d72-123">In the **Add Counters** dialog box, select **ServiceModelOperation 3.0.0.0, ServiceModelEndpoint 3.0.0.0, or ServiceModelService 3.0.0.0** in the Performance object drop down list box.</span></span> <span data-ttu-id="f9d72-124">Выберите в списке нужные счетчики.</span><span class="sxs-lookup"><span data-stu-id="f9d72-124">Select the counters you want to view from the list.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="f9d72-125">Нет счетчиков производительности WCF для службы, если на компьютере не выполняются службы WCF.</span><span class="sxs-lookup"><span data-stu-id="f9d72-125">There are no WCF performance counters for a service if there are no WCF services running on the computer.</span></span>  
  
### <a name="to-use-the-configuration-editor-to-enable-counters"></a><span data-ttu-id="f9d72-126">Включение счетчиков с помощью редактора конфигураций</span><span class="sxs-lookup"><span data-stu-id="f9d72-126">To use the Configuration Editor to enable counters</span></span>  
  
1. <span data-ttu-id="f9d72-127">Откройте экземпляр программы SvcConfigEditor.exe.</span><span class="sxs-lookup"><span data-stu-id="f9d72-127">Open an instance of the SvcConfigEditor.exe.</span></span>  
  
2. <span data-ttu-id="f9d72-128">В меню Файл выберите команду **Открыть** , а затем щелкните **файл конфигурации.**...</span><span class="sxs-lookup"><span data-stu-id="f9d72-128">On the File menu, click **Open** and then click **Config file…**.</span></span>  
  
3. <span data-ttu-id="f9d72-129">Перейдите в папку службы примера приложения и откройте файл Web.config.</span><span class="sxs-lookup"><span data-stu-id="f9d72-129">Navigate to the sample application's service folder and open the Web.config file.</span></span>  
  
4. <span data-ttu-id="f9d72-130">Щелкните **Диагностика** в дереве конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f9d72-130">Click **Diagnostics** on the Configuration tree.</span></span>  
  
5. <span data-ttu-id="f9d72-131">Чтобы отобразить "все", переключите **Счетчик производительности** в окне " **Диагностика** ".</span><span class="sxs-lookup"><span data-stu-id="f9d72-131">Toggle **Performance Counter** in the **Diagnostics** window to show 'All'.</span></span>  
  
6. <span data-ttu-id="f9d72-132">Сохраните файл конфигурации и закройте редактор.</span><span class="sxs-lookup"><span data-stu-id="f9d72-132">Save the configuration file and exit the editor.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="f9d72-133">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f9d72-133">The samples may already be installed on your computer.</span></span> <span data-ttu-id="f9d72-134">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="f9d72-134">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="f9d72-135">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="f9d72-135">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f9d72-136">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="f9d72-136">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\PerfCounters`  
  
## <a name="see-also"></a><span data-ttu-id="f9d72-137">См. также</span><span class="sxs-lookup"><span data-stu-id="f9d72-137">See also</span></span>

- <span data-ttu-id="f9d72-138">[Образцы наблюдения за AppFabric](/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="f9d72-138">[AppFabric Monitoring Samples](/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
