---
title: Средство редактирования конфигурации (SvcConfigEditor.exe)
description: Узнайте, как управлять параметрами привязок, поведения, служб и диагностики WCF с помощью редактора конфигурации службы WCF.
ms.date: 03/30/2017
helpviewer_keywords:
- configuration files, creating
- configuration files
- Configuration file
- configuration file schema
ms.assetid: 2db21a57-5f64-426f-89df-fb0dc2d2def5
ms.openlocfilehash: 258437ff616b969d40feabbfff364ad2cc6b25bc
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247653"
---
# <a name="configuration-editor-tool-svcconfigeditorexe"></a><span data-ttu-id="d2b8e-103">Средство редактирования конфигурации (SvcConfigEditor.exe)</span><span class="sxs-lookup"><span data-stu-id="d2b8e-103">Configuration Editor Tool (SvcConfigEditor.exe)</span></span>

<span data-ttu-id="d2b8e-104">Редактор конфигурации служб Windows Communication Foundation (WCF) (SvcConfigEditor.exe) позволяет администраторам и разработчикам создавать и изменять параметры конфигурации служб WCF при помощи графического пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-104">The Windows Communication Foundation (WCF) Service Configuration Editor (SvcConfigEditor.exe) allows administrators and developers to create and modify configuration settings for WCF services using a graphical user interface.</span></span> <span data-ttu-id="d2b8e-105">С помощью этого средства можно управлять параметрами привязок WCF, поведений, служб и диагностики без необходимости непосредственного изменения XML-файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-105">With this tool, you can manage settings for WCF bindings, behaviors, services, and diagnostics without having to directly edit XML configuration files.</span></span>

<span data-ttu-id="d2b8e-106">Редактор конфигураций служб находится в папке C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-106">Service Configuration Editor can be found in the C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin folder.</span></span>

## <a name="the-wcf-configuration-editor"></a><span data-ttu-id="d2b8e-107">Редактор конфигураций WCF</span><span class="sxs-lookup"><span data-stu-id="d2b8e-107">The WCF Configuration Editor</span></span>

<span data-ttu-id="d2b8e-108">Редактор конфигурации служб поставляется с мастером, который используется для настройки служб и клиентов WCF.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-108">Service Configuration Editor comes with a wizard that guides you through all the steps in configuring a WCF service or client.</span></span> <span data-ttu-id="d2b8e-109">Настоятельно рекомендуется использовать этот мастер, а не сам редактор.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-109">You are strongly advised to use the wizard instead of the editor directly.</span></span>

<span data-ttu-id="d2b8e-110">Если уже имеются файлы конфигурации, которые соответствуют стандартной схеме системной конфигурации, то с помощью пользовательского интерфейса можно управлять специальными параметрами привязок, поведения, служб и диагностики.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-110">If you already have some configuration files that comply with the standard System.Configuration schema, you can manage specific settings for bindings, behavior, services, and diagnostics with the user interface.</span></span> <span data-ttu-id="d2b8e-111">Редактор конфигурации служб позволяет управлять параметрами существующих файлов конфигурации WCF, а также исполняемых файлов, служб COM+ и служб, размещенных на веб-сервере.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-111">The Service Configuration Editor enables you to manage the settings for existing WCF configuration files as well as executable files, COM+ services, and Web-hosted services.</span></span> <span data-ttu-id="d2b8e-112">Когда служба, размещаемая на веб-сервере, открывается в редакторе конфигурации служб, то отображается и собственная конфигурация служб, и разделы конфигурации, унаследованные от узлов верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-112">When opening a Web-hosted service with Service Configuration Editor, both the service’s own configuration and inherited configurations sections of upper level nodes are shown.</span></span>

<span data-ttu-id="d2b8e-113">Поскольку параметры конфигурации WCF находятся в разделе `<system.serviceModel>` файла конфигурации, редактор работает исключительно с содержимым этого элемента и не осуществляет доступ к другим элементам в данном файле.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-113">Because WCF configuration settings are located in the `<system.serviceModel>` section of the configuration file, the editor operates exclusively on the content of this element and does not access other elements in the same file.</span></span> <span data-ttu-id="d2b8e-114">Можно напрямую перейти к существующим файлам конфигурации или выбрать сборку, содержащую службу, виртуальный каталог или службу COM+.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-114">You can navigate to existing configuration files directly or you can select an assembly that contains a service, virtual directory, or COM+ service.</span></span> <span data-ttu-id="d2b8e-115">Редактор загружает файл конфигурации для конкретной службы и позволяет пользователю добавить новые или изменить существующие элементы, расположенные в разделе `<system.serviceModel>` файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-115">The editor loads the configuration file for that particular service and allows the user to either add new elements or edit existing elements nested in the `<system.serviceModel>` section of the configuration file.</span></span>

<span data-ttu-id="d2b8e-116">Редактор поддерживает технологию IntelliSense и обеспечивает соответствие схеме.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-116">The editor supports IntelliSense and enforces schema compliance.</span></span> <span data-ttu-id="d2b8e-117">Редактор гарантирует, что результирующие выходные данные будут соответствовать схеме файла конфигурации и иметь синтаксически правильные значения.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-117">The resulting output is guaranteed to comply with the schema of the configuration file and to have syntactically correct data values.</span></span> <span data-ttu-id="d2b8e-118">Однако редактор не гарантирует, что файл конфигурации будет допустимым с точки зрения семантики.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-118">However, the editor does not guarantee that the configuration file is semantically valid.</span></span> <span data-ttu-id="d2b8e-119">Другими словами, редактор не гарантирует, что файл конфигурации будет работать со службой, которая в нем настраивается.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-119">In other words, the editor does not guarantee that the configuration file can work with the service it configures.</span></span>

> [!CAUTION]
> <span data-ttu-id="d2b8e-120">После изменения элемента конфигурации редактор не позволяет удалить его из файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-120">The editor cannot purge a configuration element from the configuration file once you have modified the element.</span></span> <span data-ttu-id="d2b8e-121">Например, при использовании редактора для задания и сохранения непустого строкового имени конечной точки файл конфигурации будет включать содержимое, показанное в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-121">For example, if you use the editor to set the endpoint name to a non-empty string and save it, the configuration file has the following content, as shown in the following example.</span></span>
>
> `<endpoint binding="basicHttpBinding" name="somename" />`
>
> <span data-ttu-id="d2b8e-122">Если попытаться удалить имя путем задания пустой строки и сохранить файл, то файл конфигурации будет по-прежнему включать атрибут `name`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-122">If you attempt to remove the name by setting it to an empty string and save the file, the configuration file still contains the `name` attribute, as shown in the following example.</span></span>
>
> `<endpoint binding="basicHttpBinding" name="" />`
>
> <span data-ttu-id="d2b8e-123">Чтобы удалить атрибут, необходимо вручную изменить элемент с помощью другого текстового редактора.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-123">To purge the attribute, you must manually edit the element using another text editor.</span></span>
>
> <span data-ttu-id="d2b8e-124">Это особенно следует учитывать при использовании элемента `issueToken` поведения `clientCredential` конечной точки.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-124">You should be especially careful with this issue when you use the `issueToken` element of the `clientCredential` Endpoint behavior.</span></span> <span data-ttu-id="d2b8e-125">В частности, атрибут `address` вложенного элемента `localIssuer` не должен быть пустой строкой.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-125">Specifically, the `address` attribute of its `localIssuer` sub-element must not be an empty string.</span></span> <span data-ttu-id="d2b8e-126">Чтобы удалить атрибут `address`, измененный с помощью редактора конфигураций, необходимо использовать средство, отличное от этого редактора.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-126">If you have modified the `address` attribute using the Configuration Editor and want to remove it completely, you should do so using a tool other than the Editor.</span></span> <span data-ttu-id="d2b8e-127">В противном случае атрибут будет содержать пустую строку и в приложении возникнет исключение.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-127">Otherwise, the attribute contains an empty string and your application throws an exception.</span></span>

## <a name="using-the-configuration-editor"></a><span data-ttu-id="d2b8e-128">Использование редактора конфигураций</span><span class="sxs-lookup"><span data-stu-id="d2b8e-128">Using the Configuration Editor</span></span>

<span data-ttu-id="d2b8e-129">Редактор конфигураций служб находится в папке установки Windows SDK:</span><span class="sxs-lookup"><span data-stu-id="d2b8e-129">The Service Configuration Editor can be found at the following Windows SDK installation location:</span></span>

<span data-ttu-id="d2b8e-130">C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin\SvcConfigEditor.exe</span><span class="sxs-lookup"><span data-stu-id="d2b8e-130">C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin\SvcConfigEditor.exe</span></span>

