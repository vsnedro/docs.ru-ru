---
title: Практическое руководство. Установка и удаление служб Windows
description: Узнайте, как устанавливать и удалять службы Windows. Если вы разрабатываете службу Windows с помощью .NET, можно использовать программу InstallUtil.exe или PowerShell.
ms.date: 02/05/2019
helpviewer_keywords:
- Windows Service applications, deploying
- services, uninstalling
- services, installing
- installing Windows Services
- uninstalling applications, apps, Windows services
- installation, Windows services
- uninstalling Windows services
- installutil.exe tool
ms.assetid: c89c5169-f567-4305-9d62-db31a1de5481
author: ghogen
ms.openlocfilehash: 5597043bb1c5af05f5f3633cba6ee6e6de1c52c1
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925609"
---
# <a name="how-to-install-and-uninstall-windows-services"></a><span data-ttu-id="474be-104">Практическое руководство. Установка и удаление служб Windows</span><span class="sxs-lookup"><span data-stu-id="474be-104">How to: Install and uninstall Windows services</span></span>

<span data-ttu-id="474be-105">Если вы разрабатываете службу Windows с помощью .NET Framework, вы можете быстро установить приложение службы с помощью служебной программы командной строки [*InstallUtil.exe*](../tools/installutil-exe-installer-tool.md) или [PowerShell](/powershell/scripting/overview).</span><span class="sxs-lookup"><span data-stu-id="474be-105">If you’re developing a Windows service with the .NET Framework, you can quickly install your service app by using the [*InstallUtil.exe*](../tools/installutil-exe-installer-tool.md) command-line utility or [PowerShell](/powershell/scripting/overview).</span></span> <span data-ttu-id="474be-106">Если вы являетесь разработчиком и хотите создать службу Windows, которую пользователи могут устанавливать и удалять, необходимо использовать InstallShield.</span><span class="sxs-lookup"><span data-stu-id="474be-106">Developers who want to release a Windows service that users can install and uninstall should use InstallShield.</span></span> <span data-ttu-id="474be-107">См. сведения о [создании пакета установщика (классическое приложение Windows)](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).</span><span class="sxs-lookup"><span data-stu-id="474be-107">For more information, see [Create an installer package (Windows desktop)](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).</span></span>

> [!WARNING]
> <span data-ttu-id="474be-108">Если вы хотите удалить службу на своем компьютере, не выполняйте процедуру, описанную в этой статье.</span><span class="sxs-lookup"><span data-stu-id="474be-108">If you want to uninstall a service from your computer, don’t follow the steps in this article.</span></span> <span data-ttu-id="474be-109">Вместо этого определите, какая программа (или программный пакет) установила эту службу, а затем выберите **Приложения** в параметрах, чтобы удалить эту программу.</span><span class="sxs-lookup"><span data-stu-id="474be-109">Instead, find out which program or software package installed the service, and then choose **Apps** in Settings to uninstall that program.</span></span> <span data-ttu-id="474be-110">Следует отметить, что многие службы являются составной частью ОС Windows. Если их удалить, это может привести к нестабильной работе системы.</span><span class="sxs-lookup"><span data-stu-id="474be-110">Note that many services are integral parts of Windows; if you remove them, you might cause system instability.</span></span>

