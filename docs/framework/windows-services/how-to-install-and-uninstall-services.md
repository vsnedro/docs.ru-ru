---
title: 'Как: Установка и удаление служб Windows'
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
ms.openlocfilehash: 8937ef8b4007253b06444e59b292395084e4df2f
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/17/2020
ms.locfileid: "81607923"
---
# <a name="how-to-install-and-uninstall-windows-services"></a><span data-ttu-id="b7f06-102">Как: Установка и удаление служб Windows</span><span class="sxs-lookup"><span data-stu-id="b7f06-102">How to: Install and uninstall Windows services</span></span>

<span data-ttu-id="b7f06-103">Если вы разрабатываете службу Windows с помощью системы .NET, вы можете быстро установить приложение обслуживания с помощью утилиты командной строки [*InstallUtil.exe*](../tools/installutil-exe-installer-tool.md) или [PowerShell.](/powershell/scripting/overview)</span><span class="sxs-lookup"><span data-stu-id="b7f06-103">If you’re developing a Windows service with the .NET Framework, you can quickly install your service app by using the [*InstallUtil.exe*](../tools/installutil-exe-installer-tool.md) command-line utility or [PowerShell](/powershell/scripting/overview).</span></span> <span data-ttu-id="b7f06-104">Если вы являетесь разработчиком и хотите создать службу Windows, которую пользователи могут устанавливать и удалять, необходимо использовать InstallShield.</span><span class="sxs-lookup"><span data-stu-id="b7f06-104">Developers who want to release a Windows service that users can install and uninstall should use InstallShield.</span></span> <span data-ttu-id="b7f06-105">Для получения дополнительной информации [см.](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop)</span><span class="sxs-lookup"><span data-stu-id="b7f06-105">For more information, see [Create an installer package (Windows desktop)](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).</span></span>

> [!WARNING]
> <span data-ttu-id="b7f06-106">Если вы хотите удалить службу на своем компьютере, не выполняйте процедуру, описанную в этой статье.</span><span class="sxs-lookup"><span data-stu-id="b7f06-106">If you want to uninstall a service from your computer, don’t follow the steps in this article.</span></span> <span data-ttu-id="b7f06-107">Вместо этого определите, какая программа (или программный пакет) установила эту службу, а затем выберите **Приложения** в параметрах, чтобы удалить эту программу.</span><span class="sxs-lookup"><span data-stu-id="b7f06-107">Instead, find out which program or software package installed the service, and then choose **Apps** in Settings to uninstall that program.</span></span> <span data-ttu-id="b7f06-108">Следует отметить, что многие службы являются составной частью ОС Windows. Если их удалить, это может привести к нестабильной работе системы.</span><span class="sxs-lookup"><span data-stu-id="b7f06-108">Note that many services are integral parts of Windows; if you remove them, you might cause system instability.</span></span>