<span data-ttu-id="d2b8e-131">После запуска редактора конфигурации служб можно использовать меню **файл/открыть** для поиска службы или сборки, которыми требуется управлять.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-131">After you launch the Service Configuration Editor, you can use the **File/Open** menu to browse for the service or assembly you want to manage.</span></span> <span data-ttu-id="d2b8e-132">Можно непосредственно открывать файлы конфигурации, выбирать службы WCF/COM+ и открывать файлы конфигурации для служб, размещенных на веб-сервере.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-132">You can open configuration files directly, browse for WCF /COM+ services, and open configuration files for Web-hosted services.</span></span>

<span data-ttu-id="d2b8e-133">Пользовательский интерфейс редактора конфигураций служб разделен на следующие области.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-133">The Service Configuration Editor's user interface is divided into the following areas:</span></span>

- <span data-ttu-id="d2b8e-134">Область дерева, в которой элементы конфигурации отображаются в виде древовидной структуры слева.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-134">Tree View Pane, which displays configuration elements in a tree structure on the left.</span></span> <span data-ttu-id="d2b8e-135">Операции в дереве можно выполнять, щелкая узлы правой кнопкой мыши.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-135">You can perform operations in the tree by right-clicking the nodes.</span></span>

- <span data-ttu-id="d2b8e-136">Область задач, где в левой нижней части окна показаны распространенные задачи для текущих элементов</span><span class="sxs-lookup"><span data-stu-id="d2b8e-136">Task Pane, which displays common tasks for current elements on the lower-left of the window</span></span>

- <span data-ttu-id="d2b8e-137">Область сведений, где подробно отображаются параметры узла конфигурации, выбранного в области дерева справа.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-137">Detail Pane, which displays detailed settings of the configuration node selected in the Tree View on the right.</span></span>

### <a name="opening-a-configuration-file"></a><span data-ttu-id="d2b8e-138">Открытие файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="d2b8e-138">Opening a Configuration File</span></span>

1. <span data-ttu-id="d2b8e-139">Запустите редактор конфигурации служб, используя командное окно, чтобы перейти к расположению установки WCF, а затем введите `SvcConfigEditor.exe` .</span><span class="sxs-lookup"><span data-stu-id="d2b8e-139">Start Service Configuration Editor by using a command window to navigate to your WCF installation location, and then type `SvcConfigEditor.exe`.</span></span>

2. <span data-ttu-id="d2b8e-140">В меню **файл** выберите **Открыть** и выберите тип файла, которым требуется управлять.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-140">From the **File** menu, select **Open** and click the type of file you want to manage.</span></span>

3. <span data-ttu-id="d2b8e-141">В диалоговом окне **Открыть** перейдите к определенному файлу, который требуется изменить, и дважды щелкните его.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-141">In the **Open** dialog box, navigate to the specific file you want to manage and double-click it.</span></span>

<span data-ttu-id="d2b8e-142">Средство просмотра автоматически следует пути слияния конфигураций и создает представление объединенной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-142">The viewer automatically follows the configuration merge path and creates a view of the merged configuration.</span></span> <span data-ttu-id="d2b8e-143">Например, действующая конфигурация неразмещенной службы представляет собой сочетание файлов Machine.config и App.config. Любые изменения, вносимые в редакторе SvcConfigEditor, применяются к активному файлу.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-143">For example, the actual configuration of a non-hosted service is a combination of Machine.config and App.config. Any changes are applied to the active file in the SvcConfigEditor.</span></span> <span data-ttu-id="d2b8e-144">Чтобы изменить конкретный файл в пути слияния конфигураций, его необходимо открыть напрямую.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-144">If you want to edit a specific file in the configuration merge path, you should open it directly.</span></span>

> [!NOTE]
> <span data-ttu-id="d2b8e-145">Редактор конфигураций повторно загружает открытый в данный момент файл конфигурации при его изменении вне редактора.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-145">Configuration Editor reloads the currently opened configuration file when the latter has been modified outside the Editor.</span></span> <span data-ttu-id="d2b8e-146">Когда это происходит, теряются все изменения, которые не были сохранены в редакторе.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-146">When this happens, all the changes that are not durably saved inside the Editor are lost.</span></span> <span data-ttu-id="d2b8e-147">Наиболее вероятной причиной постоянной повторной загрузки является постоянный доступ к файлу конфигурации со стороны некоторой службы, например антивирусной программы, работающей в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-147">If reloading happens consistently, the most likely cause is a service that constantly accesses the configuration file, for example, an antivirus software running in the background.</span></span> <span data-ttu-id="d2b8e-148">Для решения этой проблемы обеспечьте, чтобы редактор конфигураций был единственным процессом, который может осуществлять доступ к файлу, когда он открыт.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-148">To resolve this, ensure that Configuration Editor is the only process that can access the file when it is opened.</span></span>

### <a name="services"></a><span data-ttu-id="d2b8e-149">Службы</span><span class="sxs-lookup"><span data-stu-id="d2b8e-149">Services</span></span>

<span data-ttu-id="d2b8e-150">В узле **службы** отображаются все службы, назначенные в данный момент в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-150">The **Services** node displays all of the services currently assigned in the configuration file.</span></span> <span data-ttu-id="d2b8e-151">Каждый подузел в дереве соответствует вложенному элементу <`services` элемента> в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-151">Each sub-node in the tree corresponds to a sub-element of the <`services`> element in the configuration file.</span></span>

<span data-ttu-id="d2b8e-152">Щелкнув узел **службы** , можно просмотреть или выполнить задачи на странице Сводка службы в области **сведений** .</span><span class="sxs-lookup"><span data-stu-id="d2b8e-152">When you click the **Services** node, you can view or perform tasks on the service Summary Page in the **Detail** Pane.</span></span>

#### <a name="creating-a-new-service-configuration"></a><span data-ttu-id="d2b8e-153">Создание конфигурации службы</span><span class="sxs-lookup"><span data-stu-id="d2b8e-153">Creating a new Service Configuration</span></span>

<span data-ttu-id="d2b8e-154">Новую конфигурацию службы можно создать одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-154">You can create a new service configuration in the following ways:</span></span>

- <span data-ttu-id="d2b8e-155">Использование мастера: щелкните ссылку **создать новую службу...**</span><span class="sxs-lookup"><span data-stu-id="d2b8e-155">Using a Wizard: Click the link **Create a New Service…**</span></span> <span data-ttu-id="d2b8e-156">в области задач или на странице Сводка, чтобы запустить мастер.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-156">on the Task Pane or Summary Page to launch the wizard.</span></span> <span data-ttu-id="d2b8e-157">Это также можно сделать в меню **файл** — > **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-157">You can also do so in the **File** menu -> **Add New Item**.</span></span>

- <span data-ttu-id="d2b8e-158">Создать вручную. можно щелкнуть правой кнопкой мыши узел **службы** и выбрать пункт **создать службу**.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-158">Create manually: You can right-click the **Services** node and choose **New Service**.</span></span>

#### <a name="creating-a-new-service-endpoint-configuration"></a><span data-ttu-id="d2b8e-159">Создание новой конфигурации конечной точки службы</span><span class="sxs-lookup"><span data-stu-id="d2b8e-159">Creating a new Service Endpoint Configuration</span></span>

<span data-ttu-id="d2b8e-160">Новую конфигурацию конечной точки службы можно создать одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-160">You can create a new service endpoint configuration in the following ways:</span></span>

- <span data-ttu-id="d2b8e-161">Создание с помощью мастера: щелкните ссылку **создать новую конечную точку службы...**</span><span class="sxs-lookup"><span data-stu-id="d2b8e-161">Create using a Wizard: click the link **Create a New Service Endpoint…**</span></span> <span data-ttu-id="d2b8e-162">в области задач или на странице Сводка, чтобы запустить мастер.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-162">on the Task Pane or Summary Page to launch the wizard.</span></span> <span data-ttu-id="d2b8e-163">Это также можно сделать в меню **файл** — > **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-163">You can also do so in the **File** menu -> **Add New Item**.</span></span>

- <span data-ttu-id="d2b8e-164">Создание вручную. После создания службы можно щелкнуть правой кнопкой мыши узел **конечные точки** и выбрать пункт "**создать конечную точку службы**".</span><span class="sxs-lookup"><span data-stu-id="d2b8e-164">Create manually: Once you created a Service, you can right-click the **Endpoints** node and choose "**New Service Endpoint**".</span></span>

#### <a name="editing-a-service-configuration"></a><span data-ttu-id="d2b8e-165">Изменение конфигурации службы</span><span class="sxs-lookup"><span data-stu-id="d2b8e-165">Editing a Service Configuration</span></span>