<span data-ttu-id="474be-111">Чтобы использовать процедуру, описанную в этой статье, сначала необходимо добавить установщик службы в свою службу Windows.</span><span class="sxs-lookup"><span data-stu-id="474be-111">To use the steps in this article, you first need to add a service installer to your Windows service.</span></span> <span data-ttu-id="474be-112">Дополнительные сведения см. в разделе [Пошаговое руководство: создание диспетчера служб Windows](walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span><span class="sxs-lookup"><span data-stu-id="474be-112">For more information, see [Walkthrough: Creating a Windows service app](walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span></span>

<span data-ttu-id="474be-113">Проекты служб Windows нельзя запускать непосредственно из среды разработки Visual Studio путем нажатия клавиши F5.</span><span class="sxs-lookup"><span data-stu-id="474be-113">You can't run Windows service projects directly from the Visual Studio development environment by pressing F5.</span></span> <span data-ttu-id="474be-114">Перед запуском проекта необходимо установить службу в проекте.</span><span class="sxs-lookup"><span data-stu-id="474be-114">Before you can run the project, you must install the service in the project.</span></span>

> [!TIP]
> <span data-ttu-id="474be-115">Запустите **обозреватель сервера** и убедитесь, что служба установлена или удалена.</span><span class="sxs-lookup"><span data-stu-id="474be-115">You can use **Server Explorer** to verify that you've installed or uninstalled your service.</span></span> <span data-ttu-id="474be-116">Дополнительные сведения см. в разделе [Практическое руководство. Использование обозревателя сервера в Visual Studio](https://support.microsoft.com/help/316649/how-to-use-the-server-explorer-in-visual-studio-net-and-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="474be-116">For more information, see [How to use Server Explorer in Visual Studio](https://support.microsoft.com/help/316649/how-to-use-the-server-explorer-in-visual-studio-net-and-visual-studio).</span></span>

### <a name="install-your-service-manually-using-installutilexe-utility"></a><span data-ttu-id="474be-117">Установка службы вручную с помощью служебной программы InstallUtil.exe</span><span class="sxs-lookup"><span data-stu-id="474be-117">Install your service manually using InstallUtil.exe utility</span></span>

1. <span data-ttu-id="474be-118">В меню **Пуск** выберите каталог **Visual Studio \<*version*>** и затем **Командная строка разработчика для VS \<*version*>** .</span><span class="sxs-lookup"><span data-stu-id="474be-118">From the **Start** menu, select the **Visual Studio \<*version*>** directory, then select **Developer Command Prompt for VS \<*version*>**.</span></span>

     <span data-ttu-id="474be-119">Появится командная строка разработчика для Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="474be-119">The Developer Command Prompt for Visual Studio appears.</span></span>

2. <span data-ttu-id="474be-120">Откройте каталог, где находится скомпилированный исполняемый файл вашего проекта.</span><span class="sxs-lookup"><span data-stu-id="474be-120">Access the directory where your project's compiled executable file is located.</span></span>

3. <span data-ttu-id="474be-121">Запустите *InstallUtil.exe* из командной строки, указав исполняемый файл проекта в качестве параметра:</span><span class="sxs-lookup"><span data-stu-id="474be-121">Run *InstallUtil.exe* from the command prompt with your project's executable as a parameter:</span></span>

    ```console
    installutil <yourproject>.exe
    ```

     <span data-ttu-id="474be-122">Если вы используете командную строку разработчика для Visual Studio, системный путь должен указывать на файл *InstallUtil.exe*.</span><span class="sxs-lookup"><span data-stu-id="474be-122">If you’re using the Developer Command Prompt for Visual Studio, *InstallUtil.exe* should be on the system path.</span></span> <span data-ttu-id="474be-123">Если это не так, можно добавить его в путь или использовать полный путь для его вызова.</span><span class="sxs-lookup"><span data-stu-id="474be-123">Otherwise, you can add it to the path, or use the fully qualified path to invoke it.</span></span> <span data-ttu-id="474be-124">Этот инструмент устанавливается вместе с платформой .NET Framework в папку *%WINDIR%\Microsoft.NET\Framework[64]\\<версия_платформы\>* .</span><span class="sxs-lookup"><span data-stu-id="474be-124">This tool is installed with the .NET Framework in *%WINDIR%\Microsoft.NET\Framework[64]\\<framework_version\>*.</span></span>

     <span data-ttu-id="474be-125">Пример:</span><span class="sxs-lookup"><span data-stu-id="474be-125">For example:</span></span>
     - <span data-ttu-id="474be-126">Для 32-разрядной версии .NET Framework 4 или 4.5 и более поздних версий: если каталог установки Windows — *C:\Windows*, по умолчанию используется путь *C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.</span><span class="sxs-lookup"><span data-stu-id="474be-126">For the 32-bit version of the .NET Framework 4 or 4.5 and later, if your Windows installation directory is *C:\Windows*, the default path is *C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.</span></span>
     - <span data-ttu-id="474be-127">Для 64-разрядной версии .NET Framework 4 или 4.5 и более поздних версий: по умолчанию используется путь *C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.</span><span class="sxs-lookup"><span data-stu-id="474be-127">For the 64-bit version of the .NET Framework 4 or 4.5 and later, the default path is *C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.</span></span>

### <a name="uninstall-your-service-manually-using-installutilexe-utility"></a><span data-ttu-id="474be-128">Удаление службы вручную с помощью служебной программы InstallUtil.exe</span><span class="sxs-lookup"><span data-stu-id="474be-128">Uninstall your service manually using InstallUtil.exe utility</span></span>

1. <span data-ttu-id="474be-129">В меню **Пуск** выберите каталог **Visual Studio \<*version*>** и затем **Командная строка разработчика для VS \<*version*>** .</span><span class="sxs-lookup"><span data-stu-id="474be-129">From the **Start** menu, select the **Visual Studio \<*version*>** directory, then select **Developer Command Prompt for VS \<*version*>**.</span></span>

     <span data-ttu-id="474be-130">Появится командная строка разработчика для Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="474be-130">The Developer Command Prompt for Visual Studio appears.</span></span>

2. <span data-ttu-id="474be-131">Запустите *InstallUtil.exe* из командной строки, указав выходные данные проекта в качестве параметра:</span><span class="sxs-lookup"><span data-stu-id="474be-131">Run *InstallUtil.exe* from the command prompt with your project's output as a parameter:</span></span>

    ```console
    installutil /u <yourproject>.exe
    ```

3. <span data-ttu-id="474be-132">После удаления исполняемого файла для службы сама служба может по-прежнему присутствовать в реестре.</span><span class="sxs-lookup"><span data-stu-id="474be-132">After the executable for a service is deleted, the service might still be present in the registry.</span></span> <span data-ttu-id="474be-133">В этом случае удалить запись службы из реестра можно с помощью команды [sc delete](/windows-server/administration/windows-commands/sc-delete).</span><span class="sxs-lookup"><span data-stu-id="474be-133">If that's the case, use the command [sc delete](/windows-server/administration/windows-commands/sc-delete) to remove the entry for the service from the registry.</span></span>

### <a name="install-your-service-manually-using-powershell"></a><span data-ttu-id="474be-134">Установка службы вручную с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="474be-134">Install your service manually using PowerShell</span></span>

1. <span data-ttu-id="474be-135">В меню **Пуск** выберите **Каталог Windows PowerShell** и **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="474be-135">From the **Start** menu, select the **Windows PowerShell** directory, then select **Windows PowerShell**.</span></span>

2. <span data-ttu-id="474be-136">Откройте каталог, где находится скомпилированный исполняемый файл вашего проекта.</span><span class="sxs-lookup"><span data-stu-id="474be-136">Access the directory where your project's compiled executable file is located.</span></span>

3. <span data-ttu-id="474be-137">Выполните командлет [**New-Service**](/powershell/module/microsoft.powershell.management/new-service), указав в качестве параметров выходные данные проекта и имя службы.</span><span class="sxs-lookup"><span data-stu-id="474be-137">Run the [**New-Service**](/powershell/module/microsoft.powershell.management/new-service) cmdlet with the with your project's output and a service name as parameters:</span></span>

    ```powershell
    New-Service -Name "YourServiceName" -BinaryPathName <yourproject>.exe
    ```

### <a name="uninstall-your-service-manually-using-powershell"></a><span data-ttu-id="474be-138">Удаление службы вручную с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="474be-138">Uninstall your service manually using PowerShell</span></span>

1. <span data-ttu-id="474be-139">В меню **Пуск** выберите **Каталог Windows PowerShell** и **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="474be-139">From the **Start** menu, select the **Windows PowerShell** directory, then select **Windows PowerShell**.</span></span>

2. <span data-ttu-id="474be-140">Выполните командлет [**Remove-Service**](/powershell/module/microsoft.powershell.management/remove-service), указав в качестве параметра имя службы.</span><span class="sxs-lookup"><span data-stu-id="474be-140">Run the [**Remove-Service**](/powershell/module/microsoft.powershell.management/remove-service) cmdlet with the name of your service as parameter:</span></span>

    ```powershell
    Remove-Service -Name "YourServiceName"
    ```

3. <span data-ttu-id="474be-141">После удаления исполняемого файла для службы сама служба может по-прежнему присутствовать в реестре.</span><span class="sxs-lookup"><span data-stu-id="474be-141">After the executable for a service is deleted, the service might still be present in the registry.</span></span> <span data-ttu-id="474be-142">В этом случае удалить запись службы из реестра можно с помощью команды [sc delete](/windows-server/administration/windows-commands/sc-delete).</span><span class="sxs-lookup"><span data-stu-id="474be-142">If that's the case, use the command [sc delete](/windows-server/administration/windows-commands/sc-delete) to remove the entry for the service from the registry.</span></span>

    ```powershell
    sc.exe delete "YourServiceName"
    ```

## <a name="see-also"></a><span data-ttu-id="474be-143">См. также</span><span class="sxs-lookup"><span data-stu-id="474be-143">See also</span></span>

- [<span data-ttu-id="474be-144">Знакомство с приложениями служб Windows</span><span class="sxs-lookup"><span data-stu-id="474be-144">Introduction to Windows service applications</span></span>](introduction-to-windows-service-applications.md)
- [<span data-ttu-id="474be-145">Практическое руководство. Создание служб Windows</span><span class="sxs-lookup"><span data-stu-id="474be-145">How to: Create Windows services</span></span>](how-to-create-windows-services.md)
- [<span data-ttu-id="474be-146">Практическое руководство. Добавление установщиков в приложение-службу</span><span class="sxs-lookup"><span data-stu-id="474be-146">How to: Add installers to your service application</span></span>](how-to-add-installers-to-your-service-application.md)
- [<span data-ttu-id="474be-147">Installutil.exe (установщик)</span><span class="sxs-lookup"><span data-stu-id="474be-147">Installutil.exe (Installer tool)</span></span>](../tools/installutil-exe-installer-tool.md)
