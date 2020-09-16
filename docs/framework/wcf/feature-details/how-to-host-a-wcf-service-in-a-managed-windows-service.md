---
title: Практическое руководство. Размещение службы WCF в управляемой службе Windows
description: Узнайте, как создать службу WCF, размещенную в службе Windows. Данный вариант размещения доступен во всех версиях Windows.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8e37363b-4dad-4fb6-907f-73c30fac1d9a
ms.openlocfilehash: 21d3dcb05e48154eb3f9f10d8308dc14bd046ae1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546345"
---
# <a name="how-to-host-a-wcf-service-in-a-managed-windows-service"></a><span data-ttu-id="22f13-104">Практическое руководство. Размещение службы WCF в управляемой службе Windows</span><span class="sxs-lookup"><span data-stu-id="22f13-104">How to: Host a WCF Service in a Managed Windows Service</span></span>

<span data-ttu-id="22f13-105">В этом разделе описаны основные шаги, необходимые для создания службы Windows Communication Foundation (WCF), размещенной в службе Windows.</span><span class="sxs-lookup"><span data-stu-id="22f13-105">This topic outlines the basic steps required to create a Windows Communication Foundation (WCF) service that is hosted by a Windows Service.</span></span> <span data-ttu-id="22f13-106">Сценарий включается параметром размещения управляемой службы Windows, который является длительно запущенной службой WCF, размещенной вне службы IIS (IIS) в безопасной среде, которая не является активируемой для сообщения.</span><span class="sxs-lookup"><span data-stu-id="22f13-106">The scenario is enabled by the managed Windows service hosting option that is a long-running WCF service hosted outside of Internet Information Services (IIS) in a secure environment that is not message activated.</span></span> <span data-ttu-id="22f13-107">Вместо этого время существования службы контролируется операционной системой.</span><span class="sxs-lookup"><span data-stu-id="22f13-107">The lifetime of the service is controlled instead by the operating system.</span></span> <span data-ttu-id="22f13-108">Данный вариант размещения доступен во всех версиях Windows.</span><span class="sxs-lookup"><span data-stu-id="22f13-108">This hosting option is available in all versions of Windows.</span></span>

<span data-ttu-id="22f13-109">Службами Windows можно управлять при помощи Microsoft.ManagementConsole.SnapIn в консоли управления (MMC) и можно настроить их автоматический запуск при загрузке системы.</span><span class="sxs-lookup"><span data-stu-id="22f13-109">Windows services can be managed with the Microsoft.ManagementConsole.SnapIn in Microsoft Management Console (MMC) and can be configured to start up automatically when the system boots up.</span></span> <span data-ttu-id="22f13-110">Этот вариант размещения состоит из регистрации домена приложения (AppDomain), в котором размещена служба WCF, в качестве управляемой службы Windows, чтобы время существования процесса службы управлялось диспетчером управления службами (SCM) для служб Windows.</span><span class="sxs-lookup"><span data-stu-id="22f13-110">This hosting option consists of registering the application domain (AppDomain) that hosts a WCF service as a managed Windows service so that the process lifetime of the service is controlled by the Service Control Manager (SCM) for Windows services.</span></span>