1. <span data-ttu-id="d2b8e-166">Щелкните узел **службы** .</span><span class="sxs-lookup"><span data-stu-id="d2b8e-166">Click a **Service** node.</span></span>

2. <span data-ttu-id="d2b8e-167">Измените параметры в сетках свойств.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-167">Edit the settings in the property grids.</span></span>

#### <a name="editing-a-service-endpoint-configuration"></a><span data-ttu-id="d2b8e-168">Изменение конфигурации конечной точки службы</span><span class="sxs-lookup"><span data-stu-id="d2b8e-168">Editing a Service Endpoint Configuration</span></span>

1. <span data-ttu-id="d2b8e-169">Щелкните узел **конечной точки службы** .</span><span class="sxs-lookup"><span data-stu-id="d2b8e-169">Click a **Service Endpoint** node.</span></span>

2. <span data-ttu-id="d2b8e-170">Измените параметры в сетках свойств.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-170">Edit the settings in the property grids.</span></span>

#### <a name="adding-a-base-address"></a><span data-ttu-id="d2b8e-171">Добавление базового адреса</span><span class="sxs-lookup"><span data-stu-id="d2b8e-171">Adding a Base Address</span></span>

1. <span data-ttu-id="d2b8e-172">Щелкните узел **узла** .</span><span class="sxs-lookup"><span data-stu-id="d2b8e-172">Click the **Host** node.</span></span>

2. <span data-ttu-id="d2b8e-173">Нажмите кнопку **Создать…**</span><span class="sxs-lookup"><span data-stu-id="d2b8e-173">Click the **New…**</span></span> <span data-ttu-id="d2b8e-174">(основные адреса) в разделе **базовых адресов** .</span><span class="sxs-lookup"><span data-stu-id="d2b8e-174">button in the **Base Addresses** section.</span></span>

3. <span data-ttu-id="d2b8e-175">Введите URI базового адреса в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-175">Type in the base address URI in the dialog box.</span></span>

4. <span data-ttu-id="d2b8e-176">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-176">Click **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="d2b8e-177">Значение [\<baseAddressPrefixFilters>](../configure-apps/file-schema/wcf/baseaddressprefixfilters.md) внутри этого средства изменить нельзя.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-177">You cannot edit the value of [\<baseAddressPrefixFilters>](../configure-apps/file-schema/wcf/baseaddressprefixfilters.md) inside this tool.</span></span> <span data-ttu-id="d2b8e-178">Чтобы добавить или изменить данный элемент, используйте текстовый редактор или среду Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-178">To add or modify this element, you should use a text editor or Visual Studio.</span></span>

### <a name="client"></a><span data-ttu-id="d2b8e-179">клиент</span><span class="sxs-lookup"><span data-stu-id="d2b8e-179">Client</span></span>

<span data-ttu-id="d2b8e-180">Узел **клиента** отображает все конечные точки клиента в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-180">The **Client** node displays all of the client endpoints in the configuration file.</span></span> <span data-ttu-id="d2b8e-181">Каждый подузел в дереве соответствует вложенному элементу <`client` элемента> в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-181">Every sub-node in the tree corresponds to a sub-element of the <`client`> element in the configuration file.</span></span>

<span data-ttu-id="d2b8e-182">Щелкнув узел **клиента** , можно просмотреть или выполнить задачи на **странице Сводка** клиента в **области сведений**.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-182">When you click the **Client** node, you can view or perform tasks on the client **Summary Page** in the **Detail Pane**.</span></span>

#### <a name="creating-a-new-client-endpoint-configuration"></a><span data-ttu-id="d2b8e-183">Создание конфигурации конечной точки клиента</span><span class="sxs-lookup"><span data-stu-id="d2b8e-183">Creating a new Client Endpoint Configuration</span></span>

<span data-ttu-id="d2b8e-184">Новую конфигурацию конечной точки клиента можно создать одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-184">You can create a new client endpoint configuration in the following ways:</span></span>

- <span data-ttu-id="d2b8e-185">Создание с помощью мастера: щелкните ссылку **создать новый клиент...**</span><span class="sxs-lookup"><span data-stu-id="d2b8e-185">Create by Wizard: Click the link **Create a New Client…**</span></span> <span data-ttu-id="d2b8e-186">в **области задач** в левом нижнем углу окна или на **странице Сводка** для запуска мастера.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-186">on the **Task Pane** on the lower-left of the window, or **Summary Page** to launch the wizard.</span></span> <span data-ttu-id="d2b8e-187">Это также можно сделать в меню **файл** — > **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-187">You can also do so in the **File** menu -> **Add New Item**.</span></span> <span data-ttu-id="d2b8e-188">Мастер предложит указать расположение конфигурации службы, из которой создается конфигурация клиента.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-188">The wizard prompts you to point to the location of the service configuration, from which the client configuration is generated.</span></span> <span data-ttu-id="d2b8e-189">Затем можно выбрать конечную точку службы для подключения.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-189">You can then choose the service endpoint to connect to.</span></span>

- <span data-ttu-id="d2b8e-190">Создать вручную. Щелкните правой кнопкой мыши узел **конечные точки** в разделе **клиент**и выберите пункт **новая конечная точка клиента**.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-190">Create manually: Right-click the **Endpoints** node under **Client**, and choose **New Client Endpoint**.</span></span>

#### <a name="editing-a-client-endpoint-configuration"></a><span data-ttu-id="d2b8e-191">Изменение конфигурации конечной точки клиента</span><span class="sxs-lookup"><span data-stu-id="d2b8e-191">Editing a Client Endpoint Configuration</span></span>

1. <span data-ttu-id="d2b8e-192">Щелкните узел **конечной точки клиента** .</span><span class="sxs-lookup"><span data-stu-id="d2b8e-192">Click a **Client Endpoint** node.</span></span>

2. <span data-ttu-id="d2b8e-193">Измените параметры в сетках свойств.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-193">Edit the settings in the property grids.</span></span>

### <a name="standard-endpoint"></a><span data-ttu-id="d2b8e-194">Стандартная конечная точка</span><span class="sxs-lookup"><span data-stu-id="d2b8e-194">Standard Endpoint</span></span>

<span data-ttu-id="d2b8e-195">Стандартные конечные точки - это специальные точки, в которых один или несколько аспектов адреса, контракта и привязки установлены в значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-195">Standard endpoints are specialized endpoints that have one or more aspects of the address, contract and binding set to default values.</span></span>

<span data-ttu-id="d2b8e-196">Такие параметры конфигурации хранятся в узле **стандартной конечной точки** .</span><span class="sxs-lookup"><span data-stu-id="d2b8e-196">Such configuration settings are stored in the **Standard Endpoint** node.</span></span> <span data-ttu-id="d2b8e-197">Узел **стандартной конечной точки** отображает все стандартные параметры конечной точки в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-197">The **Standard Endpoint** node displays all of the standard endpoint settings in the configuration file.</span></span> <span data-ttu-id="d2b8e-198">Каждый вложенный узел в дереве соответствует вложенному элементу в `<standardEndpoints>` элементе файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-198">Every sub-node in the tree corresponds to a sub-element in the `<standardEndpoints>` element in the configuration file.</span></span>

<span data-ttu-id="d2b8e-199">Щелкнув узел **стандартной конечной точки** , можно просмотреть или выполнить задачи на **странице Сводка по** стандартной конечной точке в **области сведений**.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-199">When you click the **Standard Endpoint** node, you can view or perform tasks on the standard endpoint **Summary Page** in the **Detail Pane**.</span></span>

#### <a name="creating-a-new-standard-endpoint-configuration"></a><span data-ttu-id="d2b8e-200">Создание новой конфигурации стандартной конечной точки</span><span class="sxs-lookup"><span data-stu-id="d2b8e-200">Creating a New Standard Endpoint Configuration</span></span>

<span data-ttu-id="d2b8e-201">Новую конфигурацию стандартной конечной точки можно создать одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-201">You can create a new standard endpoint configuration in the following ways:</span></span>

- <span data-ttu-id="d2b8e-202">Щелкните правой кнопкой мыши узел **стандартной конечной точки** и выберите **создать стандартную конфигурацию конечной точки...**</span><span class="sxs-lookup"><span data-stu-id="d2b8e-202">Right-click the **Standard Endpoint** node and select **New Standard Endpoint Configuration…**</span></span> <span data-ttu-id="d2b8e-203">Выберите тип привязки в диалоговом окне и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-203">Select the binding type in the dialog box and click **OK**.</span></span>

