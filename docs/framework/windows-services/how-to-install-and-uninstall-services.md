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
ms.openlocfilehash: 6b7cfd8b241df4fe01c9c2a08888c88a1c749d13
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609685"
---
# <a name="how-to-install-and-uninstall-windows-services"></a>Практическое руководство. Установка и удаление служб Windows

Если вы разрабатываете службу Windows с помощью .NET Framework, вы можете быстро установить приложение службы с помощью служебной программы командной строки [*InstallUtil.exe*](../tools/installutil-exe-installer-tool.md) или [PowerShell](/powershell/scripting/overview). Если вы являетесь разработчиком и хотите создать службу Windows, которую пользователи могут устанавливать и удалять, можно использовать [набор инструментов WiX](https://wixtoolset.org/) или коммерческие средства, такие как [Advanced Installer](https://www.advancedinstaller.com/), [InstallShield](https://www.revenera.com/install/products/installshield.html) или другие. См. сведения о [создании пакета установщика (классическое приложение Windows)](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).

> [!WARNING]
> Если вы хотите удалить службу на своем компьютере, не выполняйте процедуру, описанную в этой статье. Вместо этого определите, какая программа (или программный пакет) установила эту службу, а затем выберите **Приложения** в параметрах, чтобы удалить эту программу. Следует отметить, что многие службы являются составной частью ОС Windows. Если их удалить, это может привести к нестабильной работе системы.

Чтобы использовать процедуру, описанную в этой статье, сначала необходимо добавить установщик службы в свою службу Windows. Дополнительные сведения см. в разделе [Пошаговое руководство: создание диспетчера служб Windows](walkthrough-creating-a-windows-service-application-in-the-component-designer.md).

Проекты служб Windows нельзя запускать непосредственно из среды разработки Visual Studio путем нажатия клавиши F5. Перед запуском проекта необходимо установить службу в проекте.

> [!TIP]
> Запустите **обозреватель сервера** и убедитесь, что служба установлена или удалена. Дополнительные сведения см. в разделе [Практическое руководство. Использование обозревателя сервера в Visual Studio](https://support.microsoft.com/help/316649/how-to-use-the-server-explorer-in-visual-studio-net-and-visual-studio).

### <a name="install-your-service-manually-using-installutilexe-utility"></a>Установка службы вручную с помощью служебной программы InstallUtil.exe

1. В меню **Пуск** выберите каталог **Visual Studio \<*version*>** и затем **Командная строка разработчика для VS \<*version*>** .

     Появится командная строка разработчика для Visual Studio.

2. Откройте каталог, где находится скомпилированный исполняемый файл вашего проекта.

3. Запустите *InstallUtil.exe* из командной строки, указав исполняемый файл проекта в качестве параметра:

    ```console
    installutil <yourproject>.exe
    ```

     Если вы используете командную строку разработчика для Visual Studio, системный путь должен указывать на файл *InstallUtil.exe*. Если это не так, можно добавить его в путь или использовать полный путь для его вызова. Этот инструмент устанавливается вместе с платформой .NET Framework в папку *%WINDIR%\Microsoft.NET\Framework[64]\\<версия_платформы\>* .

     Пример:
     - Для 32-разрядной версии .NET Framework 4 или 4.5 и более поздних версий: если каталог установки Windows — *C:\Windows*, по умолчанию используется путь *C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.
     - Для 64-разрядной версии .NET Framework 4 или 4.5 и более поздних версий: по умолчанию используется путь *C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.

### <a name="uninstall-your-service-manually-using-installutilexe-utility"></a>Удаление службы вручную с помощью служебной программы InstallUtil.exe

1. В меню **Пуск** выберите каталог **Visual Studio \<*version*>** и затем **Командная строка разработчика для VS \<*version*>** .

     Появится командная строка разработчика для Visual Studio.

2. Запустите *InstallUtil.exe* из командной строки, указав выходные данные проекта в качестве параметра:

    ```console
    installutil /u <yourproject>.exe
    ```

3. После удаления исполняемого файла для службы сама служба может по-прежнему присутствовать в реестре. В этом случае удалить запись службы из реестра можно с помощью команды [sc delete](/windows-server/administration/windows-commands/sc-delete).

### <a name="install-your-service-manually-using-powershell"></a>Установка службы вручную с помощью PowerShell

1. В меню **Пуск** выберите **Каталог Windows PowerShell** и **Windows PowerShell**.

2. Откройте каталог, где находится скомпилированный исполняемый файл вашего проекта.

3. Выполните командлет [**New-Service**](/powershell/module/microsoft.powershell.management/new-service), указав в качестве параметров выходные данные проекта и имя службы.

    ```powershell
    New-Service -Name "YourServiceName" -BinaryPathName <yourproject>.exe
    ```

### <a name="uninstall-your-service-manually-using-powershell"></a>Удаление службы вручную с помощью PowerShell

1. В меню **Пуск** выберите **Каталог Windows PowerShell** и **Windows PowerShell**.

2. Выполните командлет [**Remove-Service**](/powershell/module/microsoft.powershell.management/remove-service), указав в качестве параметра имя службы.

    ```powershell
    Remove-Service -Name "YourServiceName"
    ```

3. После удаления исполняемого файла для службы сама служба может по-прежнему присутствовать в реестре. В этом случае удалить запись службы из реестра можно с помощью команды [sc delete](/windows-server/administration/windows-commands/sc-delete).

    ```powershell
    sc.exe delete "YourServiceName"
    ```

## <a name="see-also"></a>См. также

- [Знакомство с приложениями служб Windows](introduction-to-windows-service-applications.md)
- [Практическое руководство. Создание служб Windows](how-to-create-windows-services.md)
- [Практическое руководство. Добавление установщиков в приложение-службу](how-to-add-installers-to-your-service-application.md)
- [Installutil.exe (установщик)](../tools/installutil-exe-installer-tool.md)