<span data-ttu-id="22f13-111">Код службы включает в себя реализацию службы контракта службы, класс службы Windows и класс установщика.</span><span class="sxs-lookup"><span data-stu-id="22f13-111">The service code includes a service implementation of the service contract, a Windows Service class, and an installer class.</span></span> <span data-ttu-id="22f13-112">Класс реализации службы, `CalculatorService` , — это служба WCF.</span><span class="sxs-lookup"><span data-stu-id="22f13-112">The service implementation class, `CalculatorService`, is a WCF service.</span></span> <span data-ttu-id="22f13-113">Класс `CalculatorWindowsService` является службой Windows.</span><span class="sxs-lookup"><span data-stu-id="22f13-113">The `CalculatorWindowsService` is a Windows service.</span></span> <span data-ttu-id="22f13-114">Чтобы считаться службой Windows, этот класс наследует от класса `ServiceBase` и реализует методы `OnStart` и `OnStop`.</span><span class="sxs-lookup"><span data-stu-id="22f13-114">To qualify as a Windows service, the class inherits from `ServiceBase` and implements the `OnStart` and `OnStop` methods.</span></span> <span data-ttu-id="22f13-115">В методе `OnStart` создается объект <xref:System.ServiceModel.ServiceHost> для типа `CalculatorService` и открывается.</span><span class="sxs-lookup"><span data-stu-id="22f13-115">In `OnStart`, a <xref:System.ServiceModel.ServiceHost> is created for the `CalculatorService` type and opened.</span></span> <span data-ttu-id="22f13-116">В методе `OnStop` служба останавливается и освобождается.</span><span class="sxs-lookup"><span data-stu-id="22f13-116">In `OnStop`, the service is stopped and disposed.</span></span> <span data-ttu-id="22f13-117">Ведущее приложение также отвечает за предоставление базового адреса для узла службы, настроенного в параметрах приложения.</span><span class="sxs-lookup"><span data-stu-id="22f13-117">The host is also responsible for providing a base address to the service host, which has been configured in application settings.</span></span> <span data-ttu-id="22f13-118">Класс установщика, унаследованный от класса <xref:System.Configuration.Install.Installer>, позволяет выполнить установку программы как службы Windows с помощью Installutil.exe.</span><span class="sxs-lookup"><span data-stu-id="22f13-118">The installer class, which inherits from <xref:System.Configuration.Install.Installer>, allows the program to be installed as a Windows service by the Installutil.exe tool.</span></span>

## <a name="construct-the-service-and-provide-the-hosting-code"></a><span data-ttu-id="22f13-119">Создание службы и предоставление кода размещения</span><span class="sxs-lookup"><span data-stu-id="22f13-119">Construct the service and provide the hosting code</span></span>

1. <span data-ttu-id="22f13-120">Создайте новый проект **консольного приложения** Visual Studio с именем **Service**.</span><span class="sxs-lookup"><span data-stu-id="22f13-120">Create a new Visual Studio **Console app** project called **Service**.</span></span>

2. <span data-ttu-id="22f13-121">Измените имя файла Program.cs на Service.cs.</span><span class="sxs-lookup"><span data-stu-id="22f13-121">Rename Program.cs to Service.cs.</span></span>

3. <span data-ttu-id="22f13-122">Измените пространство имен на `Microsoft.ServiceModel.Samples` .</span><span class="sxs-lookup"><span data-stu-id="22f13-122">Change the namespace to `Microsoft.ServiceModel.Samples`.</span></span>

4. <span data-ttu-id="22f13-123">Добавьте ссылки на следующие сборки:</span><span class="sxs-lookup"><span data-stu-id="22f13-123">Add references to the following assemblies:</span></span>

    - <span data-ttu-id="22f13-124">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="22f13-124">System.ServiceModel.dll</span></span>

    - <span data-ttu-id="22f13-125">System.ServiceProcess.dll</span><span class="sxs-lookup"><span data-stu-id="22f13-125">System.ServiceProcess.dll</span></span>

    - <span data-ttu-id="22f13-126">System.Configuration.Install.dll</span><span class="sxs-lookup"><span data-stu-id="22f13-126">System.Configuration.Install.dll</span></span>