- <span data-ttu-id="d2b8e-204">Выберите узел **Стандартная конечная точка** и нажмите кнопку **создать стандартную конфигурацию конечной точки...**</span><span class="sxs-lookup"><span data-stu-id="d2b8e-204">Select the **Standard Endpoint** node and click **New Standard Endpoint Configuration…**</span></span> <span data-ttu-id="d2b8e-205">в **области задач** в левом нижнем углу окна.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-205">in the **Task Pane** on the lower-left of the window.</span></span>

<span data-ttu-id="d2b8e-206">Откроется диалоговое окно **Создание новой стандартной конечной точки** , в котором перечислены все зарегистрированные типы стандартных конечных точек.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-206">The **Creating a New Standard Endpoint** dialog box displays and lists all registered standard endpoint types.</span></span>

#### <a name="viewing-and-editing-a-standard-endpoint-configuration"></a><span data-ttu-id="d2b8e-207">Просмотр и изменение конфигурации стандартной конечной точки</span><span class="sxs-lookup"><span data-stu-id="d2b8e-207">Viewing and Editing a Standard Endpoint Configuration</span></span>

<span data-ttu-id="d2b8e-208">Конфигурацию стандартной конечной точки можно открыть для просмотра и изменения следующими способами.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-208">You can open a standard endpoint configuration for viewing and editing in the following ways:</span></span>

- <span data-ttu-id="d2b8e-209">Щелкните, чтобы развернуть узел **стандартной конечной точки** и щелкнуть соответствующий вложенный узел конечной точки.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-209">Click to expand the **Standard Endpoint** node and click the respective endpoint sub-node.</span></span>

- <span data-ttu-id="d2b8e-210">Щелкните узел **Стандартная конечная точка** и выберите соответствующую конечную точку в области сведений.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-210">Click the **Standard Endpoint** node and click the respective endpoint on the Detail pane.</span></span>

<span data-ttu-id="d2b8e-211">Атрибуты конечной точки будут доступны для изменения в правой области окна.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-211">Attributes for the endpoint are shown in the right pane for editing.</span></span>

#### <a name="deleting-a-standard-endpoint-configuration"></a><span data-ttu-id="d2b8e-212">Удаление конфигурации стандартной конечной точки</span><span class="sxs-lookup"><span data-stu-id="d2b8e-212">Deleting a Standard Endpoint Configuration</span></span>

<span data-ttu-id="d2b8e-213">Конфигурацию стандартной конечной точки можно удалить одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-213">You can delete a standard endpoint configuration in the following ways:</span></span>

- <span data-ttu-id="d2b8e-214">Щелкните, чтобы развернуть узел **стандартной конечной точки** и щелкнуть правой кнопкой мыши соответствующий вложенный узел конечной точки.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-214">Click to expand the **Standard Endpoint** node and right-click the respective endpoint sub-node.</span></span> <span data-ttu-id="d2b8e-215">Чтобы удалить конечную точку, используйте контекстную команду **удалить стандартную конфигурацию конечной точки** .</span><span class="sxs-lookup"><span data-stu-id="d2b8e-215">Use the context command **Delete Standard Endpoint Configuration** to delete the endpoint.</span></span>

- <span data-ttu-id="d2b8e-216">Щелкните узел **Стандартная конечная точка** .</span><span class="sxs-lookup"><span data-stu-id="d2b8e-216">Click the **Standard Endpoint** node.</span></span> <span data-ttu-id="d2b8e-217">В области **задач** щелкните **удалить стандартную конфигурацию конечной точки**.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-217">In the **Task** pane, click **Delete Standard Endpoint Configuration**.</span></span>

<span data-ttu-id="d2b8e-218">Если используется стандартная конечная точка, при попытке ее удаления выводится предупреждающее сообщение: **используется стандартная конечная точка. Если удалить его сейчас, обязательно удалите все ссылки в других частях конфигурации (например, в конечной точке службы или конечной точке клиента). В противном случае конфигурация будет недопустима, и ее нельзя будет открыть в следующий раз. Вы действительно хотите удалить стандартную конечную точку? "**</span><span class="sxs-lookup"><span data-stu-id="d2b8e-218">If the standard endpoint is in used, a warning message is displayed when you attempt to delete it: **The standard endpoint is in use. If you delete it now, please be sure to delete all of its references in other parts of the configuration (for example, in the service endpoint or client endpoint). Otherwise, the configuration will be invalid and cannot be opened next time. Are you sure you want to delete the standard endpoint?"**</span></span>

### <a name="binding"></a><span data-ttu-id="d2b8e-219">Привязка</span><span class="sxs-lookup"><span data-stu-id="d2b8e-219">Binding</span></span>

<span data-ttu-id="d2b8e-220">Конфигурации привязок используются для настройки привязок на конечных точках.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-220">Binding configurations are used to configure bindings on endpoints.</span></span> <span data-ttu-id="d2b8e-221">Такие параметры конфигурации хранятся в узле **привязки** .</span><span class="sxs-lookup"><span data-stu-id="d2b8e-221">Such configuration settings are stored in the **Binding** node.</span></span> <span data-ttu-id="d2b8e-222">Конечные точки обращаются к конфигурации привязки по имени, причем к одной конфигурации привязки может обращаться несколько конечных точек.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-222">Endpoints reference binding configurations by name and multiple endpoints can reference a single binding configuration.</span></span>

<span data-ttu-id="d2b8e-223">Узел **привязки** отображает все параметры привязки в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-223">The **Bindings** node displays all of the binding settings in the configuration file.</span></span> <span data-ttu-id="d2b8e-224">Каждый вложенный узел в дереве соответствует вложенному элементу в `bindings` элементе <> в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-224">Every sub-node in the tree corresponds to a sub-element in the <`bindings`> element in the configuration file.</span></span>

<span data-ttu-id="d2b8e-225">Щелкнув узел **привязки** , можно просмотреть или выполнить задачи на **странице Сводка** по привязке в **области сведений**.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-225">When you click the **Bindings** node, you can view or perform tasks on the binding **Summary Page** in the **Detail Pane**.</span></span>

#### <a name="creating-a-new-binding-configuration"></a><span data-ttu-id="d2b8e-226">Создание конфигурации привязки</span><span class="sxs-lookup"><span data-stu-id="d2b8e-226">Creating a New Binding Configuration</span></span>

<span data-ttu-id="d2b8e-227">Новую конфигурацию привязки можно создать одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-227">You can create a new binding configuration in the following ways.</span></span>

- <span data-ttu-id="d2b8e-228">Щелкните правой кнопкой мыши узел **привязки** и выберите пункт **создать конфигурацию привязки**...</span><span class="sxs-lookup"><span data-stu-id="d2b8e-228">Right-click the **Bindings** node and select **New Binding Configuration**…</span></span> <span data-ttu-id="d2b8e-229">Выберите тип привязки в диалоговом окне и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-229">Select the binding type in the dialog box and click **OK**.</span></span>

- <span data-ttu-id="d2b8e-230">Выберите узел **привязки** и щелкните **создать конфигурацию привязки**...</span><span class="sxs-lookup"><span data-stu-id="d2b8e-230">Select the **Bindings** node and click **New Binding Configuration**…</span></span> <span data-ttu-id="d2b8e-231">в **области задач** в левом нижнем углу окна.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-231">in the **Task Pane** on the lower-left of the window.</span></span>

- <span data-ttu-id="d2b8e-232">На странице Сводка службы или клиента щелкните **щелкните, чтобы создать** в поле **Конфигурация привязки** , чтобы создать конфигурацию привязки для соответствующей конечной точки.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-232">In the service or client summary page, click **Click to Create** in the **Binding Configuration** field to create a binding configuration for the corresponding endpoint.</span></span>

#### <a name="adding-binding-element-extensions-to-a-custom-binding"></a><span data-ttu-id="d2b8e-233">Добавление расширений элементов привязки в пользовательскую привязку</span><span class="sxs-lookup"><span data-stu-id="d2b8e-233">Adding Binding Element Extensions to a Custom Binding</span></span>

1. <span data-ttu-id="d2b8e-234">Выберите привязку, в которую требуется добавить элемент расширения.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-234">Select the binding you want to add an extension element to.</span></span>

2. <span data-ttu-id="d2b8e-235">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-235">Click **Add**.</span></span>

3. <span data-ttu-id="d2b8e-236">В списке доступных расширений выберите расширение элемента привязки, которое требуется добавить.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-236">From the list of available extensions, select the binding element extension you want to add.</span></span> <span data-ttu-id="d2b8e-237">Чтобы выбрать несколько элементов, удерживайте нажатой клавишу CTRL.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-237">To select multiple items, press the CTRL key simultaneously.</span></span>

4. <span data-ttu-id="d2b8e-238">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-238">Click **Add**.</span></span>

