---
title: Трассировка ETW
description: В этом примере показано, как реализовать сквозную трассировку (E2E) с помощью трассировки событий для Windows (ETW) и Етвтрацелистенер.
ms.date: 03/30/2017
ms.assetid: ac99a063-e2d2-40cc-b659-d23c2f783f92
ms.openlocfilehash: 6e7526ef05d672b550599e3b12a4b083e9130b96
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90547145"
---
# <a name="etw-tracing"></a><span data-ttu-id="82d00-103">Трассировка ETW</span><span class="sxs-lookup"><span data-stu-id="82d00-103">ETW Tracing</span></span>
<span data-ttu-id="82d00-104">В этом примере показано, как реализовать сквозную трассировку (E2E) с помощью трассировки событий для Windows (трассировка событий Windows) и `ETWTraceListener`, предоставляемого с этим примером.</span><span class="sxs-lookup"><span data-stu-id="82d00-104">This sample demonstrates how to implement End-to-End (E2E) tracing using Event Tracing for Windows (ETW) and the `ETWTraceListener` that is provided with this sample.</span></span> <span data-ttu-id="82d00-105">Образец основан на [Начало работы](getting-started-sample.md) и включает трассировку ETW.</span><span class="sxs-lookup"><span data-stu-id="82d00-105">The sample is based on the [Getting Started](getting-started-sample.md) and includes ETW tracing.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="82d00-106">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="82d00-106">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="82d00-107">В этом примере предполагается, что вы знакомы с [трассировкой и ведением журнала сообщений](tracing-and-message-logging.md).</span><span class="sxs-lookup"><span data-stu-id="82d00-107">This sample assumes that you are familiar with [Tracing and Message Logging](tracing-and-message-logging.md).</span></span>  
  
 <span data-ttu-id="82d00-108">Каждый источник трассировки в модели трассировки <xref:System.Diagnostics> может иметь несколько прослушивателей трассировки, которые определяют место и способ трассировки данных.</span><span class="sxs-lookup"><span data-stu-id="82d00-108">Each trace source in the <xref:System.Diagnostics> tracing model can have multiple trace listeners that determine where and how the data is traced.</span></span> <span data-ttu-id="82d00-109">Тип прослушивателя определяет формат записи данных трассировки в журнал.</span><span class="sxs-lookup"><span data-stu-id="82d00-109">The type of listener defines the format in which trace data is logged.</span></span> <span data-ttu-id="82d00-110">В следующем образце кода показано, как добавить прослушиватель в конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="82d00-110">The following code sample shows how to add the listener to configuration.</span></span>  
  