5. <span data-ttu-id="22f13-127">Добавьте следующие операторы using в файл Service.cs.</span><span class="sxs-lookup"><span data-stu-id="22f13-127">Add the following using statements to Service.cs.</span></span>

     [!code-csharp[c_HowTo_HostInNTService#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#0)]
     [!code-vb[c_HowTo_HostInNTService#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#0)]

6. <span data-ttu-id="22f13-128">Определите контракт службы `ICalculator`, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="22f13-128">Define the `ICalculator` service contract as shown in the following code.</span></span>

     [!code-csharp[c_HowTo_HostInNTService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#1)]
     [!code-vb[c_HowTo_HostInNTService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#1)]

7. <span data-ttu-id="22f13-129">Реализуйте контракт службы в классе с именем `CalculatorService`, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="22f13-129">Implement the service contract in a class called `CalculatorService` as shown in the following code.</span></span>

     [!code-csharp[c_HowTo_HostInNTService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#2)]
     [!code-vb[c_HowTo_HostInNTService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#2)]

8. <span data-ttu-id="22f13-130">Создайте новый класс с именем `CalculatorWindowsService`, производный от класса <xref:System.ServiceProcess.ServiceBase>.</span><span class="sxs-lookup"><span data-stu-id="22f13-130">Create a new class called `CalculatorWindowsService` that inherits from the <xref:System.ServiceProcess.ServiceBase> class.</span></span> <span data-ttu-id="22f13-131">Добавьте локальную переменную с именем `serviceHost`, чтобы создать ссылку на экземпляр <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="22f13-131">Add a local variable called `serviceHost` to reference the <xref:System.ServiceModel.ServiceHost> instance.</span></span> <span data-ttu-id="22f13-132">Определите метод `Main`, который вызывает `ServiceBase.Run(new CalculatorWindowsService)`.</span><span class="sxs-lookup"><span data-stu-id="22f13-132">Define the `Main` method that calls `ServiceBase.Run(new CalculatorWindowsService)`</span></span>

     [!code-csharp[c_HowTo_HostInNTService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#3)]
     [!code-vb[c_HowTo_HostInNTService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#3)]

9. <span data-ttu-id="22f13-133">Переопределите метод <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29>, создав и открыв новый экземпляр <xref:System.ServiceModel.ServiceHost>, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="22f13-133">Override the <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> method by creating and opening a new <xref:System.ServiceModel.ServiceHost> instance as shown in the following code.</span></span>

     [!code-csharp[c_HowTo_HostInNTService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#4)]
     [!code-vb[c_HowTo_HostInNTService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#4)]

10. <span data-ttu-id="22f13-134">Переопределите метод <xref:System.ServiceProcess.ServiceBase.OnStop%2A>, закрывающий <xref:System.ServiceModel.ServiceHost>, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="22f13-134">Override the <xref:System.ServiceProcess.ServiceBase.OnStop%2A> method closing the <xref:System.ServiceModel.ServiceHost> as shown in the following code.</span></span>

     [!code-csharp[c_HowTo_HostInNTService#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#5)]
     [!code-vb[c_HowTo_HostInNTService#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#5)]

11. <span data-ttu-id="22f13-135">Создайте новый класс с именем `ProjectInstaller`, производный от <xref:System.Configuration.Install.Installer> и помеченный атрибутом <xref:System.ComponentModel.RunInstallerAttribute>, установленным в значение `true`.</span><span class="sxs-lookup"><span data-stu-id="22f13-135">Create a new class called `ProjectInstaller` that inherits from <xref:System.Configuration.Install.Installer> and that is marked with the <xref:System.ComponentModel.RunInstallerAttribute> set to `true`.</span></span> <span data-ttu-id="22f13-136">Это позволяет устанавливать службу Windows программой Installutil.exe.</span><span class="sxs-lookup"><span data-stu-id="22f13-136">This allows the Windows service to be installed by the Installutil.exe tool.</span></span>

     [!code-csharp[c_HowTo_HostInNTService#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#6)]
     [!code-vb[c_HowTo_HostInNTService#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#6)]

12. <span data-ttu-id="22f13-137">Удалите класс `Service`, созданный при создании проекта.</span><span class="sxs-lookup"><span data-stu-id="22f13-137">Remove the `Service` class that was generated when you created the project.</span></span>

13. <span data-ttu-id="22f13-138">Добавьте в проект файл конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="22f13-138">Add an application configuration file to the project.</span></span> <span data-ttu-id="22f13-139">Замените содержимое этого файла следующим XML-кодом конфигурации.</span><span class="sxs-lookup"><span data-stu-id="22f13-139">Replace the contents of the file with the following configuration XML.</span></span>

    ```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <system.serviceModel>    <services>
          <!-- This section is optional with the new configuration model
               introduced in .NET Framework 4. -->
          <service name="Microsoft.ServiceModel.Samples.CalculatorService"
                   behaviorConfiguration="CalculatorServiceBehavior">
            <host>
              <baseAddresses>
                <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>
              </baseAddresses>
            </host>
            <!-- this endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service  -->
            <endpoint address=""
                      binding="wsHttpBinding"
                      contract="Microsoft.ServiceModel.Samples.ICalculator" />
            <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->
            <endpoint address="mex"
                      binding="mexHttpBinding"
                      contract="IMetadataExchange" />
          </service>
        </services>
        <behaviors>
          <serviceBehaviors>
            <behavior name="CalculatorServiceBehavior">
              <serviceMetadata httpGetEnabled="true"/>
              <serviceDebug includeExceptionDetailInFaults="False"/>
            </behavior>
          </serviceBehaviors>
        </behaviors>
      </system.serviceModel>
    </configuration>
    ```

     <span data-ttu-id="22f13-140">Щелкните правой кнопкой мыши файл App.config в **Обозреватель решений** и выберите пункт **свойства**.</span><span class="sxs-lookup"><span data-stu-id="22f13-140">Right click the App.config file in the **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="22f13-141">В разделе **Копировать в выходной каталог** выберите **Копировать, если новее**.</span><span class="sxs-lookup"><span data-stu-id="22f13-141">Under **Copy to Output Directory** select **Copy if Newer**.</span></span>

     <span data-ttu-id="22f13-142">В этом примере конечные точки явно задаются в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="22f13-142">This example explicitly specifies endpoints in the configuration file.</span></span> <span data-ttu-id="22f13-143">Если в службу не добавлена ни одна конечная точка, то среда выполнения добавляет конечные точки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="22f13-143">If you do not add any endpoints to the service, the runtime adds default endpoints for you.</span></span> <span data-ttu-id="22f13-144">В этом примере, поскольку для службы параметр <xref:System.ServiceModel.Description.ServiceMetadataBehavior> установлен в значение `true`, в ней также будет включена публикация метаданных.</span><span class="sxs-lookup"><span data-stu-id="22f13-144">In this example, because the service has a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> set to `true`, your service also has publishing metadata enabled.</span></span> <span data-ttu-id="22f13-145">Дополнительные сведения о конечных точках по умолчанию, привязках и режимах работы см. в разделах [Упрощенная конфигурация](../simplified-configuration.md) и [Упрощенная конфигурация служб WCF](../samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="22f13-145">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](../simplified-configuration.md) and [Simplified Configuration for WCF Services](../samples/simplified-configuration-for-wcf-services.md).</span></span>

## <a name="install-and-run-the-service"></a><span data-ttu-id="22f13-146">Установка и запуск службы</span><span class="sxs-lookup"><span data-stu-id="22f13-146">Install and run the service</span></span>

1. <span data-ttu-id="22f13-147">Постройте решение, чтобы создать исполняемый файл `Service.exe`.</span><span class="sxs-lookup"><span data-stu-id="22f13-147">Build the solution to create the `Service.exe` executable.</span></span>

2. <span data-ttu-id="22f13-148">Откройте Командная строка разработчика для Visual Studio и перейдите в каталог проекта.</span><span class="sxs-lookup"><span data-stu-id="22f13-148">Open Developer Command Prompt for Visual Studio and navigate to the project directory.</span></span> <span data-ttu-id="22f13-149">В командной строке введите `installutil bin\service.exe`, чтобы установить службу Windows.</span><span class="sxs-lookup"><span data-stu-id="22f13-149">Type `installutil bin\service.exe` at the command prompt to install the Windows service.</span></span>

     <span data-ttu-id="22f13-150">В командной строке введите `services.msc`, чтобы получить доступ к диспетчеру служб.</span><span class="sxs-lookup"><span data-stu-id="22f13-150">Type `services.msc` at the command prompt to access the Service Control Manager (SCM).</span></span> <span data-ttu-id="22f13-151">Служба Windows должна появиться в списке служб с именем WCFWindowsServiceSample.</span><span class="sxs-lookup"><span data-stu-id="22f13-151">The Windows service should appear in Services as "WCFWindowsServiceSample".</span></span> <span data-ttu-id="22f13-152">Служба WCF может отвечать только на клиенты, если запущена служба Windows.</span><span class="sxs-lookup"><span data-stu-id="22f13-152">The WCF service can only respond to clients if the Windows service is running.</span></span> <span data-ttu-id="22f13-153">Чтобы запустить службу, щелкните ее правой кнопкой мыши в SCM и выберите "запустить" или введите **net start WCFWindowsServiceSample** в командной строке.</span><span class="sxs-lookup"><span data-stu-id="22f13-153">To start the service, right-click it in the SCM and select "Start", or type **net start WCFWindowsServiceSample** at the command prompt.</span></span>

3. <span data-ttu-id="22f13-154">Чтобы внести изменения в службу, необходимо предварительно остановить ее и удалить.</span><span class="sxs-lookup"><span data-stu-id="22f13-154">If you make changes to the service, you must first stop it and uninstall it.</span></span> <span data-ttu-id="22f13-155">Чтобы отключить службу, щелкните правой кнопкой мыши службу в SCM и выберите пункт "Закрыть" или введите команду **net Service WCFWindowsServiceSample** в командной строке.</span><span class="sxs-lookup"><span data-stu-id="22f13-155">To stop the service, right-click the service in the SCM and select "Stop", or **type net stop WCFWindowsServiceSample** at the command prompt.</span></span> <span data-ttu-id="22f13-156">Учтите, что если остановить службу Windows, а затем запустить клиент, то когда клиент попытается обратиться к службе, будет вызвано исключение <xref:System.ServiceModel.EndpointNotFoundException>.</span><span class="sxs-lookup"><span data-stu-id="22f13-156">Note that if you stop the Windows service and then run a client, an <xref:System.ServiceModel.EndpointNotFoundException> exception occurs when a client attempts to access the service.</span></span> <span data-ttu-id="22f13-157">Чтобы удалить службу Windows, введите в командной строке команду **installutil/u bin\service.exe** .</span><span class="sxs-lookup"><span data-stu-id="22f13-157">To uninstall the Windows service type **installutil /u bin\service.exe** at the command prompt.</span></span>

## <a name="example"></a><span data-ttu-id="22f13-158">Пример</span><span class="sxs-lookup"><span data-stu-id="22f13-158">Example</span></span>

<span data-ttu-id="22f13-159">Ниже приведен полный список кода, используемого в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="22f13-159">The following is a complete listing of the code used by this topic:</span></span>

[!code-csharp[c_HowTo_HostInNTService#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#8)]
[!code-vb[c_HowTo_HostInNTService#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#8)]

<span data-ttu-id="22f13-160">Как и в случае резидентного размещения, среда размещения службы Windows требует, чтобы код размещения являлся частью приложения.</span><span class="sxs-lookup"><span data-stu-id="22f13-160">Like the "Self-Hosting" option, the Windows service hosting environment requires that some hosting code be written as part of the application.</span></span> <span data-ttu-id="22f13-161">Служба реализуется как консольное приложение и содержит собственный код размещения.</span><span class="sxs-lookup"><span data-stu-id="22f13-161">The service is implemented as a console application and contains its own hosting code.</span></span> <span data-ttu-id="22f13-162">В других средах размещения, таких как служба активации Windows (WAS), размещающих в IIS, писать код размещения необязательно.</span><span class="sxs-lookup"><span data-stu-id="22f13-162">In other hosting environments, such as Windows Process Activation Service (WAS) hosting in Internet Information Services (IIS), it is not necessary for developers to write hosting code.</span></span>

## <a name="see-also"></a><span data-ttu-id="22f13-163">См. также</span><span class="sxs-lookup"><span data-stu-id="22f13-163">See also</span></span>

- [<span data-ttu-id="22f13-164">Упрощенная конфигурация</span><span class="sxs-lookup"><span data-stu-id="22f13-164">Simplified Configuration</span></span>](../simplified-configuration.md)
- [<span data-ttu-id="22f13-165">Размещение в управляемом приложении</span><span class="sxs-lookup"><span data-stu-id="22f13-165">Hosting in a Managed Application</span></span>](hosting-in-a-managed-application.md)
- [<span data-ttu-id="22f13-166">Размещение служб</span><span class="sxs-lookup"><span data-stu-id="22f13-166">Hosting Services</span></span>](../hosting-services.md)
- <span data-ttu-id="22f13-167">[Функции размещения Windows Server App Fabric](/previous-versions/appfabric/ee677189(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="22f13-167">[Windows Server App Fabric Hosting Features](/previous-versions/appfabric/ee677189(v=azure.10))</span></span>