#### <a name="adjusting-the-extension-position-in-a-custom-binding"></a><span data-ttu-id="d2b8e-239">Настройка положения расширения в пользовательской привязке</span><span class="sxs-lookup"><span data-stu-id="d2b8e-239">Adjusting the Extension Position in a Custom Binding</span></span>

<span data-ttu-id="d2b8e-240">Пользовательская привязка - это коллекция элементов привязки, образующих стек.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-240">A custom binding is a collection of binding elements that form a stack.</span></span> <span data-ttu-id="d2b8e-241">Каждый элемент привязки в стеке имеет собственные параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-241">Each binding element on the stack has its own configuration settings.</span></span> <span data-ttu-id="d2b8e-242">Порядок расширений элементов привязки в пользовательской привязке определяет их положение в стеке.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-242">The order of the binding element extensions in a custom binding indicates their positions in the stack.</span></span> <span data-ttu-id="d2b8e-243">Верхние элементы стека применяются в первую очередь.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-243">Elements at the top of the stack are applied first.</span></span> <span data-ttu-id="d2b8e-244">Чтобы изменить порядок, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-244">To change the ordering:</span></span>

1. <span data-ttu-id="d2b8e-245">Выберите узел пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-245">Select the custom binding node.</span></span>

2. <span data-ttu-id="d2b8e-246">Выберите один элемент расширения привязки в разделе " **Расположение расширения элемента привязки** ".</span><span class="sxs-lookup"><span data-stu-id="d2b8e-246">Select one binding extension element in the **Binding Element Extension Position** section.</span></span>

3. <span data-ttu-id="d2b8e-247">Используйте кнопку **вверх** или **вниз** в левой части списка, чтобы изменить расположение выбранного элемента.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-247">Use the **Up** or **Down** button on the left side of the list to change the position of the selected element.</span></span>

#### <a name="editing-the-configuration-of-binding-element-extensions-in-a-custom-binding"></a><span data-ttu-id="d2b8e-248">Изменение конфигурации расширений элементов привязки в пользовательской привязке</span><span class="sxs-lookup"><span data-stu-id="d2b8e-248">Editing the Configuration of Binding Element Extensions in a Custom Binding</span></span>

1. <span data-ttu-id="d2b8e-249">Выберите узел привязки в дереве.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-249">Select the binding node in the tree.</span></span>

2. <span data-ttu-id="d2b8e-250">Выберите пользовательскую привязку, содержащую элемент, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-250">Select the custom binding that contains the element you want to edit.</span></span>

3. <span data-ttu-id="d2b8e-251">Выберите расширение элемента привязки, которое необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-251">Select the binding element extension you want to edit.</span></span> <span data-ttu-id="d2b8e-252">Параметры элемента отображаются в области справа, где их можно изменить.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-252">The settings of the element appear in the right pane, where they can be edited.</span></span>

### <a name="diagnostics"></a><span data-ttu-id="d2b8e-253">Диагностика</span><span class="sxs-lookup"><span data-stu-id="d2b8e-253">Diagnostics</span></span>

<span data-ttu-id="d2b8e-254">Узел **Диагностика** отображает все параметры диагностики в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-254">The **Diagnostics** node displays all of the diagnostic settings in the configuration file.</span></span> <span data-ttu-id="d2b8e-255">Он позволяет включать или отключать счетчики производительности, включать или отключать инструментарий управления Windows (WMI) (WMI), настраивать трассировку WCF и настраивать ведение журнала сообщений WCF.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-255">It enables you to turn performance counters on or off, enable or disable Windows Management Instrumentation (WMI), configure WCF tracing, and configure WCF message logging.</span></span> <span data-ttu-id="d2b8e-256">Параметры в узле **Диагностика** соответствуют `system.diagnostics` разделу> <и `<diagnostics>` разделу в `<system.serviceModel>` файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-256">The settings in the **Diagnostics** node correspond to the <`system.diagnostics`> section, and `<diagnostics>` section in `<system.serviceModel>` in the configuration file.</span></span>

<span data-ttu-id="d2b8e-257">Щелкнув узел **Диагностика** , можно просмотреть или выполнить задачи на **странице Сводка** по диагностике в **области сведений**.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-257">When you click the **Diagnostics** node, you can view or perform tasks on the diagnostics **Summary Page** in the **Detail Pane**.</span></span>

#### <a name="configuring-performance-counters-and-wmi"></a><span data-ttu-id="d2b8e-258">Настройка счетчиков производительности и инструментария WMI</span><span class="sxs-lookup"><span data-stu-id="d2b8e-258">Configuring performance counters and WMI</span></span>

1. <span data-ttu-id="d2b8e-259">Щелкните узел **Диагностика** .</span><span class="sxs-lookup"><span data-stu-id="d2b8e-259">Click the **Diagnostics** node.</span></span>

2. <span data-ttu-id="d2b8e-260">Щелкните **Переключить счетчики производительности**.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-260">Click **Toggle Performance Counters**.</span></span> <span data-ttu-id="d2b8e-261">Счетчик производительности может находиться в трех состояниях: Off (по умолчанию), ServiceOnly и All.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-261">The performance counter has three states: Off (default), ServiceOnly, and All.</span></span> <span data-ttu-id="d2b8e-262">Для переключения между этими тремя состояниями следует щелкнуть ссылку соответствующее число раз.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-262">Clicking the link toggles the setting among these three states.</span></span>

#### <a name="configuring-wmi-provider"></a><span data-ttu-id="d2b8e-263">Настройка поставщика WMI</span><span class="sxs-lookup"><span data-stu-id="d2b8e-263">Configuring WMI Provider</span></span>

1. <span data-ttu-id="d2b8e-264">Щелкните узел **Диагностика** .</span><span class="sxs-lookup"><span data-stu-id="d2b8e-264">Click the **Diagnostics** node.</span></span>

2. <span data-ttu-id="d2b8e-265">Чтобы включить поставщик WMI, щелкните ссылку **включить поставщик WMI** .</span><span class="sxs-lookup"><span data-stu-id="d2b8e-265">To enable WMI provider, click the **Enable WMI Provider** link.</span></span>

#### <a name="enabling-wcf-tracing"></a><span data-ttu-id="d2b8e-266">Включение трассировки WCF</span><span class="sxs-lookup"><span data-stu-id="d2b8e-266">Enabling WCF Tracing</span></span>

<span data-ttu-id="d2b8e-267">Можно создать файл трассировки WCF со стандартными параметрами или пользовательский файл трассировки.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-267">You can create a WCF trace file with standard properties or set up a custom trace file.</span></span>

1. <span data-ttu-id="d2b8e-268">Щелкните узел **Диагностика** .</span><span class="sxs-lookup"><span data-stu-id="d2b8e-268">Click the **Diagnostics** node.</span></span>

2. <span data-ttu-id="d2b8e-269">Щелкните **включить трассировку**.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-269">Click **Enable Tracing**.</span></span>

3. <span data-ttu-id="d2b8e-270">Щелкните ссылку **уровень трассировки** , чтобы настроить уровень трассировки.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-270">Click the **Trace Level** link to adjust the trace level.</span></span> <span data-ttu-id="d2b8e-271">Существует шесть уровней трассировки: Off, Critical, Error, Warning, Information и Verbose.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-271">There are six trace levels: Off, Critical, Error, Warning, Information, and Verbose.</span></span> <span data-ttu-id="d2b8e-272">Параметр действия **Трассировка** и **распространение** действия позволяет использовать функцию трассировки действий WCF.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-272">The **Activity Tracing** and **Propagate Activity** option enable you to use the WCF activity tracing feature.</span></span>

4. <span data-ttu-id="d2b8e-273">Выберите имя прослушивателя трассировки, чтобы задать файл трассировки и параметры.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-273">Click the trace listener name to specify the trace file and options.</span></span>

#### <a name="enabling-wcf-logging"></a><span data-ttu-id="d2b8e-274">Включение ведения журнала WCF</span><span class="sxs-lookup"><span data-stu-id="d2b8e-274">Enabling WCF Logging</span></span>

<span data-ttu-id="d2b8e-275">Можно создать файл трассировки WCF со стандартными параметрами или пользовательский файл трассировки.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-275">You can create a WCF trace file with standard properties or set up a custom trace file.</span></span>

1. <span data-ttu-id="d2b8e-276">Щелкните узел **Диагностика** .</span><span class="sxs-lookup"><span data-stu-id="d2b8e-276">Click the **Diagnostics** node.</span></span>

2. <span data-ttu-id="d2b8e-277">Щелкните **включить ведение журнала сообщений**.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-277">Click **Enable Message Logging**.</span></span>

