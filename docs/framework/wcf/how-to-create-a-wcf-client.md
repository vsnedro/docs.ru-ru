---
title: Учебник. Создание клиента Windows Communication Foundation
description: Узнайте, как создать клиент, извлекая метаданные из службы WCF в составе серии статей, которые помогут приступить к созданию приложения WCF.
ms.date: 03/19/2019
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: d5a2a2b5175c9e34eaf1dbaff20ac57f34117c4e
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246328"
---
# <a name="tutorial-create-a-windows-communication-foundation-client"></a><span data-ttu-id="38ef7-103">Учебник. Создание клиента Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="38ef7-103">Tutorial: Create a Windows Communication Foundation client</span></span>

<span data-ttu-id="38ef7-104">В этом руководстве описываются четвертые из пяти задач, необходимых для создания базового приложения Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="38ef7-104">This tutorial describes the fourth of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="38ef7-105">Общие сведения о учебниках см. в разделе [учебник. Начало работы с Windows Communication Foundation приложениями](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="38ef7-105">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="38ef7-106">Следующей задачей для создания приложения WCF является создание клиента путем извлечения метаданных из службы WCF.</span><span class="sxs-lookup"><span data-stu-id="38ef7-106">The next task for creating a WCF application is to create a client by retrieving metadata from a WCF service.</span></span> <span data-ttu-id="38ef7-107">Для добавления ссылки на службу, которая получает метаданные из конечной точки обмена метаданными службы, используется Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="38ef7-107">You use Visual Studio to add a service reference, which gets the metadata from the service’s MEX endpoint.</span></span> <span data-ttu-id="38ef7-108">Затем Visual Studio создает управляемый файл исходного кода для прокси клиента на выбранном языке.</span><span class="sxs-lookup"><span data-stu-id="38ef7-108">Visual Studio then generates a managed source code file for a client proxy in the language you've chosen.</span></span> <span data-ttu-id="38ef7-109">Он также создает файл конфигурации клиента (*App.config*).</span><span class="sxs-lookup"><span data-stu-id="38ef7-109">It also creates a client configuration file (*App.config*).</span></span> <span data-ttu-id="38ef7-110">Этот файл позволяет клиентскому приложению подключаться к службе в конечной точке.</span><span class="sxs-lookup"><span data-stu-id="38ef7-110">This file enables the client application to connect to the service at an endpoint.</span></span>

> [!NOTE]
> <span data-ttu-id="38ef7-111">При вызове службы WCF из проекта библиотеки классов в Visual Studio используйте функцию **Добавление ссылки на службу** для автоматического создания прокси-сервера и связанного файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="38ef7-111">If you call a WCF service from a class library project in Visual Studio, use the **Add Service Reference** feature to automatically generate a proxy and associated configuration file.</span></span> <span data-ttu-id="38ef7-112">Однако, поскольку проекты библиотеки классов не используют этот файл конфигурации, необходимо добавить параметры в созданный файл конфигурации в файл *App.config* для исполняемого файла, вызывающего библиотеку классов.</span><span class="sxs-lookup"><span data-stu-id="38ef7-112">However, because class library projects don't use this configuration file, you need to add the settings in the generated configuration file to the *App.config* file for the executable that calls the class library.</span></span>

> [!NOTE]
> <span data-ttu-id="38ef7-113">В качестве альтернативы для создания прокси-класса и файла конфигурации вместо Visual Studio следует использовать [средство служебной программы для метаданных ServiceModel](#servicemodel-metadata-utility-tool) .</span><span class="sxs-lookup"><span data-stu-id="38ef7-113">As an alternative, use the [ServiceModel Metadata Utility tool](#servicemodel-metadata-utility-tool) instead of Visual Studio to generate the proxy class and configuration file.</span></span>

<span data-ttu-id="38ef7-114">Клиентское приложение использует созданный прокси-класс для взаимодействия со службой.</span><span class="sxs-lookup"><span data-stu-id="38ef7-114">The client application uses the generated proxy class to communicate with the service.</span></span> <span data-ttu-id="38ef7-115">Эта процедура описана в разделе [учебник. Использование клиента](how-to-use-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="38ef7-115">This procedure is described in [Tutorial: Use a client](how-to-use-a-wcf-client.md).</span></span>

<span data-ttu-id="38ef7-116">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="38ef7-116">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="38ef7-117">Создание и Настройка проекта консольного приложения для клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="38ef7-117">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="38ef7-118">Добавьте ссылку на службу WCF для создания прокси-класса и файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="38ef7-118">Add a service reference to the WCF service to generate the proxy class and configuration files.</span></span>

## <a name="create-a-windows-communication-foundation-client"></a><span data-ttu-id="38ef7-119">Создание клиента Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="38ef7-119">Create a Windows Communication Foundation client</span></span>

1. <span data-ttu-id="38ef7-120">Создание проекта консольного приложения в Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="38ef7-120">Create a console app project in Visual Studio:</span></span>

    1. <span data-ttu-id="38ef7-121">В меню **файл** выберите команду **Открыть**  >  **проект или решение** и перейдите к созданному ранее решению **GettingStarted** (*GettingStarted. sln*).</span><span class="sxs-lookup"><span data-stu-id="38ef7-121">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="38ef7-122">Щелкните **Open**(Открыть).</span><span class="sxs-lookup"><span data-stu-id="38ef7-122">Select **Open**.</span></span>

    2. <span data-ttu-id="38ef7-123">В меню **вид** выберите **Обозреватель решений**.</span><span class="sxs-lookup"><span data-stu-id="38ef7-123">From the **View** menu, select **Solution Explorer**.</span></span>

    3. <span data-ttu-id="38ef7-124">В окне **Обозреватель решений** выберите решение **GettingStarted** (верхний узел), а затем в контекстном меню выберите **добавить**  >  **Новый проект** .</span><span class="sxs-lookup"><span data-stu-id="38ef7-124">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span>

    4. <span data-ttu-id="38ef7-125">В левой части окна **Добавление нового проекта** выберите категорию **Рабочий стол Windows** в разделе **Visual C#** или **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="38ef7-125">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span>

    5. <span data-ttu-id="38ef7-126">Выберите шаблон **консольное приложение (.NET Framework)** и введите *GettingStartedClient* в поле **имя**.</span><span class="sxs-lookup"><span data-stu-id="38ef7-126">Select the **Console App (.NET Framework)** template, and enter *GettingStartedClient* for the **Name**.</span></span> <span data-ttu-id="38ef7-127">Щелкните **ОК**.</span><span class="sxs-lookup"><span data-stu-id="38ef7-127">Select **OK**.</span></span>

2. <span data-ttu-id="38ef7-128">Добавьте ссылку в проект **GettingStartedClient** в <xref:System.ServiceModel> сборку:</span><span class="sxs-lookup"><span data-stu-id="38ef7-128">Add a reference in the **GettingStartedClient** project to the <xref:System.ServiceModel> assembly:</span></span>

    1. <span data-ttu-id="38ef7-129">В окне **Обозреватель решений** выберите папку **References** в проекте **GettingStartedClient** , а затем в контекстном меню выберите пункт **Добавить ссылку** .</span><span class="sxs-lookup"><span data-stu-id="38ef7-129">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Reference** from the shortcut menu.</span></span>

    2. <span data-ttu-id="38ef7-130">В окне **Добавление ссылки** в разделе **сборки** в левой части окна выберите **платформа**.</span><span class="sxs-lookup"><span data-stu-id="38ef7-130">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span>

    3. <span data-ttu-id="38ef7-131">Найдите и выберите **System. ServiceModel**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="38ef7-131">Find and select **System.ServiceModel**, and then choose **OK**.</span></span>

    4. <span data-ttu-id="38ef7-132">Сохраните решение, выбрав **файл**  >  **сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="38ef7-132">Save the solution by selecting **File** > **Save All**.</span></span>

3. <span data-ttu-id="38ef7-133">Добавьте ссылку на службу в службу калькулятора:</span><span class="sxs-lookup"><span data-stu-id="38ef7-133">Add a service reference to the calculator service:</span></span>

   1. <span data-ttu-id="38ef7-134">В окне **Обозреватель решений** выберите папку **References** в проекте **GettingStartedClient** , а затем в контекстном меню выберите **Добавление ссылки на службу** .</span><span class="sxs-lookup"><span data-stu-id="38ef7-134">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Service Reference** from the shortcut menu.</span></span>

   2. <span data-ttu-id="38ef7-135">В окне **Добавление ссылки на службу** выберите **Обнаружение**.</span><span class="sxs-lookup"><span data-stu-id="38ef7-135">In the **Add Service Reference** window, select **Discover**.</span></span>

      <span data-ttu-id="38ef7-136">Служба CalculatorService запускается, и Visual Studio отображает ее в окне **службы** .</span><span class="sxs-lookup"><span data-stu-id="38ef7-136">The CalculatorService service starts and Visual Studio displays it in the **Services** box.</span></span>

   3. <span data-ttu-id="38ef7-137">Выберите **CalculatorService** , чтобы развернуть его и отобразить контракты службы, реализованные службой.</span><span class="sxs-lookup"><span data-stu-id="38ef7-137">Select **CalculatorService** to expand it and display the service contracts implemented by the service.</span></span> <span data-ttu-id="38ef7-138">Оставьте **пространство имен** по умолчанию и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="38ef7-138">Leave the default **Namespace** and choose **OK**.</span></span>

      <span data-ttu-id="38ef7-139">Visual Studio добавит новый элемент в папку **подключенные службы** проекта **GettingStartedClient** .</span><span class="sxs-lookup"><span data-stu-id="38ef7-139">Visual Studio adds a new item under the **Connected Services** folder in the **GettingStartedClient** project.</span></span>

### <a name="servicemodel-metadata-utility-tool"></a><span data-ttu-id="38ef7-140">Средство служебной программы метаданных ServiceModel</span><span class="sxs-lookup"><span data-stu-id="38ef7-140">ServiceModel Metadata Utility tool</span></span>

<span data-ttu-id="38ef7-141">В следующих примерах показано, как при необходимости использовать [средство служебной программы метаданных ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) для создания файла прокси-класса.</span><span class="sxs-lookup"><span data-stu-id="38ef7-141">The following examples show how to optionally use the [ServiceModel Metadata Utility tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the proxy class file.</span></span> <span data-ttu-id="38ef7-142">Это средство создает файл прокси-класса и файл *App.config* .</span><span class="sxs-lookup"><span data-stu-id="38ef7-142">This tool generates the proxy class file and the *App.config* file.</span></span> <span data-ttu-id="38ef7-143">В следующих примерах показано, как создать прокси-сервер в C# и Visual Basic соответственно:</span><span class="sxs-lookup"><span data-stu-id="38ef7-143">The following examples show how to generate the proxy in C# and Visual Basic, respectively:</span></span>

```shell
svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

```shell
svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

### <a name="client-configuration-file"></a><span data-ttu-id="38ef7-144">Файл конфигурации клиента</span><span class="sxs-lookup"><span data-stu-id="38ef7-144">Client configuration file</span></span>

<span data-ttu-id="38ef7-145">После создания клиента Visual Studio создаст файл конфигурации **App.config** в проекте **GettingStartedClient** , который должен быть похож на следующий пример:</span><span class="sxs-lookup"><span data-stu-id="38ef7-145">After you've created the client, Visual Studio creates the **App.config** configuration file in the **GettingStartedClient** project, which should be similar to the following example:</span></span>

```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
        <startup>
            <!-- specifies the version of WCF to use-->
            <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6.1" />
        </startup>
        <system.serviceModel>
            <bindings>
                <!-- Uses wsHttpBinding-->
                <wsHttpBinding>
                    <binding name="WSHttpBinding_ICalculator" />
                </wsHttpBinding>
            </bindings>
            <client>
                <!-- specifies the endpoint to use when calling the service -->
                <endpoint address="http://localhost:8000/GettingStarted/CalculatorService"
                    binding="wsHttpBinding" bindingConfiguration="WSHttpBinding_ICalculator"
                    contract="ServiceReference1.ICalculator" name="WSHttpBinding_ICalculator">
                    <identity>
                        <dns value="localhost" />
                    </identity>
                </endpoint>
            </client>
        </system.serviceModel>
    </configuration>
```

<span data-ttu-id="38ef7-146">В [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) разделе Обратите внимание на [\<endpoint>](../configure-apps/file-schema/wcf/endpoint-element.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="38ef7-146">Under the [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) section, notice the [\<endpoint>](../configure-apps/file-schema/wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="38ef7-147">Элемент \*\* &lt; Endpoint &gt; \*\* определяет конечную точку, которую клиент использует для доступа к службе следующим образом:</span><span class="sxs-lookup"><span data-stu-id="38ef7-147">The **&lt;endpoint&gt;** element defines the endpoint that the client uses to access the service as follows:</span></span>

- <span data-ttu-id="38ef7-148">Адрес: `http://localhost:8000/GettingStarted/CalculatorService` .</span><span class="sxs-lookup"><span data-stu-id="38ef7-148">Address: `http://localhost:8000/GettingStarted/CalculatorService`.</span></span> <span data-ttu-id="38ef7-149">Адрес конечной точки.</span><span class="sxs-lookup"><span data-stu-id="38ef7-149">The address of the endpoint.</span></span>
- <span data-ttu-id="38ef7-150">Контракт службы: `ServiceReference1.ICalculator` .</span><span class="sxs-lookup"><span data-stu-id="38ef7-150">Service contract: `ServiceReference1.ICalculator`.</span></span> <span data-ttu-id="38ef7-151">Контракт службы обрабатывает взаимодействие между клиентом WCF и службой.</span><span class="sxs-lookup"><span data-stu-id="38ef7-151">The service contract handles communication between the WCF client and the service.</span></span> <span data-ttu-id="38ef7-152">Visual Studio создала этот контракт при использовании функции **Добавление ссылки на службу** .</span><span class="sxs-lookup"><span data-stu-id="38ef7-152">Visual Studio generated this contract when you used its **Add Service Reference** function.</span></span> <span data-ttu-id="38ef7-153">По сути, это копия контракта, определенного в проекте Жеттингстартедлиб.</span><span class="sxs-lookup"><span data-stu-id="38ef7-153">It's essentially a copy of the contract that you defined in the GettingStartedLib project.</span></span>
- <span data-ttu-id="38ef7-154">Привязка: <xref:System.ServiceModel.WSHttpBinding> .</span><span class="sxs-lookup"><span data-stu-id="38ef7-154">Binding: <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="38ef7-155">Привязка указывает HTTP как транспорт, взаимодействующую безопасность и другие сведения о конфигурации.</span><span class="sxs-lookup"><span data-stu-id="38ef7-155">The binding specifies HTTP as the transport, interoperable security, and other configuration details.</span></span>

## <a name="next-steps"></a><span data-ttu-id="38ef7-156">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="38ef7-156">Next steps</span></span>

<span data-ttu-id="38ef7-157">В этом руководстве вы узнали, как выполнять следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="38ef7-157">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="38ef7-158">Создание и Настройка проекта консольного приложения для клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="38ef7-158">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="38ef7-159">Добавьте ссылку на службу WCF, чтобы создать класс прокси и файлы конфигурации для клиентского приложения.</span><span class="sxs-lookup"><span data-stu-id="38ef7-159">Add a service reference to the WCF service to generate the proxy class and configuration files for the client application.</span></span>

<span data-ttu-id="38ef7-160">Перейдите к следующему руководству, чтобы узнать, как использовать созданный клиент.</span><span class="sxs-lookup"><span data-stu-id="38ef7-160">Advance to the next tutorial to learn how to use the generated client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="38ef7-161">Учебник. Использование клиента WCF</span><span class="sxs-lookup"><span data-stu-id="38ef7-161">Tutorial: Use a WCF client</span></span>](how-to-use-a-wcf-client.md)