<span data-ttu-id="b7f06-109">Чтобы использовать процедуру, описанную в этой статье, сначала необходимо добавить установщик службы в свою службу Windows.</span><span class="sxs-lookup"><span data-stu-id="b7f06-109">To use the steps in this article, you first need to add a service installer to your Windows service.</span></span> <span data-ttu-id="b7f06-110">Для получения дополнительной информации [см.](../windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)</span><span class="sxs-lookup"><span data-stu-id="b7f06-110">For more information, see [Walkthrough: Creating a Windows service app](../windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span></span>

<span data-ttu-id="b7f06-111">Проекты служб Windows нельзя запускать непосредственно из среды разработки Visual Studio путем нажатия клавиши F5.</span><span class="sxs-lookup"><span data-stu-id="b7f06-111">You can't run Windows service projects directly from the Visual Studio development environment by pressing F5.</span></span> <span data-ttu-id="b7f06-112">Перед запуском проекта необходимо установить службу в проекте.</span><span class="sxs-lookup"><span data-stu-id="b7f06-112">Before you can run the project, you must install the service in the project.</span></span>

> [!TIP]
> <span data-ttu-id="b7f06-113">Запустите **обозреватель сервера** и убедитесь, что служба установлена или удалена.</span><span class="sxs-lookup"><span data-stu-id="b7f06-113">You can use **Server Explorer** to verify that you've installed or uninstalled your service.</span></span> <span data-ttu-id="b7f06-114">Дополнительные сведения см. в разделе [Практическое руководство. Использование обозревателя сервера в Visual Studio](https://support.microsoft.com/help/316649/how-to-use-the-server-explorer-in-visual-studio-net-and-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="b7f06-114">For more information, see [How to use Server Explorer in Visual Studio](https://support.microsoft.com/help/316649/how-to-use-the-server-explorer-in-visual-studio-net-and-visual-studio).</span></span>

### <a name="install-your-service-manually-using-installutilexe-utility"></a><span data-ttu-id="b7f06-115">Установите сервис вручную с помощью утилиты InstallUtil.exe</span><span class="sxs-lookup"><span data-stu-id="b7f06-115">Install your service manually using InstallUtil.exe utility</span></span>

1. <span data-ttu-id="b7f06-116">В меню **Пуск** выберите каталог **Visual Studio \<*версия*>**, а затем выберите **Командная строка разработчика для VS \<*версия*>**.</span><span class="sxs-lookup"><span data-stu-id="b7f06-116">From the **Start** menu, select the **Visual Studio \<*version*>** directory, then select **Developer Command Prompt for VS \<*version*>**.</span></span>

     <span data-ttu-id="b7f06-117">Появится командная строка разработчика для Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b7f06-117">The Developer Command Prompt for Visual Studio appears.</span></span>

2. <span data-ttu-id="b7f06-118">Откройте каталог, где находится скомпилированный исполняемый файл вашего проекта.</span><span class="sxs-lookup"><span data-stu-id="b7f06-118">Access the directory where your project's compiled executable file is located.</span></span>

3. <span data-ttu-id="b7f06-119">Запустите *InstallUtil.exe* из командной строки, указав исполняемый файл проекта в качестве параметра:</span><span class="sxs-lookup"><span data-stu-id="b7f06-119">Run *InstallUtil.exe* from the command prompt with your project's executable as a parameter:</span></span>

    ```console
    installutil <yourproject>.exe
    ```

     <span data-ttu-id="b7f06-120">Если вы используете командную строку разработчика для Visual Studio, системный путь должен указывать на файл *InstallUtil.exe*.</span><span class="sxs-lookup"><span data-stu-id="b7f06-120">If you’re using the Developer Command Prompt for Visual Studio, *InstallUtil.exe* should be on the system path.</span></span> <span data-ttu-id="b7f06-121">Если это не так, можно добавить его в путь или использовать полный путь для его вызова.</span><span class="sxs-lookup"><span data-stu-id="b7f06-121">Otherwise, you can add it to the path, or use the fully qualified path to invoke it.</span></span> <span data-ttu-id="b7f06-122">Этот инструмент устанавливается с помощью рамочной системы .NET в *%WINDIR% -Microsoft.NET-Framework framework_version\\ \><.*</span><span class="sxs-lookup"><span data-stu-id="b7f06-122">This tool is installed with the .NET Framework in *%WINDIR%\Microsoft.NET\Framework[64]\\<framework_version\>*.</span></span>

     <span data-ttu-id="b7f06-123">Пример:</span><span class="sxs-lookup"><span data-stu-id="b7f06-123">For example:</span></span>
     - <span data-ttu-id="b7f06-124">Для 32-разрядной версии .NET Framework 4 или 4.5 и более поздних версий: если каталог установки Windows — *C:\Windows*, по умолчанию используется путь *C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.</span><span class="sxs-lookup"><span data-stu-id="b7f06-124">For the 32-bit version of the .NET Framework 4 or 4.5 and later, if your Windows installation directory is *C:\Windows*, the default path is *C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.</span></span>
     - <span data-ttu-id="b7f06-125">Для 64-разрядной версии .NET Framework 4 или 4.5 и более поздних версий: по умолчанию используется путь *C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.</span><span class="sxs-lookup"><span data-stu-id="b7f06-125">For the 64-bit version of the .NET Framework 4 or 4.5 and later, the default path is *C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.</span></span>

### <a name="uninstall-your-service-manually-using-installutilexe-utility"></a><span data-ttu-id="b7f06-126">Удалите службу вручную с помощью утилиты InstallUtil.exe</span><span class="sxs-lookup"><span data-stu-id="b7f06-126">Uninstall your service manually using InstallUtil.exe utility</span></span>

1. <span data-ttu-id="b7f06-127">В меню **Пуск** выберите каталог **Visual Studio \<*версия*>**, а затем выберите **Командная строка разработчика для VS \<*версия*>**.</span><span class="sxs-lookup"><span data-stu-id="b7f06-127">From the **Start** menu, select the **Visual Studio \<*version*>** directory, then select **Developer Command Prompt for VS \<*version*>**.</span></span>

     <span data-ttu-id="b7f06-128">Появится командная строка разработчика для Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b7f06-128">The Developer Command Prompt for Visual Studio appears.</span></span>

2. <span data-ttu-id="b7f06-129">Выполнить *InstallUtil.exe* из запроса команды с выходом проекта в качестве параметра:</span><span class="sxs-lookup"><span data-stu-id="b7f06-129">Run *InstallUtil.exe* from the command prompt with your project's output as a parameter:</span></span>

    ```console
    installutil /u <yourproject>.exe
    ```

3. <span data-ttu-id="b7f06-130">После удаления исполняемого файла для службы сама служба может по-прежнему присутствовать в реестре.</span><span class="sxs-lookup"><span data-stu-id="b7f06-130">After the executable for a service is deleted, the service might still be present in the registry.</span></span> <span data-ttu-id="b7f06-131">В этом случае удалить запись службы из реестра можно с помощью команды [sc delete](/windows-server/administration/windows-commands/sc-delete).</span><span class="sxs-lookup"><span data-stu-id="b7f06-131">If that's the case, use the command [sc delete](/windows-server/administration/windows-commands/sc-delete) to remove the entry for the service from the registry.</span></span>

### <a name="install-your-service-manually-using-powershell"></a><span data-ttu-id="b7f06-132">Установите службу вручную с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7f06-132">Install your service manually using PowerShell</span></span>

1. <span data-ttu-id="b7f06-133">Из меню **«Пуск»** выберите каталог **Windows PowerShell,** а затем выберите **Windows PowerShell.**</span><span class="sxs-lookup"><span data-stu-id="b7f06-133">From the **Start** menu, select the **Windows PowerShell** directory, then select **Windows PowerShell**.</span></span>

2. <span data-ttu-id="b7f06-134">Откройте каталог, где находится скомпилированный исполняемый файл вашего проекта.</span><span class="sxs-lookup"><span data-stu-id="b7f06-134">Access the directory where your project's compiled executable file is located.</span></span>

3. <span data-ttu-id="b7f06-135">Запустите cmdlet [**New-Service**](/powershell/module/microsoft.powershell.management/new-service) с выходом проекта и названием службы в качестве параметров:</span><span class="sxs-lookup"><span data-stu-id="b7f06-135">Run the [**New-Service**](/powershell/module/microsoft.powershell.management/new-service) cmdlet with the with your project's output and a service name as parameters:</span></span>

    ```powershell
    New-Service -Name "YourServiceName" -BinaryPathName <yourproject>.exe
    ```

### <a name="uninstall-your-service-manually-using-powershell"></a><span data-ttu-id="b7f06-136">Удалите службу вручную с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7f06-136">Uninstall your service manually using PowerShell</span></span>

1. <span data-ttu-id="b7f06-137">Из меню **«Пуск»** выберите каталог **Windows PowerShell,** а затем выберите **Windows PowerShell.**</span><span class="sxs-lookup"><span data-stu-id="b7f06-137">From the **Start** menu, select the **Windows PowerShell** directory, then select **Windows PowerShell**.</span></span>

2. <span data-ttu-id="b7f06-138">Выполнить cmdlet [**Remove-Service**](/powershell/module/microsoft.powershell.management/remove-service) с названием службы в качестве параметра:</span><span class="sxs-lookup"><span data-stu-id="b7f06-138">Run the [**Remove-Service**](/powershell/module/microsoft.powershell.management/remove-service) cmdlet with the name of your service as parameter:</span></span>

    ```powershell
    Remove-Service -Name "YourServiceName"
    ```

3. <span data-ttu-id="b7f06-139">После удаления исполняемого файла для службы сама служба может по-прежнему присутствовать в реестре.</span><span class="sxs-lookup"><span data-stu-id="b7f06-139">After the executable for a service is deleted, the service might still be present in the registry.</span></span> <span data-ttu-id="b7f06-140">В этом случае удалить запись службы из реестра можно с помощью команды [sc delete](/windows-server/administration/windows-commands/sc-delete).</span><span class="sxs-lookup"><span data-stu-id="b7f06-140">If that's the case, use the command [sc delete](/windows-server/administration/windows-commands/sc-delete) to remove the entry for the service from the registry.</span></span>

    ```powershell
    sc.exe delete "YourServiceName"
    ```

## <a name="see-also"></a><span data-ttu-id="b7f06-141">См. также</span><span class="sxs-lookup"><span data-stu-id="b7f06-141">See also</span></span>

- [<span data-ttu-id="b7f06-142">Введение в приложения службы Windows</span><span class="sxs-lookup"><span data-stu-id="b7f06-142">Introduction to Windows service applications</span></span>](../windows-services/introduction-to-windows-service-applications.md)
- [<span data-ttu-id="b7f06-143">Как: Создание служб Windows</span><span class="sxs-lookup"><span data-stu-id="b7f06-143">How to: Create Windows services</span></span>](../windows-services/how-to-create-windows-services.md)
- [<span data-ttu-id="b7f06-144">Как: Добавление инсталляторов в свое сервисное приложение</span><span class="sxs-lookup"><span data-stu-id="b7f06-144">How to: Add installers to your service application</span></span>](../windows-services/how-to-add-installers-to-your-service-application.md)
- [<span data-ttu-id="b7f06-145">Installutil.exe (установщик)</span><span class="sxs-lookup"><span data-stu-id="b7f06-145">Installutil.exe (Installer tool)</span></span>](../tools/installutil-exe-installer-tool.md)