3. <span data-ttu-id="d2b8e-278">Щелкните ссылку **уровень ведения журнала** , чтобы настроить уровень ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-278">Click the **Log Level** link to adjust the log level.</span></span> <span data-ttu-id="d2b8e-279">Существует три уровня ведения журнала: Повреждения, Службы и Транспорт.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-279">There are three log levels: Malformed, Service, and Transport.</span></span>

4. <span data-ttu-id="d2b8e-280">Выберите имя прослушивателя, чтобы задать файл журнала и параметры.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-280">Click the listener name to specify the log file and options.</span></span>

> [!NOTE]
> <span data-ttu-id="d2b8e-281">Если требуется, чтобы журналы трассировки и сообщений автоматически удалялись при закрытии приложения, включите параметр **автоматической очистки** .</span><span class="sxs-lookup"><span data-stu-id="d2b8e-281">If you want the trace and message logs to be flushed automatically when your application is closed, enable the **Auto Flush** option.</span></span>

<span data-ttu-id="d2b8e-282">**Страница "Сводка** **диагностики** " позволяет выполнять наиболее распространенные задачи в настройке диагностики.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-282">The **Diagnostics** **Summary Page** enables you to accomplish the most common tasks in configuring diagnostics.</span></span> <span data-ttu-id="d2b8e-283">Однако если вы хотите вручную изменить параметры прослушивателей и источников, необходимо развернуть узел **Диагностика** и изменить параметры в узле **ведение журнала сообщений**, **прослушиватели** и **источники** .</span><span class="sxs-lookup"><span data-stu-id="d2b8e-283">However, if you want to manually edit the Listeners and Sources settings, you must expand the **Diagnostics** node and edit settings in **Message Logging**, **Listeners** and **Sources** node.</span></span>

#### <a name="enabling-wcf-custom-tracing-or-message-logging"></a><span data-ttu-id="d2b8e-284">Включение пользовательской трассировки или ведения журналов сообщений WCF</span><span class="sxs-lookup"><span data-stu-id="d2b8e-284">Enabling WCF Custom Tracing or Message Logging</span></span>

1. <span data-ttu-id="d2b8e-285">Щелкните узел **Диагностика** и разверните его.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-285">Click the **Diagnostics** node, and expand it.</span></span>

2. <span data-ttu-id="d2b8e-286">Щелкните правой кнопкой мыши узел **прослушиватели** и выберите команду **создать прослушиватель**.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-286">Right-click the **Listeners** node and select **New Listener**.</span></span>

3. <span data-ttu-id="d2b8e-287">Введите имя файла трассировки в поле **InitData** .</span><span class="sxs-lookup"><span data-stu-id="d2b8e-287">Type in the trace file name in the **InitData** field.</span></span> <span data-ttu-id="d2b8e-288">Можно нажать кнопку "..." (обзор), чтобы перейти к пути.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-288">You can click the "…" button to browse to a path.</span></span>

4. <span data-ttu-id="d2b8e-289">При щелчке строки **TypeName** отображается "..." переключатель.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-289">Clicking the **TypeName** line displays a "…" button.</span></span> <span data-ttu-id="d2b8e-290">Нажмите эту кнопку, чтобы открыть **браузер типа прослушивателя трассировки**, который можно использовать для поиска уже установленных ранее прослушивателей трассировки.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-290">Click this button to open the **Trace Listener Type Browser**, which you can use to find pre-configured trace listeners that are already installed.</span></span>

5. <span data-ttu-id="d2b8e-291">Обратите внимание на раздел **Source** .</span><span class="sxs-lookup"><span data-stu-id="d2b8e-291">Note the **Source** section.</span></span> <span data-ttu-id="d2b8e-292">Нажмите кнопку **Добавить** в этом разделе, чтобы открыть диалоговое окно с раскрывающимися меню, в котором перечислены доступные источники трассировки.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-292">Click **Add** in this section to open a dialog box with a drop-down menu, which lists available tracing sources.</span></span> <span data-ttu-id="d2b8e-293">Выберите источник трассировки и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-293">Select a tracing source and click **OK**.</span></span>

6. <span data-ttu-id="d2b8e-294">Чтобы изменить параметры ведения журнала сообщений, щелкните узел **ведение журнала сообщений** .</span><span class="sxs-lookup"><span data-stu-id="d2b8e-294">To edit Message Logging settings, click the **Message Logging** node.</span></span> <span data-ttu-id="d2b8e-295">Параметры можно изменять в сетке свойств.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-295">You can edit the settings in the property grid.</span></span>

### <a name="advanced"></a><span data-ttu-id="d2b8e-296">Продвинутый уровень</span><span class="sxs-lookup"><span data-stu-id="d2b8e-296">Advanced</span></span>

#### <a name="behaviors"></a><span data-ttu-id="d2b8e-297">поведения</span><span class="sxs-lookup"><span data-stu-id="d2b8e-297">Behaviors</span></span>

<span data-ttu-id="d2b8e-298">Узел **поведения** отображает поведение, которое в настоящее время определено в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-298">The **Behaviors** node displays the behaviors that are currently defined in the configuration file.</span></span>

<span data-ttu-id="d2b8e-299">Конфигурации поведения используются для настройки поведений конечных точек и служб.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-299">Behavior configurations are used to configure behaviors of endpoints and services.</span></span> <span data-ttu-id="d2b8e-300">Такие параметры конфигурации хранятся в узле **Дополнительно** в разделе **поведения службы** и **поведения конечной точки**.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-300">Such configuration settings are stored in the **Advanced** node under **Service Behaviors** and **Endpoint Behaviors**.</span></span> <span data-ttu-id="d2b8e-301">Поведения служб используются службами, а поведения конечных точек - конечными точками.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-301">Service behaviors are used by services; whereas endpoint behaviors by endpoints.</span></span>

<span data-ttu-id="d2b8e-302">Поведения - это коллекции элементов расширения, образующих стек.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-302">Behaviors are a collection of extension elements that for a stack.</span></span> <span data-ttu-id="d2b8e-303">Верхний элемент стека применяется в первую очередь.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-303">The element at the top of the stack is applied first.</span></span> <span data-ttu-id="d2b8e-304">Каждый элемент расширения может иметь собственную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-304">Each extension element can have its own configuration.</span></span>

##### <a name="creating-a-new-behavior-configuration"></a><span data-ttu-id="d2b8e-305">Создание новой конфигурации поведения</span><span class="sxs-lookup"><span data-stu-id="d2b8e-305">Creating a new Behavior Configuration</span></span>

<span data-ttu-id="d2b8e-306">Новую конфигурацию поведения можно создать одним из двух способов.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-306">You can create a new behavior configuration in two ways.</span></span>

- <span data-ttu-id="d2b8e-307">Щелкните правой кнопкой мыши один из узлов поведения и выберите пункт "**создать конфигурацию поведения...".**</span><span class="sxs-lookup"><span data-stu-id="d2b8e-307">Right-click one of the behavior nodes and select "**New Behavior Configuration…**</span></span>

- <span data-ttu-id="d2b8e-308">Выберите один из узлов поведения и щелкните **новую конфигурацию поведения**...</span><span class="sxs-lookup"><span data-stu-id="d2b8e-308">Select one of the behavior nodes and click the **New Behavior Configuration**…</span></span> <span data-ttu-id="d2b8e-309">в **области задач** в левом нижнем углу окна.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-309">in the **Task Pane** on the lower-left of the window.</span></span>

##### <a name="adding-behavior-element-extensions-to-a-behavior"></a><span data-ttu-id="d2b8e-310">Добавление расширений элементов поведения в поведение</span><span class="sxs-lookup"><span data-stu-id="d2b8e-310">Adding Behavior Element Extensions to a Behavior</span></span>

1. <span data-ttu-id="d2b8e-311">Выберите один из узлов поведения.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-311">Select one of the behavior nodes.</span></span>

2. <span data-ttu-id="d2b8e-312">Выберите поведение, которое требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-312">Select the behavior you want edit.</span></span>

3. <span data-ttu-id="d2b8e-313">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-313">Click **Add**.</span></span>

4. <span data-ttu-id="d2b8e-314">В списке доступных расширений выберите расширение элемента поведения, которое требуется добавить.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-314">From the list of available extensions, select the behavior element extension you want to add.</span></span>

5. <span data-ttu-id="d2b8e-315">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-315">Click **Add**.</span></span>

##### <a name="adjusting-the-extension-position-in-a-behavior"></a><span data-ttu-id="d2b8e-316">Настройка положения расширения в поведении</span><span class="sxs-lookup"><span data-stu-id="d2b8e-316">Adjusting the Extension Position in a Behavior</span></span>