```xml  
<system.diagnostics>  
    <sources>  
        <source name="System.ServiceModel"
             switchValue="Verbose,ActivityTracing"  
             propagateActivity="true">  
            <listeners>  
                <add type=  
                   "System.Diagnostics.DefaultTraceListener"  
                   name="Default">  
                   <filter type="" />  
                </add>  
                <add name="ETW">  
                    <filter type="" />  
                </add>  
            </listeners>  
        </source>  
    </sources>  
    <sharedListeners>  
        <add type=  
            "Microsoft.ServiceModel.Samples.EtwTraceListener, ETWTraceListener"  
            name="ETW" traceOutputOptions="Timestamp">  
            <filter type="" />  
       </add>  
    </sharedListeners>  
</system.diagnostics>  
```  
  
 <span data-ttu-id="82d00-111">Перед использованием этого прослушивателя необходимо запустить сеанс трассировки событий Windows.</span><span class="sxs-lookup"><span data-stu-id="82d00-111">Before using this listener, an ETW Trace Session must be started.</span></span> <span data-ttu-id="82d00-112">Этот сеанс может быть запущен с помощью программ Logman.exe или Tracelog.exe.</span><span class="sxs-lookup"><span data-stu-id="82d00-112">This session can be started by using Logman.exe or Tracelog.exe.</span></span> <span data-ttu-id="82d00-113">В этот образец включен файл SetupETW.bat, поэтому можно настроить сеанс трассировки событий Windows вместе с файлом CleanupETW.bat для закрытия сеанса и завершения выполнения файла журнала.</span><span class="sxs-lookup"><span data-stu-id="82d00-113">A SetupETW.bat file is included with this sample so that you can set up the ETW Trace Session along with a CleanupETW.bat file for closing the session and completing the log file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="82d00-114">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="82d00-114">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span> <span data-ttu-id="82d00-115">Дополнительные сведения об этих средствах см. в разделе <https://go.microsoft.com/fwlink/?LinkId=56580></span><span class="sxs-lookup"><span data-stu-id="82d00-115">For more information about these tools, see <https://go.microsoft.com/fwlink/?LinkId=56580></span></span>  
  
 <span data-ttu-id="82d00-116">При использовании ETWTraceListener трассировки заносятся в журнал в двоичных файлах с расширением ETL.</span><span class="sxs-lookup"><span data-stu-id="82d00-116">When using the ETWTraceListener, traces are logged in binary .etl files.</span></span> <span data-ttu-id="82d00-117">Если трассировка ServiceModel включена, все созданные трассировки отображаются в одном и том же файле.</span><span class="sxs-lookup"><span data-stu-id="82d00-117">With ServiceModel tracing turned on, all generated traces appear in the same file.</span></span> <span data-ttu-id="82d00-118">Используйте [средство Service Trace Viewer (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) для просмотра файлов журнала ETL и SVCLOG.</span><span class="sxs-lookup"><span data-stu-id="82d00-118">Use [Service Trace Viewer Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) for viewing .etl and .svclog log files.</span></span> <span data-ttu-id="82d00-119">Средство просмотра создает сквозное представление системы, позволяющее выполнять трассировку сообщения на пути от источника в место назначения и точку потребления.</span><span class="sxs-lookup"><span data-stu-id="82d00-119">The viewer creates an end-to-end view of the system that makes it possible to trace a message from its source to its destination and point of consumption.</span></span>  
  
 <span data-ttu-id="82d00-120">Прослушиватель трассировки событий Windows поддерживает циклическое ведение журнала.</span><span class="sxs-lookup"><span data-stu-id="82d00-120">The ETW Trace Listener supports circular logging.</span></span> <span data-ttu-id="82d00-121">Чтобы включить эту функцию, перейдите в раздел **Пуск**, **запустите** и введите, `cmd` чтобы запустить консоль командной строки.</span><span class="sxs-lookup"><span data-stu-id="82d00-121">To enable this feature, go to **Start**, **Run** and type `cmd` to start a command console.</span></span> <span data-ttu-id="82d00-122">В следующей команде замените параметр `<logfilename>` на имя требуемого файла журнала.</span><span class="sxs-lookup"><span data-stu-id="82d00-122">In the following command, replace the `<logfilename>` parameter with the name of your log file.</span></span>  
  
```console  
logman create trace Wcf -o <logfilename> -p "{411a0819-c24b-428c-83e2-26b41091702e}" -f bincirc -max 1000  
```  
  
 <span data-ttu-id="82d00-123">Коммутаторы `-f` и `-max` необязательны.</span><span class="sxs-lookup"><span data-stu-id="82d00-123">The `-f` and `-max` switches are optional.</span></span> <span data-ttu-id="82d00-124">Они указывают двоичный циклический формат и максимальный размер журнала (1000 МБ) соответственно.</span><span class="sxs-lookup"><span data-stu-id="82d00-124">They specify the binary circular format and max log size of 1000MB respectively.</span></span> <span data-ttu-id="82d00-125">Коммутатор `-p` используется для указания поставщика трассировки.</span><span class="sxs-lookup"><span data-stu-id="82d00-125">The `-p` switch is used to specify the trace provider.</span></span> <span data-ttu-id="82d00-126">В этом примере `"{411a0819-c24b-428c-83e2-26b41091702e}"` является идентификатором GUID для примера поставщика трассировки событий Windows XML.</span><span class="sxs-lookup"><span data-stu-id="82d00-126">In our example, `"{411a0819-c24b-428c-83e2-26b41091702e}"` is the GUID for "XML ETW Sample Provider".</span></span>  
  
 <span data-ttu-id="82d00-127">Для запуска сеанса введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="82d00-127">To start the session, type in the following command.</span></span>  
  
```console  
logman start Wcf  
```  
  
 <span data-ttu-id="82d00-128">По завершении ведения журнала можно остановить сеанс с помощью следующей команды.</span><span class="sxs-lookup"><span data-stu-id="82d00-128">After you have finished logging, you can stop the session with the following command.</span></span>  
  
```console  
logman stop Wcf  
```  
  
 <span data-ttu-id="82d00-129">Этот процесс создает двоичные циклические журналы, которые можно обработать с помощью выбранного инструмента, включая средство [Service Trace Viewer (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) или Tracerpt.</span><span class="sxs-lookup"><span data-stu-id="82d00-129">This process generates binary circular logs that you can process with your tool of choice, including [Service Trace Viewer Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) or Tracerpt.</span></span>  
  
 <span data-ttu-id="82d00-130">Вы также можете ознакомиться с примером [циклической трассировки](circular-tracing.md) для получения дополнительных сведений о альтернативном прослушивателе для выполнения циклического ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="82d00-130">You can also review the [Circular Tracing](circular-tracing.md) sample for more information on an alternative listener to perform circular logging.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="82d00-131">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="82d00-131">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="82d00-132">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="82d00-132">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="82d00-133">Чтобы выполнить сборку решения, следуйте инструкциям в разделе [Создание примеров Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="82d00-133">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="82d00-134">Для запуска команд RegisterProvider.bat, SetupETW.bat и CleanupETW.bat необходимо использовать учетную запись локального администратора.</span><span class="sxs-lookup"><span data-stu-id="82d00-134">To use the RegisterProvider.bat, SetupETW.bat and CleanupETW.bat commands, you must run under a local administrator account.</span></span> <span data-ttu-id="82d00-135">При использовании Windows Vista или более поздней версии необходимо также запустить командную строку с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="82d00-135">If you are using Windows Vista or later, you must also run the command prompt with elevated privileges.</span></span> <span data-ttu-id="82d00-136">Для этого щелкните правой кнопкой мыши значок командной строки и выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="82d00-136">To do so, right-click the command prompt icon, then click **Run as administrator**.</span></span>  
  
3. <span data-ttu-id="82d00-137">Перед выполнением примера запустите файл RegisterProvider.bat на стороне клиента и сервера.</span><span class="sxs-lookup"><span data-stu-id="82d00-137">Before running the sample, run RegisterProvider.bat on the client and server.</span></span> <span data-ttu-id="82d00-138">При этом выполняется настройка получаемого файла ETWTracingSampleLog.etl для создания трассировок, которые можно считать с помощью программы Service Trace Viewer.</span><span class="sxs-lookup"><span data-stu-id="82d00-138">This sets up the resulting ETWTracingSampleLog.etl file to generate traces that can be read by the Service Trace Viewer.</span></span> <span data-ttu-id="82d00-139">Этот файл можно найти в папке C:\logs.</span><span class="sxs-lookup"><span data-stu-id="82d00-139">This file can be found in the C:\logs folder.</span></span> <span data-ttu-id="82d00-140">Если эта папка не существует, ее необходимо создать, в противном случае трассировки создаваться не будут.</span><span class="sxs-lookup"><span data-stu-id="82d00-140">If this folder does not exist, it must be created or no traces are generated.</span></span> <span data-ttu-id="82d00-141">Затем запустите файл SetupETW.bat на клиентском и серверном компьютерах, чтобы начать сеанс трассировки событий Windows.</span><span class="sxs-lookup"><span data-stu-id="82d00-141">Then, run SetupETW.bat on the client and server computers to begin the ETW Trace Session.</span></span> <span data-ttu-id="82d00-142">Файл SetupETW.bat можно найти в папке CS\Client.</span><span class="sxs-lookup"><span data-stu-id="82d00-142">The SetupETW.bat file can be found under the CS\Client folder.</span></span>  
  
4. <span data-ttu-id="82d00-143">Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="82d00-143">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
5. <span data-ttu-id="82d00-144">По завершении образца запустите файл CleanupETW.bat, чтобы завершить создание файла ETWTracingSampleLog.etl.</span><span class="sxs-lookup"><span data-stu-id="82d00-144">When the sample is completed, run CleanupETW.bat to complete the creation of the ETWTracingSampleLog.etl file.</span></span>  
  
6. <span data-ttu-id="82d00-145">Откройте файл ETWTracingSampleLog.etl с помощью программы Service Trace Viewer.</span><span class="sxs-lookup"><span data-stu-id="82d00-145">Open the ETWTracingSampleLog.etl file from within the Service Trace Viewer.</span></span> <span data-ttu-id="82d00-146">Будет предложено сохранить двоичный файл как файл с расширением SVCLOG.</span><span class="sxs-lookup"><span data-stu-id="82d00-146">You will be prompted to save the binary formatted file as a .svclog file.</span></span>  
  
7. <span data-ttu-id="82d00-147">Откройте только что созданный файл с расширением SVCLOG с помощью программы Service Trace Viewer, чтобы просмотреть трассировки событий Windows и трассировки ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="82d00-147">Open the newly created .svclog file from within the Service Trace Viewer to view the ETW and ServiceModel traces.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="82d00-148">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="82d00-148">The samples may already be installed on your computer.</span></span> <span data-ttu-id="82d00-149">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="82d00-149">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="82d00-150">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="82d00-150">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="82d00-151">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="82d00-151">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\AnalyticTrace`  
  
## <a name="see-also"></a><span data-ttu-id="82d00-152">См. также</span><span class="sxs-lookup"><span data-stu-id="82d00-152">See also</span></span>

- <span data-ttu-id="82d00-153">[Образцы наблюдения за AppFabric](/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="82d00-153">[AppFabric Monitoring Samples](/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