<span data-ttu-id="d2b8e-317">Поведения — это коллекции элементов, образующих стек.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-317">Behaviors are collections of elements that form a stack.</span></span> <span data-ttu-id="d2b8e-318">Каждый элемент в стеке имеет собственную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-318">Each element on the stack has its own configuration.</span></span> <span data-ttu-id="d2b8e-319">Порядок расширений элементов поведения в поведении определяет их положение в стеке.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-319">The order of the behavior element extensions in a behavior indicates their positions in the stack.</span></span> <span data-ttu-id="d2b8e-320">Верхние элементы стека применяются в первую очередь.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-320">Elements at the top of the stack are applied first.</span></span> <span data-ttu-id="d2b8e-321">Чтобы изменить порядок, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-321">To change the ordering:</span></span>

1. <span data-ttu-id="d2b8e-322">Выберите один из узлов поведения.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-322">Select one of the behavior nodes.</span></span>

2. <span data-ttu-id="d2b8e-323">Выберите поведение, которое требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-323">Select the behavior you want edit.</span></span>

3. <span data-ttu-id="d2b8e-324">Выберите элемент расширения поведения в разделе " **Расположение расширения элемента поведения** ".</span><span class="sxs-lookup"><span data-stu-id="d2b8e-324">Select a behavior extension element in the **Behavior Element Extension Position** section.</span></span>

4. <span data-ttu-id="d2b8e-325">Используйте кнопку **вверх** или **вниз** в левой части списка, чтобы изменить расположение выбранного элемента.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-325">Use the **Up** or **Down** button on the left side of the list to change the position of the selected element.</span></span>

##### <a name="editing-the-configuration-of-behavior-element-extensions"></a><span data-ttu-id="d2b8e-326">Изменение конфигурации расширений элементов поведения</span><span class="sxs-lookup"><span data-stu-id="d2b8e-326">Editing the Configuration of Behavior Element Extensions</span></span>

1. <span data-ttu-id="d2b8e-327">Выберите один из узлов поведения в дереве.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-327">Select one of the behavior nodes in the tree.</span></span>

2. <span data-ttu-id="d2b8e-328">Выберите поведение, содержащее элемент, который необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-328">Select the behavior that contains the element you want to edit.</span></span>

3. <span data-ttu-id="d2b8e-329">Выберите расширение элемента поведения, которое необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-329">Select the behavior element extension you want to edit.</span></span> <span data-ttu-id="d2b8e-330">Параметры элемента отображаются в области справа, где их можно изменить.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-330">The settings of the element appear in the right pane where they can be edited.</span></span>

#### <a name="protocolmapping"></a><span data-ttu-id="d2b8e-331">ProtocolMapping</span><span class="sxs-lookup"><span data-stu-id="d2b8e-331">ProtocolMapping</span></span>

<span data-ttu-id="d2b8e-332">В этом разделе можно задавать типы привязки по умолчанию для различных протоколов, таких как HTTP, TCP, MSMQ или net.pipe, посредством определенного сопоставления между адресными схемами протоколов и возможными привязками.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-332">This section allows you to set default binding types for different protocols such as http, tcp, MSMQ or net.pipe through defined mapping between protocol address schemes and the possible bindings.</span></span> <span data-ttu-id="d2b8e-333">Также можно добавлять новые сопоставления для других протоколов.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-333">You can also add new mappings to other protocols.</span></span>

#### <a name="extensions"></a><span data-ttu-id="d2b8e-334">Модули</span><span class="sxs-lookup"><span data-stu-id="d2b8e-334">Extensions</span></span>

<span data-ttu-id="d2b8e-335">Новые расширения привязки, расширения элементов привязки, расширения стандартных конечных точек и расширения поведения могут быть зарегистрированы для использования в конфигурации WCF.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-335">New binding extensions, binding element extensions, standard endpoint extensions and behavior extensions can be registered for use in WCF configuration.</span></span> <span data-ttu-id="d2b8e-336">Расширения представляют собой пары "имя/тип".</span><span class="sxs-lookup"><span data-stu-id="d2b8e-336">Extensions are name/type pairs.</span></span> <span data-ttu-id="d2b8e-337">Имя определяет имя расширения в конфигурации, а тип реализует расширение.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-337">The name defines the name of the extension in configuration, whereas the type implements the extension.</span></span> <span data-ttu-id="d2b8e-338">Существует четыре типа расширений.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-338">There are four types of extensions:</span></span>

- <span data-ttu-id="d2b8e-339">Расширения привязки определяют общий тип привязки.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-339">Binding extensions define an entire binding type.</span></span> <span data-ttu-id="d2b8e-340">Например, `basicHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-340">Example: `basicHttpBinding`.</span></span>

- <span data-ttu-id="d2b8e-341">Расширения элементов привязки определяют элемент привязки.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-341">Binding element extensions define an element of a binding.</span></span> <span data-ttu-id="d2b8e-342">Например, `textMessageEncoding`.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-342">Example: `textMessageEncoding`.</span></span>

- <span data-ttu-id="d2b8e-343">Расширения стандартных конечных точек определяют целую стандартную конечную точку.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-343">Standard endpoint extensions define an entire standard endpoint.</span></span> <span data-ttu-id="d2b8e-344">Например, `discoveryEndpoint`.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-344">Example: `discoveryEndpoint`.</span></span>

- <span data-ttu-id="d2b8e-345">Расширения элементов поведения определяют элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-345">Behavior element extensions define an element of a behavior.</span></span> <span data-ttu-id="d2b8e-346">Например, `clientVia`.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-346">Example: `clientVia`.</span></span>

 <span data-ttu-id="d2b8e-347">Расширения, зарегистрированные в конфигурации, могут быть использованы как любой другой компонент WCF такого же типа.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-347">Extensions that have been registered in configuration can be used like any other WCF component of the same type.</span></span>

##### <a name="adding-a-new-extension"></a><span data-ttu-id="d2b8e-348">Добавление нового расширения</span><span class="sxs-lookup"><span data-stu-id="d2b8e-348">Adding a new extension</span></span>

<span data-ttu-id="d2b8e-349">Выберите один из узлов расширения среди дополнительных узлов.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-349">Select one of the extension nodes in the advanced nodes:</span></span>

1. <span data-ttu-id="d2b8e-350">Нажмите кнопку **New** (Создать).</span><span class="sxs-lookup"><span data-stu-id="d2b8e-350">Click **New**.</span></span>

2. <span data-ttu-id="d2b8e-351">Введите имя и тип.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-351">Enter a name and type.</span></span>

3. <span data-ttu-id="d2b8e-352">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-352">Click **OK**.</span></span>

4. <span data-ttu-id="d2b8e-353">Теперь расширение отображается в соответствующем месте редактора.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-353">The extension now appears in the appropriate place in the Editor.</span></span> <span data-ttu-id="d2b8e-354">Например, если добавить расширение элемента поведения, оно появится в списке доступных расширений.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-354">For example, if you add a behavior element extension, it appears in the list of available extensions.</span></span>

#### <a name="hosting-environment"></a><span data-ttu-id="d2b8e-355">Среда размещения</span><span class="sxs-lookup"><span data-stu-id="d2b8e-355">Hosting Environment</span></span>

<span data-ttu-id="d2b8e-356">В этом разделе можно определять параметры создания экземпляров для среды, где размещается служба.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-356">This section allows you to define instantiation settings for the service hosting environment.</span></span>

### <a name="creating-a-configuration-file-using-the-wizard"></a><span data-ttu-id="d2b8e-357">Создание файла конфигурации с помощью мастера</span><span class="sxs-lookup"><span data-stu-id="d2b8e-357">Creating a Configuration File Using the Wizard</span></span>

<span data-ttu-id="d2b8e-358">Один из способов создания нового файла конфигурации — использование мастера создания элементов службы.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-358">One way to create a new configuration file is to use the New Service Element Wizard.</span></span> <span data-ttu-id="d2b8e-359">Мастер находит установленные типы служб и другие элементы, совместимые с WCF, на компьютере, включая COM+ и виртуальные каталоги, размещенные в Интернете, и загружает их для значительного упрощения создания конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-359">The wizard finds the installed service types and other elements compatible with WCF on the computer, including COM+ and Web-hosted virtual directories, and loads them to make creating the configuration much more streamlined.</span></span>

#### <a name="creating-a-configuration-file"></a><span data-ttu-id="d2b8e-360">Создание файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="d2b8e-360">Creating a Configuration File</span></span>

1. <span data-ttu-id="d2b8e-361">Запустите редактор конфигурации служб, используя командное окно, чтобы перейти к расположению установки WCF, а затем введите `SvcConfigEditor.exe` .</span><span class="sxs-lookup"><span data-stu-id="d2b8e-361">Start Service Configuration Editor by using a command window to navigate to your WCF installation location, and then type `SvcConfigEditor.exe`.</span></span>

2. <span data-ttu-id="d2b8e-362">В меню **файл** выберите **Открыть** и щелкните **исполняемый**файл, **Служба COM+** или **Служба WebHost**, в зависимости от типа файла конфигурации, который требуется создать.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-362">From the **File** menu, select **Open** and click **Executable**, **COM+ Service**, or **WebHosted Service**, depending on the type of configuration file you want to create.</span></span>

3. <span data-ttu-id="d2b8e-363">В диалоговом окне **Открыть** перейдите к конкретному файлу, для которого нужно создать файл конфигурации, и дважды щелкните его.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-363">In the **Open** dialog box, navigate to the specific file you want to create a configuration file for and double-click it.</span></span>

4. <span data-ttu-id="d2b8e-364">В меню **файл** наведите указатель мыши на пункт **Добавить новый элемент** и выберите пункт **Служба**.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-364">In the **File** menu, point to **Add New Item** and click **Service**.</span></span> <span data-ttu-id="d2b8e-365">Откроется мастер создания элементов службы.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-365">The New Service Element Wizard opens.</span></span>

5. <span data-ttu-id="d2b8e-366">Для создания новой службы следуйте инструкциям мастера.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-366">Follow the steps in the wizard to create the new service.</span></span>

> [!NOTE]
> <span data-ttu-id="d2b8e-367">Чтобы использовать привязку NetPeerTcpBinding из файла конфигурации, созданного мастером, необходимо вручную добавить элемент конфигурации привязки и изменить значение атрибута `mode` элемента `security` на «Нет».</span><span class="sxs-lookup"><span data-stu-id="d2b8e-367">If you want to use the NetPeerTcpBinding from the configuration file generated by the Wizard, you have to manually add a binding configuration element and modify the `mode` attribute of its `security` element to "None".</span></span>

## <a name="configuring-com"></a><span data-ttu-id="d2b8e-368">Настройка COM+</span><span class="sxs-lookup"><span data-stu-id="d2b8e-368">Configuring COM+</span></span>

<span data-ttu-id="d2b8e-369">Редактор конфигураций служб позволяет создавать новые файлы конфигурации для существующих приложений COM+, а также изменять имеющиеся конфигурации COM+.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-369">The Service Configuration Editor enables you to create a new configuration file for an existing COM+ application, or edit an existing COM+ configuration.</span></span> <span data-ttu-id="d2b8e-370">Узел **контракта com** отображается только в том случае, если `comContract` раздел <> существует в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-370">The **COM Contract** node is only visible when the <`comContract`> section exists in the configuration file.</span></span>

### <a name="creating-a-new-com-configuration"></a><span data-ttu-id="d2b8e-371">Создание новой конфигурации COM+</span><span class="sxs-lookup"><span data-stu-id="d2b8e-371">Creating a New COM+ Configuration</span></span>

<span data-ttu-id="d2b8e-372">Перед созданием конфигурации COM+ следует убедиться, что приложение COM+ установлено в службах компонентов и зарегистрировано в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-372">Before creating a new COM+ configuration, make sure that your COM+ application is installed in Component Services, and registered in the Global Assembly Cache (GAC).</span></span>

1. <span data-ttu-id="d2b8e-373">Выберите меню **файл** — > **интегрировать**  ->  **приложение COM+.**</span><span class="sxs-lookup"><span data-stu-id="d2b8e-373">Select **File** menu -> **Integrate** -> **COM+ Application.**</span></span> <span data-ttu-id="d2b8e-374">В результате этого действия открытый в данный момент файл закрывается.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-374">This operation closes the current opened file.</span></span> <span data-ttu-id="d2b8e-375">Если в текущем файле есть несохраненные данные, то появится диалоговое окно сохранения.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-375">If there is unsaved data in the current file, a Save dialog appears.</span></span> <span data-ttu-id="d2b8e-376">Затем запускается **Мастер интеграции COM+** .</span><span class="sxs-lookup"><span data-stu-id="d2b8e-376">The **COM+ Integration Wizard** is then launched.</span></span>

2. <span data-ttu-id="d2b8e-377">В дереве на первой странице выберите приложение COM+.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-377">In the first page, select the COM+ application from the tree.</span></span> <span data-ttu-id="d2b8e-378">Если приложение COM+ не удается найти в дереве, проверьте, установлено ли оно в службах компонентов и зарегистрировано ли в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-378">If you cannot find your COM+ application in the tree, verify that it is installed in the Component Services and registered in the Global Assembly Cache (GAC).</span></span>

3. <span data-ttu-id="d2b8e-379">На следующей странице выберите метод(ы), которые будут отображаться как службы WCF.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-379">In the next page, select which method(s) you want to expose as WCF services.</span></span> <span data-ttu-id="d2b8e-380">Все поддерживаемые в приложении COM+ методы отображаются и выбираются по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-380">All the supported methods in the COM+ application are displayed and selected by default.</span></span>

4. <span data-ttu-id="d2b8e-381">Выберите метод размещения.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-381">Choose a hosting method.</span></span>

5. <span data-ttu-id="d2b8e-382">Настройте остальные параметры в соответствии с указаниями мастера.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-382">Configure other settings according to the guides in the wizard.</span></span>

6. <span data-ttu-id="d2b8e-383">Редактор конфигураций служб использует средство ComSvcConfig.exe, запущенное в фоновом режиме, для создания файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-383">Service Configuration Editor utilizes ComSvcConfig.exe in the background to generate configuration file.</span></span> <span data-ttu-id="d2b8e-384">После выполнения этих действий можно просмотреть отчет и выйти из мастера.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-384">After this is completed, you can view a summary and exit the wizard.</span></span> <span data-ttu-id="d2b8e-385">Созданный файл конфигурации открывается для непосредственного редактирования.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-385">The generated configuration file is opened so that you can edit it directly.</span></span>

### <a name="editing-an-existing-com-configuration"></a><span data-ttu-id="d2b8e-386">Изменение существующей конфигурации COM+</span><span class="sxs-lookup"><span data-stu-id="d2b8e-386">Editing an Existing COM+ Configuration</span></span>

1. <span data-ttu-id="d2b8e-387">Выберите меню " **файл** "-> **Открыть**  ->  **службу COM+**...</span><span class="sxs-lookup"><span data-stu-id="d2b8e-387">Select **File** menu -> **Open** -> **COM+ Service**…</span></span>

2. <span data-ttu-id="d2b8e-388">Выберите в списке службу COM+, которую требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-388">Select the COM+ Service you want to edit from the list.</span></span>

3. <span data-ttu-id="d2b8e-389">Измените параметры конфигурации в узле **контракты COM** .</span><span class="sxs-lookup"><span data-stu-id="d2b8e-389">Edit configuration settings in the **COM Contracts** node.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2b8e-390">Также можно напрямую открыть и отредактировать файл конфигурации, в котором содержатся COM-контракты.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-390">You can also directly open and edit a configuration file that contains COM contracts.</span></span>

## <a name="security"></a><span data-ttu-id="d2b8e-391">Безопасность</span><span class="sxs-lookup"><span data-stu-id="d2b8e-391">Security</span></span>

<span data-ttu-id="d2b8e-392">Редактор конфигураций, с помощью которого создаются файлы конфигурации служб, не гарантирует безопасность.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-392">A service configuration file generated by the Configuration Editor is not guaranteed to be secure.</span></span> <span data-ttu-id="d2b8e-393">Ознакомьтесь с документацией по [безопасности](./feature-details/security.md) , чтобы узнать, как защитить службы WCF.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-393">Please refer to the [Security](./feature-details/security.md) documentation to find out how to secure your WCF services.</span></span>

<span data-ttu-id="d2b8e-394">Кроме того, редактор конфигурации может использоваться только для чтения и записи допустимых элементов конфигурации WCF.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-394">In addition, the Configuration Editor can only be used to read and write valid WCF configuration elements.</span></span> <span data-ttu-id="d2b8e-395">Он пропускает пользовательские элементы, совместимые со схемой.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-395">The tool ignores schema-compliant, user-defined elements.</span></span> <span data-ttu-id="d2b8e-396">Более того, этот редактор не предпринимает попыток удаления таких элементов из файла конфигурации или определения их воздействия на известные элементы WCF.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-396">It also does not attempt remove these elements from the configuration file or determine their effects on the known WCF elements.</span></span> <span data-ttu-id="d2b8e-397">Пользователю необходимо самостоятельно определять, представляют ли эти элементы угрозу для приложения или системы.</span><span class="sxs-lookup"><span data-stu-id="d2b8e-397">It is the user’s responsibility to determine whether these elements pose a threat to the application or the system.</span></span>
